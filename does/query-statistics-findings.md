# 综合查询与统计中心：功能深入章节

## 证据边界

- 综合查询 7 个入口：`evidence/module-06.json`，Evidence `ev_38947e25f18f5c3530edafcc8a81c9e535540d7a35a161748e64dc800d952267`（下记 E6），记录持续 12,994 ms。
- 统计中心 12 个入口：`evidence/module-07.json`，Evidence `ev_09a45f0a06a75d1316e52ebd6f6fa25316e841f7362f861659f9969d3c364feb`（E7），记录持续 20,656 ms。
- 分析只离线读取两份 REA 已保存场景证据，没有连接浏览器/API、执行代码、运行查询、打开详情、导出或修改业务记录。名称按当前菜单目录；部分旧 HTML title 是“广告数据统计”，不将旧 title 当作真实业务名称。
- 两份 Evidence 均声明 `completeness=incomplete`、missing_sections 为 events；观察仅覆盖打开初始页和短暂等待。未观察到某请求不代表该接口不存在或该能力不可用。
- 本文显示路径、参数名称、状态字段和计算公式，不显示客户/员工记录、电话号码、账号/项目 ID 值、token 或完整运行时查询 URL。源码身份和事务关联保存在本地派生 manifest。

## 综合查询：7 个入口

### 1. 综合查询

以 service_id/cust_id 绑定客户，`qryBasic` 验证 mainForm1 后请求客户基本信息，并展示标签、会员信息、关联房产；另有客户报事、订单、欠费分支 `/web-seo/pc/qry_cust_bs`、`qry_cust_order`、`qry_arrearageMoney`（源 S1 L75–121、L175–215、L727–795、L893–958）。初始普通入口只初始化组织/项目与客户模糊选择器；特定 link/type 返回参数才自动查客户，文件未声明 delayLoad 字段，本次只观察到组织/项目权限请求。客户不存在分支隐藏结果并提示；欠费计算来源、客户/房产完整关联和各明细分支未验证。

### 2. 开门记录

筛选 org_id/service_id、起止时间（附 00:00:00 / 23:59:59）、door_name、record_type_cd、status_cd、fields_type/value；表格显示来源、客户、门名称、开门时间、status_name 和备注，来源分支可增显示 bespeak_id（S2 L16–60、L91–157）。列表 `/web-seo/pc/telOpenDoorList` 使用 delayLoad=true，本次仅观察组织/项目及来源/状态字典请求，未观察列表查询。记录状态语义、门禁来源对应关系和实际查询结果未验证；该页面分析不涉及开门动作。

### 3. 客户号码变更查询

列表 `/web-seo/custUpdateLog/selectList` 将项目/客户/房产与 old_contact/new_contact、note、update_channel、updateDate、update_user_code/name 关联，筛选 service_id、start_time/end_time、cust_name（S3 L1–63、L113–123）。delayLoad=true，本次只观察组织/项目初始化请求；这是一组变更审计展示字段，文件未声明业务状态筛选。变更触发源、是否覆盖全部号码变化、旧新号码脱敏及审计不可变性未验证。

### 4. 员工评价

列表 `/web-bus/EvaluationRecordsController/initialization` 显示员工 staff_name、grade、评价标签/备注、客户、房号、提交时间和评价来源，筛选 service_id、grade_cd、staff_name、时间与 SourcesEvaluation_cd（S4 L51–114、L227–237）。delayLoad=true，只观察 permission/common 组织/项目权限、queryConfig 与 qianyueConfig 配置读取；这些配置请求不是评价记录列表已加载的证明。评分量表、评价来源字典与统计公平性须后端/结果证据；当前脚本没有提供完整业务状态机。

### 5. 一户一档

