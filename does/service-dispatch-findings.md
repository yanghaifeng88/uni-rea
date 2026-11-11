# 服务调度2：诉求管理与管家关系配置深入分析

## 证据与范围

- 唯一原始输入：`evidence/module-02.json`，operation `capture_browser_scenario`。
- Evidence ID：`ev_f9175384011de182c5dbe803f89ff1c503383011d5e38b8400f1b55b5997fe5f`。
- 这次记录覆盖两入口的打开、等待和关闭；分析工作仅离线读取保存的页面/脚本响应、DOM 与网络事件，没有新增请求、运行脚本或点击业务动作。
- 场景持续 5,619 ms，保留 1,039 个事件，丢弃数为 0；Evidence 自身完整性标记 `incomplete`、`missing_sections=[events]`，部分网络正文不可用。HTTP 200 只证明该事务得到响应，不等于业务成功、查询完成或全功能覆盖。
- 下述只列路径、字段名及业务字典值，不列账号、客户资料、运行时查询值、完整运行时 URL 或凭据。

## 实际打开的两个入口

| 入口 | 观察证据 | 主要前端资源 |
| --- | --- | --- |
| 诉求管理 | request-102：GET `/web-cust/pc/html/work/sqgl.html`，HTTP 200；sequence 504/507 | request-126：`/web-cust/pc/html/work/js/sqgl.js`，HTTP 200；seq 569/627 |
| 管家关系配置 | request-158：GET `/web-cust/pc/html/stewardConfig/stewardConfigList.html`，HTTP 200；seq 789/792 | request-167：`/web-cust/pc/html/stewardConfig/js/stewardConfigList.js`，HTTP 200；seq 809/899 |

页面加载参数名称为 `privilege_id`、`t`；脚本带版本参数名称 `v`。URL 值不在报告中展开。

两页都使用 LigerUI 服务端分页表格、20 条默认页长，可选 10/20/50；初次 `delayLoad=true`。诉求页 `getColums` 和管家页 `init` 都保留“取消默认查询”的实现；仅在返回/特定关联入口才自动查列表。本次保存网络记录**没有**对应 `workEventQueryList` 或 `queryStewardConfigList` 事务。因此“入口成功打开”和“业务列表已查出结果”须分开。

## 诉求管理：字段与列表契约

源码依据：`sqgl.html` L45–158；`sqgl.js initQueryData` L857–889。

| UI/语义 | 提交字段 | 说明 |
| --- | --- | --- |
| 城市公司、服务中心 | `service_id` | 公司用于项目联动；普通列表查询对象未提交 `org_id` |
| 开始/结束时间 | `start_time`、`end_time` | 日期控件相互约束最大/最小日期；默认一周设置已注释 |
| 报事类型 | `bulletin_type` | 初始化字典屏蔽 code=3 的“投诉”项 |
| 状态 | `we_status_cd` | 首次列配置成功后默认 1000“待派单” |
| 渠道 | `channel_we` | 来自配置字典 |
| 房号、联系人、电话等模糊条件 | `extra_msg` | 实际匹配范围由后台实现决定 |
| 工单类型 | `work_type_name` | 文本输入 |
| 报事内容 | `event_content` | 文本输入 |
| 处理人 | `handleUserName` | 大小写按源码保留 |
| 处理方 | `responsible_party` | 字典“物业/地产/无法处理” |
| 工单编码、报事编号 | `event_code`、`event_id` | 两种身份分开；event_id 在函数中重复赋同值 |
| 按紧急程度排序、超时工单 | `order_by_ed`、`is_time_out` | 点击自定义复选框写 `yes/not`，不同于通用表格排序 |
| 页面固定业务类型 | `event_type=1` | 前端常量，不是客户数据 |

