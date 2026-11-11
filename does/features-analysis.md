# 中海物业平台功能页面和接口分析

当前账号菜单包含 79 个功能。本分析覆盖保存的页面加载证据，梳理表单字段、列表表头、按钮、前端脚本及网络请求；按钮所对应的业务流程仍需进一步验证。

## 覆盖范围

共读取 10 份 REA 采集证据，79 个菜单路由已有页面请求，79 个功能已取得 HTML，79 个功能已关联捕获的外部脚本。0 个功能出现 HTTP 错误页面；捕获到 66 个不同方法和路径组合的 XHR 或 Fetch 请求。

## 功能覆盖表

| 模块 | 功能 | 页面路由 | 页面状态 | HTML | 已捕获外部 JS |
| --- | --- | --- | --- | --- | --- |
| 报表管理 | 员工评价报表 | /web-report/pc/html/employeeEvaluationStatement/groupView1.html | 200 | 是 | 10 |
| 系统中心 | 用户管理 | /web-sys/pc/html/empee/empee_list.html | 200 | 是 | 11 |
| 服务调度 | 诉求管理 | /web-cust/pc/html/work/sqgl.html | 200 | 是 | 15 |
| 客户管理 | 客户管理 | /web-cust/pc/html/Customers/CustomerList.html | 200 | 是 | 14 |
| 运营中心 | 公告公示 | /web-bus/pc/html/procla/proclaList.html | 200 | 是 | 18 |
| 综合查询 | 综合查询 | /web-seo/pc/html/zhcx/zhcx.html | 200 | 是 | 11 |
| 统计中心 | 电子发票管理 | /web-cust/pc/html/invoiceSalesInfo/invoiceSalesInfoList.html | 200 | 是 | 14 |
| 配置管理 | 装修配置 | /web-bus/pc/html/decorationConfig/decorationConfig.html | 200 | 是 | 17 |
| 配置管理 | 图片管理 | /web-cust/pc/html/confManagement/imgConfList.html | 200 | 是 | 14 |
| 客户服务 | 待办任务 | /web-cust/pc/html/workbench/toDoTask.html | 200 | 是 | 16 |
| 客户服务 | 报事 | /web-cust/pc/html/work/sqgl.html | 200 | 是 | 15 |
| 服务调度 | 管家关系配置 | /web-cust/pc/html/stewardConfig/stewardConfigList.html | 200 | 是 | 15 |
| 系统中心 | 角色管理 | /web-sys/pc/html/roleManage/roleList.html | 200 | 是 | 5 |
| 运营中心 | 广告管理 | /web-bus/pc/html/admanage/advertisingList.html | 200 | 是 | 7 |
| 客户管理 | 房产管理 | /web-cust/pc/html/Customers/HourseList.html | 200 | 是 | 10 |
| 综合查询 | 开门记录 | /web-seo/pc/html/telOpenDoor/telOpenDoorList.html | 200 | 是 | 11 |
| 配置管理 | 门设备管理 | /web-bus/pc/html/DoorEquipmentManagement/doorEquipList.html | 200 | 是 | 14 |
| 配置管理 | 消息模板 | /web-bus/pc/html/templateManage/templateList.html | 200 | 是 | 5 |
| 统计中心 | 用户使用详情 | /web-seo/pc/html/useInfo/useInfo.html | 200 | 是 | 11 |
| 客户服务 | 代缴代扣管理 | /web-cust/pc/html/bankWithholding/bankWithholding.html | 200 | 是 | 14 |
| 综合查询 | 客户号码变更查询 | /web-seo/pc/html/custUpdateLog/custUpdateLog.html | 200 | 是 | 10 |
| 配置管理 | 问卷配置 | /web-bus/pc/html/questionsConfig/questionsConfigList.html | 200 | 是 | 9 |
| 统计中心 | 员工登录清单 | /web-seo/pc/html/staffLoginList/staffLoginList.html | 200 | 是 | 11 |
| 客户服务 | 放行条 | /web-cust/pc/html/releaseBar/releaseBarList.html | 200 | 是 | 15 |
| 报表管理 | 服务调度 | /web-report/pc/html/schedulingEfficiency/efficiencyView1.html | 200 | 是 | 10 |
| 运营中心 | 便民电话 | /web-cust/pc/html/fastTelephone/telephoneList.html | 200 | 是 | 14 |
| 统计中心 | 业主登录清单 | /web-seo/pc/html/esmpLoginCust/esmpLoginCustList.html | 200 | 是 | 13 |
| 系统中心 | 服务中心管理 | /web-sys/pc/html/centermanagement/centerone.html | 200 | 是 | 1 |
| 报表管理 | 诉求管理 | /web-report/pc/html/accountStatement/accountStatementList.html | 200 | 是 | 18 |
| 统计中心 | 问卷结果 | /web-seo/pc/html/QuestionnaireResult/questionList.html | 200 | 是 | 12 |
| 客户服务 | 访客预约 | /web-cust/pc/html/visitorBespeak/listVisitorBespeakPC.html | 200 | 是 | 9 |
| 统计中心 | 费用查询 | /web-seo/pc/html/chargeQuery/chargeQueryList.html | 200 | 是 | 13 |
| 客户服务 | 投诉 | /web-cust/pc/html/work/tsList.html | 200 | 是 | 14 |
| 报表管理 | 用户量 | /web-report/pc/html/userStatistics/ReportUserStatisticsRegisterList.html | 200 | 是 | 11 |
| 运营中心 | 房产交易 | /web-bus/pc/html/houseSell/houseSellList.html | 200 | 是 | 15 |
| 系统中心 | 消息发送 | /web-sys/pc/html/messageManage/messageList.html | 200 | 是 | 4 |
| 报表管理 | 积分报表 | /web-cust/pc/html/integralStatements/integralStatementsByOrg.html | 200 | 是 | 11 |
| 配置管理 | 评价二维码管理 | /web-bus/pc/html/scanEvaluate/qrCode/qrCodeList.html | 200 | 是 | 4 |
| 综合查询 | 员工评价 | /web-bus/pc/html/evaluationRecords/evaluationRecords.html | 200 | 是 | 14 |
| 综合查询 | 一户一档 | /un-pc-fronted/#/formsManagement/gearPerHousehold/index | 200 | 是 | 3 |
| 报表管理 | 工作计划报表 | /web-seo/pc/html/workPlanStatement/groupView1.html | 200 | 是 | 10 |
| 客户服务 | 认证申请 | /web-cust/pc/html/certificationApplication/caList.html | 200 | 是 | 15 |
| 系统中心 | 接口日志管理 | /web-sys/pc/html/interfaceLogManage/interfaceLogList.html | 200 | 是 | 14 |
| 统计中心 | 公开问答报表管理 | /web-cust/pc/html/faq/faqStatementsByCity.html | 200 | 是 | 11 |
| 配置管理 | 手机开门推送配置 | /web-bus/pc/html/openDoor/push_manage_list.html | 200 | 是 | 3 |
| 统计中心 | 员工受欢迎指数报表 | /web-seo/pc/html/StaffPopularity/staff_popularity_orglist.html | 200 | 是 | 12 |
| 报表管理 | 过程效率 | /web-report/pc/html/processEfficiency/efficiencyView.html | 200 | 是 | 11 |
| 报表管理 | 星海图 | /web-report/pc/html/viewport/viewportImage.html | 200 | 是 | 1 |
| 配置管理 | 电梯管理 | /web-bus/pc/html/elevatorManage/elevator_manage.html?checkVisitor=1 | 200 | 是 | 4 |
| 系统中心 | 消息通知 | /portal/notice/notice.html | 200 | 是 | 12 |
| 客户服务 | 评价结果 | /web-cust/pc/html/commentResult/commentResult.html | 200 | 是 | 18 |
| 运营中心 | 社区活动 | /web-odm/pc/html/communityActivity/communityActivityList.html | 200 | 是 | 16 |
| 报表管理 | 装修信息报表 | /web-report/pc/html/fitmentMsgReport/index.html | 200 | 是 | 13 |
| 客户服务 | 工作计划 | /web-cust/pc/html/workPlan/workPlanList.html | 200 | 是 | 15 |
| 配置管理 | 抵扣券导入 | /web-cust/pc/html/deductionVoucher/deductionVoucherList.html | 200 | 是 | 14 |
| 报表管理 | 装修户巡查动态报表 | /web-report/pc/html/activeReport/index.html | 200 | 是 | 15 |
| 客户服务 | 邻里社交 | /web-odm/pc/html/neighbourSocial/neighbourSocialList.html | 200 | 是 | 13 |
| 配置管理 | 报告台岗位管理 | /web-cust/pc/html/report/postPoolList.html | 200 | 是 | 12 |
| 统计中心 | 活跃度统计报表 | /web-cust/pc/html/activationForOrg/activationForOrg.html | 200 | 是 | 15 |
| 配置管理 | 报告台基础配置管理 | /web-cust/pc/html/report/baseConfigList.html | 200 | 是 | 12 |
| 客户服务 | 意见反馈 | /web-seo/pc/html/feedbackInfo/feedbackInfoList.html | 200 | 是 | 11 |
| 配置管理 | 质检员点位管理 | /web-cust/pc/html/inspectionManagement/inspeConfList.html | 200 | 是 | 16 |
| 综合查询 | 活动 | /web-odm/pc/html/groupBusiness/activityList.html | 200 | 是 | 14 |
| 运营中心 | 议事大厅 | /web-cust/pc/html/discuss/discuss_list.html | 200 | 是 | 16 |
| 综合查询 | 违约金减免清单 | /web-seo/pc/html/liquidatedList/liquidatedList.html | 200 | 是 | 13 |
| 统计中心 | 品检追踪 | /web-seo/pc/html/qualityProblemsTrack/index.html | 200 | 是 | 15 |
| 统计中心 | 扫码评价运营报表 | /web-seo/pc/html/CodeScanningEvaluationReport/codeEvaluationView.html | 200 | 是 | 11 |
| 客户服务 | 空置房申请 | /web-bus/pc/html/vacantRoomApply/vacantRoomApplyPC.html | 200 | 是 | 14 |
| 报表管理 | 管家服务分析看板 | /un-pc-fronted/#/formsManagement/wecomHousekeepBoard/index | 200 | 是 | 3 |
| 配置管理 | 空置房配置 | /web-bus/pc/html/vacantRoomConfigure/vacantRoomConfigureByPC.html | 200 | 是 | 15 |
| 报表管理 | 企微管家应用情况 | /web-report/pc/html/wecomReport/index.html | 200 | 是 | 1 |
| 配置管理 | 缴费二维码管理 | /un-pc-fronted/#/formsManagement/paymentQRcodeManagement/index | 200 | 是 | 3 |
| 统计中心 | 扫码评价统计报表 | /web-seo/pc/html/CodeScanningStatisticsReport/codeEvaluationView.html | 200 | 是 | 11 |
| 客户服务 | 装修申报 | /web-bus/pc/html/decorationManagement/index.html | 200 | 是 | 5 |
| 配置管理 | 角色清单导出 | /un-pc-fronted/#/formsManagement/roleListExport/index | 200 | 是 | 3 |
| 客户服务 | 装修巡查清单 | /web-bus/pc/html/inspectionList/index.html | 200 | 是 | 4 |
| 客户服务 | 装修整改通知函 | /web-bus/pc/html/decorationNotice/index.html | 200 | 是 | 4 |
| 客户服务 | 访客登记记录 | /un-pc-fronted/#/personAccess/registrationRecords/index | 200 | 是 | 3 |
| 客户服务 | 访客通行记录 | /un-pc-fronted/#/personAccess/transitRecords/index | 200 | 是 | 3 |

## 运行异常与捕获缺口

9 模块加载步骤共记录 129 条页面错误、27 条请求中止和 40 条 HTTP 错误资源响应。菜单文档均返回 200，仍有资源及接口失败。381 条脚本响应内容未能取得，38 个功能存在部分关联脚本内容缺失；这不等同于脚本没有在浏览器运行。

页面错误主要包含 ServiceWorkerRegistration invalid state；具体业务页面还出现 null、undefined config 及非 JSON 响应解析错误。部分请求 net::ERR_ABORTED 可能与关闭前端页面的采样时序相关，其业务影响需要进一步验证。所有原始 Evidence 的 completeness 均为 incomplete，且 dropped events 为 0；不能据此推断完整网络覆盖。

逐事务 [页面专用脚本缺口核查](/Volumes/MOVESPEED/Projects/uni-rea/does/script-availability-audit.md) 进一步确认：未取得内容的 381 条脚本响应属于公共库或共享界面工具，已观察响应中未发现专属业务脚本内容缺失。380 条是 HTTP 304 的 body-read-failed，另 1 条 jquery.placeholder.js 是 HTTP 404 的 request-failed。评价二维码目录的 viewer_default.js 经 HTML 引用和已捕获版本确认是跨四个菜单使用的图片预览初始化工具；其未取得内容的原始事务仍保留未知，其他事务没有填补其字节缺口。这些结果不证明未观察到的动态脚本或整体业务源码完整。

## SPA 动态界面补充观察

6 个 SPA 功能另外取得了原始内置浏览器的只读渲染 DOM 结构，来源见 [SPA 界面观察](/Volumes/MOVESPEED/Projects/uni-rea/does/spa-ui-observations.json)。这是当前账号的另一浏览器上下文，采用 UI-SPA 独立引用，补充动态占位符、表头和按钮；不会覆盖 REA 专用 Chrome 的错误、捕获缺口或未知。

访客登记记录、访客通行记录、缴费二维码管理、角色清单导出的动态列表结构已经部分确认；一户一档仅确认查询、导入、导出按钮，动态列仍未知；管家服务分析看板仅确认日期控件和导出按钮，指标口径及公式仍未知。

## 报表管理 员工评价报表

路由 `/web-report/pc/html/employeeEvaluationStatement/groupView1.html`。菜单来源 `ev_25226ae15c591aa25247b4d7ef5e89e5ddd4162209de1bcb9259a6a2f7d462cc`。

菜单定义的操作：员工评价导出列表1、员工评价导出列表2、员工评价导出列表3、员工评价导出列表4、查询。这些是菜单权限定义，不代表流程已执行验证。

页面字段：start_time、end_time。

页面按钮：查询、导出。

