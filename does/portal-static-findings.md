# 中海物业平台：门户和待办静态发现

## 证据范围

- 输入：`evidence/001-portal.json`；REA operation：`inspect_web_page`。
- Evidence ID：`ev_da3ff6eb84fbc4f5b3acc8ddeddd8052fc05ac869edd66d8930bbdc935aa4bde`。
- 本报告只分析该记录中的 `normalized_result.scripts.items` 与 `normalized_result.dom`；没有连接浏览器、执行目标代码、点击菜单或请求接口。
- 保存的脚本包含 31 项。下述行号以原始 `source.artifact.text` 按行拆分为准；`derived-portal-sources/` 是从该 Evidence 提取的本地副本，不是新抓取的材料。
- DOM 为结构摘要：1,731 个节点，包含一个 IFRAME、两个 FORM；仅有节点种类、父子关系、属性名称和文本长度，无文本及属性值。因此不能凭本报告列出实际账号的全部菜单、实际权限集合、查询结果或导出表单 action。

## 门户加载和功能导航

| 结论 | 证据类型 | 位置 |
| --- | --- | --- |
| `Index_menu.ajaxFindUserData` 使用 `/portal/menu/queryMenu` 得到 `userInfo`、`menuData`、`sessionActiveTime`、`bnPriv`、`privageMap`。`bnPriv` 还被写入 localStorage。 | 源码事实 | index_menu.js L151–174 |
| 该请求封装 `Dic.Ajax.request` 的默认行为为同步 POST、JSON 响应、60 秒超时。函数上方写“异步”的注释与实现不同。 | 源码事实 | portal/esmp_base.js L324–339 |
| 一级菜单来自 `menuData` 中 `LEVEL_ID == 1` 的项；以 `PRIVILEGE_ID` 建索引，以 `PRIVILEGE_CODE` 标识菜单 DOM。子菜单按 `PARENT_PRIVILEGE_ID` 关联。 | 源码事实 | index_menu.js `initFirstMenu` L219；`writeFirstMenu` L238；`joinMenu` L423 |
| 入口行为由 `MENU_TARGET` 决定：`newWin/new_open` 使用新窗口，`mainFrm` 使用门户 iframe 页签。初始优先选 `privilege_code=100103`；不存在时选首个子菜单。 | 源码事实 | index_menu.js `initSecondMenu` L338–399 |
| `un-pc-fronted` 和 `crmeb.unee.com.cn` 入口的一些分支从 localStorage 取 `token`，拼接 `type=oldUNPC&token=…` 做跨系统导航。这里只保留源码字段名，没有取回任何凭据值。 | 源码事实；具体对接成功与权限未知 | index_menu.js L367–384 |
| 活跃导航走 `onloadChildSystemPage → addIfream`：以 `PRIVILEGE_CODE` 复用页签，上限 10 个；首次 URL 追加 `privilege_id` 与时间戳 `t`。切换页签隐藏旧 iframe、显示已有 iframe。 | 源码事实 | index_menu.js L440–568 |
| `refreshTab` 将当前 iframe 的 `src` 设为其 `newSrc`；`closeCurrentTab` 删除当前 iframe 和页签，然后选相邻页签。 | 源码事实 | index_menu.js L594–615 |
| 文件仍包含上限 8 页签的旧 `showMainFrmPage` / `Custom_tabpanel` 实现，但当前 `onloadChildSystemPage` 对它的调用已注释。不能把“8 页签”作为当前入口上限。 | 源码事实 | index_menu.js L455、L462–493 |
| `hasPermission(priv)` 返回 `privageMap[priv]`；`getButtonPriv` 从当前页签找菜单 ID，返回对应 `bnPriv`。 | 源码事实 | index_menu.js L653–658、L743–750 |

由以上可推断，门户是服务端提供菜单/权限信息、浏览器负责展示并聚合多个业务子系统的架构。该推断不证明服务端是否在每个业务接口重新校验权限，也不证明隐藏菜单覆盖全部平台能力。

## 待办任务查询、分页和导出

分析对象：`https://o2o.unee.com.cn/web-cust/pc/html/workbench/toDoTtask.js?v=3.3.2`。