Vue 编译脚本以平台公司/城市公司/项目联动，结合 buildId、hourseId、stewardId 选择房屋，`getListData` 要求 serviceId 并发送 serviceId/stewardId/buildId/hourseId/startNum/pageSize，响应 list/totalRecord 用于卡片和分页；前端同时引用 hourseStatusCode 与 payHabitCode 等房屋字段（S5，原始 L1，字符偏移 2,244–2,913、11,379；S6 L1 偏移 25,494）。这里不使用 LigerUI delayLoad，组件初始化实际调用 getListData，本次观察 `/web-cust/mobile/one/hourse/page` POST 200，body 仅有 serviceId/startNum/pageSize，并观察组织、管理中心、项目、楼栋、管家、房屋联动和字典读取。源码还含读取详情/编辑资料/更新与导出等候选 API，均未执行；房屋状态字典、详情保存校验和完整档案字段未验证，源码里“查看完整号码”权限分支不代表本次读取过号码。

### 6. 活动

活动与团购复用 `gbList.js`，以 business_type_cd 区分，筛选 group_status_cd、distribution_mode_cd、business_order_status_cd、field_value；列表关联 business_name、有效期、成团/活动状态、订单金额/总数/未发单/批次/售后/投诉计数（S7 L10–89、L239–267）。虽然 grid 声明 delayLoad=true，初始化之后实际调用查询，本次 `/web-odm/groupBusiness/queryGroupBusinessList` POST 200 已观察，并先读三组字典；“延迟初始化”不等同最终没有加载列表。文件还包含修改成团状态/取消订单状态的处理分支，未执行，计数如何聚合、订单详情和动作校验均未验证。

### 7. 违约金减免清单

筛选 org_ids/service_id、起止时间、staff_name、fields_type/value、status_cd；列表关联房产、申请人/客户/账期以及 reduceTotal、unreduce、reduced、principal 金额，候选接口 `/web-seo/pc/queryReduceLiquidatedDamageList`（S8 L8–32、L42–95、L318–329）。grid 为 delayLoad=true，但 init 内确有 queryList 调用，且 queryList 先做表单验证；本次仅观察组织/项目读取，未出现减免列表事务，不能确定未发送的具体原因（S8 L169–177）。前端还构造导出请求；减免状态含义、三项金额是否平衡、审批规则和实际查询/导出尚未验证。

## 统计中心：12 个入口

### 1. 电子发票管理

筛选 org_id/service_id、时间、inf_state、buyer_name、other_str，列表展示发票号码/代码、购销方、交付邮箱、不含税金额/税额/含税金额、inf_state_name 等，候选接口 `/web-cust/pc/invoiceSalesInfo/queryInvoiceSalesInfoList`（S9 L5–42、L137–198）。delayLoad=true、普通首次不查询；只观察组织/项目和 inf_state 字典读取，且前端过滤字典 code=3。发票状态操作、税额计算及导出接口 `/web-cust/pc/exprortInvoiceSalesInfo` 均仅有源码候选，未验证业务执行。

### 2. 用户使用详情

按公司/项目及时间查询认证户数/总户数、认证员工数/员工总数，前端比例明确为认证数÷总数×100%，总数为 0 时显示 0%，保留两位小数（S10 L4–21、L80–104）。列表 `/web-seo/useInfoController/listCustomerUseInfo` delayLoad=true，普通首次不查询；本次只观察组织/项目初始化，当前页默认起止时间均为当天（L108–126）。没有业务状态字段；认证数统计口径、按时间过滤的语义和数字准确性未验证。

### 3. 员工登录清单

筛选 service_id/org_id、起止时间、staff_code，并用 checkbox 传“checkbox”或空串分支（HTML 标签为“显示最后一次登陆”）；列表展示项目、员工、工号、电话与 login_time（S11 L17–61、L127–150）。`/web-seo/pc/queryStaffLoginList` delayLoad=true，本次只观察组织/项目权限初始化，静态导出候选 `/web-seo/pc/exportDataStaff`（L93–124）。“最后一次登录”筛选是否按人/设备/账号去重以及时间口径需运行时/后端证据，当前列表没有声明业务状态机。

### 4. 业主登录清单

