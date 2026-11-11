# 报表管理与系统中心功能分析

本文覆盖报表管理 12 个入口、系统中心 6 个入口。结论来自已保存 REA 页面加载场景的 HTML 和 JavaScript；指标名称、函数与接口声明属于前端源码事实，未执行导出、账号管理、消息发送、同步或日志重发。实际初始化请求和捕获缺口见 [逐功能报告](features-analysis.md)。

报表证据为 `evidence/module-08.json`，Evidence ID `ev_9049e649478b51750b2f229948baf3cd299a931299e31a494686e3395de48951`；系统证据为 `evidence/module-09.json`，Evidence ID `ev_0cf173243cdb26a582983b2682632c0be53484fd0b8090f23f41b058eb1f61ca`。以下路径均相对于 `https://o2o.unee.com.cn`；行号按已捕获源文件计算。

## 报表管理

| 功能 | 前端可确认的内容 | 源码位置及仍未知的内容 |
| --- | --- | --- |
| 员工评价报表 | 公司维度员工总数、被评价人数、评价人次/人数、好评率、综合评分，带查询、组织钻取与导出分支。 | `/web-report/pc/html/employeeEvaluationStatement/js/groupView1.js` L118–157；候选查询为 `/web-report/employeeEvaluationStatement/efficiencyViewQuery1`。好评率、综合评分计算口径未由当前源码证明。 |
| 服务调度 | 总工单数、派单数/率、及时派单数/率、派单平均时长，组织维度查询及下钻。 | `/web-report/pc/html/schedulingEfficiency/js/efficiencyView1.js` L169–215；候选 `/web-report/scheduEfficiency/efficiencyViewQuery1`。及时阈值和平均时长分母需要后端依据。 |
| 诉求管理 | 使用 `accountStatementList.js` 的查询、列配置、导出和业务明细分支；这是报表入口，与客户服务里的同名业务处理页不同。 | `/web-report/pc/html/accountStatement/js/accountStatementList.js` L1140、L1723，候选 `/web-report/processEfficiency/efficiencyQueryWork`。列配置会影响实际展示；源码里的其他业务列声明不能全部当作当前表头。 |
| 用户量 | 代码包含注册量、认证量、总量及比例相关查询/跳转函数和月份选择。 | `/web-report/pc/html/userStatistics/js/reportUserStaticsticsRegister.js` L290–404、L513–534。注册/认证去重、总房产口径和各比例需要逐分支结果或服务端证据。 |
| 积分报表 | 公司维度有效积分、UN+积分、电商积分、冻结积分；带查询、导出及组织下钻。 | `/web-cust/pc/html/integralStatements/js/integralStatementsByOrg.js` L65–83；候选 `/web-cust/IntegralStatements/listIntegralStatementsByOrg.do`。积分来源、冻结/解冻迁移和会计平衡未验证。 |
| 工作计划报表 | 展示工作计划项、进行中、已完成、延期完成及完成效果评分。 | `/web-seo/pc/html/workPlanStatement/js/groupView1.js` L116–146；候选 `/web-seo/workPlanStatement/efficiencyViewQuery1`。完成评分和延期判断的后端规则未知。 |
| 过程效率 | 按工单流程阶段展示数量、率、超时、及时率与平均时长；代码有公司明细读取及导出。 | `/web-report/pc/html/processEfficiency/js/efficiencyView.js` L192–251、L438；候选 `/web-report/processEfficiency/getOrgDetailData`。完整阶段阈值、时钟停止条件和分母仍需后端证明。 |
| 星海图 | 目录、页面路由与 HTML 加载已确认；实际可用前端资源及页面结构记录在逐功能报告。 | 入口内联函数仅打开后续大屏。已补采实际大屏，见 [星海图分析](viewport-findings.md)；数据算法仍按该章证据边界解释。 |
| 装修信息报表 | 年/月选择与组织筛选，显示装修户数、正在装修、未开始、已完成、巡查天数与巡查次数。 | `/web-report/pc/html/fitmentMsgReport/js/index.js` L24–142、L167–191；候选 `/web-report/timingTask/reportDecorationInformationReport/queryDecorationInformationReport`。巡查统计的去重与周期口径未知。 |
| 装修户巡查动态报表 | 关联公司、项目、楼栋、房产，显示已整改问题数、跟进问题数和违规发函单数，并有按日展示与明细分支。 | `/web-report/pc/html/activeReport/js/index.js` L204、L229–333、L410–471、L972–1001；候选 `/web-report/timingTask/decorationPatrolDynamicReport/queryDecorationPatrolDynamicReport`。单元格明细及发函业务未执行。 |
| 管家服务分析看板 | SPA 路由及共享脚本已取得；原始浏览器补充观察确认两组日期区间控件与导出按钮。 | 独立来源 `UI-SPA-930915`，见 `spa-ui-observations.json`。指标名、图表计算和跨维度关联仍未回答。 |
| 企微管家应用情况 | 目录入口、HTML 和部分相关资源已取得；REA Chrome 场景报告了两条读取 null 的页面错误。 | 具体功能字段和运行情况见逐功能报告；不能根据菜单名称确认企业微信后台实现或断言页面完全正常。 |