关联脚本中的静态表头候选：+(item.state==、+v+、城市公司、员工总人数、员工被评价人数、用户评价人次、用户评价人数、好评率、综合评分。共享脚本候选可能属于其他路由。

该加载阶段存在失败或 HTTP 错误资源：`/web-cust/pc/js/artDialog/images/plugins/artdialog/loading.gif` 404、`/portal/js/plugins/artDialog/images/plugins/artdialog/loading.gif` 404。页面关闭可能中断请求，需重新观察其影响。

页面证据：
- `ev_9049e649478b51750b2f229948baf3cd299a931299e31a494686e3395de48951`，事务 `request-102`，响应摘要 `f29c518a2bd5739242e1e133eae624c5857c3e9db3b139293ef9790b63eef038`，HTTP 200。

前端脚本：
已捕获 10 个关联脚本，地址和摘要见 JSON。业务脚本包括：`https://o2o.unee.com.cn/web-report/pc/js/common.js`、`https://o2o.unee.com.cn/web-report/pc/js/niceValidator/local/zh_CN.js`、`https://o2o.unee.com.cn/web-report/pc/html/employeeEvaluationStatement/js/resetTableHeight.js`、`https://o2o.unee.com.cn/web-report/pc/html/employeeEvaluationStatement/js/groupView1.js`。

同一页面加载步骤内观察到的请求：

| 方法 | 路径 | HTTP | 查询参数名 | 请求体参数名 | Evidence |
| --- | --- | --- | --- | --- | --- |
| POST | /web-common/common/systemUserOrg | 200 | system_user_id | not_exposed | ev_9049e649478b51750b2f229948baf3cd299a931299e31a494686e3395de48951 |
| POST | /web-common/common/systemUserArea | 200 | system_user_id | area_ids, org_ids | ev_9049e649478b51750b2f229948baf3cd299a931299e31a494686e3395de48951 |

静态 AJAX 地址候选，存在于页面或关联脚本，未据此证明业务动作执行：
- `https://o2o.unee.com.cn/web-report/pc/js/ligerUI/js/ligerui.all.js`：`...`。
- `https://o2o.unee.com.cn/web-report/pc/html/employeeEvaluationStatement/js/groupView1.js`：`/web-report/employeeEvaluationStatement/efficiencyViewQuery1`。

## 系统中心 用户管理

路由 `/web-sys/pc/html/empee/empee_list.html`。菜单来源 `ev_25226ae15c591aa25247b4d7ef5e89e5ddd4162209de1bcb9259a6a2f7d462cc`。

菜单定义的操作：查询、新增、删除、修改、冻结、解冻、重置密码、导出、工作交接、交接记录、交接记录导出、提前回岗。这些是菜单权限定义，不代表流程已执行验证。

页面字段：status_name、SYSTEM_USER_INFO、inp_assigned_org_name、inp_hr_position、open_name、nc_user_name。

页面按钮：导出、新增、交接记录、查询。

关联脚本中的静态表头候选：序号、用户账号、用户姓名、归属组织、联系电话、用户来源、邮箱、绑定微信、状态、角色、部门、岗位、承接人、交接开始时间、交接结束时间、操作。共享脚本候选可能属于其他路由。

页面运行错误：Unexpected token '无', "无权限" is not valid JSON。错误与该加载步骤在时间上关联，未证明具体调用因果。

该加载阶段存在失败或 HTTP 错误资源：`/web-cust/pc/js/artDialog/images/plugins/artdialog/loading.gif` 404、`/portal/js/plugins/artDialog/images/plugins/artdialog/loading.gif` 404、`/web-sys/empee/queryEmpeeBaseInfo` net::ERR_ABORTED、`/web-sys/pc/js/artDialog/images/plugins/artdialog/loading.gif` 404。页面关闭可能中断请求，需重新观察其影响。

页面证据：
- `ev_0cf173243cdb26a582983b2682632c0be53484fd0b8090f23f41b058eb1f61ca`，事务 `request-102`，响应摘要 `fb09bd19a841dd2ddf4a85e9fb57c412a94ac7f264158f481ebd6b413bbf8bf6`，HTTP 200。

前端脚本：
已捕获 11 个关联脚本，地址和摘要见 JSON。业务脚本包括：`https://o2o.unee.com.cn/web-sys/pc/js/table/custom_table.js`、`https://o2o.unee.com.cn/web-sys/pc/js/progressbar/custom_progressbar.js`、`https://o2o.unee.com.cn/web-sys/pc/js/esmp_base.js`、`https://o2o.unee.com.cn/web-sys/pc/js/common.js`、`https://o2o.unee.com.cn/web-sys/pc/html/empee/empee_list.js`。

HTML 内联脚本静态观察：`ev_0cf173243cdb26a582983b2682632c0be53484fd0b8090f23f41b058eb1f61ca`，内联摘要 `02462bd9fb6a8e1faec9bf3ffbc6311671f76f70b8b840ef611e864c73d794f6`，143 字符。

document.write 动态脚本声明候选 `https://o2o.unee.com.cn/web-sys/pc/html/empee/empee_list.js`，查询参数名 v；关联同功能中实际已记录的脚本请求，不执行该加载语句。

同一页面加载步骤内观察到的请求：

| 方法 | 路径 | HTTP | 查询参数名 | 请求体参数名 | Evidence |
| --- | --- | --- | --- | --- | --- |
| POST | /web-sys/empee/queryEmpeeBaseInfo | None |  | STATUS_CD, SYSTEM_USER_INFO, hc_openid, inp_assigned_org_name, inp_hr_position, nc_user_id, page, pageSize, pagesize, startNum | ev_0cf173243cdb26a582983b2682632c0be53484fd0b8090f23f41b058eb1f61ca |
| POST | /web-common/permission/common/sysConfigQueryRest | 200 |  | column_name, table_name | ev_0cf173243cdb26a582983b2682632c0be53484fd0b8090f23f41b058eb1f61ca |

静态 AJAX 地址候选，存在于页面或关联脚本，未据此证明业务动作执行：
- `https://o2o.unee.com.cn/web-sys/pc/js/ligerUI/js/ligerui.all.js`：`...`。
- `https://o2o.unee.com.cn/web-sys/pc/html/empee/empee_list.js`：`/web-common/permission/common/sysConfigQueryRest`、`/web-sys/empee/queryEmpeeBaseInfo`。

## 服务调度 诉求管理

路由 `/web-cust/pc/html/work/sqgl.html`。菜单来源 `ev_25226ae15c591aa25247b4d7ef5e89e5ddd4162209de1bcb9259a6a2f7d462cc`。

菜单定义的操作：列设置、导出、删除、查询。这些是菜单权限定义，不代表流程已执行验证。

页面字段：org_name、service_name、start_time、end_time、status_name、bulletin_type_name、work_type_name、channel_name_we、extra_msg、event_content、handleUserName、responsible_party_name、event_code、event_id。

页面按钮：返回、查询、列设置、新增、删除、导出。

关联脚本中的静态表头候选：城市公司、服务中心、房号、联系人、报事时间、报事内容、当前状态、渠道、投诉来源、关联工单、回访状态。共享脚本候选可能属于其他路由。

该加载阶段存在失败或 HTTP 错误资源：`/web-cust/pc/js/artDialog/images/plugins/artdialog/loading.gif` 404、`/portal/js/plugins/artDialog/images/plugins/artdialog/loading.gif` 404。页面关闭可能中断请求，需重新观察其影响。

页面证据：
- `ev_f9175384011de182c5dbe803f89ff1c503383011d5e38b8400f1b55b5997fe5f`，事务 `request-102`，响应摘要 `5c280663dbfaddd9cf61c4248c0584022eeddb6b40d7f7c3d25f68e59866338c`，HTTP 200。

前端脚本：
已捕获 15 个关联脚本，地址和摘要见 JSON。业务脚本包括：`https://o2o.unee.com.cn/web-cust/pc/js/common.js`、`https://o2o.unee.com.cn/web-cust/pc/html/work/js/dateFormat.js`、`https://o2o.unee.com.cn/web-cust/pc/html/work/js/dateFormat.js`、`https://o2o.unee.com.cn/web-cust/pc/html/work/js/resetTableHeight.js`、`https://o2o.unee.com.cn/web-cust/pc/html/work/js/resetTableHeight.js`、`https://o2o.unee.com.cn/web-cust/pc/js/niceValidator/local/zh_CN.js`、`https://o2o.unee.com.cn/web-cust/pc/js/niceValidator/local/zh_CN.js`、`https://o2o.unee.com.cn/web-cust/pc/html/work/js/sqgl.js`。

HTML 内联脚本静态观察：`ev_f9175384011de182c5dbe803f89ff1c503383011d5e38b8400f1b55b5997fe5f`，内联摘要 `7ef8cee276159e08dbb9adb6ad418ce457c03ccdc7dc45f14dadd64d67bda216`，104 字符。

document.write 动态脚本声明候选 `https://o2o.unee.com.cn/web-cust/pc/html/work/js/sqgl.js`，查询参数名 v；关联同功能中实际已记录的脚本请求，不执行该加载语句。

同一页面加载步骤内观察到的请求：

| 方法 | 路径 | HTTP | 查询参数名 | 请求体参数名 | Evidence |
| --- | --- | --- | --- | --- | --- |
| POST | /web-common/common/systemUserOrg | 200 | system_user_id | findPath | ev_f9175384011de182c5dbe803f89ff1c503383011d5e38b8400f1b55b5997fe5f |
| POST | /web-common/common/systemDataPermission | 200 | system_user_id, type | findPath | ev_f9175384011de182c5dbe803f89ff1c503383011d5e38b8400f1b55b5997fe5f |
| POST | /web-common/common/sysConfigQueryRest | 200 |  | column_name, table_name | ev_f9175384011de182c5dbe803f89ff1c503383011d5e38b8400f1b55b5997fe5f |
| POST | /web-cust/pc/workevent/geConfigStatusCd | 200 |  | not_exposed | ev_f9175384011de182c5dbe803f89ff1c503383011d5e38b8400f1b55b5997fe5f |
| GET | /web-bus/columnController/getShowColumn | 200 | modules_code | not_exposed | ev_f9175384011de182c5dbe803f89ff1c503383011d5e38b8400f1b55b5997fe5f |

静态 AJAX 地址候选，存在于页面或关联脚本，未据此证明业务动作执行：
- `https://o2o.unee.com.cn/web-cust/pc/js/ligerUI/js/ligerui.all.js`：`...`。
- `https://o2o.unee.com.cn/web-cust/pc/html/work/js/sqgl.js`：`/web-cust/pc/WorkEventHandle/deleteWork`、`/web-bus/columnController/getShowColumn`。

## 客户管理 客户管理

路由 `/web-cust/pc/html/Customers/CustomerList.html`。菜单来源 `ev_25226ae15c591aa25247b4d7ef5e89e5ddd4162209de1bcb9259a6a2f7d462cc`。

菜单定义的操作：删除、编辑、修改手机号码、查询。这些是菜单权限定义，不代表流程已执行验证。

页面字段：org_name、service_name、fields_name、serv_name、cust_serv_name、parmContact、historyHouse。

页面按钮：查询、删除、添加、编辑。

该加载阶段存在失败或 HTTP 错误资源：`/web-cust/pc/js/artDialog/images/plugins/artdialog/loading.gif` 404、`/portal/js/plugins/artDialog/images/plugins/artdialog/loading.gif` 404。页面关闭可能中断请求，需重新观察其影响。

页面证据：
- `ev_217ee4e01474a60978df3b0f8593f64ec81bbe05d137d4ca0cfcaf8f1e1ebccf`，事务 `request-102`，响应摘要 `22b1eeb3e785b95d77bc8a955927b22516e6f133dd94224e0b0e5c48e3195164`，HTTP 200。

前端脚本：
已捕获 14 个关联脚本，地址和摘要见 JSON。业务脚本包括：`https://o2o.unee.com.cn/web-cust/pc/js/table/custom_table.js`、`https://o2o.unee.com.cn/web-cust/pc/html/Customers/js/houseCommon.js`、`https://o2o.unee.com.cn/web-cust/pc/js/progressbar/custom_progressbar.js`、`https://o2o.unee.com.cn/web-cust/pc/js/niceValidator/local/zh_CN.js`、`https://o2o.unee.com.cn/web-cust/pc/js/niceValidator/local/zh_CN.js`、`https://o2o.unee.com.cn/web-cust/pc/js/esmp_base.js`、`https://o2o.unee.com.cn/web-cust/pc/js/esmp_base.js`、`https://o2o.unee.com.cn/web-cust/pc/html/Customers/js/CustomerList.js`。

同一页面加载步骤内观察到的请求：

| 方法 | 路径 | HTTP | 查询参数名 | 请求体参数名 | Evidence |
| --- | --- | --- | --- | --- | --- |
| POST | /web-common/common/systemUserOrg | 200 | system_user_id | findPath | ev_217ee4e01474a60978df3b0f8593f64ec81bbe05d137d4ca0cfcaf8f1e1ebccf |
| POST | /web-common/common/systemDataPermission | 200 | system_user_id, type | findPath | ev_217ee4e01474a60978df3b0f8593f64ec81bbe05d137d4ca0cfcaf8f1e1ebccf |

静态 AJAX 地址候选，存在于页面或关联脚本，未据此证明业务动作执行：
- `https://o2o.unee.com.cn/web-cust/pc/html/Customers/js/CustomerList.js`：`/web-cust/mobile/queryByContact`、`/web-cust/custManage/delCustServ`、`/web-cust/PC/queryHistoryHouse`、`/web-cust/o2o/syncCustHourseRel`。

## 运营中心 公告公示

路由 `/web-bus/pc/html/procla/proclaList.html`。菜单来源 `ev_25226ae15c591aa25247b4d7ef5e89e5ddd4162209de1bcb9259a6a2f7d462cc`。

菜单定义的操作：删除、修改、新增、评论、导出、查询。这些是菜单权限定义，不代表流程已执行验证。

页面字段：org_name、service_name、start_time、end_time、proclamation_type_name、extra_msg。

页面按钮：查询、新增、删除。

关联脚本中的静态表头候选：标题、分类、阅读数、创建人、创建时间、发布方式、审核人、最后审核时间、失效时间、公告状态、置顶、打回原因、操作。共享脚本候选可能属于其他路由。

该加载阶段存在失败或 HTTP 错误资源：`/web-cust/pc/js/artDialog/images/plugins/artdialog/loading.gif` 404、`/portal/js/plugins/artDialog/images/plugins/artdialog/loading.gif` 404。页面关闭可能中断请求，需重新观察其影响。

页面证据：
- `ev_c4d4036bc65a408c8041f833ce8889a39169173452dd7d6ae2a6a106c5d2ca2b`，事务 `request-102`，响应摘要 `3b925c247e781cbb093462a3b2d20dda83a41a13dd44bed13148cc6fd6efa87a`，HTTP 200。

前端脚本：
已捕获 18 个关联脚本，地址和摘要见 JSON。业务脚本包括：`https://o2o.unee.com.cn/web-bus/pc/js/table/custom_table.js`、`https://o2o.unee.com.cn/web-bus/pc/js/progressbar/custom_progressbar.js`、`https://o2o.unee.com.cn/web-bus/pc/js/common.js`、`https://o2o.unee.com.cn/web-bus/pc/html/procla/js/proclaList.js`、`https://o2o.unee.com.cn/web-bus/pc/js/resetTableHeight.js`、`https://o2o.unee.com.cn/web-bus/pc/html/procla/js/cookieHelper.js`、`https://o2o.unee.com.cn/web-bus/pc/html/procla/js/checkBoxForSimpleList.js`、`https://o2o.unee.com.cn/web-bus/pc/js/niceValidator/local/zh_CN.js`。

同一页面加载步骤内观察到的请求：

| 方法 | 路径 | HTTP | 查询参数名 | 请求体参数名 | Evidence |
| --- | --- | --- | --- | --- | --- |
| POST | /web-common/permission/common/systemUserOrg | 200 | system_user_id | findPath | ev_c4d4036bc65a408c8041f833ce8889a39169173452dd7d6ae2a6a106c5d2ca2b |
| POST | /web-common/common/sysConfigQueryRest | 200 |  | column_name, table_name | ev_c4d4036bc65a408c8041f833ce8889a39169173452dd7d6ae2a6a106c5d2ca2b |

静态 AJAX 地址候选，存在于页面或关联脚本，未据此证明业务动作执行：
- `https://o2o.unee.com.cn/web-bus/pc/js/ligerUI/js/ligerui.all.js`：`...`。

## 综合查询 综合查询

路由 `/web-seo/pc/html/zhcx/zhcx.html`。菜单来源 `ev_25226ae15c591aa25247b4d7ef5e89e5ddd4162209de1bcb9259a6a2f7d462cc`。

菜单定义的操作：查询。这些是菜单权限定义，不代表流程已执行验证。

页面字段：org_name、service_name、cust_name。

页面按钮：返回、查询。

关联脚本中的静态表头候选：房号、联系人、联系电话、报事时间、报事内容、渠道、当前状态、当前处理人、报事类型、公司、服务中心、批次号、订单编号、销售类型、下单客户、订单时间、购买数量、订单金额、订单状态、详情。共享脚本候选可能属于其他路由。

该加载阶段存在失败或 HTTP 错误资源：`/portal/js/plugins/artDialog/images/plugins/artdialog/loading.gif` 404、`/web-cust/pc/js/artDialog/images/plugins/artdialog/loading.gif` 404、`/web-seo/pc/js/artDialog/images/plugins/artdialog/loading.gif` 404。页面关闭可能中断请求，需重新观察其影响。

页面证据：
- `ev_38947e25f18f5c3530edafcc8a81c9e535540d7a35a161748e64dc800d952267`，事务 `request-102`，响应摘要 `edb4cf617919ce050853209277d5997801bf19181703d7047b838ef38d2bca36`，HTTP 200。

前端脚本：
已捕获 11 个关联脚本，地址和摘要见 JSON。业务脚本包括：`https://o2o.unee.com.cn/web-seo/pc/html/zhcx/js/zhcxCommon.js`、`https://o2o.unee.com.cn/web-seo/pc/js/niceValidator/local/zh_CN.js`、`https://o2o.unee.com.cn/web-seo/pc/html/zhcx/js/zhcx.js`。

同一页面加载步骤内观察到的请求：

| 方法 | 路径 | HTTP | 查询参数名 | 请求体参数名 | Evidence |
| --- | --- | --- | --- | --- | --- |
| POST | /web-common/common/systemUserOrg | 200 | system_user_id | findPath | ev_38947e25f18f5c3530edafcc8a81c9e535540d7a35a161748e64dc800d952267 |
| POST | /web-common/common/systemDataPermission | 200 | system_user_id, type | findPath | ev_38947e25f18f5c3530edafcc8a81c9e535540d7a35a161748e64dc800d952267 |

静态 AJAX 地址候选，存在于页面或关联脚本，未据此证明业务动作执行：
- `https://o2o.unee.com.cn/web-seo/pc/js/ligerUI/js/ligerui.all.js`：`...`。
- `https://o2o.unee.com.cn/web-seo/pc/html/zhcx/js/zhcx.js`：`/web-seo/pc/qry_arrearageMoney`、`/web-seo/pc/qry_arrearageMoney.json`、`/web-seo/pc/qry_cust_bs`、`/web-seo/pc/qry_cust_order`。

## 统计中心 电子发票管理

路由 `/web-cust/pc/html/invoiceSalesInfo/invoiceSalesInfoList.html`。菜单来源 `ev_25226ae15c591aa25247b4d7ef5e89e5ddd4162209de1bcb9259a6a2f7d462cc`。

菜单定义的操作：导出、查询。这些是菜单权限定义，不代表流程已执行验证。

页面字段：org_name、service_name、other_str、buyer_name、inf_state_name、start_time、end_time。

页面按钮：查询。

关联脚本中的静态表头候选：城市公司、服务中心、房号、申请人、手机号码、开票类型、购方名称、交付邮箱、销方名称、销方税号、发票代码、发票号码、不含税金额、税额、含税金额、状态、申请时间、操作。共享脚本候选可能属于其他路由。

该加载阶段存在失败或 HTTP 错误资源：`/web-cust/pc/js/artDialog/images/plugins/artdialog/loading.gif` 404、`/portal/js/plugins/artDialog/images/plugins/artdialog/loading.gif` 404。页面关闭可能中断请求，需重新观察其影响。

页面证据：
- `ev_09a45f0a06a75d1316e52ebd6f6fa25316e841f7362f861659f9969d3c364feb`，事务 `request-102`，响应摘要 `a1d51e83953e56f88d6a1d4792fc6ab7c0937a51d6ee659838bba3a2a8d18d18`，HTTP 200。

前端脚本：
已捕获 14 个关联脚本，地址和摘要见 JSON。业务脚本包括：`https://o2o.unee.com.cn/web-cust/pc/js/common.js`、`https://o2o.unee.com.cn/web-bus/pc/js/table/custom_table.js`、`https://o2o.unee.com.cn/web-cust/pc/html/invoiceSalesInfo/js/invoiceSalesInfoList.js`、`https://o2o.unee.com.cn/web-cust/pc/js/niceValidator/local/zh_CN.js`、`https://o2o.unee.com.cn/web-cust/pc/js/niceValidator/local/zh_CN.js`。

同一页面加载步骤内观察到的请求：

| 方法 | 路径 | HTTP | 查询参数名 | 请求体参数名 | Evidence |
| --- | --- | --- | --- | --- | --- |
| POST | /web-common/common/systemUserOrg | 200 | system_user_id | findPath | ev_09a45f0a06a75d1316e52ebd6f6fa25316e841f7362f861659f9969d3c364feb |
| POST | /web-common/common/systemDataPermission | 200 | system_user_id, type | findPath | ev_09a45f0a06a75d1316e52ebd6f6fa25316e841f7362f861659f9969d3c364feb |
| POST | /web-common/common/sysConfigQueryRest | 200 |  | column_name, table_name | ev_09a45f0a06a75d1316e52ebd6f6fa25316e841f7362f861659f9969d3c364feb |

静态 AJAX 地址候选，存在于页面或关联脚本，未据此证明业务动作执行：
- `https://o2o.unee.com.cn/web-cust/pc/js/ligerUI/js/ligerui.all.js`：`...`。

## 配置管理 装修配置

路由 `/web-bus/pc/html/decorationConfig/decorationConfig.html`。菜单来源 `ev_25226ae15c591aa25247b4d7ef5e89e5ddd4162209de1bcb9259a6a2f7d462cc`。

菜单定义的操作：新增、修改、删除、查询。这些是菜单权限定义，不代表流程已执行验证。

页面字段：org_name、start_time、end_time。

页面按钮：查询、删除、新增。

关联脚本中的静态表头候选：城市公司、创建人、创建时间、修改时间、操作。共享脚本候选可能属于其他路由。

该加载阶段存在失败或 HTTP 错误资源：`/web-cust/pc/js/artDialog/images/plugins/artdialog/loading.gif` 404、`/portal/js/plugins/artDialog/images/plugins/artdialog/loading.gif` 404。页面关闭可能中断请求，需重新观察其影响。

页面证据：
- `ev_c590a872a43fe0d5c14d31c18cdcb66b904bb81b4e05b852730bf8dceb6eea00`，事务 `request-102`，响应摘要 `441ef6ce71567a249e2fc0c213801dbb2aebf7b84b19457fe1cc925cc2374ec7`，HTTP 200。

前端脚本：
已捕获 17 个关联脚本，地址和摘要见 JSON。业务脚本包括：`https://o2o.unee.com.cn/web-bus/pc/js/table/custom_table.js`、`https://o2o.unee.com.cn/web-bus/pc/js/progressbar/custom_progressbar.js`、`https://o2o.unee.com.cn/web-bus/pc/html/decorationConfig/js/common.js`、`https://o2o.unee.com.cn/web-bus/pc/js/niceValidator/local/zh_CN.js`、`https://o2o.unee.com.cn/web-bus/pc/js/viewerjs/viewer.js`、`https://o2o.unee.com.cn/web-bus/pc/html/scanEvaluate/qrCode/js/viewer_default.js`、`https://o2o.unee.com.cn/web-bus/pc/html/decorationConfig/js/decorationConfig.js`。

同一页面加载步骤内观察到的请求：

| 方法 | 路径 | HTTP | 查询参数名 | 请求体参数名 | Evidence |
| --- | --- | --- | --- | --- | --- |
| POST | /web-common/common/systemUserOrg | 200 | type, system_user_id | findPath | ev_c590a872a43fe0d5c14d31c18cdcb66b904bb81b4e05b852730bf8dceb6eea00 |

静态 AJAX 地址候选，存在于页面或关联脚本，未据此证明业务动作执行：
- `https://o2o.unee.com.cn/web-bus/pc/html/decorationConfig/js/common.js`：`/web-common/common/servsList`。
- `https://o2o.unee.com.cn/web-bus/pc/js/viewerjs/viewer.js`：`src`。
- `https://o2o.unee.com.cn/web-bus/pc/html/scanEvaluate/qrCode/js/viewer_default.js`：`data-original`。
- `https://o2o.unee.com.cn/web-bus/pc/js/ligerUI/js/ligerui.all.js`：`...`。

## 配置管理 图片管理

路由 `/web-cust/pc/html/confManagement/imgConfList.html`。菜单来源 `ev_25226ae15c591aa25247b4d7ef5e89e5ddd4162209de1bcb9259a6a2f7d462cc`。

菜单定义的操作：新增、修改、删除。这些是菜单权限定义，不代表流程已执行验证。

页面字段：org_name、service_name、extra_msg。

页面按钮：查询。

关联脚本中的静态表头候选：城市公司、服务中心、使用位置、创建人、创建时间、修改时间、操作。共享脚本候选可能属于其他路由。

该加载阶段存在失败或 HTTP 错误资源：`/web-cust/pc/js/artDialog/images/plugins/artdialog/loading.gif` 404。页面关闭可能中断请求，需重新观察其影响。

页面证据：
- `ev_c590a872a43fe0d5c14d31c18cdcb66b904bb81b4e05b852730bf8dceb6eea00`，事务 `request-155`，响应摘要 `21b79326b85b41308fc6af1b45b86458cb2a4c97ccbafd7307b82ebcc8822aa1`，HTTP 200。

前端脚本：
已捕获 14 个关联脚本，地址和摘要见 JSON。业务脚本包括：`https://o2o.unee.com.cn/web-cust/pc/js/common.js`、`https://o2o.unee.com.cn/web-cust/pc/js/progressbar/custom_progressbar.js`、`https://o2o.unee.com.cn/web-cust/pc/html/confManagement/js/imgConfList.js`、`https://o2o.unee.com.cn/web-cust/pc/js/niceValidator/local/zh_CN.js`、`https://o2o.unee.com.cn/web-cust/pc/js/niceValidator/local/zh_CN.js`。

同一页面加载步骤内观察到的请求：

| 方法 | 路径 | HTTP | 查询参数名 | 请求体参数名 | Evidence |
| --- | --- | --- | --- | --- | --- |
| POST | /web-common/common/systemUserOrg | 200 | system_user_id | findPath | ev_c590a872a43fe0d5c14d31c18cdcb66b904bb81b4e05b852730bf8dceb6eea00 |
| POST | /web-common/common/systemDataPermission | 200 | system_user_id, type | findPath | ev_c590a872a43fe0d5c14d31c18cdcb66b904bb81b4e05b852730bf8dceb6eea00 |

静态 AJAX 地址候选，存在于页面或关联脚本，未据此证明业务动作执行：
- `https://o2o.unee.com.cn/web-cust/pc/js/ligerUI/js/ligerui.all.js`：`...`。

## 客户服务 待办任务

路由 `/web-cust/pc/html/workbench/toDoTask.html`。菜单来源 `ev_25226ae15c591aa25247b4d7ef5e89e5ddd4162209de1bcb9259a6a2f7d462cc`。

菜单定义的操作：数据管理、提单本人回访、工作台、导出、判定。这些是菜单权限定义，不代表流程已执行验证。

页面字段：org_name、service_name、business_type_name、channel_name、task_type_name、task_status_name、start_time、end_time、business_content、handler、approval_status_cd、approval_release_note。

页面按钮：查询、导出、工作台、返回。

关联脚本中的静态表头候选：城市公司、项目、渠道、业务类型、业务内容、任务类型、任务状态、联系人、联系电话、任务到达时间、任务人、操作。共享脚本候选可能属于其他路由。

页面证据：
- `ev_25226ae15c591aa25247b4d7ef5e89e5ddd4162209de1bcb9259a6a2f7d462cc`，事务 `request-32`，响应摘要 `9375ae318abaa470fb4e5ae98b2a99b1ae8c820df1d31b50b732a90803733495`，HTTP 200。
- `ev_f2631a7dc031a549a87680b1e2affa1a088efdd842c289a316e649c9749ad8e0`，事务 `request-32`，响应摘要 `9375ae318abaa470fb4e5ae98b2a99b1ae8c820df1d31b50b732a90803733495`，HTTP 200。
- `ev_f9175384011de182c5dbe803f89ff1c503383011d5e38b8400f1b55b5997fe5f`，事务 `request-32`，响应摘要 `9375ae318abaa470fb4e5ae98b2a99b1ae8c820df1d31b50b732a90803733495`，HTTP 200。
- `ev_c590a872a43fe0d5c14d31c18cdcb66b904bb81b4e05b852730bf8dceb6eea00`，事务 `request-32`，响应摘要 `9375ae318abaa470fb4e5ae98b2a99b1ae8c820df1d31b50b732a90803733495`，HTTP 200。
- `ev_217ee4e01474a60978df3b0f8593f64ec81bbe05d137d4ca0cfcaf8f1e1ebccf`，事务 `request-32`，响应摘要 `9375ae318abaa470fb4e5ae98b2a99b1ae8c820df1d31b50b732a90803733495`，HTTP 200。
- `ev_c4d4036bc65a408c8041f833ce8889a39169173452dd7d6ae2a6a106c5d2ca2b`，事务 `request-32`，响应摘要 `9375ae318abaa470fb4e5ae98b2a99b1ae8c820df1d31b50b732a90803733495`，HTTP 200。
- `ev_38947e25f18f5c3530edafcc8a81c9e535540d7a35a161748e64dc800d952267`，事务 `request-32`，响应摘要 `9375ae318abaa470fb4e5ae98b2a99b1ae8c820df1d31b50b732a90803733495`，HTTP 200。
- `ev_09a45f0a06a75d1316e52ebd6f6fa25316e841f7362f861659f9969d3c364feb`，事务 `request-32`，响应摘要 `9375ae318abaa470fb4e5ae98b2a99b1ae8c820df1d31b50b732a90803733495`，HTTP 200。
- `ev_9049e649478b51750b2f229948baf3cd299a931299e31a494686e3395de48951`，事务 `request-32`，响应摘要 `9375ae318abaa470fb4e5ae98b2a99b1ae8c820df1d31b50b732a90803733495`，HTTP 200。
- `ev_0cf173243cdb26a582983b2682632c0be53484fd0b8090f23f41b058eb1f61ca`，事务 `request-32`，响应摘要 `9375ae318abaa470fb4e5ae98b2a99b1ae8c820df1d31b50b732a90803733495`，HTTP 200。

前端脚本：
已捕获 16 个关联脚本，地址和摘要见 JSON。业务脚本包括：`https://o2o.unee.com.cn/web-cust/pc/js/esmp_base.js`、`https://o2o.unee.com.cn/web-cust/pc/html/workbench/taskCommon.js`、`https://o2o.unee.com.cn/web-cust/pc/html/work/js/dateFormat.js`、`https://o2o.unee.com.cn/web-cust/pc/html/work/js/resetTableHeight.js`、`https://o2o.unee.com.cn/web-cust/pc/html/workbench/toDoTtask.js`、`https://o2o.unee.com.cn/web-cust/pc/js/niceValidator/local/zh_CN.js`。

静态 AJAX 地址候选，存在于页面或关联脚本，未据此证明业务动作执行：
- `https://o2o.unee.com.cn/web-cust/pc/html/workbench/toDoTtask.js`：`/web-cust/toDoTask/queryTask`、`/web-cust/toDoTask/deleteWaitTask`、`/web-cust/toDoTask/queryUrl`、`/web-cust/toDoTask/checkRecordExists`、`/web-cust/toDoTask/checkDiscuss`、`/web-cust/toDoTask/dealReport`、`/web-odm/addActivityRest/queryActivityInfo`、`/web-cust/toDoTask/queryjddjData`、`/web-cust/toDoTask/getConfig`、`/web-cust/toDoTask/getEventId`。
- `https://o2o.unee.com.cn/web-cust/pc/js/ligerUI/js/ligerui.all.js`：`...`。

## 客户服务 报事

路由 `/web-cust/pc/html/work/sqgl.html`。菜单来源 `ev_25226ae15c591aa25247b4d7ef5e89e5ddd4162209de1bcb9259a6a2f7d462cc`。

菜单定义的操作：查看、新增、导出、列设置、删除。这些是菜单权限定义，不代表流程已执行验证。

页面字段：org_name、service_name、start_time、end_time、status_name、bulletin_type_name、work_type_name、channel_name_we、extra_msg、event_content、handleUserName、responsible_party_name、event_code、event_id。

页面按钮：返回、查询、列设置、新增、删除、导出。

关联脚本中的静态表头候选：城市公司、服务中心、房号、联系人、报事时间、报事内容、当前状态、渠道、投诉来源、关联工单、回访状态。共享脚本候选可能属于其他路由。

该加载阶段存在失败或 HTTP 错误资源：`/portal/js/plugins/artDialog/images/plugins/artdialog/loading.gif` 404、`/web-cust/pc/js/artDialog/images/plugins/artdialog/loading.gif` 404。页面关闭可能中断请求，需重新观察其影响。

页面证据：
- `ev_f2631a7dc031a549a87680b1e2affa1a088efdd842c289a316e649c9749ad8e0`，事务 `request-98`，响应摘要 `5c280663dbfaddd9cf61c4248c0584022eeddb6b40d7f7c3d25f68e59866338c`，HTTP 200。

前端脚本：
已捕获 15 个关联脚本，地址和摘要见 JSON。业务脚本包括：`https://o2o.unee.com.cn/web-cust/pc/js/common.js`、`https://o2o.unee.com.cn/web-cust/pc/html/work/js/dateFormat.js`、`https://o2o.unee.com.cn/web-cust/pc/html/work/js/dateFormat.js`、`https://o2o.unee.com.cn/web-cust/pc/html/work/js/resetTableHeight.js`、`https://o2o.unee.com.cn/web-cust/pc/html/work/js/resetTableHeight.js`、`https://o2o.unee.com.cn/web-cust/pc/js/niceValidator/local/zh_CN.js`、`https://o2o.unee.com.cn/web-cust/pc/js/niceValidator/local/zh_CN.js`、`https://o2o.unee.com.cn/web-cust/pc/html/work/js/sqgl.js`。

HTML 内联脚本静态观察：`ev_f2631a7dc031a549a87680b1e2affa1a088efdd842c289a316e649c9749ad8e0`，内联摘要 `7ef8cee276159e08dbb9adb6ad418ce457c03ccdc7dc45f14dadd64d67bda216`，104 字符。

document.write 动态脚本声明候选 `https://o2o.unee.com.cn/web-cust/pc/html/work/js/sqgl.js`，查询参数名 v；关联同功能中实际已记录的脚本请求，不执行该加载语句。

同一页面加载步骤内观察到的请求：

| 方法 | 路径 | HTTP | 查询参数名 | 请求体参数名 | Evidence |
| --- | --- | --- | --- | --- | --- |
| POST | /web-common/common/systemUserOrg | 200 | system_user_id | findPath | ev_f2631a7dc031a549a87680b1e2affa1a088efdd842c289a316e649c9749ad8e0 |
| POST | /web-common/common/systemDataPermission | 200 | system_user_id, type | findPath | ev_f2631a7dc031a549a87680b1e2affa1a088efdd842c289a316e649c9749ad8e0 |
| POST | /web-common/common/sysConfigQueryRest | 200 |  | column_name, table_name | ev_f2631a7dc031a549a87680b1e2affa1a088efdd842c289a316e649c9749ad8e0 |
| POST | /web-cust/pc/workevent/geConfigStatusCd | 200 |  | not_exposed | ev_f2631a7dc031a549a87680b1e2affa1a088efdd842c289a316e649c9749ad8e0 |
| GET | /web-bus/columnController/getShowColumn | 200 | modules_code | not_exposed | ev_f2631a7dc031a549a87680b1e2affa1a088efdd842c289a316e649c9749ad8e0 |

静态 AJAX 地址候选，存在于页面或关联脚本，未据此证明业务动作执行：
- `https://o2o.unee.com.cn/web-cust/pc/js/ligerUI/js/ligerui.all.js`：`...`。
- `https://o2o.unee.com.cn/web-cust/pc/html/work/js/sqgl.js`：`/web-cust/pc/WorkEventHandle/deleteWork`、`/web-bus/columnController/getShowColumn`。

## 服务调度 管家关系配置

路由 `/web-cust/pc/html/stewardConfig/stewardConfigList.html`。菜单来源 `ev_25226ae15c591aa25247b4d7ef5e89e5ddd4162209de1bcb9259a6a2f7d462cc`。

菜单定义的操作：查询、新增、删除。这些是菜单权限定义，不代表流程已执行验证。

页面字段：org_name、service_name、fields_value。

页面按钮：新增、删除、查询。

关联脚本中的静态表头候选：管家花名、管家实名、工号、联系电话、管理区域。共享脚本候选可能属于其他路由。

页面证据：
- `ev_f9175384011de182c5dbe803f89ff1c503383011d5e38b8400f1b55b5997fe5f`，事务 `request-158`，响应摘要 `9c3730ada04fc9b12d24658224422a26cd445714c4d1430f81589455219efd56`，HTTP 200。

前端脚本：
已捕获 15 个关联脚本，地址和摘要见 JSON。业务脚本包括：`https://o2o.unee.com.cn/web-cust/pc/js/common.js`、`https://o2o.unee.com.cn/web-cust/pc/js/table/custom_table.js`、`https://o2o.unee.com.cn/web-cust/pc/js/progressbar/custom_progressbar.js`、`https://o2o.unee.com.cn/web-cust/pc/html/stewardConfig/js/stewardConfigList.js`、`https://o2o.unee.com.cn/web-cust/pc/js/niceValidator/local/zh_CN.js`、`https://o2o.unee.com.cn/web-cust/pc/js/niceValidator/local/zh_CN.js`。

同一页面加载步骤内观察到的请求：

| 方法 | 路径 | HTTP | 查询参数名 | 请求体参数名 | Evidence |
| --- | --- | --- | --- | --- | --- |
| POST | /web-common/common/systemUserOrg | 200 | system_user_id | findPath | ev_f9175384011de182c5dbe803f89ff1c503383011d5e38b8400f1b55b5997fe5f |
| POST | /web-common/common/systemDataPermission | 200 | system_user_id, type | findPath | ev_f9175384011de182c5dbe803f89ff1c503383011d5e38b8400f1b55b5997fe5f |

静态 AJAX 地址候选，存在于页面或关联脚本，未据此证明业务动作执行：
- `https://o2o.unee.com.cn/web-cust/pc/html/stewardConfig/js/stewardConfigList.js`：`/web-cust/stewardConfig/queryStewardConfigList`。
- `https://o2o.unee.com.cn/web-cust/pc/js/ligerUI/js/ligerui.all.js`：`...`。

## 系统中心 角色管理

路由 `/web-sys/pc/html/roleManage/roleList.html`。菜单来源 `ev_25226ae15c591aa25247b4d7ef5e89e5ddd4162209de1bcb9259a6a2f7d462cc`。

菜单定义的操作：批量分配角色、查询。这些是菜单权限定义，不代表流程已执行验证。

页面字段：role_level_name、role_name、ROLE_CODE。

页面按钮：查 询。

关联脚本中的静态表头候选：角色编码、角色名称、角色级别、创建人、备注、操作。共享脚本候选可能属于其他路由。

页面证据：
- `ev_0cf173243cdb26a582983b2682632c0be53484fd0b8090f23f41b058eb1f61ca`，事务 `request-146`，响应摘要 `4e6205feb1689ea088d4f55529a3638b5cf0b6b774eb01a0ee3749c8681795db`，HTTP 200。

前端脚本：
已捕获 5 个关联脚本，地址和摘要见 JSON。业务脚本包括：`https://o2o.unee.com.cn/web-sys/pc/js/common.js`、`https://o2o.unee.com.cn/web-sys/pc/js/niceValidator/local/zh_CN.js`、`https://o2o.unee.com.cn/web-sys/pc/js/progressbar/custom_progressbar.js`、`https://o2o.unee.com.cn/web-sys/pc/html/roleManage/js/esmp_base.js`、`https://o2o.unee.com.cn/web-sys/pc/html/roleManage/js/roleList.js`。

同一页面加载步骤内观察到的请求：

| 方法 | 路径 | HTTP | 查询参数名 | 请求体参数名 | Evidence |
| --- | --- | --- | --- | --- | --- |
| POST | /web-sys/role/queryRoleLevel | 200 |  | captured | ev_0cf173243cdb26a582983b2682632c0be53484fd0b8090f23f41b058eb1f61ca |
| POST | /web-sys/role/queryRoleInfo | 200 |  | ROLE_CODE, ROLE_LEVEL_CD, page, pageSize, pagesize, startNum, viewkey | ev_0cf173243cdb26a582983b2682632c0be53484fd0b8090f23f41b058eb1f61ca |

静态 AJAX 地址候选，存在于页面或关联脚本，未据此证明业务动作执行：
- `https://o2o.unee.com.cn/web-sys/pc/html/roleManage/js/roleList.js`：`/web-sys/role/queryRoleLevel`、`/web-sys/role/queryRoleInfo`。

## 运营中心 广告管理

路由 `/web-bus/pc/html/admanage/advertisingList.html`。菜单来源 `ev_25226ae15c591aa25247b4d7ef5e89e5ddd4162209de1bcb9259a6a2f7d462cc`。

菜单定义的操作：上架、下架、保存、保存为草稿、添加、修改、置顶、查询。这些是菜单权限定义，不代表流程已执行验证。

页面字段：org_name、service_name、initiator_type_name、ad_type_name、ad_location_name、status_name、status_top_name、AD_TITLE。

页面按钮：查询、新增、二维码下载、诺谱盾广告获取。

关联脚本中的静态表头候选：广告类型、广告标题、广告商、广告位置、有效期、提交时间、广告状态、置顶状态、二维码、操作。共享脚本候选可能属于其他路由。

页面证据：
- `ev_c4d4036bc65a408c8041f833ce8889a39169173452dd7d6ae2a6a106c5d2ca2b`，事务 `request-157`，响应摘要 `bcc6e9e19de22864eb3eac98a71d1ec9c450a4408d7f4a116ba292328f2da62f`，HTTP 200。

前端脚本：
已捕获 7 个关联脚本，地址和摘要见 JSON。业务脚本包括：`https://o2o.unee.com.cn/web-bus/pc/js/progressbar/custom_progressbar.js`、`https://o2o.unee.com.cn/web-bus/pc/js/niceValidator/local/zh_CN.js`、`https://o2o.unee.com.cn/web-bus/pc/js/viewerjs/viewer.js`、`https://o2o.unee.com.cn/web-bus/pc/html/scanEvaluate/qrCode/js/viewer_default.js`、`https://o2o.unee.com.cn/web-bus/pc/html/admanage/js/common.js`、`https://o2o.unee.com.cn/web-bus/pc/html/admanage/js/resetTableHeight.js`、`https://o2o.unee.com.cn/web-bus/pc/html/admanage/js/adonfPre.js`。

HTML 内联脚本静态观察：`ev_c4d4036bc65a408c8041f833ce8889a39169173452dd7d6ae2a6a106c5d2ca2b`，内联摘要 `9900b0e9786211c5da9ca1bf906691462550e2e8bef3b104b9a84222430fd8b8`，437 字符。

document.write 动态脚本声明候选 `https://o2o.unee.com.cn/web-bus/pc/html/admanage/js/common.js`，查询参数名 v；关联同功能中实际已记录的脚本请求，不执行该加载语句。

document.write 动态脚本声明候选 `https://o2o.unee.com.cn/web-bus/pc/html/admanage/js/resetTableHeight.js`，查询参数名 v；关联同功能中实际已记录的脚本请求，不执行该加载语句。

document.write 动态脚本声明候选 `https://o2o.unee.com.cn/web-bus/pc/html/admanage/js/adonfPre.js`，查询参数名 v；关联同功能中实际已记录的脚本请求，不执行该加载语句。

document.write 动态脚本声明候选 `https://o2o.unee.com.cn/web-bus/pc/html/admanage/js/advertisingListLiger.js`，查询参数名 v；关联同功能中实际已记录的脚本请求，不执行该加载语句。

同一页面加载步骤内观察到的请求：

| 方法 | 路径 | HTTP | 查询参数名 | 请求体参数名 | Evidence |
| --- | --- | --- | --- | --- | --- |
| POST | /web-common/common/systemUserOrg | 200 | system_user_id | findPath | ev_c4d4036bc65a408c8041f833ce8889a39169173452dd7d6ae2a6a106c5d2ca2b |
| POST | /web-common/common/systemDataPermission | 200 | system_user_id, type | findPath | ev_c4d4036bc65a408c8041f833ce8889a39169173452dd7d6ae2a6a106c5d2ca2b |
| POST | /web-common/common/sysConfigQueryRest | 200 |  | column_name, table_name | ev_c4d4036bc65a408c8041f833ce8889a39169173452dd7d6ae2a6a106c5d2ca2b |

静态 AJAX 地址候选，存在于页面或关联脚本，未据此证明业务动作执行：
- `https://o2o.unee.com.cn/web-bus/pc/js/viewerjs/viewer.js`：`src`。
- `https://o2o.unee.com.cn/web-bus/pc/html/scanEvaluate/qrCode/js/viewer_default.js`：`data-original`。
- `https://o2o.unee.com.cn/web-bus/pc/html/admanage/js/adonfPre.js`：`/web-bus/adonoff/onCheck`、`/web-bus/adonoff/offCheck`。
- `https://o2o.unee.com.cn/web-bus/pc/html/admanage/js/advertisingListLiger.js`：`/web-bus/mobile/thirdParty/syncThirdAdData`、`/web-bus/advertising/advertisingListQuery`、`/web-bus/advertising/addQrCode`。

## 客户管理 房产管理

路由 `/web-cust/pc/html/Customers/HourseList.html`。菜单来源 `ev_25226ae15c591aa25247b4d7ef5e89e5ddd4162209de1bcb9259a6a2f7d462cc`。

菜单定义的操作：使用人查看、查询。这些是菜单权限定义，不代表流程已执行验证。

页面字段：org_name、service_name、build_name、hourse_name。

页面按钮：查询。

关联脚本中的静态表头候选：房号、楼层、房产名称、房产类型、建筑面积、计费面积、公摊面积、入伙日期、操作。共享脚本候选可能属于其他路由。

页面证据：
- `ev_217ee4e01474a60978df3b0f8593f64ec81bbe05d137d4ca0cfcaf8f1e1ebccf`，事务 `request-134`，响应摘要 `adf8f5b8d1431d022a84759251bde2174582c38c9f4ef993fb4c50d413d8d278`，HTTP 200。

前端脚本：
已捕获 10 个关联脚本，地址和摘要见 JSON。业务脚本包括：`https://o2o.unee.com.cn/web-cust/pc/html/Customers/js/houseCommon.js`、`https://o2o.unee.com.cn/web-cust/pc/js/niceValidator/local/zh_CN.js`、`https://o2o.unee.com.cn/web-cust/pc/js/niceValidator/local/zh_CN.js`、`https://o2o.unee.com.cn/web-cust/pc/html/work/js/resetTableHeight.js`、`https://o2o.unee.com.cn/web-cust/pc/html/work/js/resetTableHeight.js`、`https://o2o.unee.com.cn/web-cust/pc/html/Customers/js/houseTable.js`。

同一页面加载步骤内观察到的请求：

| 方法 | 路径 | HTTP | 查询参数名 | 请求体参数名 | Evidence |
| --- | --- | --- | --- | --- | --- |
| POST | /web-common/common/systemUserOrg | 200 | system_user_id | findPath | ev_217ee4e01474a60978df3b0f8593f64ec81bbe05d137d4ca0cfcaf8f1e1ebccf |
| POST | /web-common/common/systemDataPermission | 200 | system_user_id, type | findPath | ev_217ee4e01474a60978df3b0f8593f64ec81bbe05d137d4ca0cfcaf8f1e1ebccf |
| POST | /web-cust/mobile/queryld | 200 |  | mothodType, service_id | ev_217ee4e01474a60978df3b0f8593f64ec81bbe05d137d4ca0cfcaf8f1e1ebccf |

静态 AJAX 地址候选，存在于页面或关联脚本，未据此证明业务动作执行：
- `https://o2o.unee.com.cn/web-cust/pc/js/ligerUI/js/ligerui.all.js`：`...`。
- `https://o2o.unee.com.cn/web-cust/pc/html/Customers/js/houseTable.js`：`/web-cust/pc/queryhourselist`。

## 综合查询 开门记录

路由 `/web-seo/pc/html/telOpenDoor/telOpenDoorList.html`。菜单来源 `ev_25226ae15c591aa25247b4d7ef5e89e5ddd4162209de1bcb9259a6a2f7d462cc`。

菜单定义的操作：导出、查询。这些是菜单权限定义，不代表流程已执行验证。

页面字段：org_name、service_name、start_time、end_time、door_name、record_type_name、status_name、fields_name、fields_value。

页面按钮：查询。

关联脚本中的静态表头候选：来源、客户姓名、联系电话、访客预约单号、门名称、开门时间、开门状态、备注。共享脚本候选可能属于其他路由。

页面证据：
- `ev_38947e25f18f5c3530edafcc8a81c9e535540d7a35a161748e64dc800d952267`，事务 `request-141`，响应摘要 `5c5dba7519763566659ccadbb5e39669f9e878e2454922b43c00f2820f3b2bc0`，HTTP 200。

前端脚本：
已捕获 11 个关联脚本，地址和摘要见 JSON。业务脚本包括：`https://o2o.unee.com.cn/web-seo/pc/js/common.js`、`https://o2o.unee.com.cn/web-seo/pc/js/progressbar/custom_progressbar.js`、`https://o2o.unee.com.cn/web-seo/pc/js/niceValidator/local/zh_CN.js`、`https://o2o.unee.com.cn/web-seo/pc/html/telOpenDoor/js/telOpenDoorList.js`。

同一页面加载步骤内观察到的请求：

| 方法 | 路径 | HTTP | 查询参数名 | 请求体参数名 | Evidence |
| --- | --- | --- | --- | --- | --- |
| POST | /web-common/common/systemUserOrg | 200 | system_user_id | findPath | ev_38947e25f18f5c3530edafcc8a81c9e535540d7a35a161748e64dc800d952267 |
| POST | /web-common/common/systemDataPermission | 200 | system_user_id, type | findPath | ev_38947e25f18f5c3530edafcc8a81c9e535540d7a35a161748e64dc800d952267 |
| POST | /web-common/common/sysConfigQueryRest | 200 |  | column_name, table_name | ev_38947e25f18f5c3530edafcc8a81c9e535540d7a35a161748e64dc800d952267 |

静态 AJAX 地址候选，存在于页面或关联脚本，未据此证明业务动作执行：
- `https://o2o.unee.com.cn/web-seo/pc/js/ligerUI/js/ligerui.all.js`：`...`。
- `https://o2o.unee.com.cn/web-seo/pc/html/telOpenDoor/js/telOpenDoorList.js`：`/web-seo/pc/telOpenDoorList`。

## 配置管理 门设备管理

路由 `/web-bus/pc/html/DoorEquipmentManagement/doorEquipList.html`。菜单来源 `ev_25226ae15c591aa25247b4d7ef5e89e5ddd4162209de1bcb9259a6a2f7d462cc`。

菜单定义的操作：新增、批量新增、导出、查询。这些是菜单权限定义，不代表流程已执行验证。

页面字段：org_name、service_name、door_type_name、door_name。

页面按钮：导出、新增、批量新增、查询。

关联脚本中的静态表头候选：设备厂商、门类型、门名称、设备ID、物理地址、设备MAC、描述、设备类型、固件版本、密钥、修改时间、修改人、操作。共享脚本候选可能属于其他路由。

页面证据：
- `ev_c590a872a43fe0d5c14d31c18cdcb66b904bb81b4e05b852730bf8dceb6eea00`，事务 `request-205`，响应摘要 `37a2435559186a86914f4b7deb1b393629a46959d343b2aa9d351890a1894709`，HTTP 200。

前端脚本：
已捕获 14 个关联脚本，地址和摘要见 JSON。业务脚本包括：`https://o2o.unee.com.cn/web-bus/pc/js/common.js`、`https://o2o.unee.com.cn/web-bus/pc/js/progressbar/custom_progressbar.js`、`https://o2o.unee.com.cn/web-bus/pc/html/DoorEquipmentManagement/js/resetTableHeight.js`、`https://o2o.unee.com.cn/web-bus/pc/js/niceValidator/local/zh_CN.js`、`https://o2o.unee.com.cn/web-bus/pc/html/DoorEquipmentManagement/js/doorEquipList.js`。

同一页面加载步骤内观察到的请求：

| 方法 | 路径 | HTTP | 查询参数名 | 请求体参数名 | Evidence |
| --- | --- | --- | --- | --- | --- |
| POST | /web-common/common/sysConfigQueryRest | 200 |  | column_name, table_name | ev_c590a872a43fe0d5c14d31c18cdcb66b904bb81b4e05b852730bf8dceb6eea00 |
| POST | /web-common/permission/common/systemUserOrg | 200 | system_user_id | findPath | ev_c590a872a43fe0d5c14d31c18cdcb66b904bb81b4e05b852730bf8dceb6eea00 |
| POST | /web-common/permission/common/systemDataPermission | 200 | system_user_id, type | findPath | ev_c590a872a43fe0d5c14d31c18cdcb66b904bb81b4e05b852730bf8dceb6eea00 |

静态 AJAX 地址候选，存在于页面或关联脚本，未据此证明业务动作执行：
- `https://o2o.unee.com.cn/web-bus/pc/js/ligerUI/js/ligerui.all.js`：`...`。
- `https://o2o.unee.com.cn/web-bus/pc/html/DoorEquipmentManagement/js/doorEquipList.js`：`/web-bus/doorEquip/doorEquipListQuery`。

## 配置管理 消息模板

路由 `/web-bus/pc/html/templateManage/templateList.html`。菜单来源 `ev_25226ae15c591aa25247b4d7ef5e89e5ddd4162209de1bcb9259a6a2f7d462cc`。

菜单定义的操作：查看、新增、删除、查询。这些是菜单权限定义，不代表流程已执行验证。

页面字段：org_name、service_name、template_name。

页面按钮：新增、删除、查询。

关联脚本中的静态表头候选：序号、城市公司、服务中心、使用位置、模板类型、标题、是否生效、创建人、创建时间、修改时间。共享脚本候选可能属于其他路由。

该加载阶段存在失败或 HTTP 错误资源：`/web-cust/pc/js/artDialog/images/plugins/artdialog/loading.gif` 404。页面关闭可能中断请求，需重新观察其影响。

页面证据：
- `ev_c590a872a43fe0d5c14d31c18cdcb66b904bb81b4e05b852730bf8dceb6eea00`，事务 `request-255`，响应摘要 `f7907e40fac5871d8043798f33cea11652b2e570b05d8455d152be1a1f87d6a1`，HTTP 200。

前端脚本：
已捕获 5 个关联脚本，地址和摘要见 JSON。业务脚本包括：`https://o2o.unee.com.cn/web-bus/pc/js/common.js`、`https://o2o.unee.com.cn/web-bus/pc/js/progressbar/custom_progressbar.js`、`https://o2o.unee.com.cn/web-bus/pc/js/niceValidator/local/zh_CN.js`、`https://o2o.unee.com.cn/web-bus/pc/js/resetTableHeight.js`、`https://o2o.unee.com.cn/web-bus/pc/html/templateManage/js/templateList.js`。

同一页面加载步骤内观察到的请求：

| 方法 | 路径 | HTTP | 查询参数名 | 请求体参数名 | Evidence |
| --- | --- | --- | --- | --- | --- |
| POST | /web-common/permission/common/systemUserOrg | 200 | system_user_id | findPath | ev_c590a872a43fe0d5c14d31c18cdcb66b904bb81b4e05b852730bf8dceb6eea00 |
| POST | /web-common/permission/common/systemDataPermission | 200 | system_user_id, type | findPath | ev_c590a872a43fe0d5c14d31c18cdcb66b904bb81b4e05b852730bf8dceb6eea00 |

静态 AJAX 地址候选，存在于页面或关联脚本，未据此证明业务动作执行：
- `https://o2o.unee.com.cn/web-bus/pc/html/templateManage/js/templateList.js`：`/web-bus/template/templateListQuery`。

## 统计中心 用户使用详情

路由 `/web-seo/pc/html/useInfo/useInfo.html`。菜单来源 `ev_25226ae15c591aa25247b4d7ef5e89e5ddd4162209de1bcb9259a6a2f7d462cc`。

菜单定义的操作：查询、导出。这些是菜单权限定义，不代表流程已执行验证。

页面字段：org_name、service_name、start_time、end_time。

页面按钮：查询。

关联脚本中的静态表头候选：项目名称、项目编码、认证户数、小区总户数、业主认证比例、员工认证数、小区员工总数、员工认证比例。共享脚本候选可能属于其他路由。

页面运行错误：Cannot read properties of undefined (reading 'config')。错误与该加载步骤在时间上关联，未证明具体调用因果。

页面证据：
- `ev_09a45f0a06a75d1316e52ebd6f6fa25316e841f7362f861659f9969d3c364feb`，事务 `request-152`，响应摘要 `b5003c3bac177a3978fd085dcc2c963356b1b5a67128555ba0e6175463c17ee1`，HTTP 200。

前端脚本：
已捕获 11 个关联脚本，地址和摘要见 JSON。业务脚本包括：`https://o2o.unee.com.cn/web-seo/pc/html/useInfo/js/common.js`、`https://o2o.unee.com.cn/web-seo/pc/js/progressbar/custom_progressbar.js`、`https://o2o.unee.com.cn/web-seo/pc/js/niceValidator/local/zh_CN.js`、`https://o2o.unee.com.cn/web-seo/pc/html/useInfo/js/useInfo.js`。

同一页面加载步骤内观察到的请求：

| 方法 | 路径 | HTTP | 查询参数名 | 请求体参数名 | Evidence |
| --- | --- | --- | --- | --- | --- |
| POST | /web-common/common/systemUserOrg | 200 | system_user_id | findPath | ev_09a45f0a06a75d1316e52ebd6f6fa25316e841f7362f861659f9969d3c364feb |
| POST | /web-common/common/systemDataPermission | 200 | system_user_id, type | findPath | ev_09a45f0a06a75d1316e52ebd6f6fa25316e841f7362f861659f9969d3c364feb |

静态 AJAX 地址候选，存在于页面或关联脚本，未据此证明业务动作执行：
- `https://o2o.unee.com.cn/web-seo/pc/js/ligerUI/js/ligerui.all.js`：`...`。
- `https://o2o.unee.com.cn/web-seo/pc/html/useInfo/js/useInfo.js`：`/web-seo/useInfoController/listCustomerUseInfo`。

## 客户服务 代缴代扣管理

路由 `/web-cust/pc/html/bankWithholding/bankWithholding.html`。菜单来源 `ev_25226ae15c591aa25247b4d7ef5e89e5ddd4162209de1bcb9259a6a2f7d462cc`。

菜单定义的操作：查询、导出。这些是菜单权限定义，不代表流程已执行验证。

页面字段：org_name、service_name、keyword_name、buyer_name、status_name、agreement_source_name、start_time、end_time、house_property、business_type_name。

页面按钮：查询、导出。

关联脚本中的静态表头候选：城市公司、服务中心、默认房产、签约人姓名、签约户号、签约人手机号、持卡人姓名、签约证件、卡号、银行预留手机号、签约时间、解约时间、协议号、状态、签约来源、操作。共享脚本候选可能属于其他路由。

页面证据：
- `ev_f2631a7dc031a549a87680b1e2affa1a088efdd842c289a316e649c9749ad8e0`，事务 `request-155`，响应摘要 `370da021e271ed9ce0cf5afea4cdac7234ed7fd3359803564cd8a1f8b9140e80`，HTTP 200。

前端脚本：
已捕获 14 个关联脚本，地址和摘要见 JSON。业务脚本包括：`https://o2o.unee.com.cn/web-cust/pc/html/bankWithholding/js/bankCommon.js`、`https://o2o.unee.com.cn/web-cust/pc/js/table/custom_table.js`、`https://o2o.unee.com.cn/web-cust/pc/js/niceValidator/local/zh_CN.js`、`https://o2o.unee.com.cn/web-cust/pc/js/niceValidator/local/zh_CN.js`、`https://o2o.unee.com.cn/web-cust/pc/html/bankWithholding/js/bankWithholding.js`。

同一页面加载步骤内观察到的请求：

| 方法 | 路径 | HTTP | 查询参数名 | 请求体参数名 | Evidence |
| --- | --- | --- | --- | --- | --- |
| POST | /web-common/common/systemUserOrg | 200 | system_user_id | findPath | ev_f2631a7dc031a549a87680b1e2affa1a088efdd842c289a316e649c9749ad8e0 |
| POST | /web-common/common/systemDataPermission | 200 | system_user_id, type | findPath | ev_f2631a7dc031a549a87680b1e2affa1a088efdd842c289a316e649c9749ad8e0 |
| POST | /web-cust/bankWithholding/queryConfig | 200 |  | not_exposed | ev_f2631a7dc031a549a87680b1e2affa1a088efdd842c289a316e649c9749ad8e0 |
| POST | /web-cust/bankWithholding/qianyueConfig | 200 |  | not_exposed | ev_f2631a7dc031a549a87680b1e2affa1a088efdd842c289a316e649c9749ad8e0 |
| POST | /web-cust/bankWithholding/qianyueleixingConfig | 200 |  | not_exposed | ev_f2631a7dc031a549a87680b1e2affa1a088efdd842c289a316e649c9749ad8e0 |
| POST | /web-cust/bankWithholding/keywordConfig | 200 |  | not_exposed | ev_f2631a7dc031a549a87680b1e2affa1a088efdd842c289a316e649c9749ad8e0 |

静态 AJAX 地址候选，存在于页面或关联脚本，未据此证明业务动作执行：
- `https://o2o.unee.com.cn/web-cust/pc/js/ligerUI/js/ligerui.all.js`：`...`。
- `https://o2o.unee.com.cn/web-cust/pc/html/bankWithholding/js/bankWithholding.js`：`/web-cust/bankWithholding/initialization`、`/web-cust/bankWithholding/queryConfig`、`/web-cust/bankWithholding/qianyueConfig`、`/web-cust/bankWithholding/qianyueleixingConfig`、`/web-cust/bankWithholding/keywordConfig`。

## 综合查询 客户号码变更查询

路由 `/web-seo/pc/html/custUpdateLog/custUpdateLog.html`。菜单来源 `ev_25226ae15c591aa25247b4d7ef5e89e5ddd4162209de1bcb9259a6a2f7d462cc`。

菜单定义的操作：导出、查询。这些是菜单权限定义，不代表流程已执行验证。

页面字段：org_name、service_name、start_time、end_time、cust_name。

页面按钮：查询。

关联脚本中的静态表头候选：项目名称、客户名称、房产、原手机号、新手机号、变更原因、变更渠道、修改时间、员工工号、员工姓名。共享脚本候选可能属于其他路由。

页面运行错误：Cannot read properties of undefined (reading 'config')。错误与该加载步骤在时间上关联，未证明具体调用因果。

页面证据：
- `ev_38947e25f18f5c3530edafcc8a81c9e535540d7a35a161748e64dc800d952267`，事务 `request-189`，响应摘要 `5427abe0e4040ee841ef83af9dfd644b9cef84f33ffb6bfe334ca77ed349fc57`，HTTP 200。

前端脚本：
已捕获 10 个关联脚本，地址和摘要见 JSON。业务脚本包括：`https://o2o.unee.com.cn/web-seo/pc/js/common.js`、`https://o2o.unee.com.cn/web-seo/pc/js/progressbar/custom_progressbar.js`、`https://o2o.unee.com.cn/web-seo/pc/js/niceValidator/local/zh_CN.js`、`https://o2o.unee.com.cn/web-seo/pc/html/custUpdateLog/js/custUpdateLog.js`。

同一页面加载步骤内观察到的请求：

| 方法 | 路径 | HTTP | 查询参数名 | 请求体参数名 | Evidence |
| --- | --- | --- | --- | --- | --- |
| POST | /web-common/common/systemUserOrg | 200 | system_user_id | findPath | ev_38947e25f18f5c3530edafcc8a81c9e535540d7a35a161748e64dc800d952267 |
| POST | /web-common/common/systemDataPermission | 200 | system_user_id, type | findPath | ev_38947e25f18f5c3530edafcc8a81c9e535540d7a35a161748e64dc800d952267 |

静态 AJAX 地址候选，存在于页面或关联脚本，未据此证明业务动作执行：
- `https://o2o.unee.com.cn/web-seo/pc/js/ligerUI/js/ligerui.all.js`：`...`。
- `https://o2o.unee.com.cn/web-seo/pc/html/custUpdateLog/js/custUpdateLog.js`：`/web-seo/custUpdateLog/selectList`。

## 配置管理 问卷配置

路由 `/web-bus/pc/html/questionsConfig/questionsConfigList.html`。菜单来源 `ev_25226ae15c591aa25247b4d7ef5e89e5ddd4162209de1bcb9259a6a2f7d462cc`。

菜单定义的操作：新增、复制、修改、删除、启用、停止、问卷链接、新增模版、删除模版、复制模版、修改模版、启用模版、停止模版、模版问卷链接、二维码下载、消息推送、短信推送、查询。这些是菜单权限定义，不代表流程已执行验证。

页面字段：org_name、service_name、control_type_name、status_name、start_time、end_time、ques_name。

页面按钮：查询、项目二维码、二维码下载。

关联脚本中的静态表头候选：问卷名称、发布渠道、管控范围、用户组织、状态、创建时间、生效时间、失效时间、停止时间、二维码、操作。共享脚本候选可能属于其他路由。

该加载阶段存在失败或 HTTP 错误资源：`/web-bus/pc/js/ligerUI/skins/ligerui-icons.css` net::ERR_ABORTED。页面关闭可能中断请求，需重新观察其影响。

页面证据：
- `ev_c590a872a43fe0d5c14d31c18cdcb66b904bb81b4e05b852730bf8dceb6eea00`，事务 `request-306`，响应摘要 `da444e337fc45645f999672ad547209645334ca908fcef6506bf9de43c31f664`，HTTP 200。

前端脚本：
已捕获 9 个关联脚本，地址和摘要见 JSON。业务脚本包括：`https://o2o.unee.com.cn/web-bus/pc/js/table/custom_table.js`、`https://o2o.unee.com.cn/web-bus/pc/js/progressbar/custom_progressbar.js`、`https://o2o.unee.com.cn/web-bus/pc/html/questionsConfig/js/common.js`、`https://o2o.unee.com.cn/web-bus/pc/js/niceValidator/local/zh_CN.js`、`https://o2o.unee.com.cn/web-bus/pc/js/viewerjs/viewer.js`、`https://o2o.unee.com.cn/web-bus/pc/html/scanEvaluate/qrCode/js/viewer_default.js`、`https://o2o.unee.com.cn/web-bus/pc/html/questionsConfig/js/questionsConfigList.js`。

同一页面加载步骤内观察到的请求：

| 方法 | 路径 | HTTP | 查询参数名 | 请求体参数名 | Evidence |
| --- | --- | --- | --- | --- | --- |
| POST | /web-common/common/systemUserOrg | 200 | system_user_id | findPath | ev_c590a872a43fe0d5c14d31c18cdcb66b904bb81b4e05b852730bf8dceb6eea00 |
| POST | /web-common/common/systemDataPermission | 200 | system_user_id, type | findPath | ev_c590a872a43fe0d5c14d31c18cdcb66b904bb81b4e05b852730bf8dceb6eea00 |
| POST | /web-common/common/sysConfigQueryRest | 200 |  | column_name, table_name | ev_c590a872a43fe0d5c14d31c18cdcb66b904bb81b4e05b852730bf8dceb6eea00 |
| POST | /web-bus/quesQrCodeInfoController/qrCodeManageListQuery | 200 |  | not_exposed | ev_c590a872a43fe0d5c14d31c18cdcb66b904bb81b4e05b852730bf8dceb6eea00 |
| POST | /web-bus/pc/initControlTypeName | 200 |  | not_exposed | ev_c590a872a43fe0d5c14d31c18cdcb66b904bb81b4e05b852730bf8dceb6eea00 |

静态 AJAX 地址候选，存在于页面或关联脚本，未据此证明业务动作执行：
- `https://o2o.unee.com.cn/web-bus/pc/js/viewerjs/viewer.js`：`src`。
- `https://o2o.unee.com.cn/web-bus/pc/html/scanEvaluate/qrCode/js/viewer_default.js`：`data-original`。
- `https://o2o.unee.com.cn/web-bus/pc/html/questionsConfig/js/questionsConfigList.js`：`/web-bus/quesQrCodeInfoController/qrCodeManageListQuery`、`/web-bus/pc/initControlTypeName`、`/web-bus/quesBaseInfoController/copyQuesBaseInfo`、`/web-bus/pc/stopTemplateStatus`、`/web-bus/pc/stopStatus`、`/web-bus/pc/questionConfig/createQuesTemplate`、`/web-bus/pc/ques/createQuestionsQR`、`/web-bus/pc/ques/getMessagePushNum`、`/web-bus/pc/checkTemplateStatus`。

## 统计中心 员工登录清单

路由 `/web-seo/pc/html/staffLoginList/staffLoginList.html`。菜单来源 `ev_25226ae15c591aa25247b4d7ef5e89e5ddd4162209de1bcb9259a6a2f7d462cc`。

菜单定义的操作：导出、查询。这些是菜单权限定义，不代表流程已执行验证。

页面字段：org_name、service_name、start_time、end_time、staff_code、checkbox。

页面按钮：导出、查询。

关联脚本中的静态表头候选：服务中心、员工名称、工号、联系电话、登录时间。共享脚本候选可能属于其他路由。

页面证据：
- `ev_09a45f0a06a75d1316e52ebd6f6fa25316e841f7362f861659f9969d3c364feb`，事务 `request-197`，响应摘要 `374e328f89f249c3ca66b919179d53c9b62236d573965566abeb3473a045aa9c`，HTTP 200。

前端脚本：
已捕获 11 个关联脚本，地址和摘要见 JSON。业务脚本包括：`https://o2o.unee.com.cn/web-seo/pc/html/useInfo/js/common.js`、`https://o2o.unee.com.cn/web-seo/pc/js/progressbar/custom_progressbar.js`、`https://o2o.unee.com.cn/web-seo/pc/js/niceValidator/local/zh_CN.js`、`https://o2o.unee.com.cn/web-seo/pc/html/staffLoginList/js/staffLoginList.js`。

同一页面加载步骤内观察到的请求：

| 方法 | 路径 | HTTP | 查询参数名 | 请求体参数名 | Evidence |
| --- | --- | --- | --- | --- | --- |
| POST | /web-common/common/systemUserOrg | 200 | system_user_id | findPath | ev_09a45f0a06a75d1316e52ebd6f6fa25316e841f7362f861659f9969d3c364feb |
| POST | /web-common/common/systemDataPermission | 200 | system_user_id, type | findPath | ev_09a45f0a06a75d1316e52ebd6f6fa25316e841f7362f861659f9969d3c364feb |

静态 AJAX 地址候选，存在于页面或关联脚本，未据此证明业务动作执行：
- `https://o2o.unee.com.cn/web-seo/pc/js/ligerUI/js/ligerui.all.js`：`...`。
- `https://o2o.unee.com.cn/web-seo/pc/html/staffLoginList/js/staffLoginList.js`：`/web-seo/pc/queryStaffLoginList`。

## 客户服务 放行条

路由 `/web-cust/pc/html/releaseBar/releaseBarList.html`。菜单来源 `ev_25226ae15c591aa25247b4d7ef5e89e5ddd4162209de1bcb9259a6a2f7d462cc`。

菜单定义的操作：查询、打印。这些是菜单权限定义，不代表流程已执行验证。

页面字段：org_name、service_name、start_time、end_time、status_name、extra_msg、release_id、apply_year、apply_month、apply_day、apply_hour、apply_minute、cust_name、contact、apply_note、approval_status_cd、approval_release_note。

页面按钮：返回、查询、审批、新增、打印。

关联脚本中的静态表头候选：序号、放行ID、房号、申请人、联系电话、放行时间、物品清单、欠费状态、业主姓名、业主电话、状态、备注、操作。共享脚本候选可能属于其他路由。

页面证据：
- `ev_f2631a7dc031a549a87680b1e2affa1a088efdd842c289a316e649c9749ad8e0`，事务 `request-207`，响应摘要 `163b48f1a8f6c90ef03932d3b47c08f424c859fdaf9e10bf386716b5d802e810`，HTTP 200。

前端脚本：
已捕获 15 个关联脚本，地址和摘要见 JSON。业务脚本包括：`https://o2o.unee.com.cn/web-cust/pc/js/table/custom_table.js`、`https://o2o.unee.com.cn/web-cust/pc/js/progressbar/custom_progressbar.js`、`https://o2o.unee.com.cn/web-cust/pc/js/common.js`、`https://o2o.unee.com.cn/web-cust/pc/js/esmp_base.js`、`https://o2o.unee.com.cn/web-cust/pc/js/esmp_base.js`、`https://o2o.unee.com.cn/web-cust/pc/js/autocomplete/autoSelect.js`、`https://o2o.unee.com.cn/web-cust/pc/js/niceValidator/local/zh_CN.js`、`https://o2o.unee.com.cn/web-cust/pc/js/niceValidator/local/zh_CN.js`、`https://o2o.unee.com.cn/web-cust/pc/html/releaseBar/js/releaseBarList.js`。

同一页面加载步骤内观察到的请求：

| 方法 | 路径 | HTTP | 查询参数名 | 请求体参数名 | Evidence |
| --- | --- | --- | --- | --- | --- |
| POST | /web-common/common/systemUserOrg | 200 | system_user_id | findPath | ev_f2631a7dc031a549a87680b1e2affa1a088efdd842c289a316e649c9749ad8e0 |
| POST | /web-common/common/systemDataPermission | 200 | system_user_id, type | findPath | ev_f2631a7dc031a549a87680b1e2affa1a088efdd842c289a316e649c9749ad8e0 |

静态 AJAX 地址候选，存在于页面或关联脚本，未据此证明业务动作执行：
- `https://o2o.unee.com.cn/web-cust/pc/js/ligerUI/js/ligerui.all.js`：`...`。
- `https://o2o.unee.com.cn/web-cust/pc/html/releaseBar/js/releaseBarList.js`：`/web-cust/pc/queryReleaseBarInfoById`、`/web-cust/pc/queryReleaseBarInfoList`。

## 报表管理 服务调度

路由 `/web-report/pc/html/schedulingEfficiency/efficiencyView1.html`。菜单来源 `ev_25226ae15c591aa25247b4d7ef5e89e5ddd4162209de1bcb9259a6a2f7d462cc`。

菜单定义的操作：调度导出列表1、调度导出列表2、调度导出列表3、调度导出列表4、列设置、查询。这些是菜单权限定义，不代表流程已执行验证。

页面字段：start_time、end_time。

页面按钮：查询、导出。

关联脚本中的静态表头候选：+(item.state==、+v+、城市公司、总工单数、派单数、派单率、及时派单数、及时派单率、派单平均时长(小时)。共享脚本候选可能属于其他路由。

页面证据：
- `ev_9049e649478b51750b2f229948baf3cd299a931299e31a494686e3395de48951`，事务 `request-145`，响应摘要 `1a74908fad62b657e32de11f3c86008b6b8d1a25b1e5380cff5f360b795e8b0e`，HTTP 200。

前端脚本：
已捕获 10 个关联脚本，地址和摘要见 JSON。业务脚本包括：`https://o2o.unee.com.cn/web-report/pc/js/common.js`、`https://o2o.unee.com.cn/web-report/pc/js/niceValidator/local/zh_CN.js`、`https://o2o.unee.com.cn/web-report/pc/html/schedulingEfficiency/js/resetTableHeight.js`、`https://o2o.unee.com.cn/web-report/pc/html/schedulingEfficiency/js/efficiencyView1.js`。

同一页面加载步骤内观察到的请求：

| 方法 | 路径 | HTTP | 查询参数名 | 请求体参数名 | Evidence |
| --- | --- | --- | --- | --- | --- |
| POST | /web-common/common/systemUserOrg | 200 | system_user_id | not_exposed | ev_9049e649478b51750b2f229948baf3cd299a931299e31a494686e3395de48951 |
| POST | /web-common/common/systemUserArea | 200 | system_user_id | org_ids | ev_9049e649478b51750b2f229948baf3cd299a931299e31a494686e3395de48951 |
| POST | /web-common/common/sysConfigQueryRest | 200 |  | column_name, table_name | ev_9049e649478b51750b2f229948baf3cd299a931299e31a494686e3395de48951 |

静态 AJAX 地址候选，存在于页面或关联脚本，未据此证明业务动作执行：
- `https://o2o.unee.com.cn/web-report/pc/js/ligerUI/js/ligerui.all.js`：`...`。
- `https://o2o.unee.com.cn/web-report/pc/html/schedulingEfficiency/js/efficiencyView1.js`：`/web-report/scheduEfficiency/efficiencyViewQuery1`。

## 运营中心 便民电话

路由 `/web-cust/pc/html/fastTelephone/telephoneList.html`。菜单来源 `ev_25226ae15c591aa25247b4d7ef5e89e5ddd4162209de1bcb9259a6a2f7d462cc`。

菜单定义的操作：查看、新增、删除、查询。这些是菜单权限定义，不代表流程已执行验证。

页面字段：org_name、service_name、telephone_type_name、company_name。

页面按钮：新增、删除、查询。

关联脚本中的静态表头候选：序号、城市公司、服务中心、单位名称、类别、电话号码、物品、存放地点。共享脚本候选可能属于其他路由。

该加载阶段存在失败或 HTTP 错误资源：`/web-cust/pc/js/artDialog/images/plugins/artdialog/loading.gif` 404。页面关闭可能中断请求，需重新观察其影响。

页面证据：
- `ev_c4d4036bc65a408c8041f833ce8889a39169173452dd7d6ae2a6a106c5d2ca2b`，事务 `request-215`，响应摘要 `bc74f124f6d4d796a2aa173d1c01553b5d2f1999d91e47e854d7fb5d4b4d6da4`，HTTP 200。

前端脚本：
已捕获 14 个关联脚本，地址和摘要见 JSON。业务脚本包括：`https://o2o.unee.com.cn/web-cust/pc/js/common.js`、`https://o2o.unee.com.cn/web-cust/pc/js/progressbar/custom_progressbar.js`、`https://o2o.unee.com.cn/web-cust/pc/js/niceValidator/local/zh_CN.js`、`https://o2o.unee.com.cn/web-cust/pc/js/niceValidator/local/zh_CN.js`、`https://o2o.unee.com.cn/web-cust/pc/html/fastTelephone/js/resetTableHeight.js`、`https://o2o.unee.com.cn/web-cust/pc/html/fastTelephone/js/telephoneList.js`。

同一页面加载步骤内观察到的请求：

| 方法 | 路径 | HTTP | 查询参数名 | 请求体参数名 | Evidence |
| --- | --- | --- | --- | --- | --- |
| POST | /web-common/common/systemUserOrg | 200 | system_user_id | findPath | ev_c4d4036bc65a408c8041f833ce8889a39169173452dd7d6ae2a6a106c5d2ca2b |
| POST | /web-common/common/systemDataPermission | 200 | system_user_id, type | findPath | ev_c4d4036bc65a408c8041f833ce8889a39169173452dd7d6ae2a6a106c5d2ca2b |
| POST | /web-common/common/sysConfigQueryRest | 200 |  | column_name, table_name | ev_c4d4036bc65a408c8041f833ce8889a39169173452dd7d6ae2a6a106c5d2ca2b |

静态 AJAX 地址候选，存在于页面或关联脚本，未据此证明业务动作执行：
- `https://o2o.unee.com.cn/web-cust/pc/js/ligerUI/js/ligerui.all.js`：`...`。
- `https://o2o.unee.com.cn/web-cust/pc/html/fastTelephone/js/telephoneList.js`：`/web-cust/fastTelephone/telephoneListQuery`、`/web-common/common/sysConfigQueryRest`。

## 统计中心 业主登录清单

路由 `/web-seo/pc/html/esmpLoginCust/esmpLoginCustList.html`。菜单来源 `ev_25226ae15c591aa25247b4d7ef5e89e5ddd4162209de1bcb9259a6a2f7d462cc`。

菜单定义的操作：导出、查询。这些是菜单权限定义，不代表流程已执行验证。

页面字段：org_name、service_name、start_time、end_time、phone_num、is_last_login。

页面按钮：导出、查询。

关联脚本中的静态表头候选：服务中心、客户名称、手机号码、房号、登录时间。共享脚本候选可能属于其他路由。

该加载阶段存在失败或 HTTP 错误资源：`/web-seo/pc/js/artDialog/images/plugins/artdialog/loading.gif` 404。页面关闭可能中断请求，需重新观察其影响。

页面证据：
- `ev_09a45f0a06a75d1316e52ebd6f6fa25316e841f7362f861659f9969d3c364feb`，事务 `request-243`，响应摘要 `5d7c14a7b4ec41bd7187aa205153c959bdf6bdabea65155172a13dfe939d48f7`，HTTP 200。

前端脚本：
已捕获 13 个关联脚本，地址和摘要见 JSON。业务脚本包括：`https://o2o.unee.com.cn/web-seo/pc/html/esmpLoginCust/js/common.js`、`https://o2o.unee.com.cn/web-seo/pc/js/progressbar/custom_progressbar.js`、`https://o2o.unee.com.cn/web-seo/pc/js/niceValidator/local/zh_CN.js`、`https://o2o.unee.com.cn/web-seo/pc/html/esmpLoginCust/js/esmpLoginCustList.js`。

同一页面加载步骤内观察到的请求：

| 方法 | 路径 | HTTP | 查询参数名 | 请求体参数名 | Evidence |
| --- | --- | --- | --- | --- | --- |
| POST | /web-common/common/systemUserOrg | 200 | system_user_id | findPath | ev_09a45f0a06a75d1316e52ebd6f6fa25316e841f7362f861659f9969d3c364feb |
| POST | /web-common/common/systemDataPermission | 200 | system_user_id, type | findPath | ev_09a45f0a06a75d1316e52ebd6f6fa25316e841f7362f861659f9969d3c364feb |

静态 AJAX 地址候选，存在于页面或关联脚本，未据此证明业务动作执行：
- `https://o2o.unee.com.cn/web-seo/pc/js/ligerUI/js/ligerui.all.js`：`...`。
- `https://o2o.unee.com.cn/web-seo/pc/html/esmpLoginCust/js/esmpLoginCustList.js`：`/web-seo/pc/queryEsmpLoginCustList`、`/web-seo/pc/queryEsmpLoginCustCount`。

## 系统中心 服务中心管理

路由 `/web-sys/pc/html/centermanagement/centerone.html`。菜单来源 `ev_25226ae15c591aa25247b4d7ef5e89e5ddd4162209de1bcb9259a6a2f7d462cc`。

菜单定义的操作：查询、编辑FMC报修标志、编辑物业CRM工单标志。这些是菜单权限定义，不代表流程已执行验证。

页面字段：status_name、fields_name、fields_value。

页面按钮：新增、查询。

关联脚本中的静态表头候选：服务中心编码(NC)、服务中心编码(HR)、服务中心编码(MDM)、服务中心名称、所属公司、管理中心、创建时间、状态、联系电话、操作。共享脚本候选可能属于其他路由。

页面证据：
- `ev_0cf173243cdb26a582983b2682632c0be53484fd0b8090f23f41b058eb1f61ca`，事务 `request-192`，响应摘要 `cbe4ef8022cc7e9b2a7e0fab316d195bfd24665cd43856f882d7b03aa4fc16a8`，HTTP 200。

前端脚本：
已捕获 1 个关联脚本，地址和摘要见 JSON。业务脚本包括：`https://o2o.unee.com.cn/web-sys/pc/js/common.js`、`https://o2o.unee.com.cn/web-sys/pc/html/centermanagement/js/serviceCenter.js`。

同一页面加载步骤内观察到的请求：

| 方法 | 路径 | HTTP | 查询参数名 | 请求体参数名 | Evidence |
| --- | --- | --- | --- | --- | --- |
| POST | /web-sys/center/queryServiceCenterList | 200 |  | fields_nameh, fields_value, page, pageSize, pagesize, startNum, status_cd | ev_0cf173243cdb26a582983b2682632c0be53484fd0b8090f23f41b058eb1f61ca |

静态 AJAX 地址候选，存在于页面或关联脚本，未据此证明业务动作执行：
- `https://o2o.unee.com.cn/web-sys/pc/html/centermanagement/js/serviceCenter.js`：`/web-sys/center/queryServiceCenterList`、`/web-sys/center/isCheckedCenter`、`/web-bus/batchMasterDataController/syncMdmFromCrm`、`/web-sys/center/updateCenterStatus`。

## 报表管理 诉求管理

路由 `/web-report/pc/html/accountStatement/accountStatementList.html`。菜单来源 `ev_25226ae15c591aa25247b4d7ef5e89e5ddd4162209de1bcb9259a6a2f7d462cc`。

菜单定义的操作：导出、列设置、查询。这些是菜单权限定义，不代表流程已执行验证。

页面字段：start_time、end_time、user_name、work_content。

页面按钮：查询、列设置、导出。

关联脚本中的静态表头候选：服务中心、房号、申请人姓名、申请人联系电话、申请身份、状态、申请时间、申请来源、审批结果、提交人、审批人、审批时间、操作。共享脚本候选可能属于其他路由。

该加载阶段存在失败或 HTTP 错误资源：`/web-report/pc/js/artDialog/images/plugins/artdialog/loading.gif` 404。页面关闭可能中断请求，需重新观察其影响。

页面证据：
- `ev_9049e649478b51750b2f229948baf3cd299a931299e31a494686e3395de48951`，事务 `request-190`，响应摘要 `79ac344dabb2cad961ac3271622fa266af8c2c554e4fe30450e76d3419c8de20`，HTTP 200。

前端脚本：
已捕获 18 个关联脚本，地址和摘要见 JSON。业务脚本包括：`https://o2o.unee.com.cn/web-report/pc/html/accountStatement/js/select.js`、`https://o2o.unee.com.cn/web-report/pc/js/table/custom_table.js`、`https://o2o.unee.com.cn/web-report/pc/js/progressbar/custom_progressbar.js`、`https://o2o.unee.com.cn/web-report/pc/html/accountStatement/js/accountStatementList.js`、`https://o2o.unee.com.cn/web-report/pc/html/accountStatement/js/resetTableHeight.js`、`https://o2o.unee.com.cn/web-report/pc/js/common.js`、`https://o2o.unee.com.cn/web-report/pc/js/niceValidator/local/zh_CN.js`、`https://o2o.unee.com.cn/web-report/pc/js/virtual-select.min.js`。

同一页面加载步骤内观察到的请求：

| 方法 | 路径 | HTTP | 查询参数名 | 请求体参数名 | Evidence |
| --- | --- | --- | --- | --- | --- |
| POST | /web-common/common/systemUserOrg | 200 | system_user_id | not_exposed | ev_9049e649478b51750b2f229948baf3cd299a931299e31a494686e3395de48951 |
| POST | /web-common/common/sysConfigQueryRest | 200 |  | column_name, table_name | ev_9049e649478b51750b2f229948baf3cd299a931299e31a494686e3395de48951 |
| GET | /web-bus/columnController/getShowColumn | 200 | modules_code | not_exposed | ev_9049e649478b51750b2f229948baf3cd299a931299e31a494686e3395de48951 |
| POST | /web-common/common/systemDataPermission | 200 | system_user_id, org_id | not_exposed | ev_9049e649478b51750b2f229948baf3cd299a931299e31a494686e3395de48951 |
| POST | /web-common/common/systemUserArea | 200 | system_user_id | org_ids | ev_9049e649478b51750b2f229948baf3cd299a931299e31a494686e3395de48951 |

静态 AJAX 地址候选，存在于页面或关联脚本，未据此证明业务动作执行：
- `https://o2o.unee.com.cn/web-report/pc/html/accountStatement/js/accountStatementList.js`：`/web-bus/columnController/getShowColumn`、`/web-report/processEfficiency/efficiencyQueryWork`。
- `https://o2o.unee.com.cn/web-report/pc/js/ligerUI/js/ligerui.all.js`：`...`。

## 统计中心 问卷结果

路由 `/web-seo/pc/html/QuestionnaireResult/questionList.html`。菜单来源 `ev_25226ae15c591aa25247b4d7ef5e89e5ddd4162209de1bcb9259a6a2f7d462cc`。

菜单定义的操作：查询、导出、问卷题目答案导出。这些是菜单权限定义，不代表流程已执行验证。

页面字段：status_name、control_type_name、start_time、end_time、ques_type_name、ques_name。

页面按钮：导出、查询。

关联脚本中的静态表头候选：问卷名称、问卷类型、发布渠道、管控范围、归属组织、问卷状态、生效时间、失效时间、提交总人数、业主人数、家属人数、租客人数。共享脚本候选可能属于其他路由。

页面证据：
- `ev_09a45f0a06a75d1316e52ebd6f6fa25316e841f7362f861659f9969d3c364feb`，事务 `request-292`，响应摘要 `bc3984081c122bc1ec69a3714db8eb2abe4c3f91cfd61c1a03bbf4e660e0dd8d`，HTTP 200。

前端脚本：
已捕获 12 个关联脚本，地址和摘要见 JSON。业务脚本包括：`https://o2o.unee.com.cn/web-seo/pc/js/common.js`、`https://o2o.unee.com.cn/web-seo/pc/js/progressbar/custom_progressbar.js`、`https://o2o.unee.com.cn/web-seo/pc/html/QuestionnaireResult/js/resetTableHeight.js`、`https://o2o.unee.com.cn/web-seo/pc/js/niceValidator/local/zh_CN.js`、`https://o2o.unee.com.cn/web-seo/pc/html/QuestionnaireResult/js/questionList.js`。

同一页面加载步骤内观察到的请求：

| 方法 | 路径 | HTTP | 查询参数名 | 请求体参数名 | Evidence |
| --- | --- | --- | --- | --- | --- |
| POST | /web-common/common/sysConfigQueryRest | 200 |  | column_name, table_name | ev_09a45f0a06a75d1316e52ebd6f6fa25316e841f7362f861659f9969d3c364feb |

静态 AJAX 地址候选，存在于页面或关联脚本，未据此证明业务动作执行：
- `https://o2o.unee.com.cn/web-seo/pc/js/ligerUI/js/ligerui.all.js`：`...`。
- `https://o2o.unee.com.cn/web-seo/pc/html/QuestionnaireResult/js/questionList.js`：`/web-seo/pc/questionnaire/queryList`。

## 客户服务 访客预约

路由 `/web-cust/pc/html/visitorBespeak/listVisitorBespeakPC.html`。菜单来源 `ev_25226ae15c591aa25247b4d7ef5e89e5ddd4162209de1bcb9259a6a2f7d462cc`。

菜单定义的操作：查询、导出。这些是菜单权限定义，不代表流程已执行验证。

页面字段：org_name、service_name、start_time、end_time、key_word。

页面按钮：导出、返回、查询。

关联脚本中的静态表头候选：访客编号、房号、客户、联系方式、来访时间、访客人数、访客姓名、来访备注、开门类型、是否登记、操作。共享脚本候选可能属于其他路由。

页面证据：
- `ev_f2631a7dc031a549a87680b1e2affa1a088efdd842c289a316e649c9749ad8e0`，事务 `request-258`，响应摘要 `203d2ebf9f908dc7cd3ce79bc275019a6de99fc77245a2ef4d323f68f4409cd8`，HTTP 200。

前端脚本：
已捕获 9 个关联脚本，地址和摘要见 JSON。业务脚本包括：`https://o2o.unee.com.cn/web-cust/pc/js/common.js`、`https://o2o.unee.com.cn/web-cust/pc/js/progressbar/custom_progressbar.js`、`https://o2o.unee.com.cn/web-cust/pc/js/niceValidator/local/zh_CN.js`、`https://o2o.unee.com.cn/web-cust/pc/js/niceValidator/local/zh_CN.js`、`https://o2o.unee.com.cn/web-cust/pc/html/visitorBespeak/js/listVisitorBespeakPC.js`。

同一页面加载步骤内观察到的请求：

| 方法 | 路径 | HTTP | 查询参数名 | 请求体参数名 | Evidence |
| --- | --- | --- | --- | --- | --- |
| POST | /web-common/common/systemUserOrg | 200 | system_user_id | findPath | ev_f2631a7dc031a549a87680b1e2affa1a088efdd842c289a316e649c9749ad8e0 |
| POST | /web-common/common/systemDataPermission | 200 | system_user_id, type | findPath | ev_f2631a7dc031a549a87680b1e2affa1a088efdd842c289a316e649c9749ad8e0 |

静态 AJAX 地址候选，存在于页面或关联脚本，未据此证明业务动作执行：
- `https://o2o.unee.com.cn/web-cust/pc/js/ligerUI/js/ligerui.all.js`：`...`。
- `https://o2o.unee.com.cn/web-cust/pc/html/visitorBespeak/js/listVisitorBespeakPC.js`：`/web-cust/visitorBespeakPC/queryVisitor2StaffPCDemo`。

## 统计中心 费用查询

路由 `/web-seo/pc/html/chargeQuery/chargeQueryList.html`。菜单来源 `ev_25226ae15c591aa25247b4d7ef5e89e5ddd4162209de1bcb9259a6a2f7d462cc`。

菜单定义的操作：查询、导出。这些是菜单权限定义，不代表流程已执行验证。

页面字段：cost_names、org_name、service_name、start_time、end_time、fields_name、fields_value、pay_method_name、pay_channels_name、pay_status_names。

页面按钮：导出、返回、查询。

关联脚本中的静态表头候选：业务、服务中心、房产名称、房产编码、缴费客户、联系电话、付费客户、金额、入账金额、缴费时间、流水号、缴费方式、缴费渠道、卡类型、卡号、状态、备注、创二维码者、操作。共享脚本候选可能属于其他路由。

页面证据：
- `ev_09a45f0a06a75d1316e52ebd6f6fa25316e841f7362f861659f9969d3c364feb`，事务 `request-338`，响应摘要 `dfef3d25aa25ae8affe809842602a6368c9be18fd3d8d5a825bce701ade47d24`，HTTP 200。

前端脚本：
已捕获 13 个关联脚本，地址和摘要见 JSON。业务脚本包括：`https://o2o.unee.com.cn/web-seo/pc/html/chargeQuery/js/common.js`、`https://o2o.unee.com.cn/web-seo/pc/js/progressbar/custom_progressbar.js`、`https://o2o.unee.com.cn/web-seo/pc/js/niceValidator/local/zh_CN.js`、`https://o2o.unee.com.cn/web-seo/pc/html/chargeQuery/js/chargeQueryList.js`。

HTML 内联脚本静态观察：`ev_09a45f0a06a75d1316e52ebd6f6fa25316e841f7362f861659f9969d3c364feb`，内联摘要 `6879ed5a4885a645d817a041a50df8fde53e38708720a1986654dd7f59f61fbc`，126 字符。

document.write 动态脚本声明候选 `https://o2o.unee.com.cn/web-seo/pc/html/chargeQuery/js/chargeQueryList.js`，查询参数名 v；关联同功能中实际已记录的脚本请求，不执行该加载语句。

同一页面加载步骤内观察到的请求：

| 方法 | 路径 | HTTP | 查询参数名 | 请求体参数名 | Evidence |
| --- | --- | --- | --- | --- | --- |
| POST | /web-seo/pc/queryCodeConfig | 200 |  | column_name, table_name | ev_09a45f0a06a75d1316e52ebd6f6fa25316e841f7362f861659f9969d3c364feb |
| POST | /web-common/common/systemUserOrg | 200 | system_user_id | findPath | ev_09a45f0a06a75d1316e52ebd6f6fa25316e841f7362f861659f9969d3c364feb |
| POST | /web-common/common/systemDataPermission | 200 | system_user_id, type | findPath | ev_09a45f0a06a75d1316e52ebd6f6fa25316e841f7362f861659f9969d3c364feb |
| POST | /web-bus/getPushMessage/6520159 | 200 |  | not_exposed | ev_09a45f0a06a75d1316e52ebd6f6fa25316e841f7362f861659f9969d3c364feb |

静态 AJAX 地址候选，存在于页面或关联脚本，未据此证明业务动作执行：
- `https://o2o.unee.com.cn/web-seo/pc/js/ligerUI/js/ligerui.all.js`：`...`。
- `https://o2o.unee.com.cn/web-seo/pc/html/chargeQuery/js/chargeQueryList.js`：`/web-seo/pc/queryChargeQueryList`。

## 客户服务 投诉

路由 `/web-cust/pc/html/work/tsList.html`。菜单来源 `ev_25226ae15c591aa25247b4d7ef5e89e5ddd4162209de1bcb9259a6a2f7d462cc`。

菜单定义的操作：导出。这些是菜单权限定义，不代表流程已执行验证。

页面字段：org_name、service_name、channel_name、complaint_source_name、visit_name、visit_name1、ts_status、ts_status1、start_time、end_time、extra_msg、handleUserName、event_id。

页面按钮：查询、列设置。

关联脚本中的静态表头候选：城市公司、服务中心、房号、联系人、报事时间、报事内容、当前状态、渠道、投诉来源、关联工单、回访状态。共享脚本候选可能属于其他路由。

该加载阶段存在失败或 HTTP 错误资源：`/web-cust/pc/js/ligerUI/skins/ligerui-icons.css` net::ERR_ABORTED、`/web-cust/pc/js/artDialog/style.css` net::ERR_ABORTED、`/web-cust/pc/js/artDialog/images/plugins/artdialog/loading.gif` 404。页面关闭可能中断请求，需重新观察其影响。

页面证据：
- `ev_f2631a7dc031a549a87680b1e2affa1a088efdd842c289a316e649c9749ad8e0`，事务 `request-304`，响应摘要 `5db38613936144763869d4bc1f29b39ea9c3d64ba15acbaa3a98ee7f9fd6bf0b`，HTTP 200。

前端脚本：
已捕获 14 个关联脚本，地址和摘要见 JSON。业务脚本包括：`https://o2o.unee.com.cn/web-cust/pc/js/common.js`、`https://o2o.unee.com.cn/web-cust/pc/html/work/js/tsList.js`、`https://o2o.unee.com.cn/web-cust/pc/html/work/js/cookieHelper.js`、`https://o2o.unee.com.cn/web-cust/pc/html/work/js/resetTableHeight.js`、`https://o2o.unee.com.cn/web-cust/pc/html/work/js/resetTableHeight.js`、`https://o2o.unee.com.cn/web-cust/pc/js/niceValidator/local/zh_CN.js`、`https://o2o.unee.com.cn/web-cust/pc/js/niceValidator/local/zh_CN.js`。

同一页面加载步骤内观察到的请求：

| 方法 | 路径 | HTTP | 查询参数名 | 请求体参数名 | Evidence |
| --- | --- | --- | --- | --- | --- |
| POST | /web-common/common/systemUserOrg | 200 | system_user_id | findPath | ev_f2631a7dc031a549a87680b1e2affa1a088efdd842c289a316e649c9749ad8e0 |
| POST | /web-common/common/systemDataPermission | 200 | system_user_id, type | findPath | ev_f2631a7dc031a549a87680b1e2affa1a088efdd842c289a316e649c9749ad8e0 |
| POST | /web-common/common/sysConfigQueryRest | 200 |  | column_name, table_name | ev_f2631a7dc031a549a87680b1e2affa1a088efdd842c289a316e649c9749ad8e0 |
| GET | /web-bus/columnController/getShowColumn | 200 | modules_code | not_exposed | ev_f2631a7dc031a549a87680b1e2affa1a088efdd842c289a316e649c9749ad8e0 |

静态 AJAX 地址候选，存在于页面或关联脚本，未据此证明业务动作执行：
- `https://o2o.unee.com.cn/web-cust/pc/html/work/js/tsList.js`：`/web-bus/columnController/getShowColumn`。
- `https://o2o.unee.com.cn/web-cust/pc/js/ligerUI/js/ligerui.all.js`：`...`。

## 报表管理 用户量

路由 `/web-report/pc/html/userStatistics/ReportUserStatisticsRegisterList.html`。菜单来源 `ev_25226ae15c591aa25247b4d7ef5e89e5ddd4162209de1bcb9259a6a2f7d462cc`。

菜单定义的操作：城市公司导出、服务中心导出、房产认证导出。这些是菜单权限定义，不代表流程已执行验证。

页面字段：org_name、start_time、end_time。

页面按钮：查询。

关联脚本中的静态表头候选：城市公司、总房产数。共享脚本候选可能属于其他路由。

页面证据：
- `ev_9049e649478b51750b2f229948baf3cd299a931299e31a494686e3395de48951`，事务 `request-254`，响应摘要 `c2f272e2b9ab2764af14436c1924f48c41610fe687b5dfd73dd68f7081f5feda`，HTTP 200。

前端脚本：
已捕获 11 个关联脚本，地址和摘要见 JSON。业务脚本包括：`https://o2o.unee.com.cn/web-report/pc/html/userStatistics/js/common.js`、`https://o2o.unee.com.cn/web-report/pc/js/progressbar/custom_progressbar.js`、`https://o2o.unee.com.cn/web-report/pc/js/niceValidator/local/zh_CN.js`、`https://o2o.unee.com.cn/web-report/pc/html/userStatistics/js/reportUserStaticsticsRegister.js`。

同一页面加载步骤内观察到的请求：

| 方法 | 路径 | HTTP | 查询参数名 | 请求体参数名 | Evidence |
| --- | --- | --- | --- | --- | --- |
| POST | /web-common/common/systemUserOrgIncrease | 200 | system_user_id, type | findPath | ev_9049e649478b51750b2f229948baf3cd299a931299e31a494686e3395de48951 |
| POST | /web-report/pc/userStatistics/getMounth | 200 |  | endTime, startTime | ev_9049e649478b51750b2f229948baf3cd299a931299e31a494686e3395de48951 |

静态 AJAX 地址候选，存在于页面或关联脚本，未据此证明业务动作执行：
- `https://o2o.unee.com.cn/web-report/pc/js/ligerUI/js/ligerui.all.js`：`...`。
- `https://o2o.unee.com.cn/web-report/pc/html/userStatistics/js/reportUserStaticsticsRegister.js`：`/web-report/pc/userStatistics/getMounth`。

## 运营中心 房产交易

路由 `/web-bus/pc/html/houseSell/houseSellList.html`。菜单来源 `ev_25226ae15c591aa25247b4d7ef5e89e5ddd4162209de1bcb9259a6a2f7d462cc`。

菜单定义的操作：全市均价、房产交易新增、房产交易删除、全市均价新增、全市均价删除、房产交易修改、导出、查询。这些是菜单权限定义，不代表流程已执行验证。

页面字段：area_name1、service_name、sell_type_name。

页面按钮：租售信息、全市均价、新增、删除、查询。

关联脚本中的静态表头候选：编号、类型、客户、联系电话、户型、面积、价格、备注。共享脚本候选可能属于其他路由。

页面证据：
- `ev_c4d4036bc65a408c8041f833ce8889a39169173452dd7d6ae2a6a106c5d2ca2b`，事务 `request-266`，响应摘要 `563835154fa9c4b1d08a147cfb1328414e1236e1af2d06c13666c676ed4aaf40`，HTTP 200。

前端脚本：
已捕获 15 个关联脚本，地址和摘要见 JSON。业务脚本包括：`https://o2o.unee.com.cn/web-bus/pc/js/table/custom_table.js`、`https://o2o.unee.com.cn/web-bus/pc/js/progressbar/custom_progressbar.js`、`https://o2o.unee.com.cn/web-bus/pc/html/houseSell/js/resetTableHeight.js`、`https://o2o.unee.com.cn/web-bus/pc/js/niceValidator/local/zh_CN.js`、`https://o2o.unee.com.cn/web-bus/pc/js/common.js`、`https://o2o.unee.com.cn/web-bus/pc/html/houseSell/js/houseSellList1.js`。

同一页面加载步骤内观察到的请求：

| 方法 | 路径 | HTTP | 查询参数名 | 请求体参数名 | Evidence |
| --- | --- | --- | --- | --- | --- |
| POST | /web-common/common/systemUserArea | 200 | system_user_id | findPath | ev_c4d4036bc65a408c8041f833ce8889a39169173452dd7d6ae2a6a106c5d2ca2b |
| POST | /web-common/permission/common/systemDataPermission | 200 | system_user_id, type | findPath | ev_c4d4036bc65a408c8041f833ce8889a39169173452dd7d6ae2a6a106c5d2ca2b |
| POST | /web-common/common/sysConfigQueryRest | 200 |  | column_name, table_name | ev_c4d4036bc65a408c8041f833ce8889a39169173452dd7d6ae2a6a106c5d2ca2b |

静态 AJAX 地址候选，存在于页面或关联脚本，未据此证明业务动作执行：
- `https://o2o.unee.com.cn/web-bus/pc/js/ligerUI/js/ligerui.all.js`：`...`。
- `https://o2o.unee.com.cn/web-bus/pc/html/houseSell/js/houseSellList1.js`：`/web-bus/pc/qry_house_sell_list`。

## 系统中心 消息发送

路由 `/web-sys/pc/html/messageManage/messageList.html`。菜单来源 `ev_25226ae15c591aa25247b4d7ef5e89e5ddd4162209de1bcb9259a6a2f7d462cc`。

菜单定义的操作：查询。这些是菜单权限定义，不代表流程已执行验证。

页面字段：channel_name、start_time、end_time、message_title。

页面按钮：新增、查询。

关联脚本中的静态表头候选：序号、渠道、标题、内容、创建时间、状态、操作。共享脚本候选可能属于其他路由。

页面证据：
- `ev_0cf173243cdb26a582983b2682632c0be53484fd0b8090f23f41b058eb1f61ca`，事务 `request-230`，响应摘要 `2c0540328ab311415b1b6ff8858591de635b6c0f3adc85cda78bcf55101b386f`，HTTP 200。

前端脚本：
已捕获 4 个关联脚本，地址和摘要见 JSON。业务脚本包括：`https://o2o.unee.com.cn/web-sys/pc/js/common.js`、`https://o2o.unee.com.cn/web-sys/pc/js/table/custom_table.js`、`https://o2o.unee.com.cn/web-sys/pc/js/progressbar/custom_progressbar.js`、`https://o2o.unee.com.cn/web-sys/pc/html/messageManage/js/sendMessage.js`、`https://o2o.unee.com.cn/web-sys/pc/html/messageManage/js/messageList.js`。

静态 AJAX 地址候选，存在于页面或关联脚本，未据此证明业务动作执行：
- `https://o2o.unee.com.cn/web-sys/pc/html/messageManage/js/messageList.js`：`/web-sys/message/queryMessageList`。

## 报表管理 积分报表

路由 `/web-cust/pc/html/integralStatements/integralStatementsByOrg.html`。菜单来源 `ev_25226ae15c591aa25247b4d7ef5e89e5ddd4162209de1bcb9259a6a2f7d462cc`。

菜单定义的操作：城市公司积分报表导出、服务中心积分报表导出、查询。这些是菜单权限定义，不代表流程已执行验证。

页面字段：start_time、end_time。

页面按钮：查询、导出。

关联脚本中的静态表头候选：+(item.state==、+v+、城市公司、有效积分、UN+积分、电商积分、冻结积分。共享脚本候选可能属于其他路由。

页面证据：
- `ev_9049e649478b51750b2f229948baf3cd299a931299e31a494686e3395de48951`，事务 `request-300`，响应摘要 `82e2314988d1244d0e547e13f786ea0fd4bda9a3eacf118e565d682065869dd5`，HTTP 200。

前端脚本：
已捕获 11 个关联脚本，地址和摘要见 JSON。业务脚本包括：`https://o2o.unee.com.cn/web-cust/pc/js/common.js`、`https://o2o.unee.com.cn/web-cust/pc/js/niceValidator/local/zh_CN.js`、`https://o2o.unee.com.cn/web-cust/pc/js/niceValidator/local/zh_CN.js`、`https://o2o.unee.com.cn/web-cust/pc/html/integralStatements/js/resetTableHeight.js`、`https://o2o.unee.com.cn/web-cust/pc/html/integralStatements/js/integralStatementsByOrgHead.js`、`https://o2o.unee.com.cn/web-cust/pc/html/integralStatements/js/integralStatementsByOrg.js`。

同一页面加载步骤内观察到的请求：

| 方法 | 路径 | HTTP | 查询参数名 | 请求体参数名 | Evidence |
| --- | --- | --- | --- | --- | --- |
| POST | /web-common/common/systemUserOrg | 200 | system_user_id | not_exposed | ev_9049e649478b51750b2f229948baf3cd299a931299e31a494686e3395de48951 |
| POST | /web-common/common/systemUserArea | 200 | system_user_id | org_ids | ev_9049e649478b51750b2f229948baf3cd299a931299e31a494686e3395de48951 |

静态 AJAX 地址候选，存在于页面或关联脚本，未据此证明业务动作执行：
- `https://o2o.unee.com.cn/web-cust/pc/js/ligerUI/js/ligerui.all.js`：`...`。
- `https://o2o.unee.com.cn/web-cust/pc/html/integralStatements/js/integralStatementsByOrg.js`：`/web-cust/IntegralStatements/listIntegralStatementsByOrg.do`。

## 配置管理 评价二维码管理

路由 `/web-bus/pc/html/scanEvaluate/qrCode/qrCodeList.html`。菜单来源 `ev_25226ae15c591aa25247b4d7ef5e89e5ddd4162209de1bcb9259a6a2f7d462cc`。

菜单定义的操作：新增、修改、删除、二维码下载、导出、查询。这些是菜单权限定义，不代表流程已执行验证。

页面字段：org_name、service_name、paste_location、status_name、create_date_start、create_date_end、evaluate_classify_name。

页面按钮：查询、新增、二维码下载、导出。

关联脚本中的静态表头候选：城市公司、服务中心、二维码粘贴地点、互动点位、评价对象、创建时间、状态、二维码、项目二维码、操作。共享脚本候选可能属于其他路由。

页面证据：
- `ev_c590a872a43fe0d5c14d31c18cdcb66b904bb81b4e05b852730bf8dceb6eea00`，事务 `request-364`，响应摘要 `57905578d3df3e9d2870dd9c3f717a0071a48fa5ac0ddfab95eda8d382f21dfe`，HTTP 200。

前端脚本：
已捕获 4 个关联脚本，地址和摘要见 JSON。业务脚本包括：`https://o2o.unee.com.cn/web-bus/pc/js/common.js`、`https://o2o.unee.com.cn/web-bus/pc/js/progressbar/custom_progressbar.js`、`https://o2o.unee.com.cn/web-bus/pc/js/niceValidator/local/zh_CN.js`、`https://o2o.unee.com.cn/web-bus/pc/html/scanEvaluate/qrCode/js/qrCodeList.js`、`https://o2o.unee.com.cn/web-bus/pc/html/scanEvaluate/qrCode/js/resetTableHeight.js`、`https://o2o.unee.com.cn/web-bus/pc/js/viewerjs/viewer.js`、`https://o2o.unee.com.cn/web-bus/pc/html/scanEvaluate/qrCode/js/viewer_default.js`。

同一页面加载步骤内观察到的请求：

| 方法 | 路径 | HTTP | 查询参数名 | 请求体参数名 | Evidence |
| --- | --- | --- | --- | --- | --- |
| GET | /web-bus/quesQrCodeInfoController/getQrcodeType | 200 |  | not_exposed | ev_c590a872a43fe0d5c14d31c18cdcb66b904bb81b4e05b852730bf8dceb6eea00 |
| POST | /web-common/permission/common/systemUserOrg | 200 | system_user_id | findPath | ev_c590a872a43fe0d5c14d31c18cdcb66b904bb81b4e05b852730bf8dceb6eea00 |
| POST | /web-common/permission/common/systemDataPermission | 200 | system_user_id, type | findPath | ev_c590a872a43fe0d5c14d31c18cdcb66b904bb81b4e05b852730bf8dceb6eea00 |
| GET | /web-bus/quesQrCodeInfoController/getStatusCode | 200 |  | not_exposed | ev_c590a872a43fe0d5c14d31c18cdcb66b904bb81b4e05b852730bf8dceb6eea00 |
| POST | /web-bus/getPushMessage/6520159 | 200 |  | not_exposed | ev_c590a872a43fe0d5c14d31c18cdcb66b904bb81b4e05b852730bf8dceb6eea00 |

静态 AJAX 地址候选，存在于页面或关联脚本，未据此证明业务动作执行：
- `https://o2o.unee.com.cn/web-bus/pc/html/scanEvaluate/qrCode/js/qrCodeList.js`：`/web-bus/quesQrCodeInfoController/getQrcodeType`、`/web-bus/quesQrCodeInfoController/qrCodeListQuery`、`/web-bus/quesQrCodeInfoController/getStatusCode`。

## 综合查询 员工评价

路由 `/web-bus/pc/html/evaluationRecords/evaluationRecords.html`。菜单来源 `ev_25226ae15c591aa25247b4d7ef5e89e5ddd4162209de1bcb9259a6a2f7d462cc`。

菜单定义的操作：查询、导出。这些是菜单权限定义，不代表流程已执行验证。

页面字段：org_name、service_name、grade、staff_name、start_time、end_time、SourcesEvaluation。

页面按钮：查询、导出。

关联脚本中的静态表头候选：城市公司、服务中心、员工姓名、评分、评价内容、用户姓名、房号、手机号码、提交时间、评价来源。共享脚本候选可能属于其他路由。

页面证据：
- `ev_38947e25f18f5c3530edafcc8a81c9e535540d7a35a161748e64dc800d952267`，事务 `request-231`，响应摘要 `5582b0d5df256cdba3ad8d58e7d3a3b3c39ac0580bbd94b0a8e21ae93beb3308`，HTTP 200。

前端脚本：
已捕获 14 个关联脚本，地址和摘要见 JSON。业务脚本包括：`https://o2o.unee.com.cn/web-bus/pc/js/table/custom_table.js`、`https://o2o.unee.com.cn/web-bus/pc/js/niceValidator/local/zh_CN.js`、`https://o2o.unee.com.cn/web-bus/pc/js/common.js`、`https://o2o.unee.com.cn/web-bus/pc/html/evaluationRecords/js/evaluationRecords.js`。

HTML 内联脚本静态观察：`ev_38947e25f18f5c3530edafcc8a81c9e535540d7a35a161748e64dc800d952267`，内联摘要 `0d42bb8c2ef467d79a1ca67039183afa72b082a8de34085f5109b2847f609fe3`，231 字符。

document.write 动态脚本声明候选 `https://o2o.unee.com.cn/web-bus/pc/js/common.js`，查询参数名 v；关联同功能中实际已记录的脚本请求，不执行该加载语句。

document.write 动态脚本声明候选 `https://o2o.unee.com.cn/web-bus/pc/html/evaluationRecords/js/evaluationRecords.js`，查询参数名 v；关联同功能中实际已记录的脚本请求，不执行该加载语句。

同一页面加载步骤内观察到的请求：

| 方法 | 路径 | HTTP | 查询参数名 | 请求体参数名 | Evidence |
| --- | --- | --- | --- | --- | --- |
| POST | /web-common/permission/common/systemUserOrg | 200 | system_user_id | findPath | ev_38947e25f18f5c3530edafcc8a81c9e535540d7a35a161748e64dc800d952267 |
| POST | /web-common/permission/common/systemDataPermission | 200 | system_user_id, type | findPath | ev_38947e25f18f5c3530edafcc8a81c9e535540d7a35a161748e64dc800d952267 |
| POST | /web-bus/EvaluationRecordsController/queryConfig | 200 |  | not_exposed | ev_38947e25f18f5c3530edafcc8a81c9e535540d7a35a161748e64dc800d952267 |
| POST | /web-cust/bankWithholding/qianyueConfig | 200 |  | not_exposed | ev_38947e25f18f5c3530edafcc8a81c9e535540d7a35a161748e64dc800d952267 |

静态 AJAX 地址候选，存在于页面或关联脚本，未据此证明业务动作执行：
- `https://o2o.unee.com.cn/web-bus/pc/js/ligerUI/js/ligerui.all.js`：`...`。
- `https://o2o.unee.com.cn/web-bus/pc/html/evaluationRecords/js/evaluationRecords.js`：`/web-bus/EvaluationRecordsController/initialization`、`/web-bus/EvaluationRecordsController/queryConfig`、`/web-cust/bankWithholding/qianyueConfig`。

## 综合查询 一户一档

路由 `/un-pc-fronted/#/formsManagement/gearPerHousehold/index`。菜单来源 `ev_25226ae15c591aa25247b4d7ef5e89e5ddd4162209de1bcb9259a6a2f7d462cc`。

菜单定义的操作：查看手机号、催缴记录导出、导入。这些是菜单权限定义，不代表流程已执行验证。

这是 SPA 路由，REA 捕获的共享 HTML 壳和 bundle 不等于该路由完整界面。REA 静态解析没有恢复动态字段；以下独立浏览器观察补充了部分运行时界面结构。

补充界面观察 `UI-SPA-500005`，来源 [原始内置浏览器渲染 DOM](/Volumes/MOVESPEED/Projects/uni-rea/does/spa-ui-observations.json)；与 REA 专用 Chrome 是独立浏览器上下文。

动态界面按钮：查 询、导 出、导 入。

该 DOM 观察没有取得原生表头元素，一户一档的动态列和完整表单语义仍未知。

页面运行错误：Cannot read properties of null (reading '1')。错误与该加载步骤在时间上关联，未证明具体调用因果。

页面证据：
- `ev_38947e25f18f5c3530edafcc8a81c9e535540d7a35a161748e64dc800d952267`，事务 `request-282`，响应摘要 `fb4004b266dc7cdab0c8eb0fbe54850f25894027bc46dcba4c6f1a8398da4918`，HTTP 200。
- `ev_38947e25f18f5c3530edafcc8a81c9e535540d7a35a161748e64dc800d952267`，事务 `request-487`，响应摘要 `fb4004b266dc7cdab0c8eb0fbe54850f25894027bc46dcba4c6f1a8398da4918`，HTTP 200。
- `ev_38947e25f18f5c3530edafcc8a81c9e535540d7a35a161748e64dc800d952267`，事务 `request-488`，响应摘要 `fb4004b266dc7cdab0c8eb0fbe54850f25894027bc46dcba4c6f1a8398da4918`，HTTP 200。

前端脚本：
已捕获 3 个关联脚本，地址和摘要见 JSON。业务脚本包括：`https://o2o.unee.com.cn/un-pc-fronted/less.min.js`、`https://o2o.unee.com.cn/un-pc-fronted/js/chunk-vendors.f0e6600a.js`、`https://o2o.unee.com.cn/un-pc-fronted/js/app.a069b50e.js`。

同一页面加载步骤内观察到的请求：

| 方法 | 路径 | HTTP | 查询参数名 | 请求体参数名 | Evidence |
| --- | --- | --- | --- | --- | --- |
| GET | /un-pc-fronted/ | 200 |  | not_exposed | ev_38947e25f18f5c3530edafcc8a81c9e535540d7a35a161748e64dc800d952267 |
| POST | /cent-cust/userInfo/queryPCStaffInfo | 200 |  | not_exposed | ev_38947e25f18f5c3530edafcc8a81c9e535540d7a35a161748e64dc800d952267 |
| POST | /web-common/list/queryOrgList | 200 | userId | not_exposed | ev_38947e25f18f5c3530edafcc8a81c9e535540d7a35a161748e64dc800d952267 |
| POST | /web-common/list/queryRegionalList | 200 | userId, orgIds | not_exposed | ev_38947e25f18f5c3530edafcc8a81c9e535540d7a35a161748e64dc800d952267 |
| POST | /web-common/list/queryServiceList | 200 | userId, orgIds, regionalIds | not_exposed | ev_38947e25f18f5c3530edafcc8a81c9e535540d7a35a161748e64dc800d952267 |
| POST | /web-common/list/queryBuildList | 200 | serviceIds | not_exposed | ev_38947e25f18f5c3530edafcc8a81c9e535540d7a35a161748e64dc800d952267 |
| POST | /web-common/list/queryServiceStewards | 200 | serviceId | not_exposed | ev_38947e25f18f5c3530edafcc8a81c9e535540d7a35a161748e64dc800d952267 |
| POST | /web-common/common/sysConfigQueryRest | 200 | column_name, table_name | not_exposed | ev_38947e25f18f5c3530edafcc8a81c9e535540d7a35a161748e64dc800d952267 |
| POST | /web-common/list/queryServiceHourseList | 200 | serviceId, hourseName | not_exposed | ev_38947e25f18f5c3530edafcc8a81c9e535540d7a35a161748e64dc800d952267 |
| POST | /web-cust/mobile/one/hourse/page | 200 |  | pageSize, serviceId, startNum | ev_38947e25f18f5c3530edafcc8a81c9e535540d7a35a161748e64dc800d952267 |

静态 AJAX 地址候选，存在于页面或关联脚本，未据此证明业务动作执行：
- `https://o2o.unee.com.cn/un-pc-fronted/js/chunk-vendors.f0e6600a.js`：`%s is not a valid %s`、`Link source`、`链接地址`。
- `https://o2o.unee.com.cn/un-pc-fronted/js/app.a069b50e.js`：`/cent-cust/userInfo/queryPCStaffInfo`、`/web-common/common/sysConfigQueryRest`、`/cent-cust/custInfo/statistics/orgRegionServiceList`、`/web-common/list/organization/queryOrgList`、`/web-common/list/organization/queryRegionalList`、`/web-common/list/organization/queryServiceList`、`/web-cust/mobile/queryld`、`/web-cust/mobile/queryhoursename`、`/cent-cust/configCodes/queryConfigCodeList`、`/sso/login`。

## 报表管理 工作计划报表

路由 `/web-seo/pc/html/workPlanStatement/groupView1.html`。菜单来源 `ev_25226ae15c591aa25247b4d7ef5e89e5ddd4162209de1bcb9259a6a2f7d462cc`。

菜单定义的操作：工作计划导出列表1、工作计划导出列表2、工作计划导出列表3、工作计划导出列表4、查询。这些是菜单权限定义，不代表流程已执行验证。

页面字段：start_time、end_time。

页面按钮：查询、导出。

关联脚本中的静态表头候选：+(item.state==、+v+、城市公司、工作计划项、进行中、已完成、延期完成、完成效果评分。共享脚本候选可能属于其他路由。

页面证据：
- `ev_9049e649478b51750b2f229948baf3cd299a931299e31a494686e3395de48951`，事务 `request-344`，响应摘要 `66d06b2baddfa9198e983a564c4c37facfb122a79f73e2f3ed33b7b49bb65cb8`，HTTP 200。

前端脚本：
已捕获 10 个关联脚本，地址和摘要见 JSON。业务脚本包括：`https://o2o.unee.com.cn/web-seo/pc/js/common.js`、`https://o2o.unee.com.cn/web-seo/pc/js/niceValidator/local/zh_CN.js`、`https://o2o.unee.com.cn/web-seo/pc/html/workPlanStatement/js/resetTableHeight.js`、`https://o2o.unee.com.cn/web-seo/pc/html/workPlanStatement/js/groupView1.js`。

同一页面加载步骤内观察到的请求：

| 方法 | 路径 | HTTP | 查询参数名 | 请求体参数名 | Evidence |
| --- | --- | --- | --- | --- | --- |
| POST | /web-common/common/systemUserOrg | 200 | system_user_id | not_exposed | ev_9049e649478b51750b2f229948baf3cd299a931299e31a494686e3395de48951 |
| POST | /web-common/common/systemUserArea | 200 | system_user_id | org_ids | ev_9049e649478b51750b2f229948baf3cd299a931299e31a494686e3395de48951 |
| POST | /web-bus/getPushMessage/6520159 | 200 |  | not_exposed | ev_9049e649478b51750b2f229948baf3cd299a931299e31a494686e3395de48951 |

静态 AJAX 地址候选，存在于页面或关联脚本，未据此证明业务动作执行：
- `https://o2o.unee.com.cn/web-seo/pc/js/ligerUI/js/ligerui.all.js`：`...`。
- `https://o2o.unee.com.cn/web-seo/pc/html/workPlanStatement/js/groupView1.js`：`/web-seo/workPlanStatement/efficiencyViewQuery1`。

## 客户服务 认证申请

路由 `/web-cust/pc/html/certificationApplication/caList.html`。菜单来源 `ev_25226ae15c591aa25247b4d7ef5e89e5ddd4162209de1bcb9259a6a2f7d462cc`。

菜单定义的操作：查询。这些是菜单权限定义，不代表流程已执行验证。

页面字段：org_name、service_name、status_name、start_time、end_time、extra_msg。

页面按钮：返回、查询、列设置。

关联脚本中的静态表头候选：服务中心、房号、申请人姓名、申请人联系电话、申请身份、状态、申请时间、申请来源、审批结果、提交人、审批人、审批时间、操作。共享脚本候选可能属于其他路由。

该加载阶段存在失败或 HTTP 错误资源：`/web-cust/pc/js/niceValidator/style.css` net::ERR_ABORTED。页面关闭可能中断请求，需重新观察其影响。

页面证据：
- `ev_f2631a7dc031a549a87680b1e2affa1a088efdd842c289a316e649c9749ad8e0`，事务 `request-361`，响应摘要 `d35fca5f06aeff3f8990bb9b2bb568e63fc27f9aee5b09b420a658f24ff55ff0`，HTTP 200。

前端脚本：
已捕获 15 个关联脚本，地址和摘要见 JSON。业务脚本包括：`https://o2o.unee.com.cn/web-cust/pc/js/common.js`、`https://o2o.unee.com.cn/web-cust/pc/js/table/custom_table.js`、`https://o2o.unee.com.cn/web-cust/pc/js/progressbar/custom_progressbar.js`、`https://o2o.unee.com.cn/web-cust/pc/html/certificationApplication/js/caList.js`、`https://o2o.unee.com.cn/web-cust/pc/html/certificationApplication/js/resetTableHeight.js`、`https://o2o.unee.com.cn/web-cust/pc/js/niceValidator/local/zh_CN.js`、`https://o2o.unee.com.cn/web-cust/pc/js/niceValidator/local/zh_CN.js`。

同一页面加载步骤内观察到的请求：

| 方法 | 路径 | HTTP | 查询参数名 | 请求体参数名 | Evidence |
| --- | --- | --- | --- | --- | --- |
| POST | /web-common/common/systemUserOrg | 200 | system_user_id | findPath | ev_f2631a7dc031a549a87680b1e2affa1a088efdd842c289a316e649c9749ad8e0 |
| POST | /web-common/common/systemDataPermission | 200 | system_user_id, type | findPath | ev_f2631a7dc031a549a87680b1e2affa1a088efdd842c289a316e649c9749ad8e0 |
| POST | /web-common/common/sysConfigQueryRest | 200 |  | column_name, table_name | ev_f2631a7dc031a549a87680b1e2affa1a088efdd842c289a316e649c9749ad8e0 |
| GET | /web-bus/columnController/getShowColumn | 200 | modules_code | not_exposed | ev_f2631a7dc031a549a87680b1e2affa1a088efdd842c289a316e649c9749ad8e0 |

静态 AJAX 地址候选，存在于页面或关联脚本，未据此证明业务动作执行：
- `https://o2o.unee.com.cn/web-cust/pc/html/certificationApplication/js/caList.js`：`/web-bus/columnController/getShowColumn`。
- `https://o2o.unee.com.cn/web-cust/pc/js/ligerUI/js/ligerui.all.js`：`...`。

## 系统中心 接口日志管理

路由 `/web-sys/pc/html/interfaceLogManage/interfaceLogList.html`。菜单来源 `ev_25226ae15c591aa25247b4d7ef5e89e5ddd4162209de1bcb9259a6a2f7d462cc`。

菜单定义的操作：导出、查询。这些是菜单权限定义，不代表流程已执行验证。

页面字段：org_name、service_name、keyWord、offer_type_name、interactive_system_name、inf_direction_name、status_name、start_time、end_time。

页面按钮：查询。

关联脚本中的静态表头候选：接口流水号、城市公司、服务中心、房号、客户名称、电话、业务类别、对接系统、接口方向、接口名称、缴费流水号、状态、成功记录数、失败记录数、失败原因、发送时间、操作。共享脚本候选可能属于其他路由。

该加载阶段存在失败或 HTTP 错误资源：`/web-sys/pc/html/interfaceLogManage/js/theme/default/layer.css` 404。页面关闭可能中断请求，需重新观察其影响。

页面证据：
- `ev_0cf173243cdb26a582983b2682632c0be53484fd0b8090f23f41b058eb1f61ca`，事务 `request-270`，响应摘要 `ac4d80436896408dc5446255fdf92aa0992a3667a5327588c65823d2cc508c5f`，HTTP 200。

前端脚本：
已捕获 14 个关联脚本，地址和摘要见 JSON。业务脚本包括：`https://o2o.unee.com.cn/web-bus/pc/js/common.js`、`https://o2o.unee.com.cn/web-bus/pc/js/progressbar/custom_progressbar.js`、`https://o2o.unee.com.cn/web-sys/pc/html/interfaceLogManage/js/layer.js`、`https://o2o.unee.com.cn/web-sys/pc/html/interfaceLogManage/js/interfaceLogList.js`、`https://o2o.unee.com.cn/web-bus/pc/js/niceValidator/local/zh_CN.js`。

同一页面加载步骤内观察到的请求：

| 方法 | 路径 | HTTP | 查询参数名 | 请求体参数名 | Evidence |
| --- | --- | --- | --- | --- | --- |
| POST | /web-common/common/systemUserOrg | 200 | system_user_id | findPath | ev_0cf173243cdb26a582983b2682632c0be53484fd0b8090f23f41b058eb1f61ca |
| POST | /web-common/common/systemDataPermission | 200 | system_user_id, type | findPath | ev_0cf173243cdb26a582983b2682632c0be53484fd0b8090f23f41b058eb1f61ca |
| POST | /web-common/common/sysConfigQueryRest | 200 |  | column_name, table_name | ev_0cf173243cdb26a582983b2682632c0be53484fd0b8090f23f41b058eb1f61ca |

静态 AJAX 地址候选，存在于页面或关联脚本，未据此证明业务动作执行：
- `https://o2o.unee.com.cn/web-sys/pc/html/interfaceLogManage/js/interfaceLogList.js`：`/web-sys/interfaceLogManage/queryInterfaceLogList`。

## 统计中心 公开问答报表管理

路由 `/web-cust/pc/html/faq/faqStatementsByCity.html`。菜单来源 `ev_25226ae15c591aa25247b4d7ef5e89e5ddd4162209de1bcb9259a6a2f7d462cc`。

菜单定义的操作：公开问答报表管理导出、查询。这些是菜单权限定义，不代表流程已执行验证。

页面字段：start_time、end_time、open_faq_content、content、org_join_percent、org_objection_percent、is_upgrade。

页面按钮：查询、导出。

关联脚本中的静态表头候选：+(item.state==、+v+、城市公司、服务中心、公开问答内容、提交时间、官方回复、回复人、回复时间、处理时长（分钟）、浏览数、支持数、反对数、参与率、反对率、升级过、城市公司结果、集团结果。共享脚本候选可能属于其他路由。

页面证据：
- `ev_09a45f0a06a75d1316e52ebd6f6fa25316e841f7362f861659f9969d3c364feb`，事务 `request-390`，响应摘要 `65518a07b6568f6390cf8b702271ed4053a5242c0e5e64aca5ddee54c0dd9438`，HTTP 200。

前端脚本：
已捕获 11 个关联脚本，地址和摘要见 JSON。业务脚本包括：`https://o2o.unee.com.cn/web-cust/pc/js/common.js`、`https://o2o.unee.com.cn/web-cust/pc/js/niceValidator/local/zh_CN.js`、`https://o2o.unee.com.cn/web-cust/pc/js/niceValidator/local/zh_CN.js`、`https://o2o.unee.com.cn/web-cust/pc/html/faq/js/resetTableHeight.js`、`https://o2o.unee.com.cn/web-cust/pc/html/faq/js/faqStatementsByCityHead.js`、`https://o2o.unee.com.cn/web-cust/pc/html/faq/js/faqStatementsByCity.js`。

同一页面加载步骤内观察到的请求：

| 方法 | 路径 | HTTP | 查询参数名 | 请求体参数名 | Evidence |
| --- | --- | --- | --- | --- | --- |
| POST | /web-common/common/systemUserOrg | 200 | system_user_id | not_exposed | ev_09a45f0a06a75d1316e52ebd6f6fa25316e841f7362f861659f9969d3c364feb |
| POST | /web-common/common/systemDataPermission | 200 | system_user_id, org_id | not_exposed | ev_09a45f0a06a75d1316e52ebd6f6fa25316e841f7362f861659f9969d3c364feb |

静态 AJAX 地址候选，存在于页面或关联脚本，未据此证明业务动作执行：
- `https://o2o.unee.com.cn/web-cust/pc/js/ligerUI/js/ligerui.all.js`：`...`。
- `https://o2o.unee.com.cn/web-cust/pc/html/faq/js/faqStatementsByCity.js`：`/web-cust/pc/WarningController/listOpenFaqReply.do`。

## 配置管理 手机开门推送配置

路由 `/web-bus/pc/html/openDoor/push_manage_list.html`。菜单来源 `ev_25226ae15c591aa25247b4d7ef5e89e5ddd4162209de1bcb9259a6a2f7d462cc`。

菜单定义的操作：查询、导出、新增、删除、修改。这些是菜单权限定义，不代表流程已执行验证。

页面字段：org_name、service_name、assigned_org_name、offer_type_name、push_offer_name、validity_start_time、validity_end_time、create_start_time、create_end_time。

页面按钮：查询、导出、新增。

关联脚本中的静态表头候选：发起方、业务类别、推送业务、推送有效期、创建时间、修改时间、操作。共享脚本候选可能属于其他路由。

页面证据：
- `ev_c590a872a43fe0d5c14d31c18cdcb66b904bb81b4e05b852730bf8dceb6eea00`，事务 `request-420`，响应摘要 `ed16950b5179d0e3ba4e63f1468a28e8ca5e4a5c509531842605c294f4ffef71`，HTTP 200。

前端脚本：
已捕获 3 个关联脚本，地址和摘要见 JSON。业务脚本包括：`https://o2o.unee.com.cn/web-bus/pc/html/openDoor/js/taskCommon.js`、`https://o2o.unee.com.cn/web-bus/pc/js/niceValidator/local/zh_CN.js`、`https://o2o.unee.com.cn/web-bus/pc/html/openDoor/js/push_manager_list.js`。

同一页面加载步骤内观察到的请求：

| 方法 | 路径 | HTTP | 查询参数名 | 请求体参数名 | Evidence |
| --- | --- | --- | --- | --- | --- |
| POST | /web-common/common/systemUserOrg | 200 | system_user_id | findPath | ev_c590a872a43fe0d5c14d31c18cdcb66b904bb81b4e05b852730bf8dceb6eea00 |
| POST | /web-common/common/systemDataPermission | 200 | system_user_id, type | findPath | ev_c590a872a43fe0d5c14d31c18cdcb66b904bb81b4e05b852730bf8dceb6eea00 |
| POST | /web-bus/pc/pushManageController/queryConfig | 200 |  | not_exposed | ev_c590a872a43fe0d5c14d31c18cdcb66b904bb81b4e05b852730bf8dceb6eea00 |

静态 AJAX 地址候选，存在于页面或关联脚本，未据此证明业务动作执行：
- `https://o2o.unee.com.cn/web-bus/pc/html/openDoor/js/push_manager_list.js`：`/web-bus/DoorPagePushManageController/deleteCustAppPagePush`。

## 统计中心 员工受欢迎指数报表

路由 `/web-seo/pc/html/StaffPopularity/staff_popularity_orglist.html`。菜单来源 `ev_25226ae15c591aa25247b4d7ef5e89e5ddd4162209de1bcb9259a6a2f7d462cc`。

菜单定义的操作：查询、导出。这些是菜单权限定义，不代表流程已执行验证。

页面字段：evaluation_theme_name、ques_name。

页面按钮：查询、列设置、导出。

关联脚本中的静态表头候选：序号、平台公司、有效问卷、户均员工满意数、平均受欢迎指数、管家粘度均值、参评条线员工受欢迎指数、户均满意条线员工数、管理人员、客服条线、安全条线、工程条线、环境条线。共享脚本候选可能属于其他路由。

页面证据：
- `ev_09a45f0a06a75d1316e52ebd6f6fa25316e841f7362f861659f9969d3c364feb`，事务 `request-434`，响应摘要 `fc3544f9ed85ce96b1cd4501c70c2c7d00845e5770f1b61833fdba5a46df4014`，HTTP 200。

前端脚本：
已捕获 12 个关联脚本，地址和摘要见 JSON。业务脚本包括：`https://o2o.unee.com.cn/web-seo/pc/html/StaffPopularity/js/common.js`、`https://o2o.unee.com.cn/web-seo/pc/html/StaffPopularity/js/resetTableHeight.js`、`https://o2o.unee.com.cn/web-seo/pc/html/StaffPopularity/js/staff_popularity_orglist.js`、`https://o2o.unee.com.cn/web-seo/pc/html/StaffPopularity/js/virtual-select.min.js`。

同一页面加载步骤内观察到的请求：

| 方法 | 路径 | HTTP | 查询参数名 | 请求体参数名 | Evidence |
| --- | --- | --- | --- | --- | --- |
| POST | /web-common/common/sysConfigQueryRest | 200 |  | column_name, table_name | ev_09a45f0a06a75d1316e52ebd6f6fa25316e841f7362f861659f9969d3c364feb |
| POST | /web-seo/pc/staffPopularity/queryQuesListByEvaluationTheme | 200 |  | evaluationTheme | ev_09a45f0a06a75d1316e52ebd6f6fa25316e841f7362f861659f9969d3c364feb |
| GET | /web-bus/columnController/getShowColumn | 200 | modules_code | not_exposed | ev_09a45f0a06a75d1316e52ebd6f6fa25316e841f7362f861659f9969d3c364feb |
| POST | /web-common/list/queryOrgList | 200 |  | userId | ev_09a45f0a06a75d1316e52ebd6f6fa25316e841f7362f861659f9969d3c364feb |

静态 AJAX 地址候选，存在于页面或关联脚本，未据此证明业务动作执行：
- `https://o2o.unee.com.cn/web-seo/pc/js/ligerUI/js/ligerui.all.js`：`...`。
- `https://o2o.unee.com.cn/web-seo/pc/html/StaffPopularity/js/staff_popularity_orglist.js`：`/web-common/common/sysConfigQueryRest`、`/web-seo/pc/staffPopularity/queryQuesListByEvaluationTheme`、`/web-odm/staffPopularity/queryStaffPopularityByOrg`、`/web-bus/columnController/getShowColumn`。

## 报表管理 过程效率

路由 `/web-report/pc/html/processEfficiency/efficiencyView.html`。菜单来源 `ev_25226ae15c591aa25247b4d7ef5e89e5ddd4162209de1bcb9259a6a2f7d462cc`。

菜单定义的操作：导出列表1、导出列表2、导出列表3、导出列表4、列设置、查询。这些是菜单权限定义，不代表流程已执行验证。

页面字段：start_time、end_time。

页面按钮：查询、导出。

关联脚本中的静态表头候选：+(item.state==、+v+、平台公司、总工单数、工单关闭数、派单、派单工单数、派单率、超时工单数、派单及时率、派单平均时长(小时)、接单、接单工单数、接单率、接单及时率、接单平均时长(小时)、实施、实施工单数、实施平均时长(小时)、验收、验收工单数、验收平均时长(小时)、已完成、处理及时率、完成数、完成率、评价率、满意率。共享脚本候选可能属于其他路由。

页面证据：
- `ev_9049e649478b51750b2f229948baf3cd299a931299e31a494686e3395de48951`，事务 `request-388`，响应摘要 `8889dfef8cf2b10c1a8540b86e28ad252419457a0a877cfe745d58402b4abe77`，HTTP 200。

前端脚本：
已捕获 11 个关联脚本，地址和摘要见 JSON。业务脚本包括：`https://o2o.unee.com.cn/web-report/pc/js/common.js`、`https://o2o.unee.com.cn/web-report/pc/html/processEfficiency/js/resetTableHeight.js`、`https://o2o.unee.com.cn/web-report/pc/js/niceValidator/local/zh_CN.js`、`https://o2o.unee.com.cn/web-report/pc/html/processEfficiency/js/efficiencyView.js`、`https://o2o.unee.com.cn/web-report/pc/html/processEfficiency/js/virtual-select.min.js`。

同一页面加载步骤内观察到的请求：

| 方法 | 路径 | HTTP | 查询参数名 | 请求体参数名 | Evidence |
| --- | --- | --- | --- | --- | --- |
| POST | /web-common/list/queryOrgList | 200 |  | userId | ev_9049e649478b51750b2f229948baf3cd299a931299e31a494686e3395de48951 |
| POST | /web-common/common/getSystemUserProcessArea | 200 |  | orgIds, systemUserId | ev_9049e649478b51750b2f229948baf3cd299a931299e31a494686e3395de48951 |
| POST | /web-common/common/sysConfigQueryRest | 200 |  | column_name, table_name | ev_9049e649478b51750b2f229948baf3cd299a931299e31a494686e3395de48951 |

静态 AJAX 地址候选，存在于页面或关联脚本，未据此证明业务动作执行：
- `https://o2o.unee.com.cn/web-report/pc/js/ligerUI/js/ligerui.all.js`：`...`。
- `https://o2o.unee.com.cn/web-report/pc/html/processEfficiency/js/efficiencyView.js`：`/web-report/processEfficiency/getOrgDetailData`。

## 报表管理 星海图

路由 `/web-report/pc/html/viewport/viewportImage.html`。菜单来源 `ev_25226ae15c591aa25247b4d7ef5e89e5ddd4162209de1bcb9259a6a2f7d462cc`。

页面证据：
- `ev_9049e649478b51750b2f229948baf3cd299a931299e31a494686e3395de48951`，事务 `request-439`，响应摘要 `e7381647d77cd6fb4ca1b5cc71f260aa123d108f1f40a9a1bd8a04ca0906e310`，HTTP 200。

前端脚本：
已捕获 1 个关联脚本，地址和摘要见 JSON。业务脚本包括：。

HTML 内联脚本静态观察：`ev_9049e649478b51750b2f229948baf3cd299a931299e31a494686e3395de48951`，内联摘要 `38a7ea3105bec1e4efccf4a1c540166e7f239a49bf7b46ee7d8ddc389b7edf09`，151 字符。

window.open 静态导航路径候选 `/web-report/pc/html/viewport/viewport.html`，完整 origin 由运行时表达式构造；未打开该目标。

## 配置管理 电梯管理

路由 `/web-bus/pc/html/elevatorManage/elevator_manage.html?checkVisitor=1`。菜单来源 `ev_25226ae15c591aa25247b4d7ef5e89e5ddd4162209de1bcb9259a6a2f7d462cc`。

菜单定义的操作：导出、新增、批量新增、查询。这些是菜单权限定义，不代表流程已执行验证。

页面字段：org_name、service_name、build_name、unit_name、elevator_name。

页面按钮：导出、新增、批量新增、查询。

关联脚本中的静态表头候选：电梯名称、楼栋、单元、电梯顺序、设备厂商、主控板MAC、访客板MAC、控制单元、固件版本、密钥、描述、备注、硬件厂商楼层数据、UN+映射楼层数据、修改时间、修改人、操作。共享脚本候选可能属于其他路由。

该加载阶段存在失败或 HTTP 错误资源：`/web-bus/pc/js/ligerUI/skins/ligerui-icons.css` net::ERR_ABORTED。页面关闭可能中断请求，需重新观察其影响。

页面证据：
- `ev_c590a872a43fe0d5c14d31c18cdcb66b904bb81b4e05b852730bf8dceb6eea00`，事务 `request-469`，响应摘要 `43ed8a16b829ae9bb2ddb4b8150e232b7f54a430e0b0a42c0f7463e8cfd64956`，HTTP 200。

前端脚本：
已捕获 4 个关联脚本，地址和摘要见 JSON。业务脚本包括：`https://o2o.unee.com.cn/web-bus/pc/html/elevatorManage/js/common.js`、`https://o2o.unee.com.cn/web-bus/pc/js/progressbar/custom_progressbar.js`、`https://o2o.unee.com.cn/web-bus/pc/html/elevatorManage/js/resetTableHeight.js`、`https://o2o.unee.com.cn/web-bus/pc/js/niceValidator/local/zh_CN.js`、`https://o2o.unee.com.cn/web-bus/pc/html/elevatorManage/js/elevator_manage.js`。

同一页面加载步骤内观察到的请求：

| 方法 | 路径 | HTTP | 查询参数名 | 请求体参数名 | Evidence |
| --- | --- | --- | --- | --- | --- |
| POST | /web-common/common/systemUserOrg | 200 | type, system_user_id | findPath | ev_c590a872a43fe0d5c14d31c18cdcb66b904bb81b4e05b852730bf8dceb6eea00 |

静态 AJAX 地址候选，存在于页面或关联脚本，未据此证明业务动作执行：
- `https://o2o.unee.com.cn/web-bus/pc/html/elevatorManage/js/elevator_manage.js`：`/web-bus/CustElevatorManageController/queryCustElevatorManage`、`/web-bus/CustElevatorManageController/deleteCustElevatorManage`。

## 系统中心 消息通知

路由 `/portal/notice/notice.html`。菜单来源 `ev_25226ae15c591aa25247b4d7ef5e89e5ddd4162209de1bcb9259a6a2f7d462cc`。

菜单定义的操作：查询、批量删除。这些是菜单权限定义，不代表流程已执行验证。

页面字段：org_name、service_name、read_type_name、date_1、date_2、title_message、title_content。

页面按钮：查询、批量删除。

关联脚本中的静态表头候选：服务中心、消息标题、消息内容、发布时间、是否已阅、操作。共享脚本候选可能属于其他路由。

页面运行错误：Unexpected token '<', "<!DOCTYPE "... is not valid JSON。错误与该加载步骤在时间上关联，未证明具体调用因果。

该加载阶段存在失败或 HTTP 错误资源：`/pc/js/jquery.placeholder.js` 404、`/web-common/common/systemDataPermission` 510、`/portal/js/artDialog/images/plugins/artdialog/loading.gif` 404。页面关闭可能中断请求，需重新观察其影响。

页面证据：
- `ev_0cf173243cdb26a582983b2682632c0be53484fd0b8090f23f41b058eb1f61ca`，事务 `request-327`，响应摘要 `2037eb081ac79c4909ea6ca187093d59d3ec2f26669c7daff8bfd12f6aac7462`，HTTP 200。

前端脚本：
已捕获 12 个关联脚本，地址和摘要见 JSON。业务脚本包括：`https://o2o.unee.com.cn/portal/js/common.js`、`https://o2o.unee.com.cn/portal/js/niceValidator/local/zh_CN.js`、`https://o2o.unee.com.cn/portal/notice/js/noticeList.js`。

HTML 内联脚本静态观察：`ev_0cf173243cdb26a582983b2682632c0be53484fd0b8090f23f41b058eb1f61ca`，内联摘要 `fae0c5cd92501aceb42295a7fefdd8946f1ece09228bf2a32403cfb7721cc8f8`，110 字符。

document.write 动态脚本声明候选 `https://o2o.unee.com.cn/portal/notice/js/noticeList.js`，查询参数名 v；关联同功能中实际已记录的脚本请求，不执行该加载语句。

同一页面加载步骤内观察到的请求：

| 方法 | 路径 | HTTP | 查询参数名 | 请求体参数名 | Evidence |
| --- | --- | --- | --- | --- | --- |
| POST | /web-common/common/systemUserOrg | 200 | system_user_id | findPath | ev_0cf173243cdb26a582983b2682632c0be53484fd0b8090f23f41b058eb1f61ca |
| POST | /web-common/common/systemDataPermission | 510 | system_user_id, type | findPath | ev_0cf173243cdb26a582983b2682632c0be53484fd0b8090f23f41b058eb1f61ca |
| POST | /web-bus/getPushMessage/6520159 | 302 |  | not_exposed | ev_0cf173243cdb26a582983b2682632c0be53484fd0b8090f23f41b058eb1f61ca |
| GET | /sso/service/AuthService | 302 | clientUrl | not_exposed | ev_0cf173243cdb26a582983b2682632c0be53484fd0b8090f23f41b058eb1f61ca |
| GET | /sso/login.html | 200 | clientUrl | not_exposed | ev_0cf173243cdb26a582983b2682632c0be53484fd0b8090f23f41b058eb1f61ca |

静态 AJAX 地址候选，存在于页面或关联脚本，未据此证明业务动作执行：
- `https://o2o.unee.com.cn/portal/js/ligerUI/js/ligerui.all.js`：`...`。
- `https://o2o.unee.com.cn/portal/notice/js/noticeList.js`：`/portal/pc/noticeList`、`/portal/pc/queryAndUpdateMessage`、`/portal/pc/deleteMessage`。

## 客户服务 评价结果

路由 `/web-cust/pc/html/commentResult/commentResult.html`。菜单来源 `ev_25226ae15c591aa25247b4d7ef5e89e5ddd4162209de1bcb9259a6a2f7d462cc`。

菜单定义的操作：查询、导出。这些是菜单权限定义，不代表流程已执行验证。

页面字段：org_name、service_name、evaluate_classify_name、paste_location、evaluate_label_note、begin_date、end_date、status_name。

页面按钮：查询、导出、返回。

关联脚本中的静态表头候选：城市公司、服务中心、互动点位、二维码粘贴地点、责任主管、评价对象、评分、评价内容、意见建议、图片、提交时间、处理时间、处理状态、关联工单、操作。共享脚本候选可能属于其他路由。

该加载阶段存在失败或 HTTP 错误资源：`/web-cust/pc/css/jquery.autocomplete.css` net::ERR_ABORTED、`/web-cust/pc/js/ligerUI/skins/ligerui-icons.css` net::ERR_ABORTED、`/web-cust/pc/js/artDialog/style.css` net::ERR_ABORTED、`/web-cust/pc/js/artDialog/images/plugins/artdialog/loading.gif` 404。页面关闭可能中断请求，需重新观察其影响。

页面证据：
- `ev_f2631a7dc031a549a87680b1e2affa1a088efdd842c289a316e649c9749ad8e0`，事务 `request-416`，响应摘要 `94ca8ac91b72bdd96be0c72339eb3d7457d29fa10b5a01c047fbe38172cd5418`，HTTP 200。

前端脚本：
已捕获 18 个关联脚本，地址和摘要见 JSON。业务脚本包括：`https://o2o.unee.com.cn/web-cust/pc/js/esmp_base.js`、`https://o2o.unee.com.cn/web-cust/pc/js/esmp_base.js`、`https://o2o.unee.com.cn/web-cust/pc/html/workbench/taskCommon.js`、`https://o2o.unee.com.cn/web-cust/pc/html/workbench/taskCommon.js`、`https://o2o.unee.com.cn/web-cust/pc/html/work/js/dateFormat.js`、`https://o2o.unee.com.cn/web-cust/pc/html/work/js/dateFormat.js`、`https://o2o.unee.com.cn/web-cust/pc/html/work/js/resetTableHeight.js`、`https://o2o.unee.com.cn/web-cust/pc/html/work/js/resetTableHeight.js`、`https://o2o.unee.com.cn/web-cust/pc/js/niceValidator/local/zh_CN.js`、`https://o2o.unee.com.cn/web-cust/pc/js/niceValidator/local/zh_CN.js`、`https://o2o.unee.com.cn/web-cust/pc/js/viewerjs/viewer.js`、`https://o2o.unee.com.cn/web-cust/pc/html/commentResult/viewer_default.js`、`https://o2o.unee.com.cn/web-cust/pc/html/commentResult/commentResult.js`。

同一页面加载步骤内观察到的请求：

| 方法 | 路径 | HTTP | 查询参数名 | 请求体参数名 | Evidence |
| --- | --- | --- | --- | --- | --- |
| POST | /web-bus/getPushMessage/6520159 | 200 |  | not_exposed | ev_f2631a7dc031a549a87680b1e2affa1a088efdd842c289a316e649c9749ad8e0 |
| POST | /web-common/common/systemUserOrg | 200 | system_user_id | findPath | ev_f2631a7dc031a549a87680b1e2affa1a088efdd842c289a316e649c9749ad8e0 |
| POST | /web-common/common/systemDataPermission | 200 | system_user_id, type | findPath | ev_f2631a7dc031a549a87680b1e2affa1a088efdd842c289a316e649c9749ad8e0 |
| POST | /web-cust/commentResultController/queryConfig | 200 |  | not_exposed | ev_f2631a7dc031a549a87680b1e2affa1a088efdd842c289a316e649c9749ad8e0 |

静态 AJAX 地址候选，存在于页面或关联脚本，未据此证明业务动作执行：
- `https://o2o.unee.com.cn/web-cust/pc/js/ligerUI/js/ligerui.all.js`：`...`。
- `https://o2o.unee.com.cn/web-cust/pc/js/viewerjs/viewer.js`：`src`。
- `https://o2o.unee.com.cn/web-cust/pc/html/commentResult/viewer_default.js`：`data-original`。
- `https://o2o.unee.com.cn/web-cust/pc/html/commentResult/commentResult.js`：`/web-cust/commentResultController/queryScanEvaluateInfo`、`/web-cust/commentResultController/updateScanEvaluateInfo`、`/web-cust/commentResultController/queryEventIds`、`/web-cust/commentResultController/queryConfig`。

## 运营中心 社区活动

路由 `/web-odm/pc/html/communityActivity/communityActivityList.html`。菜单来源 `ev_25226ae15c591aa25247b4d7ef5e89e5ddd4162209de1bcb9259a6a2f7d462cc`。

菜单定义的操作：新增、修改、删除、发布、下架、置顶、取消置顶、活动评论置顶、活动评论取消置顶、活动评论删除、活动评论导出、图片下载、导出、报名清单、查询、报名清单导出。这些是菜单权限定义，不代表流程已执行验证。

页面字段：org_name、service_name、fqf_type_name、status_type_name、social_content、apply_start_time_1、apply_start_time_2、implement_start_time_1、implement_start_time_2。

页面按钮：新增、导出、查询、项目二维码、二维码下载。

关联脚本中的静态表头候选：活动标题、发起方、状态、创建时间、报名开始时间、报名结束时间、活动开始时间、活动结束时间、二维码、操作。共享脚本候选可能属于其他路由。

该加载阶段存在失败或 HTTP 错误资源：`/web-odm/pc/js/artDialog/images/plugins/artdialog/loading.gif` 404。页面关闭可能中断请求，需重新观察其影响。

页面证据：
- `ev_c4d4036bc65a408c8041f833ce8889a39169173452dd7d6ae2a6a106c5d2ca2b`，事务 `request-318`，响应摘要 `328c652f200a5fcc2d41c636170da5e737969bfd3cebe3184a76a5927c227767`，HTTP 200。

前端脚本：
已捕获 16 个关联脚本，地址和摘要见 JSON。业务脚本包括：`https://o2o.unee.com.cn/web-odm/pc/js/esmp_base.js`、`https://o2o.unee.com.cn/web-odm/pc/html/communityActivity/js/common.js`、`https://o2o.unee.com.cn/web-odm/pc/js/progressbar/custom_progressbar.js`、`https://o2o.unee.com.cn/web-odm/pc/js/niceValidator/local/zh_CN.js`、`https://o2o.unee.com.cn/web-odm/pc/js/viewerjs/viewer.js`、`https://o2o.unee.com.cn/web-odm/pc/html/communityActivity/js/viewer_default.js`、`https://o2o.unee.com.cn/web-odm/pc/html/communityActivity/js/communityActivityList.js`。

同一页面加载步骤内观察到的请求：

| 方法 | 路径 | HTTP | 查询参数名 | 请求体参数名 | Evidence |
| --- | --- | --- | --- | --- | --- |
| POST | /web-common/common/systemUserOrg | 200 | system_user_id | findPath | ev_c4d4036bc65a408c8041f833ce8889a39169173452dd7d6ae2a6a106c5d2ca2b |
| POST | /web-common/common/systemDataPermission | 200 | system_user_id, type | findPath | ev_c4d4036bc65a408c8041f833ce8889a39169173452dd7d6ae2a6a106c5d2ca2b |

静态 AJAX 地址候选，存在于页面或关联脚本，未据此证明业务动作执行：
- `https://o2o.unee.com.cn/web-odm/pc/js/viewerjs/viewer.js`：`src`。
- `https://o2o.unee.com.cn/web-odm/pc/html/communityActivity/js/viewer_default.js`：`data-original`。
- `https://o2o.unee.com.cn/web-odm/pc/js/ligerUI/js/ligerui.all.js`：`...`。
- `https://o2o.unee.com.cn/web-odm/pc/html/communityActivity/js/communityActivityList.js`：`/web-odm/pc/qry_community_activity_list`、`/web-bus/advertising/addQrCode`、`/web-odm/pc/undercarriage`、`/web-odm/pc/isTop`、`/web-odm/pc/isNotTop`。

## 报表管理 装修信息报表

路由 `/web-report/pc/html/fitmentMsgReport/index.html`。菜单来源 `ev_25226ae15c591aa25247b4d7ef5e89e5ddd4162209de1bcb9259a6a2f7d462cc`。

页面字段：yearId、year_id、quarter_name、monthId、start_time、end_time。

页面按钮：查询、导出。

关联脚本中的静态表头候选：+(item.state==、+v+、序号、平台公司、城市公司、服务中心、装修户数、正在装修、未开始、已完成、巡查天数、巡查次数、巡查周数、巡查频次（周）、巡查工作量、一般违规数、一般违规已整改数、一般违规整改率、严重违规数、严重违规已整改数、严重违规整改率、违规发函数。共享脚本候选可能属于其他路由。

页面证据：
- `ev_9049e649478b51750b2f229948baf3cd299a931299e31a494686e3395de48951`，事务 `request-443`，响应摘要 `5f53c6480119334bd189f36bbd7e34887ad9854aab9924f31bc824db3b479eec`，HTTP 200。

前端脚本：
已捕获 13 个关联脚本，地址和摘要见 JSON。业务脚本包括：`https://o2o.unee.com.cn/web-report/pc/js/common.js`、`https://o2o.unee.com.cn/web-report/pc/js/niceValidator/local/zh_CN.js`、`https://o2o.unee.com.cn/web-report/pc/html/fitmentMsgReport/js/resetTableHeight.js`、`https://o2o.unee.com.cn/web-report/pc/html/fitmentMsgReport/js/toast.js`、`https://o2o.unee.com.cn/web-report/pc/html/fitmentMsgReport/js/select.js`、`https://o2o.unee.com.cn/web-report/pc/html/fitmentMsgReport/js/index.js`、`https://o2o.unee.com.cn/web-report/pc/html/fitmentMsgReport/js/virtual-select.min.js`。

同一页面加载步骤内观察到的请求：

| 方法 | 路径 | HTTP | 查询参数名 | 请求体参数名 | Evidence |
| --- | --- | --- | --- | --- | --- |
| POST | /web-common/list/queryOrgList | 200 |  | userId | ev_9049e649478b51750b2f229948baf3cd299a931299e31a494686e3395de48951 |
| POST | /web-common/list/queryRegionalList | 200 |  | orgIds, userId | ev_9049e649478b51750b2f229948baf3cd299a931299e31a494686e3395de48951 |
| POST | /web-common/list/queryServiceList | 200 |  | orgIds, regionalIds, userId | ev_9049e649478b51750b2f229948baf3cd299a931299e31a494686e3395de48951 |

静态 AJAX 地址候选，存在于页面或关联脚本，未据此证明业务动作执行：
- `https://o2o.unee.com.cn/web-report/pc/js/ligerUI/js/ligerui.all.js`：`...`。
- `https://o2o.unee.com.cn/web-report/pc/html/fitmentMsgReport/js/index.js`：`/web-report/timingTask/reportDecorationInformationReport/queryDecorationInformationReport`。

## 客户服务 工作计划

路由 `/web-cust/pc/html/workPlan/workPlanList.html`。菜单来源 `ev_25226ae15c591aa25247b4d7ef5e89e5ddd4162209de1bcb9259a6a2f7d462cc`。

菜单定义的操作：进度列表、评论、评价、修改、新增、导入、导出、二维码下载、查询。这些是菜单权限定义，不代表流程已执行验证。

页面字段：org_name、service_name、plan_type_name、work_plan_name、person_liable_name、start_time、end_time、status_name。

页面按钮：查询。

关联脚本中的静态表头候选：城市公司、服务中心、计划分类、工作计划名称、责任人、附件、计划开始时间、计划结束时间、实际结束时间、责任人评分、关注数、浏览数、点赞数、状态、二维码、操作。共享脚本候选可能属于其他路由。

该加载阶段存在失败或 HTTP 错误资源：`/web-cust/pc/js/niceValidator/style.css` net::ERR_ABORTED。页面关闭可能中断请求，需重新观察其影响。

页面证据：
- `ev_f2631a7dc031a549a87680b1e2affa1a088efdd842c289a316e649c9749ad8e0`，事务 `request-475`，响应摘要 `9d61883154754af0a042f710ec1cb5b97ad3ba94652751ff8caaba3ec0946de7`，HTTP 200。

前端脚本：
已捕获 15 个关联脚本，地址和摘要见 JSON。业务脚本包括：`https://o2o.unee.com.cn/web-cust/pc/js/common.js`、`https://o2o.unee.com.cn/web-cust/pc/js/progressbar/custom_progressbar.js`、`https://o2o.unee.com.cn/web-cust/pc/html/workPlan/js/workPlanList.js`、`https://o2o.unee.com.cn/web-cust/pc/js/viewerjs/viewer.js`、`https://o2o.unee.com.cn/web-cust/pc/html/workPlan/js/viewer_default.js`、`https://o2o.unee.com.cn/web-cust/pc/js/niceValidator/local/zh_CN.js`、`https://o2o.unee.com.cn/web-cust/pc/js/niceValidator/local/zh_CN.js`。

同一页面加载步骤内观察到的请求：

| 方法 | 路径 | HTTP | 查询参数名 | 请求体参数名 | Evidence |
| --- | --- | --- | --- | --- | --- |
| POST | /web-common/common/systemUserOrg | 200 | system_user_id | findPath | ev_f2631a7dc031a549a87680b1e2affa1a088efdd842c289a316e649c9749ad8e0 |
| POST | /web-common/common/systemDataPermission | 200 | system_user_id, type | findPath | ev_f2631a7dc031a549a87680b1e2affa1a088efdd842c289a316e649c9749ad8e0 |
| POST | /web-common/common/sysConfigQueryRest | 200 |  | column_name, table_name | ev_f2631a7dc031a549a87680b1e2affa1a088efdd842c289a316e649c9749ad8e0 |

静态 AJAX 地址候选，存在于页面或关联脚本，未据此证明业务动作执行：
- `https://o2o.unee.com.cn/web-cust/pc/html/workPlan/js/workPlanList.js`：`/web-cust/pc/workPlan/queryWorkPlanList`。
- `https://o2o.unee.com.cn/web-cust/pc/html/workPlan/js/viewer_default.js`：`data-original`。
- `https://o2o.unee.com.cn/web-cust/pc/html/workPlan/js/ligerui.all.js`：`...`。

## 配置管理 抵扣券导入

路由 `/web-cust/pc/html/deductionVoucher/deductionVoucherList.html`。菜单来源 `ev_25226ae15c591aa25247b4d7ef5e89e5ddd4162209de1bcb9259a6a2f7d462cc`。

菜单定义的操作：模板下载、导入、导出、启用、查询。这些是菜单权限定义，不代表流程已执行验证。

页面字段：fields_name、fields_value、org_name。

页面按钮：查询、批量导入、导出、启用、解锁。

关联脚本中的静态表头候选：城市公司、第三方企业、兑换券码、金额、导入时间、状态。共享脚本候选可能属于其他路由。

该加载阶段存在失败或 HTTP 错误资源：`/web-cust/pc/js/artDialog/images/plugins/artdialog/loading.gif` 404。页面关闭可能中断请求，需重新观察其影响。

页面证据：
- `ev_c590a872a43fe0d5c14d31c18cdcb66b904bb81b4e05b852730bf8dceb6eea00`，事务 `request-518`，响应摘要 `aafd80eed8e418e0bd8fa4559fd43e40b99f80f791dbda8312a0d9a493fef856`，HTTP 200。

前端脚本：
已捕获 14 个关联脚本，地址和摘要见 JSON。业务脚本包括：`https://o2o.unee.com.cn/web-cust/pc/js/common.js`、`https://o2o.unee.com.cn/web-cust/pc/js/progressbar/custom_progressbar.js`、`https://o2o.unee.com.cn/web-cust/pc/js/niceValidator/local/zh_CN.js`、`https://o2o.unee.com.cn/web-cust/pc/js/niceValidator/local/zh_CN.js`、`https://o2o.unee.com.cn/web-cust/pc/html/deductionVoucher/js/deductionVoucherList.js`。

同一页面加载步骤内观察到的请求：

| 方法 | 路径 | HTTP | 查询参数名 | 请求体参数名 | Evidence |
| --- | --- | --- | --- | --- | --- |
| POST | /web-cust/deductionVoucher/selectList | 200 |  | org_name, page, pageSize, pagesize, startNum, status, third_enterprise | ev_c590a872a43fe0d5c14d31c18cdcb66b904bb81b4e05b852730bf8dceb6eea00 |

静态 AJAX 地址候选，存在于页面或关联脚本，未据此证明业务动作执行：
- `https://o2o.unee.com.cn/web-cust/pc/js/ligerUI/js/ligerui.all.js`：`...`。

## 报表管理 装修户巡查动态报表

路由 `/web-report/pc/html/activeReport/index.html`。菜单来源 `ev_25226ae15c591aa25247b4d7ef5e89e5ddd4162209de1bcb9259a6a2f7d462cc`。

页面字段：hourse_name、start_time。

页面按钮：查询、导出。

关联脚本中的静态表头候选：+(item.state==、+v+、已整改问题数、跟进问题数、违规发函单数、序号、平台公司、城市公司、服务中心、楼栋单元、房号、房产名称、装修状态、装修开始时间、申报装修结束时间、实际装修完成时间、巡查次数、巡查周数、巡查频次（周）。共享脚本候选可能属于其他路由。

页面证据：
- `ev_9049e649478b51750b2f229948baf3cd299a931299e31a494686e3395de48951`，事务 `request-494`，响应摘要 `d2b29b5ebe3d547ffdd4c144d522ee62b04209d9e63e6f39afb12faba19dcb2a`，HTTP 200。

前端脚本：
已捕获 15 个关联脚本，地址和摘要见 JSON。业务脚本包括：`https://o2o.unee.com.cn/web-report/pc/js/common.js`、`https://o2o.unee.com.cn/web-report/pc/js/niceValidator/local/zh_CN.js`、`https://o2o.unee.com.cn/web-report/pc/html/employeeEvaluationStatement/js/resetTableHeight.js`、`https://o2o.unee.com.cn/web-report/pc/html/activeReport/js/toast.js`、`https://o2o.unee.com.cn/web-report/pc/html/activeReport/js/select.js`、`https://o2o.unee.com.cn/web-report/pc/html/activeReport/js/resetTableHeight.js`、`https://o2o.unee.com.cn/web-report/pc/html/activeReport/js/index.js`、`https://o2o.unee.com.cn/web-report/pc/js/virtual-select.min.js`。

同一页面加载步骤内观察到的请求：

| 方法 | 路径 | HTTP | 查询参数名 | 请求体参数名 | Evidence |
| --- | --- | --- | --- | --- | --- |
| POST | /web-common/list/queryOrgList | 200 |  | userId | ev_9049e649478b51750b2f229948baf3cd299a931299e31a494686e3395de48951 |
| POST | /web-common/list/queryRegionalList | 200 |  | orgIds, userId | ev_9049e649478b51750b2f229948baf3cd299a931299e31a494686e3395de48951 |
| POST | /web-common/list/queryServiceList | 200 |  | orgIds, regionalIds, userId | ev_9049e649478b51750b2f229948baf3cd299a931299e31a494686e3395de48951 |
| POST | /web-common/list/queryBuildList | 200 |  | serviceIds | ev_9049e649478b51750b2f229948baf3cd299a931299e31a494686e3395de48951 |

静态 AJAX 地址候选，存在于页面或关联脚本，未据此证明业务动作执行：
- `https://o2o.unee.com.cn/web-report/pc/js/ligerUI/js/ligerui.all.js`：`...`。
- `https://o2o.unee.com.cn/web-report/pc/html/activeReport/js/index.js`：`/web-report/timingTask/decorationPatrolDynamicReport/queryDecorationPatrolDynamicReport`。

## 客户服务 邻里社交

路由 `/web-odm/pc/html/neighbourSocial/neighbourSocialList.html`。菜单来源 `ev_25226ae15c591aa25247b4d7ef5e89e5ddd4162209de1bcb9259a6a2f7d462cc`。

菜单定义的操作：置顶、隐藏、删除、查询。这些是菜单权限定义，不代表流程已执行验证。

页面字段：org_name、service_name、social_type_name、reply_flag_name、social_content。

页面按钮：导出、置顶、加精、隐藏、删除、查询。

关联脚本中的静态表头候选：公司、服务中心、昵称、客户、联系电话、社交类型、邻里社交内容、点赞数、评论数、状态。共享脚本候选可能属于其他路由。

该加载阶段存在失败或 HTTP 错误资源：`/web-odm/pc/js/artDialog/images/plugins/artdialog/loading.gif` 404。页面关闭可能中断请求，需重新观察其影响。

页面证据：
- `ev_f2631a7dc031a549a87680b1e2affa1a088efdd842c289a316e649c9749ad8e0`，事务 `request-531`，响应摘要 `9ee1b375075e3acd8ccb1703d3af995c8c14de7b0597875384fd0fc76533b2c8`，HTTP 200。

前端脚本：
已捕获 13 个关联脚本，地址和摘要见 JSON。业务脚本包括：`https://o2o.unee.com.cn/web-odm/pc/js/common.js`、`https://o2o.unee.com.cn/web-odm/pc/js/progressbar/custom_progressbar.js`、`https://o2o.unee.com.cn/web-odm/pc/html/neighbourSocial/js/resetTableHeight.js`、`https://o2o.unee.com.cn/web-odm/pc/js/niceValidator/local/zh_CN.js`、`https://o2o.unee.com.cn/web-odm/pc/html/neighbourSocial/js/neighbourSocialList1.js`。

同一页面加载步骤内观察到的请求：

| 方法 | 路径 | HTTP | 查询参数名 | 请求体参数名 | Evidence |
| --- | --- | --- | --- | --- | --- |
| POST | /web-common/common/systemUserOrg | 200 | system_user_id | findPath | ev_f2631a7dc031a549a87680b1e2affa1a088efdd842c289a316e649c9749ad8e0 |
| POST | /web-common/common/systemDataPermission | 200 | system_user_id, type | findPath | ev_f2631a7dc031a549a87680b1e2affa1a088efdd842c289a316e649c9749ad8e0 |
| POST | /web-common/common/sysConfigQueryRest | 200 |  | column_name, table_name | ev_f2631a7dc031a549a87680b1e2affa1a088efdd842c289a316e649c9749ad8e0 |

静态 AJAX 地址候选，存在于页面或关联脚本，未据此证明业务动作执行：
- `https://o2o.unee.com.cn/web-odm/pc/js/ligerUI/js/ligerui.all.js`：`...`。
- `https://o2o.unee.com.cn/web-odm/pc/html/neighbourSocial/js/neighbourSocialList1.js`：`/web-odm/pc/qry_neighbour_social_list`。

## 配置管理 报告台岗位管理

路由 `/web-cust/pc/html/report/postPoolList.html`。菜单来源 `ev_25226ae15c591aa25247b4d7ef5e89e5ddd4162209de1bcb9259a6a2f7d462cc`。

菜单定义的操作：新增、删除、编辑、查询。这些是菜单权限定义，不代表流程已执行验证。

页面字段：post_name。

页面按钮：查询、新增、删除。

关联脚本中的静态表头候选：岗位名称、岗位职责描述、备注、引用项目数量、操作。共享脚本候选可能属于其他路由。

页面证据：
- `ev_c590a872a43fe0d5c14d31c18cdcb66b904bb81b4e05b852730bf8dceb6eea00`，事务 `request-567`，响应摘要 `d1a9e1ced3ff5c47ce0e6b6e80f47cd134f95d3a07aa37504761716ff4a16c8a`，HTTP 200。

前端脚本：
已捕获 12 个关联脚本，地址和摘要见 JSON。业务脚本包括：`https://o2o.unee.com.cn/web-cust/pc/js/common.js`、`https://o2o.unee.com.cn/web-cust/pc/js/progressbar/custom_progressbar.js`、`https://o2o.unee.com.cn/web-cust/pc/js/niceValidator/local/zh_CN.js`、`https://o2o.unee.com.cn/web-cust/pc/js/niceValidator/local/zh_CN.js`、`https://o2o.unee.com.cn/web-cust/pc/html/report/js/postPoolList.js`。

同一页面加载步骤内观察到的请求：

| 方法 | 路径 | HTTP | 查询参数名 | 请求体参数名 | Evidence |
| --- | --- | --- | --- | --- | --- |
| POST | /web-cust/postPool/selectList | 200 |  | page, pageSize, pagesize, post_name, startNum | ev_c590a872a43fe0d5c14d31c18cdcb66b904bb81b4e05b852730bf8dceb6eea00 |

静态 AJAX 地址候选，存在于页面或关联脚本，未据此证明业务动作执行：
- `https://o2o.unee.com.cn/web-cust/pc/js/ligerUI/js/ligerui.all.js`：`...`。

## 统计中心 活跃度统计报表

路由 `/web-cust/pc/html/activationForOrg/activationForOrg.html`。菜单来源 `ev_25226ae15c591aa25247b4d7ef5e89e5ddd4162209de1bcb9259a6a2f7d462cc`。

菜单定义的操作：查询。这些是菜单权限定义，不代表流程已执行验证。

页面字段：start_time、end_time。

页面按钮：查询、导出。

关联脚本中的静态表头候选：+(item.state==、+v+、城市公司、活跃人数、注册用户数、活跃度。共享脚本候选可能属于其他路由。

该加载阶段存在失败或 HTTP 错误资源：`/web-cust/pc/js/artDialog/images/plugins/artdialog/loading.gif` 404。页面关闭可能中断请求，需重新观察其影响。

页面证据：
- `ev_09a45f0a06a75d1316e52ebd6f6fa25316e841f7362f861659f9969d3c364feb`，事务 `request-481`，响应摘要 `e395c2d44292b088bb585c6b6e46c3de42035ae387b8ad1772a256d8aaea3d3b`，HTTP 200。

前端脚本：
已捕获 15 个关联脚本，地址和摘要见 JSON。业务脚本包括：`https://o2o.unee.com.cn/web-cust/pc/js/common.js`、`https://o2o.unee.com.cn/web-cust/pc/js/progressbar/custom_progressbar.js`、`https://o2o.unee.com.cn/web-cust/pc/js/niceValidator/local/zh_CN.js`、`https://o2o.unee.com.cn/web-cust/pc/js/niceValidator/local/zh_CN.js`、`https://o2o.unee.com.cn/web-cust/pc/html/activationForOrg/js/resetTableHeight.js`、`https://o2o.unee.com.cn/web-cust/pc/html/activationForOrg/js/activationForOrg.js`。

同一页面加载步骤内观察到的请求：

| 方法 | 路径 | HTTP | 查询参数名 | 请求体参数名 | Evidence |
| --- | --- | --- | --- | --- | --- |
| POST | /web-common/common/systemUserOrgIncrease | 200 | type, system_user_id | not_exposed | ev_09a45f0a06a75d1316e52ebd6f6fa25316e841f7362f861659f9969d3c364feb |

静态 AJAX 地址候选，存在于页面或关联脚本，未据此证明业务动作执行：
- `https://o2o.unee.com.cn/web-cust/pc/js/ligerUI/js/ligerui.all.js`：`...`。
- `https://o2o.unee.com.cn/web-cust/pc/html/activationForOrg/js/activationForOrg.js`：`/web-cust/activationForOrg.do`。

## 配置管理 报告台基础配置管理

路由 `/web-cust/pc/html/report/baseConfigList.html`。菜单来源 `ev_25226ae15c591aa25247b4d7ef5e89e5ddd4162209de1bcb9259a6a2f7d462cc`。

菜单定义的操作：新增、删除、岗位详情、述职报告、启动测评、查询。这些是菜单权限定义，不代表流程已执行验证。

页面按钮：查询、新增。

关联脚本中的静态表头候选：平台公司、城市公司、项目、岗位数量、创建时间、测评状态、操作。共享脚本候选可能属于其他路由。

该加载阶段存在失败或 HTTP 错误资源：`/web-cust/pc/css/jquery.autocomplete.css` net::ERR_ABORTED、`/web-cust/pc/js/niceValidator/style.css` net::ERR_ABORTED、`/web-cust/pc/js/ligerUI/skins/ligerui-icons.css` net::ERR_ABORTED。页面关闭可能中断请求，需重新观察其影响。

页面证据：
- `ev_c590a872a43fe0d5c14d31c18cdcb66b904bb81b4e05b852730bf8dceb6eea00`，事务 `request-614`，响应摘要 `106a7886362fa33997ba609de6775fca1471f0332fe555c506923d833673ad10`，HTTP 200。

前端脚本：
已捕获 12 个关联脚本，地址和摘要见 JSON。业务脚本包括：`https://o2o.unee.com.cn/web-cust/pc/js/common.js`、`https://o2o.unee.com.cn/web-cust/pc/js/progressbar/custom_progressbar.js`、`https://o2o.unee.com.cn/web-cust/pc/js/niceValidator/local/zh_CN.js`、`https://o2o.unee.com.cn/web-cust/pc/js/niceValidator/local/zh_CN.js`、`https://o2o.unee.com.cn/web-cust/pc/html/report/js/baseConfigList.js`。

同一页面加载步骤内观察到的请求：

| 方法 | 路径 | HTTP | 查询参数名 | 请求体参数名 | Evidence |
| --- | --- | --- | --- | --- | --- |
| POST | /web-common/common/systemUserOrg | 200 | system_user_id | not_exposed | ev_c590a872a43fe0d5c14d31c18cdcb66b904bb81b4e05b852730bf8dceb6eea00 |
| POST | /web-common/common/systemUserArea | 200 | system_user_id | org_ids | ev_c590a872a43fe0d5c14d31c18cdcb66b904bb81b4e05b852730bf8dceb6eea00 |
| POST | /web-common/common/systemDataPermission | 200 | system_user_id, org_id, area_id | not_exposed | ev_c590a872a43fe0d5c14d31c18cdcb66b904bb81b4e05b852730bf8dceb6eea00 |

静态 AJAX 地址候选，存在于页面或关联脚本，未据此证明业务动作执行：
- `https://o2o.unee.com.cn/web-cust/pc/js/ligerUI/js/ligerui.all.js`：`...`。

## 客户服务 意见反馈

路由 `/web-seo/pc/html/feedbackInfo/feedbackInfoList.html`。菜单来源 `ev_25226ae15c591aa25247b4d7ef5e89e5ddd4162209de1bcb9259a6a2f7d462cc`。

菜单定义的操作：查询、导出。这些是菜单权限定义，不代表流程已执行验证。

页面字段：org_name、service_name、feedback_type_name、user_type_name、start_time、end_time、feedback_coment。

页面按钮：查询。

关联脚本中的静态表头候选：城市公司、服务中心、反馈意见、意见类型、反馈渠道、用户名称、联系电话、提交时间、操作。共享脚本候选可能属于其他路由。

页面证据：
- `ev_f2631a7dc031a549a87680b1e2affa1a088efdd842c289a316e649c9749ad8e0`，事务 `request-580`，响应摘要 `abfd828fe90b89e45eb964cdea1a70a725b41a2c081909c52cb8298892c4c71e`，HTTP 200。

前端脚本：
已捕获 11 个关联脚本，地址和摘要见 JSON。业务脚本包括：`https://o2o.unee.com.cn/web-seo/pc/html/feedbackInfo/js/common.js`、`https://o2o.unee.com.cn/web-seo/pc/js/progressbar/custom_progressbar.js`、`https://o2o.unee.com.cn/web-seo/pc/js/niceValidator/local/zh_CN.js`、`https://o2o.unee.com.cn/web-seo/pc/html/feedbackInfo/js/feedbackInfoList.js`。

同一页面加载步骤内观察到的请求：

| 方法 | 路径 | HTTP | 查询参数名 | 请求体参数名 | Evidence |
| --- | --- | --- | --- | --- | --- |
| POST | /web-common/common/sysConfigQueryRest | 200 |  | code_type, column_name, table_name | ev_f2631a7dc031a549a87680b1e2affa1a088efdd842c289a316e649c9749ad8e0 |
| POST | /web-common/common/systemUserOrg | 200 | system_user_id | findPath | ev_f2631a7dc031a549a87680b1e2affa1a088efdd842c289a316e649c9749ad8e0 |
| POST | /web-common/common/systemDataPermission | 200 | system_user_id, type | findPath | ev_f2631a7dc031a549a87680b1e2affa1a088efdd842c289a316e649c9749ad8e0 |

静态 AJAX 地址候选，存在于页面或关联脚本，未据此证明业务动作执行：
- `https://o2o.unee.com.cn/web-seo/pc/js/ligerUI/js/ligerui.all.js`：`...`。
- `https://o2o.unee.com.cn/web-seo/pc/html/feedbackInfo/js/feedbackInfoList.js`：`/web-seo/pc/feedbackInfoList`。

## 配置管理 质检员点位管理

路由 `/web-cust/pc/html/inspectionManagement/inspeConfList.html`。菜单来源 `ev_25226ae15c591aa25247b4d7ef5e89e5ddd4162209de1bcb9259a6a2f7d462cc`。

菜单定义的操作：新增、修改、删除。这些是菜单权限定义，不代表流程已执行验证。

页面字段：org_name、area_name、service_name、status_name。

页面按钮：查询。

关联脚本中的静态表头候选：平台公司、城市、服务中心、质检类型、点位名称、操作、状态。共享脚本候选可能属于其他路由。

页面证据：
- `ev_c590a872a43fe0d5c14d31c18cdcb66b904bb81b4e05b852730bf8dceb6eea00`，事务 `request-665`，响应摘要 `35d303f348ae6a18b329d01faa9cb040a12d5e7e410002ea3b34ba9262e2984f`，HTTP 200。

前端脚本：
已捕获 16 个关联脚本，地址和摘要见 JSON。业务脚本包括：`https://o2o.unee.com.cn/web-cust/pc/js/esmp_base.js`、`https://o2o.unee.com.cn/web-cust/pc/js/esmp_base.js`、`https://o2o.unee.com.cn/web-cust/pc/html/inspectionManagement/js/inspectionCommon.js`、`https://o2o.unee.com.cn/web-cust/pc/html/work/js/dateFormat.js`、`https://o2o.unee.com.cn/web-cust/pc/html/work/js/dateFormat.js`、`https://o2o.unee.com.cn/web-cust/pc/html/work/js/resetTableHeight.js`、`https://o2o.unee.com.cn/web-cust/pc/html/work/js/resetTableHeight.js`、`https://o2o.unee.com.cn/web-cust/pc/html/inspectionManagement/js/inspeConfList.js`、`https://o2o.unee.com.cn/web-cust/pc/js/niceValidator/local/zh_CN.js`、`https://o2o.unee.com.cn/web-cust/pc/js/niceValidator/local/zh_CN.js`。

同一页面加载步骤内观察到的请求：

| 方法 | 路径 | HTTP | 查询参数名 | 请求体参数名 | Evidence |
| --- | --- | --- | --- | --- | --- |
| POST | /web-common/common/systemUserOrg | 200 | system_user_id | findPath | ev_c590a872a43fe0d5c14d31c18cdcb66b904bb81b4e05b852730bf8dceb6eea00 |

静态 AJAX 地址候选，存在于页面或关联脚本，未据此证明业务动作执行：
- `https://o2o.unee.com.cn/web-cust/pc/html/inspectionManagement/js/inspectionCommon.js`：`/web-cust/pc/inspection/queryServicesByAreaId`。
- `https://o2o.unee.com.cn/web-cust/pc/html/inspectionManagement/js/inspeConfList.js`：`/web-cust/pc/inspection/confList`、`/web-cust/pc/inspection/deleteInspectionById`、`/web-cust/pc/inspection/invalidInspectionById`。
- `https://o2o.unee.com.cn/web-cust/pc/js/ligerUI/js/ligerui.all.js`：`...`。

## 综合查询 活动

路由 `/web-odm/pc/html/groupBusiness/activityList.html`。菜单来源 `ev_25226ae15c591aa25247b4d7ef5e89e5ddd4162209de1bcb9259a6a2f7d462cc`。

菜单定义的操作：查看、查询。这些是菜单权限定义，不代表流程已执行验证。

页面字段：distribution_mode_name、business_order_status_name、field_value。

页面按钮：作废、成团、查询、列设置。

关联脚本中的静态表头候选：序号、团购名称、生效时间、失效时间、成团状态、配送方式、订单总额、订单总数、未发单、订单批数、售后订单数、投诉、团购状态、活动名称、活动状态。共享脚本候选可能属于其他路由。

该加载阶段存在失败或 HTTP 错误资源：`/web-odm/pc/js/artDialog/images/plugins/artdialog/loading.gif` 404。页面关闭可能中断请求，需重新观察其影响。

页面证据：
- `ev_38947e25f18f5c3530edafcc8a81c9e535540d7a35a161748e64dc800d952267`，事务 `request-511`，响应摘要 `909960e4c49219b1666d137a66f94311c61532f28964e304b8fd1b1dd5dd530d`，HTTP 200。

前端脚本：
已捕获 14 个关联脚本，地址和摘要见 JSON。业务脚本包括：`https://o2o.unee.com.cn/web-odm/pc/js/common.js`、`https://o2o.unee.com.cn/web-odm/pc/js/table/custom_table.js`、`https://o2o.unee.com.cn/web-odm/pc/js/progressbar/custom_progressbar.js`、`https://o2o.unee.com.cn/web-odm/pc/js/niceValidator/local/zh_CN.js`、`https://o2o.unee.com.cn/web-odm/pc/html/groupBusiness/js/gbList.js`、`https://o2o.unee.com.cn/web-odm/pc/html/groupBusiness/js/resetTableHeight.js`。

同一页面加载步骤内观察到的请求：

| 方法 | 路径 | HTTP | 查询参数名 | 请求体参数名 | Evidence |
| --- | --- | --- | --- | --- | --- |
| POST | /web-common/common/sysConfigQueryRest | 200 |  | column_name, table_name | ev_38947e25f18f5c3530edafcc8a81c9e535540d7a35a161748e64dc800d952267 |
| POST | /web-odm/groupBusiness/queryGroupBusinessList | 200 |  | business_order_status_cd, business_type_cd, distribution_mode_cd, field_value, group_status_cd, page, pageMap, pageSize, pagesize, startNum | ev_38947e25f18f5c3530edafcc8a81c9e535540d7a35a161748e64dc800d952267 |
| POST | /web-bus/getPushMessage/6520159 | 200 |  | not_exposed | ev_38947e25f18f5c3530edafcc8a81c9e535540d7a35a161748e64dc800d952267 |

静态 AJAX 地址候选，存在于页面或关联脚本，未据此证明业务动作执行：
- `https://o2o.unee.com.cn/web-odm/pc/js/ligerUI/js/ligerui.all.js`：`...`。
- `https://o2o.unee.com.cn/web-odm/pc/html/groupBusiness/js/gbList.js`：`/web-odm/pc/queryBussOrderCount.json`、`/web-odm/pc/updateBussGroupStatus.json`、`/web-odm/pc/updateBussOrderStatusCance.json`。

## 运营中心 议事大厅

路由 `/web-cust/pc/html/discuss/discuss_list.html`。菜单来源 `ev_25226ae15c591aa25247b4d7ef5e89e5ddd4162209de1bcb9259a6a2f7d462cc`。

菜单定义的操作：导出、评论、投票结果、置顶、二维码下载、查询。这些是菜单权限定义，不代表流程已执行验证。

页面字段：org_name、service_name、status_name、discuss_type_name、create_user_client_name、start_time、end_time、discussName。

页面按钮：查询、导出、新增、项目二维码、二维码下载。

关联脚本中的静态表头候选：城市公司、城市、议事名称、发起方、渠道来源、归属组织、议事类型、投票结果、发起时间、发起人、关注数、浏览数、点赞数、状态、二维码、操作。共享脚本候选可能属于其他路由。

该加载阶段存在失败或 HTTP 错误资源：`/web-cust/pc/js/artDialog/images/plugins/artdialog/loading.gif` 404。页面关闭可能中断请求，需重新观察其影响。

页面证据：
- `ev_c4d4036bc65a408c8041f833ce8889a39169173452dd7d6ae2a6a106c5d2ca2b`，事务 `request-371`，响应摘要 `14d5d403d77e4c5953da8524af6ce6b78d40d1f4afc6ea6d20ce0db64421caa3`，HTTP 200。

前端脚本：
已捕获 16 个关联脚本，地址和摘要见 JSON。业务脚本包括：`https://o2o.unee.com.cn/web-cust/pc/html/discuss/js/common.js`、`https://o2o.unee.com.cn/web-cust/pc/html/work/js/dateFormat.js`、`https://o2o.unee.com.cn/web-cust/pc/html/work/js/dateFormat.js`、`https://o2o.unee.com.cn/web-cust/pc/js/niceValidator/local/zh_CN.js`、`https://o2o.unee.com.cn/web-cust/pc/js/niceValidator/local/zh_CN.js`、`https://o2o.unee.com.cn/web-cust/pc/js/viewerjs/viewer.js`、`https://o2o.unee.com.cn/web-cust/pc/html/discuss/js/viewer_default.js`、`https://o2o.unee.com.cn/web-cust/pc/html/discuss/js/discuss_list.js`。

同一页面加载步骤内观察到的请求：

| 方法 | 路径 | HTTP | 查询参数名 | 请求体参数名 | Evidence |
| --- | --- | --- | --- | --- | --- |
| POST | /web-common/common/systemUserOrg | 200 | system_user_id | findPath | ev_c4d4036bc65a408c8041f833ce8889a39169173452dd7d6ae2a6a106c5d2ca2b |
| POST | /web-common/common/systemDataPermission | 200 | system_user_id, type | findPath | ev_c4d4036bc65a408c8041f833ce8889a39169173452dd7d6ae2a6a106c5d2ca2b |
| POST | /web-cust/pc/discuss/checkUserPriv | 200 |  | methodType, system_user_id, userType | ev_c4d4036bc65a408c8041f833ce8889a39169173452dd7d6ae2a6a106c5d2ca2b |
| POST | /web-bus/getPushMessage/6520159 | 200 |  | not_exposed | ev_c4d4036bc65a408c8041f833ce8889a39169173452dd7d6ae2a6a106c5d2ca2b |

静态 AJAX 地址候选，存在于页面或关联脚本，未据此证明业务动作执行：
- `https://o2o.unee.com.cn/web-cust/pc/js/ligerUI/js/ligerui.all.js`：`...`。
- `https://o2o.unee.com.cn/web-cust/pc/js/viewerjs/viewer.js`：`src`。
- `https://o2o.unee.com.cn/web-cust/pc/html/discuss/js/viewer_default.js`：`data-original`。
- `https://o2o.unee.com.cn/web-cust/pc/html/discuss/js/discuss_list.js`：`/web-cust/pc/discuss/checkUserPriv`、`/web-cust/pc/discuss/queryDiscussList`、`/web-cust/pc/discuss/makeQrCode`、`/web-cust/pc/discuss/queryDiscussStatus`、`/web-cust/pc/discuss/updateDiscussStatus`、`/web-cust/pc/discuss/addCustSociality`。

## 综合查询 违约金减免清单

路由 `/web-seo/pc/html/liquidatedList/liquidatedList.html`。菜单来源 `ev_25226ae15c591aa25247b4d7ef5e89e5ddd4162209de1bcb9259a6a2f7d462cc`。

菜单定义的操作：导出、查询。这些是菜单权限定义，不代表流程已执行验证。

页面字段：org_name、service_name、start_time、end_time、staff_name、fields_type_name、fields_value、status_cd_name。

页面按钮：查询、导出。

关联脚本中的静态表头候选：服务中心、房产名称、申请人、申请时间、客户、账期、减免违约金（元）、未减免违约金（元）、已减免违约金（元）、账单本金（元）、状态、操作。共享脚本候选可能属于其他路由。

页面证据：
- `ev_38947e25f18f5c3530edafcc8a81c9e535540d7a35a161748e64dc800d952267`，事务 `request-563`，响应摘要 `ef337b6defb1adf6a053efc1ed0e71f896980bf747bed4f5356e937a36d2ca81`，HTTP 200。

前端脚本：
已捕获 13 个关联脚本，地址和摘要见 JSON。业务脚本包括：`https://o2o.unee.com.cn/web-seo/pc/html/liquidatedList/js/common.js`、`https://o2o.unee.com.cn/web-seo/pc/js/progressbar/custom_progressbar.js`、`https://o2o.unee.com.cn/web-seo/pc/js/niceValidator/local/zh_CN.js`、`https://o2o.unee.com.cn/web-seo/pc/html/liquidatedList/js/liquidatedList.js`。

同一页面加载步骤内观察到的请求：

| 方法 | 路径 | HTTP | 查询参数名 | 请求体参数名 | Evidence |
| --- | --- | --- | --- | --- | --- |
| POST | /web-common/common/systemUserOrg | 200 | system_user_id | findPath | ev_38947e25f18f5c3530edafcc8a81c9e535540d7a35a161748e64dc800d952267 |
| POST | /web-common/common/systemDataPermission | 200 | system_user_id | findPath | ev_38947e25f18f5c3530edafcc8a81c9e535540d7a35a161748e64dc800d952267 |

静态 AJAX 地址候选，存在于页面或关联脚本，未据此证明业务动作执行：
- `https://o2o.unee.com.cn/web-seo/pc/js/ligerUI/js/ligerui.all.js`：`...`。
- `https://o2o.unee.com.cn/web-seo/pc/html/liquidatedList/js/liquidatedList.js`：`/web-seo/pc/queryReduceLiquidatedDamageList`。

## 统计中心 品检追踪

路由 `/web-seo/pc/html/qualityProblemsTrack/index.html`。菜单来源 `ev_25226ae15c591aa25247b4d7ef5e89e5ddd4162209de1bcb9259a6a2f7d462cc`。

页面字段：work_type_name、task_status_name、task_timeout_name、task_source_name、start_time、end_time、fuzzyQuery。

页面按钮：查询、导出、批量作废。

关联脚本中的静态表头候选：问题编码、问题类型、问题描述、项目、业主认证比例、具体地点、任务来源、整改截止时间、当前处理人、状态、是否超时、操作。共享脚本候选可能属于其他路由。

页面运行错误：Cannot read properties of undefined (reading 'config')。错误与该加载步骤在时间上关联，未证明具体调用因果。

页面证据：
- `ev_09a45f0a06a75d1316e52ebd6f6fa25316e841f7362f861659f9969d3c364feb`，事务 `request-530`，响应摘要 `a294071be3a921dad4db40647e1a0e37b4c111d82f9924adec9eae77ab499fa7`，HTTP 200。

前端脚本：
已捕获 15 个关联脚本，地址和摘要见 JSON。业务脚本包括：`https://o2o.unee.com.cn/web-seo/pc/html/qualityProblemsTrack/js/common.js`、`https://o2o.unee.com.cn/web-seo/pc/html/qualityProblemsTrack/taskCommon.js`、`https://o2o.unee.com.cn/web-seo/pc/js/progressbar/custom_progressbar.js`、`https://o2o.unee.com.cn/web-seo/pc/js/niceValidator/local/zh_CN.js`、`https://o2o.unee.com.cn/web-seo/pc/html/qualityProblemsTrack/js/index.js`、`https://o2o.unee.com.cn/web-seo/pc/html/qualityProblemsTrack/js/virtual-select.min.js`。

同一页面加载步骤内观察到的请求：

| 方法 | 路径 | HTTP | 查询参数名 | 请求体参数名 | Evidence |
| --- | --- | --- | --- | --- | --- |
| POST | /web-common/list/queryOrgList | 200 |  | userId | ev_09a45f0a06a75d1316e52ebd6f6fa25316e841f7362f861659f9969d3c364feb |
| GET | /web-cust/mobile/qualityCheck/getOptions/CREATE | 200 |  | not_exposed | ev_09a45f0a06a75d1316e52ebd6f6fa25316e841f7362f861659f9969d3c364feb |
| POST | /web-common/list/queryRegionalList | 200 |  | orgIds, userId | ev_09a45f0a06a75d1316e52ebd6f6fa25316e841f7362f861659f9969d3c364feb |
| POST | /web-common/list/queryServiceList | 200 |  | orgIds, regionalIds, userId | ev_09a45f0a06a75d1316e52ebd6f6fa25316e841f7362f861659f9969d3c364feb |

静态 AJAX 地址候选，存在于页面或关联脚本，未据此证明业务动作执行：
- `https://o2o.unee.com.cn/web-seo/pc/js/ligerUI/js/ligerui.all.js`：`...`。
- `https://o2o.unee.com.cn/web-seo/pc/html/qualityProblemsTrack/js/index.js`：`/web-cust/pc/qualityCheck/getWorks`、`/web-cust/toDoTask/deleteWaitTask`。

## 统计中心 扫码评价运营报表

路由 `/web-seo/pc/html/CodeScanningEvaluationReport/codeEvaluationView.html`。菜单来源 `ev_25226ae15c591aa25247b4d7ef5e89e5ddd4162209de1bcb9259a6a2f7d462cc`。

页面字段：start_time、end_time。

页面按钮：查询、导出。

关联脚本中的静态表头候选：+(item.state==、+v+、序号、平台公司、项目总数、已上线项目数、已上线项目率、投放二维码数量、项目平均投放二维码数量、互动点位数。共享脚本候选可能属于其他路由。

页面证据：
- `ev_09a45f0a06a75d1316e52ebd6f6fa25316e841f7362f861659f9969d3c364feb`，事务 `request-584`，响应摘要 `976e89933b8ac289d82da2a74624e921f8e333ab97951a548dd6078166bb8af2`，HTTP 200。

前端脚本：
已捕获 11 个关联脚本，地址和摘要见 JSON。业务脚本包括：`https://o2o.unee.com.cn/web-seo/pc/js/common.js`、`https://o2o.unee.com.cn/web-seo/pc/js/niceValidator/local/zh_CN.js`、`https://o2o.unee.com.cn/web-seo/pc/html/CodeScanningEvaluationReport/js/resetTableHeight.js`、`https://o2o.unee.com.cn/web-seo/pc/html/CodeScanningEvaluationReport/js/codeEvaluationView.js`、`https://o2o.unee.com.cn/web-seo/pc/html/CodeScanningEvaluationReport/js/virtual-select.min.js`。

同一页面加载步骤内观察到的请求：

| 方法 | 路径 | HTTP | 查询参数名 | 请求体参数名 | Evidence |
| --- | --- | --- | --- | --- | --- |
| POST | /web-common/list/queryOrgList | 200 |  | userId | ev_09a45f0a06a75d1316e52ebd6f6fa25316e841f7362f861659f9969d3c364feb |

静态 AJAX 地址候选，存在于页面或关联脚本，未据此证明业务动作执行：
- `https://o2o.unee.com.cn/web-seo/pc/js/ligerUI/js/ligerui.all.js`：`...`。
- `https://o2o.unee.com.cn/web-seo/pc/html/CodeScanningEvaluationReport/js/codeEvaluationView.js`：`/web-seo/ScanQRCodeEvaluation/queryOperationsReportByOrg`。

## 客户服务 空置房申请

路由 `/web-bus/pc/html/vacantRoomApply/vacantRoomApplyPC.html`。菜单来源 `ev_25226ae15c591aa25247b4d7ef5e89e5ddd4162209de1bcb9259a6a2f7d462cc`。

菜单定义的操作：提交oa审核、空置房清单、取消空置、查看详情、申请查询、清单查询。这些是菜单权限定义，不代表流程已执行验证。

页面字段：org_name、service_name、status_name、start_time、end_time、extra_msg。

页面按钮：查询、空置期清单。

关联脚本中的静态表头候选：服务中心、房号、申请人姓名、申请人联系电话、申请身份、状态、申请时间、审批人、空置期、OA审核时间、OA审核状态、操作。共享脚本候选可能属于其他路由。

页面证据：
- `ev_f2631a7dc031a549a87680b1e2affa1a088efdd842c289a316e649c9749ad8e0`，事务 `request-628`，响应摘要 `b85a57cdf5bc585d9402a3a241f2bde1e614aa56d980ffe0ed5d5980189cd85d`，HTTP 200。

前端脚本：
已捕获 14 个关联脚本，地址和摘要见 JSON。业务脚本包括：`https://o2o.unee.com.cn/web-bus/pc/js/common.js`、`https://o2o.unee.com.cn/web-bus/pc/js/progressbar/custom_progressbar.js`、`https://o2o.unee.com.cn/web-bus/pc/js/niceValidator/local/zh_CN.js`、`https://o2o.unee.com.cn/web-bus/pc/html/vacantRoomApply/js/vacantRoomApplyPC.js`。

同一页面加载步骤内观察到的请求：

| 方法 | 路径 | HTTP | 查询参数名 | 请求体参数名 | Evidence |
| --- | --- | --- | --- | --- | --- |
| POST | /web-common/permission/common/systemUserOrg | 200 | system_user_id | findPath | ev_f2631a7dc031a549a87680b1e2affa1a088efdd842c289a316e649c9749ad8e0 |
| POST | /web-common/permission/common/systemDataPermission | 200 | system_user_id, type | findPath | ev_f2631a7dc031a549a87680b1e2affa1a088efdd842c289a316e649c9749ad8e0 |
| POST | /web-common/common/sysConfigQueryRest | 200 |  | column_name, table_name | ev_f2631a7dc031a549a87680b1e2affa1a088efdd842c289a316e649c9749ad8e0 |

静态 AJAX 地址候选，存在于页面或关联脚本，未据此证明业务动作执行：
- `https://o2o.unee.com.cn/web-bus/pc/js/ligerUI/js/ligerui.all.js`：`...`。
- `https://o2o.unee.com.cn/web-bus/pc/html/vacantRoomApply/js/vacantRoomApplyPC.js`：`/web-bus/pc/vacantRoomApplyByPC/getVacantRoomApplyList`。

## 报表管理 管家服务分析看板

路由 `/un-pc-fronted/#/formsManagement/wecomHousekeepBoard/index`。菜单来源 `ev_25226ae15c591aa25247b4d7ef5e89e5ddd4162209de1bcb9259a6a2f7d462cc`。

菜单定义的操作：催缴费金额统计导出。这些是菜单权限定义，不代表流程已执行验证。

这是 SPA 路由，REA 捕获的共享 HTML 壳和 bundle 不等于该路由完整界面。REA 静态解析没有恢复动态字段；以下独立浏览器观察补充了部分运行时界面结构。

补充界面观察 `UI-SPA-930915`，来源 [原始内置浏览器渲染 DOM](/Volumes/MOVESPEED/Projects/uni-rea/does/spa-ui-observations.json)；与 REA 专用 Chrome 是独立浏览器上下文。

动态控件占位符：开始日期、结束日期。

动态界面按钮：导 出。

该 DOM 观察没有取得图表指标和计算公式，指标口径仍未知。

页面运行错误：Cannot read properties of null (reading '1')。错误与该加载步骤在时间上关联，未证明具体调用因果。

该加载阶段存在失败或 HTTP 错误资源：`/web-wechat/analyse/board/v1/top` net::ERR_ABORTED、`/web-wechat/analyse/board/v1/getStewardWorkReport` net::ERR_ABORTED、`/web-wechat/analyse/board/v1/steward/charge` net::ERR_ABORTED。页面关闭可能中断请求，需重新观察其影响。

页面证据：
- `ev_9049e649478b51750b2f229948baf3cd299a931299e31a494686e3395de48951`，事务 `request-550`，响应摘要 `fb4004b266dc7cdab0c8eb0fbe54850f25894027bc46dcba4c6f1a8398da4918`，HTTP 200。
- `ev_9049e649478b51750b2f229948baf3cd299a931299e31a494686e3395de48951`，事务 `request-755`，响应摘要 `fb4004b266dc7cdab0c8eb0fbe54850f25894027bc46dcba4c6f1a8398da4918`，HTTP 200。
- `ev_9049e649478b51750b2f229948baf3cd299a931299e31a494686e3395de48951`，事务 `request-756`，响应摘要 `fb4004b266dc7cdab0c8eb0fbe54850f25894027bc46dcba4c6f1a8398da4918`，HTTP 200。

前端脚本：
已捕获 3 个关联脚本，地址和摘要见 JSON。业务脚本包括：`https://o2o.unee.com.cn/un-pc-fronted/less.min.js`、`https://o2o.unee.com.cn/un-pc-fronted/js/chunk-vendors.f0e6600a.js`、`https://o2o.unee.com.cn/un-pc-fronted/js/app.a069b50e.js`。

同一页面加载步骤内观察到的请求：

| 方法 | 路径 | HTTP | 查询参数名 | 请求体参数名 | Evidence |
| --- | --- | --- | --- | --- | --- |
| GET | /un-pc-fronted/ | 200 |  | not_exposed | ev_9049e649478b51750b2f229948baf3cd299a931299e31a494686e3395de48951 |
| POST | /cent-cust/userInfo/queryPCStaffInfo | 200 |  | not_exposed | ev_9049e649478b51750b2f229948baf3cd299a931299e31a494686e3395de48951 |
| POST | /web-common/list/organization/queryOrgList | 200 |  | userId | ev_9049e649478b51750b2f229948baf3cd299a931299e31a494686e3395de48951 |
| POST | /web-wechat/analyse/board/v1/top | None |  | captured | ev_9049e649478b51750b2f229948baf3cd299a931299e31a494686e3395de48951 |
| POST | /web-common/list/organization/queryRegionalList | 200 |  | orgIds, userId | ev_9049e649478b51750b2f229948baf3cd299a931299e31a494686e3395de48951 |
| POST | /web-common/list/organization/queryServiceList | 200 |  | orgIds, regionalIds, userId | ev_9049e649478b51750b2f229948baf3cd299a931299e31a494686e3395de48951 |
| POST | /web-wechat/analyse/board/v1/getStewardAccountAndCertify | 200 |  | serviceIds, type | ev_9049e649478b51750b2f229948baf3cd299a931299e31a494686e3395de48951 |
| POST | /web-wechat/analyse/board/v1/getCertifyCustomerRelType | 200 |  | serviceIds | ev_9049e649478b51750b2f229948baf3cd299a931299e31a494686e3395de48951 |
| POST | /web-wechat/analyse/board/v1/getStewardWorkReport | None |  | endDate, serviceIds, startDate, type | ev_9049e649478b51750b2f229948baf3cd299a931299e31a494686e3395de48951 |
| POST | /web-wechat/analyse/board/v1/steward/charge | None |  | endDate, serviceIds, startDate, type | ev_9049e649478b51750b2f229948baf3cd299a931299e31a494686e3395de48951 |

静态 AJAX 地址候选，存在于页面或关联脚本，未据此证明业务动作执行：
- `https://o2o.unee.com.cn/un-pc-fronted/js/chunk-vendors.f0e6600a.js`：`%s is not a valid %s`、`Link source`、`链接地址`。
- `https://o2o.unee.com.cn/un-pc-fronted/js/app.a069b50e.js`：`/cent-cust/userInfo/queryPCStaffInfo`、`/web-common/common/sysConfigQueryRest`、`/cent-cust/custInfo/statistics/orgRegionServiceList`、`/web-common/list/organization/queryOrgList`、`/web-common/list/organization/queryRegionalList`、`/web-common/list/organization/queryServiceList`、`/web-cust/mobile/queryld`、`/web-cust/mobile/queryhoursename`、`/cent-cust/configCodes/queryConfigCodeList`、`/sso/login`。

## 配置管理 空置房配置

路由 `/web-bus/pc/html/vacantRoomConfigure/vacantRoomConfigureByPC.html`。菜单来源 `ev_25226ae15c591aa25247b4d7ef5e89e5ddd4162209de1bcb9259a6a2f7d462cc`。

菜单定义的操作：新增、删除、修改、查询。这些是菜单权限定义，不代表流程已执行验证。

页面字段：org_name、service_name、start_time、end_time。

页面按钮：新增、删除、查询。

关联脚本中的静态表头候选：城市公司、服务中心、创建人、创建时间、修改时间、操作。共享脚本候选可能属于其他路由。

页面证据：
- `ev_c590a872a43fe0d5c14d31c18cdcb66b904bb81b4e05b852730bf8dceb6eea00`，事务 `request-713`，响应摘要 `e8de218bb463426396ee767d59c0850f7f022acf2d3a76b5ea3574629092364f`，HTTP 200。

前端脚本：
已捕获 15 个关联脚本，地址和摘要见 JSON。业务脚本包括：`https://o2o.unee.com.cn/web-bus/pc/html/vacantRoomConfigure/js/common.js`、`https://o2o.unee.com.cn/web-bus/pc/js/table/custom_table.js`、`https://o2o.unee.com.cn/web-bus/pc/js/progressbar/custom_progressbar.js`、`https://o2o.unee.com.cn/web-bus/pc/html/vacantRoomConfigure/js/vacantRoomConfigureByPC.js`、`https://o2o.unee.com.cn/web-bus/pc/js/niceValidator/local/zh_CN.js`。

同一页面加载步骤内观察到的请求：

| 方法 | 路径 | HTTP | 查询参数名 | 请求体参数名 | Evidence |
| --- | --- | --- | --- | --- | --- |
| POST | /web-common/common/systemUserOrg | 200 | type, system_user_id | findPath | ev_c590a872a43fe0d5c14d31c18cdcb66b904bb81b4e05b852730bf8dceb6eea00 |
| POST | /web-common/common/systemDataPermission | 200 | system_user_id | findPath | ev_c590a872a43fe0d5c14d31c18cdcb66b904bb81b4e05b852730bf8dceb6eea00 |
| POST | /web-bus/getPushMessage/6520159 | 200 |  | not_exposed | ev_c590a872a43fe0d5c14d31c18cdcb66b904bb81b4e05b852730bf8dceb6eea00 |

静态 AJAX 地址候选，存在于页面或关联脚本，未据此证明业务动作执行：
- `https://o2o.unee.com.cn/web-bus/pc/html/vacantRoomConfigure/js/vacantRoomConfigureByPC.js`：`/web-bus/vacantRoomConfigureByPC/queryVacantRoomConfigureList`。
- `https://o2o.unee.com.cn/web-bus/pc/js/ligerUI/js/ligerui.all.js`：`...`。

## 报表管理 企微管家应用情况

路由 `/web-report/pc/html/wecomReport/index.html`。菜单来源 `ev_25226ae15c591aa25247b4d7ef5e89e5ddd4162209de1bcb9259a6a2f7d462cc`。

页面运行错误：Cannot read properties of null (reading '1')。错误与该加载步骤在时间上关联，未证明具体调用因果。

该加载阶段存在失败或 HTTP 错误资源：`/web-wechat/report/v1/platformCompany/page` net::ERR_ABORTED。页面关闭可能中断请求，需重新观察其影响。

页面证据：
- `ev_9049e649478b51750b2f229948baf3cd299a931299e31a494686e3395de48951`，事务 `request-768`，响应摘要 `7846531651ae39146e64cc30310691a5f68b47cef0d3743fadd42574355a1379`，HTTP 200。

前端脚本：
已捕获 1 个关联脚本，地址和摘要见 JSON。业务脚本包括：。

同一页面加载步骤内观察到的请求：

| 方法 | 路径 | HTTP | 查询参数名 | 请求体参数名 | Evidence |
| --- | --- | --- | --- | --- | --- |
| GET | /un-pc-fronted/ | 200 |  | not_exposed | ev_9049e649478b51750b2f229948baf3cd299a931299e31a494686e3395de48951 |
| POST | /cent-cust/userInfo/queryPCStaffInfo | 200 |  | not_exposed | ev_9049e649478b51750b2f229948baf3cd299a931299e31a494686e3395de48951 |
| POST | /web-common/list/organization/queryOrgList | 200 |  | userId | ev_9049e649478b51750b2f229948baf3cd299a931299e31a494686e3395de48951 |
| POST | /web-wechat/report/v1/platformCompany/page | None |  | endDate, orgIds, page, size, startDate | ev_9049e649478b51750b2f229948baf3cd299a931299e31a494686e3395de48951 |

## 配置管理 缴费二维码管理

路由 `/un-pc-fronted/#/formsManagement/paymentQRcodeManagement/index`。菜单来源 `ev_25226ae15c591aa25247b4d7ef5e89e5ddd4162209de1bcb9259a6a2f7d462cc`。

这是 SPA 路由，REA 捕获的共享 HTML 壳和 bundle 不等于该路由完整界面。REA 静态解析没有恢复动态字段；以下独立浏览器观察补充了部分运行时界面结构。

补充界面观察 `UI-SPA-920989`，来源 [原始内置浏览器渲染 DOM](/Volumes/MOVESPEED/Projects/uni-rea/does/spa-ui-observations.json)；与 REA 专用 Chrome 是独立浏览器上下文。

动态列表表头：序号、平台公司、城市公司、项目、支付能力、二维码预览、操作。

动态界面按钮：查 询、批量下载二维码。

页面运行错误：Cannot read properties of null (reading '1')。错误与该加载步骤在时间上关联，未证明具体调用因果。

页面证据：
- `ev_c590a872a43fe0d5c14d31c18cdcb66b904bb81b4e05b852730bf8dceb6eea00`，事务 `request-766`，响应摘要 `fb4004b266dc7cdab0c8eb0fbe54850f25894027bc46dcba4c6f1a8398da4918`，HTTP 200。
- `ev_c590a872a43fe0d5c14d31c18cdcb66b904bb81b4e05b852730bf8dceb6eea00`，事务 `request-971`，响应摘要 `fb4004b266dc7cdab0c8eb0fbe54850f25894027bc46dcba4c6f1a8398da4918`，HTTP 200。
- `ev_c590a872a43fe0d5c14d31c18cdcb66b904bb81b4e05b852730bf8dceb6eea00`，事务 `request-972`，响应摘要 `fb4004b266dc7cdab0c8eb0fbe54850f25894027bc46dcba4c6f1a8398da4918`，HTTP 200。

前端脚本：
已捕获 3 个关联脚本，地址和摘要见 JSON。业务脚本包括：`https://o2o.unee.com.cn/un-pc-fronted/less.min.js`、`https://o2o.unee.com.cn/un-pc-fronted/js/chunk-vendors.f0e6600a.js`、`https://o2o.unee.com.cn/un-pc-fronted/js/app.a069b50e.js`。

同一页面加载步骤内观察到的请求：

| 方法 | 路径 | HTTP | 查询参数名 | 请求体参数名 | Evidence |
| --- | --- | --- | --- | --- | --- |
| GET | /un-pc-fronted/ | 200 |  | not_exposed | ev_c590a872a43fe0d5c14d31c18cdcb66b904bb81b4e05b852730bf8dceb6eea00 |
| POST | /cent-cust/userInfo/queryPCStaffInfo | 200 |  | not_exposed | ev_c590a872a43fe0d5c14d31c18cdcb66b904bb81b4e05b852730bf8dceb6eea00 |
| POST | /web-common/list/organization/queryOrgList | 200 |  | userId | ev_c590a872a43fe0d5c14d31c18cdcb66b904bb81b4e05b852730bf8dceb6eea00 |
| POST | /web-common/list/organization/queryRegionalList | 200 |  | orgIds, userId | ev_c590a872a43fe0d5c14d31c18cdcb66b904bb81b4e05b852730bf8dceb6eea00 |
| POST | /web-common/list/organization/queryServiceList | 200 |  | orgIds, regionalIds, userId | ev_c590a872a43fe0d5c14d31c18cdcb66b904bb81b4e05b852730bf8dceb6eea00 |
| POST | /cent-cust/paymentQrCodeConfig/queryPaymentQrCodeConfigList | 200 |  | pageNum, pageSize, serviceIds | ev_c590a872a43fe0d5c14d31c18cdcb66b904bb81b4e05b852730bf8dceb6eea00 |

静态 AJAX 地址候选，存在于页面或关联脚本，未据此证明业务动作执行：
- `https://o2o.unee.com.cn/un-pc-fronted/js/chunk-vendors.f0e6600a.js`：`%s is not a valid %s`、`Link source`、`链接地址`。
- `https://o2o.unee.com.cn/un-pc-fronted/js/app.a069b50e.js`：`/cent-cust/userInfo/queryPCStaffInfo`、`/web-common/common/sysConfigQueryRest`、`/cent-cust/custInfo/statistics/orgRegionServiceList`、`/web-common/list/organization/queryOrgList`、`/web-common/list/organization/queryRegionalList`、`/web-common/list/organization/queryServiceList`、`/web-cust/mobile/queryld`、`/web-cust/mobile/queryhoursename`、`/cent-cust/configCodes/queryConfigCodeList`、`/sso/login`。

## 统计中心 扫码评价统计报表

路由 `/web-seo/pc/html/CodeScanningStatisticsReport/codeEvaluationView.html`。菜单来源 `ev_25226ae15c591aa25247b4d7ef5e89e5ddd4162209de1bcb9259a6a2f7d462cc`。

页面字段：start_time、end_time。

页面按钮：查询、导出。

关联脚本中的静态表头候选：+(item.state==、+v+、序号、平台公司、扫码提交数、响应及时数、响应及时率、未处理数、转工单数、工单生成率、回访工单数。共享脚本候选可能属于其他路由。

页面证据：
- `ev_09a45f0a06a75d1316e52ebd6f6fa25316e841f7362f861659f9969d3c364feb`，事务 `request-628`，响应摘要 `1dcca9ef2ea43c069f34412dda56f76c8ef76bc4172746fa8a2297eb3183c7d2`，HTTP 200。

前端脚本：
已捕获 11 个关联脚本，地址和摘要见 JSON。业务脚本包括：`https://o2o.unee.com.cn/web-seo/pc/js/common.js`、`https://o2o.unee.com.cn/web-seo/pc/js/niceValidator/local/zh_CN.js`、`https://o2o.unee.com.cn/web-seo/pc/html/CodeScanningStatisticsReport/js/resetTableHeight.js`、`https://o2o.unee.com.cn/web-seo/pc/html/CodeScanningStatisticsReport/js/codeEvaluationView.js`、`https://o2o.unee.com.cn/web-seo/pc/html/CodeScanningStatisticsReport/js/virtual-select.min.js`。

同一页面加载步骤内观察到的请求：

| 方法 | 路径 | HTTP | 查询参数名 | 请求体参数名 | Evidence |
| --- | --- | --- | --- | --- | --- |
| POST | /web-common/list/queryOrgList | 200 |  | userId | ev_09a45f0a06a75d1316e52ebd6f6fa25316e841f7362f861659f9969d3c364feb |

静态 AJAX 地址候选，存在于页面或关联脚本，未据此证明业务动作执行：
- `https://o2o.unee.com.cn/web-seo/pc/js/ligerUI/js/ligerui.all.js`：`...`。
- `https://o2o.unee.com.cn/web-seo/pc/html/CodeScanningStatisticsReport/js/codeEvaluationView.js`：`/web-seo/ScanQRCodeEvaluation/queryStatisticalReportByOrg`。

## 客户服务 装修申报

路由 `/web-bus/pc/html/decorationManagement/index.html`。菜单来源 `ev_25226ae15c591aa25247b4d7ef5e89e5ddd4162209de1bcb9259a6a2f7d462cc`。

菜单定义的操作：导出、列设置、新增、修改、查询、删除。这些是菜单权限定义，不代表流程已执行验证。

页面字段：org_name、service_name、serv_name、status_name、renovation_type_name、extra_msg、timeSearchName、start_time、end_time。

页面按钮：查询、导出、列设置、新增、删除。

该加载阶段存在失败或 HTTP 错误资源：`/web-bus/pc/js/artDialog/style.css` net::ERR_ABORTED。页面关闭可能中断请求，需重新观察其影响。

页面证据：
- `ev_f2631a7dc031a549a87680b1e2affa1a088efdd842c289a316e649c9749ad8e0`，事务 `request-680`，响应摘要 `46a03434a87b2f01507c1d2fc7dc2b34b61c93b2ce2999030511bc181cb4726a`，HTTP 200。

前端脚本：
已捕获 5 个关联脚本，地址和摘要见 JSON。业务脚本包括：`https://o2o.unee.com.cn/web-bus/pc/html/decorationManagement/js/common.js`、`https://o2o.unee.com.cn/web-bus/pc/html/decorationManagement/js/index.js`、`https://o2o.unee.com.cn/web-bus/pc/html/decorationManagement/js/dateFormat.js`、`https://o2o.unee.com.cn/web-bus/pc/html/decorationManagement/js/resetTableHeight.js`、`https://o2o.unee.com.cn/web-bus/pc/html/decorationManagement/js/toast.js`、`https://o2o.unee.com.cn/web-bus/pc/js/niceValidator/local/zh_CN.js`。

同一页面加载步骤内观察到的请求：

| 方法 | 路径 | HTTP | 查询参数名 | 请求体参数名 | Evidence |
| --- | --- | --- | --- | --- | --- |
| POST | /web-common/common/sysConfigQueryRest | 200 |  | column_name, table_name | ev_f2631a7dc031a549a87680b1e2affa1a088efdd842c289a316e649c9749ad8e0 |
| POST | /web-bus/pc/renovationDeclare/getConfig | 200 |  | not_exposed | ev_f2631a7dc031a549a87680b1e2affa1a088efdd842c289a316e649c9749ad8e0 |
| GET | /web-bus/columnController/getShowColumn | 200 | modules_code | not_exposed | ev_f2631a7dc031a549a87680b1e2affa1a088efdd842c289a316e649c9749ad8e0 |
| POST | /web-common/common/systemUserOrg | 200 | type, system_user_id | findPath | ev_f2631a7dc031a549a87680b1e2affa1a088efdd842c289a316e649c9749ad8e0 |
| POST | /web-common/permission/common/systemDataPermission | 200 | system_user_id, type | findPath | ev_f2631a7dc031a549a87680b1e2affa1a088efdd842c289a316e649c9749ad8e0 |

静态 AJAX 地址候选，存在于页面或关联脚本，未据此证明业务动作执行：
- `https://o2o.unee.com.cn/web-bus/pc/html/decorationManagement/js/common.js`：`/web-common/common/servsList`。
- `https://o2o.unee.com.cn/web-bus/pc/html/decorationManagement/js/index.js`：`/web-common/common/sysConfigQueryRest`、`/web-bus/pc/renovationDeclare/getConfig`、`/web-common/common/servsList`、`/web-bus/columnController/getShowColumn`。

## 配置管理 角色清单导出

路由 `/un-pc-fronted/#/formsManagement/roleListExport/index`。菜单来源 `ev_25226ae15c591aa25247b4d7ef5e89e5ddd4162209de1bcb9259a6a2f7d462cc`。

菜单定义的操作：导出。这些是菜单权限定义，不代表流程已执行验证。

这是 SPA 路由，REA 捕获的共享 HTML 壳和 bundle 不等于该路由完整界面。REA 静态解析没有恢复动态字段；以下独立浏览器观察补充了部分运行时界面结构。

补充界面观察 `UI-SPA-920990`，来源 [原始内置浏览器渲染 DOM](/Volumes/MOVESPEED/Projects/uni-rea/does/spa-ui-observations.json)；与 REA 专用 Chrome 是独立浏览器上下文。

动态列表表头：序号、平台公司、城市公司、项目、项目编码、员工姓名、员工工号、员工角色。

动态界面按钮：查 询、角色清单导出。

页面运行错误：Cannot read properties of null (reading '1')。错误与该加载步骤在时间上关联，未证明具体调用因果。

该加载阶段存在失败或 HTTP 错误资源：`/web-bus/RoleListExportController/v3/pageList` net::ERR_ABORTED。页面关闭可能中断请求，需重新观察其影响。

页面证据：
- `ev_c590a872a43fe0d5c14d31c18cdcb66b904bb81b4e05b852730bf8dceb6eea00`，事务 `request-990`，响应摘要 `fb4004b266dc7cdab0c8eb0fbe54850f25894027bc46dcba4c6f1a8398da4918`，HTTP 200。
- `ev_c590a872a43fe0d5c14d31c18cdcb66b904bb81b4e05b852730bf8dceb6eea00`，事务 `request-1195`，响应摘要 `fb4004b266dc7cdab0c8eb0fbe54850f25894027bc46dcba4c6f1a8398da4918`，HTTP 200。
- `ev_c590a872a43fe0d5c14d31c18cdcb66b904bb81b4e05b852730bf8dceb6eea00`，事务 `request-1196`，响应摘要 `fb4004b266dc7cdab0c8eb0fbe54850f25894027bc46dcba4c6f1a8398da4918`，HTTP 200。

前端脚本：
已捕获 3 个关联脚本，地址和摘要见 JSON。业务脚本包括：`https://o2o.unee.com.cn/un-pc-fronted/less.min.js`、`https://o2o.unee.com.cn/un-pc-fronted/js/chunk-vendors.f0e6600a.js`、`https://o2o.unee.com.cn/un-pc-fronted/js/app.a069b50e.js`。

同一页面加载步骤内观察到的请求：

| 方法 | 路径 | HTTP | 查询参数名 | 请求体参数名 | Evidence |
| --- | --- | --- | --- | --- | --- |
| GET | /un-pc-fronted/ | 200 |  | not_exposed | ev_c590a872a43fe0d5c14d31c18cdcb66b904bb81b4e05b852730bf8dceb6eea00 |
| POST | /cent-cust/userInfo/queryPCStaffInfo | 200 |  | not_exposed | ev_c590a872a43fe0d5c14d31c18cdcb66b904bb81b4e05b852730bf8dceb6eea00 |
| POST | /web-common/list/organization/queryOrgList | 200 |  | userId | ev_c590a872a43fe0d5c14d31c18cdcb66b904bb81b4e05b852730bf8dceb6eea00 |
| POST | /web-common/list/organization/queryRegionalList | 200 |  | orgIds, userId | ev_c590a872a43fe0d5c14d31c18cdcb66b904bb81b4e05b852730bf8dceb6eea00 |
| POST | /web-common/list/organization/queryServiceList | 200 |  | orgIds, regionalIds, userId | ev_c590a872a43fe0d5c14d31c18cdcb66b904bb81b4e05b852730bf8dceb6eea00 |
| POST | /web-bus/RoleListExportController/v3/pageList | None |  | org_ids, page, pageSize, regional_ids, service_ids | ev_c590a872a43fe0d5c14d31c18cdcb66b904bb81b4e05b852730bf8dceb6eea00 |

静态 AJAX 地址候选，存在于页面或关联脚本，未据此证明业务动作执行：
- `https://o2o.unee.com.cn/un-pc-fronted/js/chunk-vendors.f0e6600a.js`：`%s is not a valid %s`、`Link source`、`链接地址`。
- `https://o2o.unee.com.cn/un-pc-fronted/js/app.a069b50e.js`：`/cent-cust/userInfo/queryPCStaffInfo`、`/web-common/common/sysConfigQueryRest`、`/cent-cust/custInfo/statistics/orgRegionServiceList`、`/web-common/list/organization/queryOrgList`、`/web-common/list/organization/queryRegionalList`、`/web-common/list/organization/queryServiceList`、`/web-cust/mobile/queryld`、`/web-cust/mobile/queryhoursename`、`/cent-cust/configCodes/queryConfigCodeList`、`/sso/login`。

## 客户服务 装修巡查清单

路由 `/web-bus/pc/html/inspectionList/index.html`。菜单来源 `ev_25226ae15c591aa25247b4d7ef5e89e5ddd4162209de1bcb9259a6a2f7d462cc`。

菜单定义的操作：列设置、导出、查询。这些是菜单权限定义，不代表流程已执行验证。

页面字段：org_name、service_name、serv_name、inspection_name、start_time、end_time、extra_msg、status_name。

页面按钮：查询、列设置、导出、返回。

该加载阶段存在失败或 HTTP 错误资源：`/web-bus/pc/css/jquery.autocomplete.css` net::ERR_ABORTED、`/web-bus/pc/js/niceValidator/style.css` net::ERR_ABORTED、`/web-bus/pc/js/ligerUI/skins/ligerui-icons.css` net::ERR_ABORTED。页面关闭可能中断请求，需重新观察其影响。

页面证据：
- `ev_f2631a7dc031a549a87680b1e2affa1a088efdd842c289a316e649c9749ad8e0`，事务 `request-738`，响应摘要 `0213ef5cbec27603b963143fc91e7255e1f240a884950e7311fd6bc78506a399`，HTTP 200。

前端脚本：
已捕获 4 个关联脚本，地址和摘要见 JSON。业务脚本包括：`https://o2o.unee.com.cn/web-bus/pc/html/inspectionList/js/common.js`、`https://o2o.unee.com.cn/web-bus/pc/html/inspectionList/js/index.js`、`https://o2o.unee.com.cn/web-bus/pc/html/inspectionList/js/dateFormat.js`、`https://o2o.unee.com.cn/web-bus/pc/html/inspectionList/js/resetTableHeight.js`、`https://o2o.unee.com.cn/web-bus/pc/js/niceValidator/local/zh_CN.js`。

同一页面加载步骤内观察到的请求：

| 方法 | 路径 | HTTP | 查询参数名 | 请求体参数名 | Evidence |
| --- | --- | --- | --- | --- | --- |
| POST | /web-common/common/sysConfigQueryRest | 200 |  | column_name, table_name | ev_f2631a7dc031a549a87680b1e2affa1a088efdd842c289a316e649c9749ad8e0 |
| GET | /web-bus/columnController/getShowColumn | 200 | modules_code | not_exposed | ev_f2631a7dc031a549a87680b1e2affa1a088efdd842c289a316e649c9749ad8e0 |
| POST | /web-common/common/systemUserOrg | 200 | type, system_user_id | findPath | ev_f2631a7dc031a549a87680b1e2affa1a088efdd842c289a316e649c9749ad8e0 |
| POST | /web-common/permission/common/systemDataPermission | 200 | system_user_id, type | findPath | ev_f2631a7dc031a549a87680b1e2affa1a088efdd842c289a316e649c9749ad8e0 |
| POST | /web-bus/getPushMessage/6520159 | 200 |  | not_exposed | ev_f2631a7dc031a549a87680b1e2affa1a088efdd842c289a316e649c9749ad8e0 |

静态 AJAX 地址候选，存在于页面或关联脚本，未据此证明业务动作执行：
- `https://o2o.unee.com.cn/web-bus/pc/html/inspectionList/js/common.js`：`/web-common/common/servsList`。
- `https://o2o.unee.com.cn/web-bus/pc/html/inspectionList/js/index.js`：`/web-common/common/sysConfigQueryRest`、`/web-common/common/servsList`、`/web-bus/pc/renovationPatrol/getCodeById`、`/web-bus/columnController/getShowColumn`。

## 客户服务 装修整改通知函

路由 `/web-bus/pc/html/decorationNotice/index.html`。菜单来源 `ev_25226ae15c591aa25247b4d7ef5e89e5ddd4162209de1bcb9259a6a2f7d462cc`。

菜单定义的操作：列设置、导出、跟踪、打印、下载、查询。这些是菜单权限定义，不代表流程已执行验证。

页面字段：org_name、service_name、serv_name、start_time、end_time、extra_msg、status_name。

页面按钮：查询、列设置、导出。

该加载阶段存在失败或 HTTP 错误资源：`/web-bus/pc/js/artDialog/style.css` net::ERR_ABORTED。页面关闭可能中断请求，需重新观察其影响。

页面证据：
- `ev_f2631a7dc031a549a87680b1e2affa1a088efdd842c289a316e649c9749ad8e0`，事务 `request-795`，响应摘要 `2d31a48d05d329c791cc47e8087ea0eca4fc1441b3dda47fe243d4a82bf3d1c4`，HTTP 200。

前端脚本：
已捕获 4 个关联脚本，地址和摘要见 JSON。业务脚本包括：`https://o2o.unee.com.cn/web-bus/pc/html/decorationNotice/js/common.js`、`https://o2o.unee.com.cn/web-bus/pc/html/decorationNotice/js/index.js`、`https://o2o.unee.com.cn/web-bus/pc/html/decorationNotice/js/dateFormat.js`、`https://o2o.unee.com.cn/web-bus/pc/html/decorationNotice/js/resetTableHeight.js`、`https://o2o.unee.com.cn/web-bus/pc/js/niceValidator/local/zh_CN.js`。

同一页面加载步骤内观察到的请求：

| 方法 | 路径 | HTTP | 查询参数名 | 请求体参数名 | Evidence |
| --- | --- | --- | --- | --- | --- |
| POST | /web-common/common/sysConfigQueryRest | 200 |  | column_name, table_name | ev_f2631a7dc031a549a87680b1e2affa1a088efdd842c289a316e649c9749ad8e0 |
| GET | /web-bus/columnController/getShowColumn | 200 | modules_code | not_exposed | ev_f2631a7dc031a549a87680b1e2affa1a088efdd842c289a316e649c9749ad8e0 |
| POST | /web-common/common/systemUserOrg | 200 | type, system_user_id | findPath | ev_f2631a7dc031a549a87680b1e2affa1a088efdd842c289a316e649c9749ad8e0 |
| POST | /web-common/permission/common/systemDataPermission | 200 | system_user_id, type | findPath | ev_f2631a7dc031a549a87680b1e2affa1a088efdd842c289a316e649c9749ad8e0 |

静态 AJAX 地址候选，存在于页面或关联脚本，未据此证明业务动作执行：
- `https://o2o.unee.com.cn/web-bus/pc/html/decorationNotice/js/common.js`：`/web-common/common/servsList`。
- `https://o2o.unee.com.cn/web-bus/pc/html/decorationNotice/js/index.js`：`/web-common/common/sysConfigQueryRest`、`/web-common/common/servsList`、`/web-bus/columnController/getShowColumn`。

## 客户服务 访客登记记录

路由 `/un-pc-fronted/#/personAccess/registrationRecords/index`。菜单来源 `ev_25226ae15c591aa25247b4d7ef5e89e5ddd4162209de1bcb9259a6a2f7d462cc`。

菜单定义的操作：查看手机号、导出、查看图片。这些是菜单权限定义，不代表流程已执行验证。

这是 SPA 路由，REA 捕获的共享 HTML 壳和 bundle 不等于该路由完整界面。REA 静态解析没有恢复动态字段；以下独立浏览器观察补充了部分运行时界面结构。

补充界面观察 `UI-SPA-100902`，来源 [原始内置浏览器渲染 DOM](/Volumes/MOVESPEED/Projects/uni-rea/does/spa-ui-observations.json)；与 REA 专用 Chrome 是独立浏览器上下文。

动态控件占位符：预约提交开始时间、预约提交结束时间、访客姓名/手机号码/住户姓名/住户手机号码。

动态列表表头：序号、平台公司、城市公司、服务中心、访客姓名、访客手机号码、来访事由、来访具体事项、来访住户姓名、来访住户手机号码、授权门禁、来访周期、来访日期、人脸头像、工作证照片、AB证、来访房间号、证明图片、备注、状态、是否删除、提交时间、审批人员、审批意见、审批时间、登记渠道。

动态界面按钮：代客登记、查 询、导出Excel。

页面运行错误：Cannot read properties of null (reading '1')。错误与该加载步骤在时间上关联，未证明具体调用因果。

该加载阶段存在失败或 HTTP 错误资源：`/web-cust/mobile/visitor/page` net::ERR_ABORTED。页面关闭可能中断请求，需重新观察其影响。

页面证据：
- `ev_f2631a7dc031a549a87680b1e2affa1a088efdd842c289a316e649c9749ad8e0`，事务 `request-848`，响应摘要 `fb4004b266dc7cdab0c8eb0fbe54850f25894027bc46dcba4c6f1a8398da4918`，HTTP 200。
- `ev_f2631a7dc031a549a87680b1e2affa1a088efdd842c289a316e649c9749ad8e0`，事务 `request-1053`，响应摘要 `fb4004b266dc7cdab0c8eb0fbe54850f25894027bc46dcba4c6f1a8398da4918`，HTTP 200。
- `ev_f2631a7dc031a549a87680b1e2affa1a088efdd842c289a316e649c9749ad8e0`，事务 `request-1054`，响应摘要 `fb4004b266dc7cdab0c8eb0fbe54850f25894027bc46dcba4c6f1a8398da4918`，HTTP 200。

前端脚本：
已捕获 3 个关联脚本，地址和摘要见 JSON。业务脚本包括：`https://o2o.unee.com.cn/un-pc-fronted/less.min.js`、`https://o2o.unee.com.cn/un-pc-fronted/js/chunk-vendors.f0e6600a.js`、`https://o2o.unee.com.cn/un-pc-fronted/js/app.a069b50e.js`。

同一页面加载步骤内观察到的请求：

| 方法 | 路径 | HTTP | 查询参数名 | 请求体参数名 | Evidence |
| --- | --- | --- | --- | --- | --- |
| GET | /un-pc-fronted/ | 200 |  | not_exposed | ev_f2631a7dc031a549a87680b1e2affa1a088efdd842c289a316e649c9749ad8e0 |
| POST | /cent-cust/userInfo/queryPCStaffInfo | 200 |  | not_exposed | ev_f2631a7dc031a549a87680b1e2affa1a088efdd842c289a316e649c9749ad8e0 |
| POST | /web-cust/mobile/visitor/matter/selectAll | 200 |  | not_exposed | ev_f2631a7dc031a549a87680b1e2affa1a088efdd842c289a316e649c9749ad8e0 |
| POST | /web-common/list/organization/queryOrgList | 200 |  | userId | ev_f2631a7dc031a549a87680b1e2affa1a088efdd842c289a316e649c9749ad8e0 |
| POST | /web-common/list/organization/queryRegionalList | 200 |  | orgIds, userId | ev_f2631a7dc031a549a87680b1e2affa1a088efdd842c289a316e649c9749ad8e0 |
| POST | /web-common/list/organization/queryServiceList | 200 |  | orgIds, regionalIds, userId | ev_f2631a7dc031a549a87680b1e2affa1a088efdd842c289a316e649c9749ad8e0 |
| POST | /web-cust/mobile/visitor/page | None |  | current, isDelete, likeNameOrPhone, projectCodes, registerSourceIds, searchEndTime, searchStartTime, size, statusList, subjectTypeIdList | ev_f2631a7dc031a549a87680b1e2affa1a088efdd842c289a316e649c9749ad8e0 |

静态 AJAX 地址候选，存在于页面或关联脚本，未据此证明业务动作执行：
- `https://o2o.unee.com.cn/un-pc-fronted/js/chunk-vendors.f0e6600a.js`：`%s is not a valid %s`、`Link source`、`链接地址`。
- `https://o2o.unee.com.cn/un-pc-fronted/js/app.a069b50e.js`：`/cent-cust/userInfo/queryPCStaffInfo`、`/web-common/common/sysConfigQueryRest`、`/cent-cust/custInfo/statistics/orgRegionServiceList`、`/web-common/list/organization/queryOrgList`、`/web-common/list/organization/queryRegionalList`、`/web-common/list/organization/queryServiceList`、`/web-cust/mobile/queryld`、`/web-cust/mobile/queryhoursename`、`/cent-cust/configCodes/queryConfigCodeList`、`/sso/login`。

## 客户服务 访客通行记录

路由 `/un-pc-fronted/#/personAccess/transitRecords/index`。菜单来源 `ev_25226ae15c591aa25247b4d7ef5e89e5ddd4162209de1bcb9259a6a2f7d462cc`。

菜单定义的操作：查看手机号、导出。这些是菜单权限定义，不代表流程已执行验证。

这是 SPA 路由，REA 捕获的共享 HTML 壳和 bundle 不等于该路由完整界面。REA 静态解析没有恢复动态字段；以下独立浏览器观察补充了部分运行时界面结构。

补充界面观察 `UI-SPA-100903`，来源 [原始内置浏览器渲染 DOM](/Volumes/MOVESPEED/Projects/uni-rea/does/spa-ui-observations.json)；与 REA 专用 Chrome 是独立浏览器上下文。

动态控件占位符：开始时间、结束时间、姓名/手机号/通行身份/点位名称。

动态列表表头：序号、平台公司、城市公司、服务中心、姓名、手机号码、访客身份、通行方向、通行方式、点位名称、通行时间、通行状态、通行人脸抓拍。

动态界面按钮：查 询、导出Excel。

页面运行错误：Cannot read properties of null (reading '1')。错误与该加载步骤在时间上关联，未证明具体调用因果。

该加载阶段存在失败或 HTTP 错误资源：`/web-cust/mobile/visitor/visitor-pass-record/page` net::ERR_ABORTED。页面关闭可能中断请求，需重新观察其影响。

页面证据：
- `ev_f2631a7dc031a549a87680b1e2affa1a088efdd842c289a316e649c9749ad8e0`，事务 `request-1064`，响应摘要 `fb4004b266dc7cdab0c8eb0fbe54850f25894027bc46dcba4c6f1a8398da4918`，HTTP 200。
- `ev_f2631a7dc031a549a87680b1e2affa1a088efdd842c289a316e649c9749ad8e0`，事务 `request-1269`，响应摘要 `fb4004b266dc7cdab0c8eb0fbe54850f25894027bc46dcba4c6f1a8398da4918`，HTTP 200。
- `ev_f2631a7dc031a549a87680b1e2affa1a088efdd842c289a316e649c9749ad8e0`，事务 `request-1270`，响应摘要 `fb4004b266dc7cdab0c8eb0fbe54850f25894027bc46dcba4c6f1a8398da4918`，HTTP 200。

前端脚本：
已捕获 3 个关联脚本，地址和摘要见 JSON。业务脚本包括：`https://o2o.unee.com.cn/un-pc-fronted/less.min.js`、`https://o2o.unee.com.cn/un-pc-fronted/js/chunk-vendors.f0e6600a.js`、`https://o2o.unee.com.cn/un-pc-fronted/js/app.a069b50e.js`。

同一页面加载步骤内观察到的请求：

| 方法 | 路径 | HTTP | 查询参数名 | 请求体参数名 | Evidence |
| --- | --- | --- | --- | --- | --- |
| GET | /un-pc-fronted/ | 200 |  | not_exposed | ev_f2631a7dc031a549a87680b1e2affa1a088efdd842c289a316e649c9749ad8e0 |
| POST | /cent-cust/userInfo/queryPCStaffInfo | 200 |  | not_exposed | ev_f2631a7dc031a549a87680b1e2affa1a088efdd842c289a316e649c9749ad8e0 |
| POST | /web-common/list/organization/queryOrgList | 200 |  | userId | ev_f2631a7dc031a549a87680b1e2affa1a088efdd842c289a316e649c9749ad8e0 |
| POST | /web-common/list/organization/queryRegionalList | 200 |  | orgIds, userId | ev_f2631a7dc031a549a87680b1e2affa1a088efdd842c289a316e649c9749ad8e0 |
| POST | /web-common/list/organization/queryServiceList | 200 |  | orgIds, regionalIds, userId | ev_f2631a7dc031a549a87680b1e2affa1a088efdd842c289a316e649c9749ad8e0 |
| POST | /web-cust/mobile/visitor/visitor-pass-record/page | None |  | current, keywords, passState, projectCodes, searchEndTime, searchStartTime, size | ev_f2631a7dc031a549a87680b1e2affa1a088efdd842c289a316e649c9749ad8e0 |

静态 AJAX 地址候选，存在于页面或关联脚本，未据此证明业务动作执行：
- `https://o2o.unee.com.cn/un-pc-fronted/js/chunk-vendors.f0e6600a.js`：`%s is not a valid %s`、`Link source`、`链接地址`。
- `https://o2o.unee.com.cn/un-pc-fronted/js/app.a069b50e.js`：`/cent-cust/userInfo/queryPCStaffInfo`、`/web-common/common/sysConfigQueryRest`、`/cent-cust/custInfo/statistics/orgRegionServiceList`、`/web-common/list/organization/queryOrgList`、`/web-common/list/organization/queryRegionalList`、`/web-common/list/organization/queryServiceList`、`/web-cust/mobile/queryld`、`/web-cust/mobile/queryhoursename`、`/cent-cust/configCodes/queryConfigCodeList`、`/sso/login`。

## 证据和解释边界

菜单接口 `/portal/menu/queryMenu` 定义当前账号可见菜单及按钮权限。这些权限名称描述可见操作，不证明服务器授权控制或按钮流程已经验证。

- 当前账号菜单的可见范围不等于平台全部能力或其他租户权限。
- 页面加载请求未验证按钮业务流程、修改成功、后端授权、数据库结构或服务器内部实现。
- 静态 AJAX 字符串是候选，无法完整解析变量和拼接路径。共享 SPA bundle 中的候选不能视为某条路由的执行事实。
- 派生报告省略运行时 URL 查询值和请求体值，只记录参数名，原始 Evidence 保留来源。
- 网络事件的步骤编号按浏览器提供方收到事件时记录；异步响应可能跨步骤，不能仅凭同一步证明请求发起因果。

完整逐条元数据、Evidence ID、事务编号、响应摘要及候选代码行号保存在 `features-analysis.json`。原始页面和响应保留在 Evidence 文件中。


## 星海图后续大屏补充分析

入口后实际大屏已另行采集，见 [星海图功能分析](/Volumes/MOVESPEED/Projects/uni-rea/does/viewport-findings.md)。观察到 8 个主要读取事务均 HTTP 200。该补采不改写原始 9 模块统计；后端业务公式和五分钟刷新范围传递仍按该章边界解释。