按 org_id/service_id、时间、phone_num 与可选 is_last_login=1 查询客户/房号/login_time，候选 `/web-seo/pc/queryEsmpLoginCustList`（S12 L17–70、L162–184）。delayLoad=true，初次只观察组织/项目读取；导出先 POST queryEsmpLoginCustCount 并要求 flag=success 后再提交导出，但本次未执行（L102–160）。登录去重、最近登录判断、导出容量约束与完整覆盖未知，无前端业务状态字段。

### 5. 问卷结果

按起止时间、status_cd/name、control_type_cd/name、ques_type、ques_name 查询，展示问卷类型/渠道/管控范围/组织/status_name、有效期与提交总数及业主/家属/租客人数（S13 L8–50、L83–104）。`/web-seo/pc/questionnaire/queryList` delayLoad=true，本次只读取三组 sysConfigQueryRest 字典，查询前校验 searchForm（L333）。人数去重、角色归属、问卷状态及导出结果口径未验证，不能将字段名推导成准确统计公式。

### 6. 费用查询

筛选 org_id/service_id、时间、cost_types、fields_type/value、pay_status_cds、pay_method_cd、pay_channels_cd，列表关联房产、实际缴费人/付费客户、金额、入账金额、支付渠道/流水号/状态；金额显示两位小数，pay_method=19 的抵扣券入账列为空（S14 L76–125、L244–264、L549–564）。`/web-seo/pc/queryChargeQueryList` delayLoad=true，本次只观察组织/项目及三组 `/web-seo/pc/queryCodeConfig` 请求。支付状态映射、手续费/入账规则、退款/明细行为与导出 `/web-seo/pc/exprortChargeQueryList` 尚未验证。

### 7. 公开问答报表管理

按时间、组织/项目、问答内容/官方回复、参与/反对比例及升级条件查询，展示回复人/时间、deal_time（分钟）、浏览/支持/反对数、比例和城市/集团结果（S15 L57–85、L99–160）。`/web-cust/pc/WarningController/listOpenFaqReply.do` delayLoad=true，本次只观察组织/项目权限读取；源码把 requestObj.deal_time 赋为 org_join_percent，属于静态字段映射不一致，实际影响未复现（L76–80）。比例分母、升级状态和汇总公式由服务端提供，导出与层级明细未验证。

### 8. 员工受欢迎指数报表

以 evaluationTheme、quesId、orgIds 查询 `/web-odm/staffPopularity/queryStaffPopularityByOrg`，实际返回的动态列配置包含有效问卷、户均员工满意度、平均受欢迎指数、管家平均黏度指数及条线指标（request-479）；导出限制最多选择 3 个组织（S16 L140–151、L224–233、L286–307、L320–382）。delayLoad=true，本次读取评价主题字典、queryQuesListByEvaluationTheme、组织列表和动态列配置，未读取指标列表。受欢迎指数、粘度及条线公式没有在当前渲染代码中计算，需服务端或算法资料；不可把字段标签当成公式证明。

### 9. 活跃度统计报表

筛选 startTime/endTime/orgId，显示 count_cust（活跃人数）、enrolment（注册用户数）与 activation，并支持从公司钻取项目报表，候选 `/web-cust/activationForOrg.do`（S17 L29–87、L451–460）。delayLoad=true，本次只观察 `/web-common/common/systemUserOrgIncrease` 组织范围读取。activation 直接取响应字段而非前端除法，因此活跃事件定义、统计窗口、去重和比例公式尚未验证。

### 10. 品检追踪

以多选 serviceId、statusMark、source、fuzzyQuery、起止时间、isTimeout、workType 查询；表格实体包含 eventId、问题类型/描述、项目/位置、sourceName、timeLimit、处理人、statusName、isTimeOut（S18 L48–101、L238–253、L344–364）。`/web-cust/pc/qualityCheck/getWorks` delayLoad=true，本次读取 `/web-cust/mobile/qualityCheck/getOptions/CREATE` 及组织/管理中心/项目联动；queryList 先验证表单并要求至少一个项目，源码还含已删除任务的 deleteWaitTask 确认分支，未执行。品质问题状态迁移、超时计算、处理/督办/详情及导出未验证。