1. `initGrid`（L45）创建 LigerUI 表格，静态列包括城市公司、项目、渠道、业务类型、业务内容、任务类型、任务状态、联系人、联系电话、任务到达时间、任务人和操作。列表端点为 `/web-cust/toDoTask/queryTask`（L174），服务端分页，默认第 1 页、20 条，可选 10/20/50；排序关闭、延迟加载（L175–193）。
2. `queryList`（L233–239）调用 `initQueryData`，更新 `parms`，把 `newPage` 设为 1，然后 `loadData()`。点击查询按钮绑定此函数（L326–328），因此重新查询回到第一页。
3. `initQueryData`（L249–266）的请求字段为 `org_id`、`service_id`、`channel`、`business_type`、`task_type`、`task_status`、`business_content`、`handler`、`query_self`、`start_time`、`end_time`，并固定 `method=queryTask`。它们是源码声明的请求字段，不是本次观察到的请求值。
4. 实际加载的 `ligerui.all.js` 默认 grid `method=post`、响应行根 `Rows`、总数根 `Total`（L9178–9186）。`loadData` 的服务端分页分支加入 `page`、`pagesize`，并额外加入 `startNum=(newPage-1)*pageSize` 和 `pageSize`（L9934–9943），最终 `$.ajax` 使用 `p.method`（L10010）。所以本页面静态契约是 POST 查询 + 四个分页参数；响应真实形态仍须运行时佐证。
5. 初始化默认时间范围为当天及前 6 天，即包含当天的 7 个日历日（taskCommon.js `setDefOneWeek` L2327–2330）。`initCompBox`（待办 L696–721）向 `/web-cust/toDoTask/getConfig` 发 POST；源码请求键保留拼写 `menthod`，由响应 `businessType`、`taskType`、`taskStatus`、`eventChannel` 初始化选择项；任务状态的默认值为 `1`。
6. 城市公司/项目选择器调用 `taskCommon.js initOrgService3`（L1991），以用户 ID 查询 `/web-common/common/systemUserOrg`；`queryServiceForOrg3`（L2135）查询 `/web-common/common/systemDataPermission?…&type=1`，再按城市公司过滤项目。是否这些接口只返回当前账号可见数据，需要运行时或服务端证据。
7. 导出点击处理器（待办 L483–487）把 `handler` 和 `business_content` 分别复制到 `pc_handler` 和 `pc_business_content`，再调用 `#searchForm.submit()`。该证据 DOM 只有 FORM 的 `action` 属性名称，无属性值；导出 endpoint、文件格式、服务端数据范围与是否沿用全部筛选项尚未确认。
8. `cecheParm`（源码保留该拼写，L785–794）保存 searchForm 内 input 的 id/value、当前页和每页大小至 `top.to_do_task_data`；有 `back` 参数时恢复这些字段与页码（L310–323）。这说明页内返回使用父窗口内存恢复上下文，不证明跨浏览器重启持久化。

## 前端权限条件

以下仅证明可见性/参数分支；不能证明后台授权执行。

| 操作/行为 | 源码条件，权限编号按原样保留 | 位置 |
| --- | --- | --- |
| 只能查询本人 | 同时缺少 `940002002` 和 `100103001` 时将 `query_self=self` | 待办 L289–291 |
| 显示新增 | `940002005` 或 `100103003` | L292–294 |
| 显示导出 | `940002006` 或 `100103004` 或 `100103006` | L295–297 |
| 显示查询按钮 | `100103005` | L298–300 |
| 提单人本人回访能力 | `940002004` 或 `100103002` 赋给 `ownerBack` | L305 |
| 行内处理按钮 | 分支综合任务状态、当前登录人是否在 handler_id 中、task_type、业务类型、AI 标记以及渠道条件 | L101–169 |

电话列把字符位置 3–8 显示成星号，但 `showTitle` 返回原电话号码；这是源码事实（L76–93）。本报告没有读取账号记录中的电话值。

## 从待办可追踪到的业务入口

这是一份代码中的分流列表，不是完整平台目录。各分流目标页面尚未独立分析。

| business_type | 源码标签/分流 | 主要路由或函数 |
| --- | --- | --- |
| 10 | 月度评价；关联回访/新增投诉 | `workbench/visitInfo.html`；`queryjddjData` |
| 15 | 报事报修；派单/回访/AI 内容 | `work/sqgl_pd.html`；`workbench/visitInfo.html`；`workbench/aiResult.html` |
| 20 | 投诉；回访/新增投诉 | `workbench/visitInfo.html`；`workbench/jddj/lr/add.html` |
| 25 | 业主卡 | `/web-bus/pc/html/billOwnerCard/…` |
| 30 | 放行条审批 | `showshenpi → approvalSubmit` |
| 35 | 社区活动 | `checkActivity` |
| 40 | 问卷配置/调查 | `/web-bus/pc/html/questionsConfig/…` |
| 45 | 扫码评价 | `commentResult/commentResult.html` |
| 50 | 社区议事 | `checkDiscuss`；`discuss/viewDiscuss.html` |
| 55 | 工作计划 | `workPlan/workPlanVerify.html`、`workPlanAdd.html` |
| 60 | 超时催单/督办 | `goToDuBan`，按 event_type 分流报事、品质整改或投诉 |
| 65 | 认证申请审批 | `certificationApplication/approval.html` |
| 70 | 报事回访相关待办 | `getEventId`；`workbench/visitInfo.html` |
| 75 | 述职报告审核 | `dealReport` |
| 85 | 品质问题跟踪 | `/web-seo/pc/html/qualityProblemsTrack/info.html` |
| 90 | 访客小程序 | `visitorMini/index.html`，转入数据项 `go_page_url` |
| 99 | AI 回访内容（按钮合成的分流类型） | `workbench/aiResult.html` |