静态列表路径：`/web-cust/pc/workevent/workEventQueryList`（sqgl.js L5、L1116–1137）。`queryList` 调表单验证，设置筛选再 `loadData`（L371–395）；查询按钮先把 newPage 设 1（L59–62）。service_name 的 HTML 设置为必填（sqgl.html L62）。实际列表参数、后端解释、响应行结构与分页结果本次未验证。

实际初始化返回的列配置有：房号、提单人、联系人、联系电话、报事时间、报事内容、渠道、支付方式、维修金额、当前状态、当前处理人、报事类型（request-156 响应）。`getColums/bindColumns` 将服务器列配置 `column_name_zh/en` 作为显示名/数据键，并按字段绑定渲染函数；静态 `default_columns` 不能等同于本账号实际列（sqgl.js L752–851、L1095–1114）。

## 诉求管理：权限与状态分流

`initPrivateButton`（sqgl.js L106–187）同时读取 `getButtonPriv()` 与 `hasPermission()`；按钮初始隐藏。以下是前端条件，后台授权仍未知。

| 能力 | 权限编码 |
| --- | --- |
| 新增 | `200100001` 或 `100101002` |
| 列设置 | `200100002` 或 `100101005` |
| 导出 | `200100003` 或 `100101003` |
| 派单 | `200100004` 或 `100101004`，赋值 `hasPaidanPri` |
| 删除 | `200100005` 或 `100101006` |
| 查询 | `200100006` 或 `100101001` |

实际返回的状态字典（request-145，seq 769，响应正文）如下。它是一组筛选标签，**不能直接证明完整状态迁移图**。

| code_val | code_name |
| --- | --- |
| `1000` | 待派单 |
| `w1000` | 待处理 |
| `1100` | 处理中 |
| `1200` | 待验收 |
| `1400` | 待评价 |
| `2000` | 已完成 |

- `renderEventContent` / `renderWorkContent` 在内容链接上传入 `service_id`、`event_id`、`work_id`、事件状态 `status_cd`、工单状态 `w_status_cd`（L1034–1048）。
- `goDetailEvent` / `goDetail`：若 `(status == 1000 || w_status == 900) && hasPaidanPri`，进入 `/web-cust/pc/html/work/sqgl_pd.html`，可追加 work_id；否则进入 `/web-cust/pc/html/workbench/visitInfo.html`，以 `flag=bs`、`business_type=15` 和实体 ID 传递上下文（L466–513）。`900` 只证明存在这一工单状态分支，当前字典未给出它的中文名称。两个详情函数对 work_id/business_id 的传递略不同，报告保留此区别。
- 所以报事/工单内容链接可以导向派单页面，而不仅是通用详情。页面是否自动写入、何时派单提交、处理/验收/评价/回访的保存接口，本次未打开目标页面，仍未知。
- `goAdd` 先保存筛选上下文，再进入 `/web-cust/pc/html/workbench/jddj/lr/add.html`（L521–527）；这里未包含新增表单或其业务校验。
- `goDel` 必须勾选至少一行并确认；`goDelInner` 以每行的 service_id/event_id/work_id 组成 JSON 数组，包装为 `datas`，POST `/web-cust/pc/WorkEventHandle/deleteWork`；仅 `result.status=s` 显示成功并刷新（L529–580）。这是静态写入路径，未执行。
- 导出 `excelExprort` 先验证表单，随后 `checkMonthDet` 限制日期跨度至 4 个月，再通过隐藏表单 POST `/web-cust/pc/workExcelExport/exportData`；URL 拼筛选字段，body 增加 `exportData`（L189–239、L891–927）。普通列表的 handleUserName、event_code、work_type_name、responsible_party、event_id 没有出现在该导出函数拼接字段中；不能假定导出等同所有当前筛选。`checkMonthDet` 形参 detMonth 未实际使用，代码固定比较 4。
- 列设置打开 `/web-bus/pc/html/columnSetting/column-setting.html`，模块编号 14（L64–76）。列保存页面未采集。

## 关联实体与上下文

源码事实：