### 11. 扫码评价运营报表

按 startDate/endDate/orgIds 查询平台公司项目总数/上线数/上线率、二维码数量/项目平均投放数、互动点位数；开始日期为空时使用源码常量 2022-10-28，候选 `/web-seo/ScanQRCodeEvaluation/queryOperationsReportByOrg`（S19 L160–176、L192–245）。delayLoad=true，本次仅读取组织列表，没有读取运营指标；导出先验证表单，再构造 `/web-seo/ScanQRCodeEvaluation/exportOperationsReportByOrg`（L83–117）。各“率/平均数”直接来自响应字段，分母和统计窗口未验证，不能依据名称声称其计算公式。

### 12. 扫码评价统计报表

同样以 startDate/endDate/orgIds 查询扫码提交数、及时响应数/率、未处理数、转工单数/率、回访工单数，并可向更细层级钻取，候选 `/web-seo/ScanQRCodeEvaluation/queryStatisticalReportByOrg`（S20 L160–176、L192–287）。delayLoad=true，本次只读取组织列表；导出候选 exportStatisticalReportByOrg 未执行。及时响应阈值、工单生成率/回访口径和明细的对应关系仍需后端或实际指标/事务证据，前端字段不证明状态迁移或因果。

## 已观察读取请求

以下表格列出入口初始化期间实际观察到的业务/配置读取事务；全部是 HTTP 200，method 按记录保留。R= `/web-common/common/systemUserOrg`，P= `/web-common/common/systemDataPermission`，C= `/web-common/common/sysConfigQueryRest`，O= `/web-common/list/queryOrgList`；不是客户端 API 名称的重写，完整路径在下表或派生 request 索引可定位。

| 入口 | 观察到的 method、路径与 transaction |
| --- | --- |
| E6 综合查询 | POST R（138）、P（139） |
| E6 开门记录 | POST R（180）、P（181）、C（182、183） |
| E6 客户号码变更 | POST R（224）、P（225） |
| E6 员工评价 | POST `/web-common/permission/common/systemUserOrg`（272）、`/web-common/permission/common/systemDataPermission`（273）、`/web-bus/EvaluationRecordsController/queryConfig`（274）、`/web-cust/bankWithholding/qianyueConfig`（275） |
| E6 一户一档 | POST `/cent-cust/userInfo/queryPCStaffInfo`（489）、O（498）、`/web-common/list/queryRegionalList`（499）、`queryServiceList`（500）、`queryBuildList`（501）、`queryServiceStewards`（502）、C（503–507、509）、`/web-common/list/queryServiceHourseList`（508）、`/web-cust/mobile/one/hourse/page`（510） |
| E6 活动 | POST C（555–557）、`/web-odm/groupBusiness/queryGroupBusinessList`（558） |
| E6 违约金减免 | POST R（604）、P（605） |
| E7 电子发票 | POST R（143）、P（144）、C（145） |
| E7 用户使用详情 | POST R（190）、P（191） |
| E7 员工登录 | POST R（236）、P（237） |
| E7 业主登录 | POST R（284）、P（285） |
| E7 问卷结果 | POST C（330–332） |
| E7 费用查询 | POST R（382）、P（383）、`/web-seo/pc/queryCodeConfig`（379–381） |
| E7 公开问答 | POST R（432）、P（433） |
| E7 员工受欢迎指数 | POST C（472）、`/web-seo/pc/staffPopularity/queryQuesListByEvaluationTheme`（473）、O（480）；GET `/web-bus/columnController/getShowColumn`（479） |
| E7 活跃度 | POST `/web-common/common/systemUserOrgIncrease`（528） |
| E7 品检追踪 | GET `/web-cust/mobile/qualityCheck/getOptions/CREATE`（575）；POST O（574）、`/web-common/list/queryRegionalList`（582）、`/web-common/list/queryServiceList`（583） |
| E7 扫码运营 | POST O（627） |
| E7 扫码统计 | POST O（671） |