## 系统中心

| 功能 | 前端可确认的内容 | 源码位置与验证边界 |
| --- | --- | --- |
| 用户管理 | 账号、姓名、组织、来源、邮箱、绑定微信、状态与角色等字段；源码定义新增、导入、导出、密码重置、冻结、解冻、删除分支。 | `/web-sys/pc/html/empee/empee_list.js` L35–248、L454–539。候选列表 `/web-sys/empee/queryEmpeeBaseInfo`；当前场景出现非 JSON 的“无权限”响应解析异常。账号操作未执行。 |
| 角色管理 | 角色编码、名称、级别、创建人和备注；代码包含修改、批量操作、角色删除及级别初始化。 | `/web-sys/pc/html/roleManage/js/roleList.js` L12–80、L208–240；候选 `/web-sys/role/queryRoleLevel`、`queryRoleInfo`。授权树、成员分配及权限保存的后续页面没有完整执行证据。 |
| 服务中心管理 | NC/HR/MDM 编码、中心名称、公司/管理中心、状态与联系电话；代码包含修改、删除、状态更新、主数据同步。 | `/web-sys/pc/html/centermanagement/js/serviceCenter.js` L6–72、L218–335。同步候选 `/web-bus/batchMasterDataController/syncMdmFromCrm` 的确认文本提示约 20–30 分钟；这是源码提示，并非本次测量。未触发同步。 |
| 消息发送 | 渠道、标题、内容、创建时间和状态；列表、详情、删除及消息发送处理函数均在已取得脚本中。 | `/web-sys/pc/html/messageManage/js/messageList.js` L28–43、L125–183，`sendMessage.js` L1–54。候选列表 `/web-sys/message/queryMessageList`；没有发送任何消息，未验证受众范围或通知到达。 |
| 接口日志管理 | 流水号、组织/项目/房产、业务类别、对接系统、方向、接口名称、支付流水、状态、成功/失败数量与原因；代码有查询、导出、详情及重发分支。 | `/web-sys/pc/html/interfaceLogManage/js/interfaceLogList.js` L164–266、L376–438；候选列表 `/web-sys/interfaceLogManage/queryInterfaceLogList`。未执行重发，无法证明幂等性或业务影响。 |
| 消息通知 | 菜单和页面可访问性已记录；本次对应步骤的 `/web-common/common/systemDataPermission` 返回 HTTP 510，并出现 HTML 被当作 JSON 解析的异常。 | 见逐功能报告的实际请求与 runtime_errors。内联 loader 已关联实际捕获的 `/portal/notice/js/noticeList.js`，静态候选为 `/portal/pc/noticeList`、`queryAndUpdateMessage`、`deleteMessage`，均未执行对应操作；业务列表、通知状态迁移和发送/阅读规则尚不能由成功加载 HTML 推断。 |

## 报表解释的边界

前端列名与查询函数能够说明“页面展示什么、以什么字段查询”，不能单独证明服务端如何算出率、平均值、排名和聚合金额。上述指标应分别保留统计窗口、分母、去重、空值与状态范围等未知项；没有证据时不能把常见公式当作该平台公式。