- **报事事件与工单**：`event_id` 和 `work_id` 分开传递；状态也分为 `status_cd` / `w_status_cd`。可推断存在一个报事事件关联工单的模型，但未得到数据库表定义、基数或后端约束。
- **项目与组织权限**：`common.js initOrgService3`（L1973）调用用户组织接口；`queryServiceForOrg3`（L2147）调用项目数据权限接口，再按 org_id 筛选项目。系统返回结构包含 area/org/regional/service 的 ID、code、name 等字段；报告不包含实际组织或项目值。
- **客户关联**：`renderSubmitUser` 仅在 create_user_client=3 时把提单人做成链接，`goZhcx` 进入 `/web-seo/pc/html/zhcx/zhcx.html`，以 cust_id/cust_name 建上下文（sqgl.js L515–519、L1050–1059）；未进入客户详情。
- **关联工单**：`relationCount>0` 时调用 `goRelation(event_id, service_id)`（L1062–1071）；这个函数定义未在当前离线提取的 sqgl.js/common.js 里找到，因此该入口实现未闭合。另一 `link=smzp` 分支用 service_id/event_ids 加载关联工单、隐藏普通筛选，返回扫码评价页面（L774–800、L1199–1241）。
- **列表返回**：诉求页将多项条件、页码等写入 localStorage，returnBack 时恢复；管家页也使用 org_id/service_id/fields_value/page/pageSize 这些通用键。这意味着同源模块存在共享上下文键，跨模块影响是否实际发生未验证，不能将此静态重名直接定为运行故障。

## 管家关系配置

源码依据：stewardConfigList.html L51–76；stewardConfigList.js L1–84、L149–387。

| 部分 | 静态实现 |
| --- | --- |
| 筛选 | 公司 org_id/org_name、服务中心 service_id/service_name、fields_value（占位文字“房号、联系人、电话…”） |
| 表单校验 | 公司和服务中心 HTML 为 required；queryStewardConfig 调 isValid，并显式要求 service_id 非空 |
| 查询请求 | `/web-cust/stewardConfig/queryStewardConfigList`，POST；自定义字段 `service_id`、`fields_value`、`mothodType=queryStewardConfigList`，拼写 mothodType 按原样保留 |
| 列表字段 | 管家花名 steward_nick_name、实名 staff_name、工号 system_user_code、电话 mob_no、管理区域 build_name 和 hourse_name（源码拼写保留） |
| 编辑入口 | 花名链接进入 updateStewardConfig.html，携带 steward_id；当前列表没有给该链接另加修改权限分支 |
| 新增 | 保存查询上下文，进入 addStewardConfig.html |
| 删除 | 收集勾选 steward_id 为逗号分隔字符串，要求非空并确认；POST `/web-cust/stewardConfig/deleteStewardConfigList`，带 service_id/steward_id/mothodType；`status=success` 显示成功并刷新 |
| 查询按钮 | `200200001` |
| 新增按钮 | `200200002` |
| 删除按钮 | `200200003` |

位置：查询 L179–201，删除 L207–258，上下文保存/恢复 L264–300，按钮绑定 L303–341，权限 L366–379。当前账号按钮是否显示、具体管家列表结果、新增/编辑页校验与保存接口均未验证。

实体关系推断：一个管家配置以 steward_id 标识，与员工/系统用户的姓名、工号、电话，以及项目范围内的楼栋/房屋管理区域一起展示；配置删除请求还要求 service_id。能确认前端关联字段，不能确认后台员工身份绑定规则、是否允许多管家重叠管理或区域唯一性。

## 已观察初始化接口

按事务证据列示；只输出路径和参数名称。request-96 的待办查询在该时段完成，但属于门户默认待办页，本报告不把它归为诉求列表查询。请求收取顺序不建立因果链。