事务编号括号为 `request-编号`，来源必须结合 E6/E7，以免跨 Evidence 重号。只有一户一档和活动在这次入口观察中实际发送主业务列表查询；不能以其他页面 delayLoad=true 的声明概括这两个例外。

参数名称与正文可用状态详见 `derived-query-statistics/observed-read-requests.json`，不含查询值。组织/项目常用 query 参数名 system_user_id/type 与 body findPath；一户一档主查询 body 名 serviceId/startNum/pageSize；活动主查询 body 名 pageMap/group_status_cd/distribution_mode_cd/business_order_status_cd/field_value/business_type_cd 和 page/pagesize/startNum/pageSize。`not_exposed` 不是正文一定为空的证明。

## 来源定位索引

每个源码 URL 以 `https://o2o.unee.com.cn` 加下表路径组成；表中省略运行时版本 query 值。行号基于原始浏览器解码响应，minified 脚本保留 L1 与字符偏移。SHA-256、response-content 对应事务和本地文件在 `derived-query-statistics/manifest.json`，不从源站重新获取。

| 源标记 | Evidence / transaction | source path |
| --- | --- | --- |
| S1 | E6 / request-121 | `/web-seo/pc/html/zhcx/js/zhcx.js` |
| S2 | E6 / request-161 | `/web-seo/pc/html/telOpenDoor/js/telOpenDoorList.js` |
| S3 | E6 / request-205 | `/web-seo/pc/html/custUpdateLog/js/custUpdateLog.js` |
| S4 | E6 / request-268 | `/web-bus/pc/html/evaluationRecords/js/evaluationRecords.js` |
| S5 | E6 / request-496 | `/un-pc-fronted/js/chunk-4b5fed3c.701db106.js` |
| S6 | E6 / request-494 | `/un-pc-fronted/js/chunk-8533dadc.90be4575.js` |
| S7 | E6 / request-532 | `/web-odm/pc/html/groupBusiness/js/gbList.js` |
| S8 | E6 / request-585 | `/web-seo/pc/html/liquidatedList/js/liquidatedList.js` |
| S9 | E7 / request-109 | `/web-cust/pc/html/invoiceSalesInfo/js/invoiceSalesInfoList.js` |
| S10 | E7 / request-171 | `/web-seo/pc/html/useInfo/js/useInfo.js` |
| S11 | E7 / request-217 | `/web-seo/pc/html/staffLoginList/js/staffLoginList.js` |
| S12 | E7 / request-265 | `/web-seo/pc/html/esmpLoginCust/js/esmpLoginCustList.js` |
| S13 | E7 / request-312 | `/web-seo/pc/html/QuestionnaireResult/js/questionList.js` |
| S14 | E7 / request-375 | `/web-seo/pc/html/chargeQuery/js/chargeQueryList.js` |
| S15 | E7 / request-409 | `/web-cust/pc/html/faq/js/faqStatementsByCity.js` |
| S16 | E7 / request-454 | `/web-seo/pc/html/StaffPopularity/js/staff_popularity_orglist.js` |
| S17 | E7 / request-506 | `/web-cust/pc/html/activationForOrg/js/activationForOrg.js` |
| S18 | E7 / request-555 | `/web-seo/pc/html/qualityProblemsTrack/js/index.js` |
| S19 | E7 / request-604 | `/web-seo/pc/html/CodeScanningEvaluationReport/js/codeEvaluationView.js` |
| S20 | E7 / request-648 | `/web-seo/pc/html/CodeScanningStatisticsReport/js/codeEvaluationView.js` |

## 覆盖结论

19 个当前账号可见入口的前端初始页、主要筛选字段、实体/状态字段、候选行为和初始读取请求已得到相应静态或观察证据；记录行、指标公式、完整明细、导出内容、写操作及后台源码仍未验证。HTTP 成功与前端名称不能扩大成全平台权限、状态迁移或数据正确性结论。