分流证据：待办脚本 L101–169（按钮渲染）、L330–481（事件绑定）、L677–694（新增投诉/回访预填）、L876–900（督办）。99 是源码生成按钮使用的类型，不能断言它也是服务端业务字典项。80 仅在“业务内容展示为普通文本”的条件中出现，没有足够依据给出业务名称。

## 交互副作用边界

静态分析已发现以下业务写入或可能写入，未执行：

- `business_type=60` 的“处理”直接 POST `/web-cust/toDoTask/deleteWaitTask`，带 `wait_task_id`、`task_status=2`、`task_status_name=已完成`，然后再跳转督办；原确认框已被注释（L393–412）。
- `dealWaitTask`（L552）、`checkDiscuss`（L571）、`checkActivity`（L628）的部分分支向 `deleteWaitTask` 发 POST。名为详情的点击也可进入 `checkActivity` 或“记录不存在”的清理流程，不能仅凭按钮文字把它认定为只读。
- `dealReport`（L609）POST `/web-cust/toDoTask/dealReport`。
- 放行条 `approvalSubmit`（L849）请求 `/web-cust/pc/approvalReleaseBar`；传入 service_id、release_ids、status_cd、status_name、release_note。前端要求选择 1100（不同意）或 2000（同意）并填写意见（L820–839）。
- 新增按钮会先 POST `/web-cust/toDoTask/queryUrl`，再打开配置的 CRM URL，拼接 userAccount 及可选 AuthToken（L492–516）。这里只确认源码对接流程，未取回 URL 或凭据值，也未打开外部 CRM。

## 未验证事项与覆盖状态

- 门户菜单加载和 iframe/tab 导航：**静态机制已回答**；实际账号全部菜单、实际页面 URL、可访问范围和后台授权：**未回答**。
- 待办查询与分页：**前端静态契约已回答**；实际请求/响应、过滤语义、总数一致性与后端实现：**未验证**。
- 导出：**点击/表单提交机制部分回答**；action、下载文件、列映射、数据范围、是否生成服务端任务：**未验证**。
- 待办业务分流：**源码候选清单已回答**；每个业务页面内部功能、业务状态机、数据库和服务器代码：**未回答**。
- 所有能力的完整覆盖：**未完成**。31 个已加载脚本只代表这次保存材料，不能代表未打开模块、其他账号权限或外部子系统。

## 关键源码身份

所有记录均来自同一个 Evidence ID，URL 参数按证据原样保留。

| scripts.items 索引 | source URL | source SHA-256 | 本地摘取副本 |
| --- | --- | --- | --- |
| 1 | `https://o2o.unee.com.cn/portal/js/esmp_base.js?v=1.0.1` | `31b601bbd7e71d6f8a9a18ba724288d77dd870e7f242e9d9676e650c02844157` | `derived-portal-sources/01-esmp_base.js.txt` |
| 2 | `https://o2o.unee.com.cn/web-cust/pc/js/ligerUI/js/ligerui.all.js` | `f2bc352e270bcb865b1812a4ea3ebc91f6b0f1bfebbb758f43218453419fa474` | `derived-portal-sources/02-ligerui.all.js.txt` |
| 9 | `https://o2o.unee.com.cn/web-cust/pc/html/workbench/taskCommon.js` | `894052897e9504e910680a252f2e7a5df09ca0be33b777c66d56f0d4d09a51d5` | `derived-portal-sources/09-taskCommon.js.txt` |
| 10 | `https://o2o.unee.com.cn/portal/index_menu.html?t=1791942264759` | `0b73e57104188eacebaae7be750b94dbe766f12a09edd3906fc0779d3440d3a3` | `derived-portal-sources/10-index_menu.html.txt` |
| 15 | `https://o2o.unee.com.cn/portal/index_menu.js?v=0.5605278858310967` | `0b7af78234ac64349c45189d9e1c3c543a3e5c7a99f15384389789d482411d31` | `derived-portal-sources/15-index_menu.js.txt` |
| 18 | `https://o2o.unee.com.cn/portal/js/plugins/panel/tabpanel.js` | `c794d99917caa434b89690d74b1920859c063d14c55e214b5f81ce959cb3dcec` | `derived-portal-sources/18-tabpanel.js.txt` |
| 27 | `https://o2o.unee.com.cn/web-cust/pc/html/workbench/toDoTtask.js?v=3.3.2` | `1e879de001af94ef2f80c38cf30a808bb0ef322e47e3e73fbb2af2c38fffd759` | `derived-portal-sources/27-toDoTtask.js.txt` |
| 28 | `https://o2o.unee.com.cn/portal/jsPush.js?v=3.7.1` | `4c70ec893f274c87219800171b19859721e2f704b3dcedf80238bbb230cadbcb` | `derived-portal-sources/28-jsPush.js.txt` |