| 入口 | transaction / response sequence | method / status | 路径 | query 参数名 | body 参数名 |
| --- | --- | --- | --- | --- | --- |
| 诉求 | request-141 / 703 | POST / 200 | `/web-common/common/systemUserOrg` | system_user_id | findPath |
| 诉求 | request-142 / 707 | POST / 200 | `/web-common/common/systemDataPermission` | system_user_id, type | findPath |
| 诉求 | request-143 / 742 | POST / 200 | `/web-common/common/sysConfigQueryRest` | 无 | column_name, table_name |
| 诉求 | request-144 / 746 | POST / 200 | 同上 | 无 | column_name, table_name |
| 诉求 | request-146 / 744 | POST / 200 | 同上 | 无 | column_name, table_name |
| 诉求 | request-145 / 769 | POST / 200 | `/web-cust/pc/workevent/geConfigStatusCd` | 无 | 正文 not_exposed；源码传空字符串 |
| 诉求 | request-156 / 781 | GET / 200 | `/web-bus/columnController/getShowColumn` | modules_code | 正文 not_exposed |
| 管家 | request-206 / 1008 | POST / 200 | `/web-common/common/systemUserOrg` | system_user_id | findPath |
| 管家 | request-207 / 1012 | POST / 200 | `/web-common/common/systemDataPermission` | system_user_id, type | findPath |

请求/响应正文字段身份由对应 network-content 事务关联，源码用于解释字典选择条件。三次 sysConfigQueryRest 分别对应报事类型、渠道、处理方；正文均实际返回配置列表，报事类型列表含投诉，但前端会过滤该项。

附带观察：诉求初始化有 artDialog loading.gif 请求返回 404（request-100、101、157）；场景还有 ServiceWorkerRegistration “document is in an invalid state” 页面错误。它们证明资源/环境异常，尚未建立这些异常导致业务功能失效的因果。

## 校验一致性与未闭合问题

以下是静态不一致或缺口，不是已复现的业务错误：

- 诉求 HTML form ID 为 `mainForm`，查询匹配此 ID；导出函数却用 `#mainform`。管家 HTML 为 `mainform`，查询却用 `#mainForm`。需核实当前 jQuery/验证器对空选择器的行为，再判断用户可见影响；本次未执行查询/导出。
- 诉求列表与导出字段集合不同；导出是否补充读取其他上下文必须由接口/下载证据确认。
- 管家花名编辑链接未在当前脚本做按钮权限分支，不代表服务端允许未授权修改。
- 电话渲染虽然掩码，showTitle 仍返回原值（诉求 L831；管家 L12–18）；这是渲染策略事实，不输出实际电话，也不推断权限漏洞。
- 后续新增、派单、处理、验收、评价和回访页面未采集。当前证据足以回答入口、筛选、前端分流和候选接口，不能回答完整业务状态迁移和所有保存校验。

## 源码身份

提取文件位于 `derived-service-dispatch/`；行号均以原始响应解码文本为准，不引用格式化后行号。

| transaction | source path | SHA-256 |
| --- | --- | --- |
| request-102 | `/web-cust/pc/html/work/sqgl.html` | `5c280663dbfaddd9cf61c4248c0584022eeddb6b40d7f7c3d25f68e59866338c` |
| request-126 | `/web-cust/pc/html/work/js/sqgl.js` | `175002b17493bb6fffbf110e1bd4f12ae9003a00bd2ef18cdfe0cc6d5850388c` |
| request-158 | `/web-cust/pc/html/stewardConfig/stewardConfigList.html` | `9c3730ada04fc9b12d24658224422a26cd445714c4d1430f81589455219efd56` |
| request-167 | `/web-cust/pc/html/stewardConfig/js/stewardConfigList.js` | `1fce729c7d649b36d726253b413b2739c73f020e992134a98b9ca4e4b649cde3` |
| request-105、161 | `/web-cust/pc/js/common.js` | `059e65652fcc0815e9e3dc10db59469a6d6d12e8e3d582fa67333545b009bb6d` |
