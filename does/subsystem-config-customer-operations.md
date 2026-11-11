# 配置管理、客户管理与运营中心：静态功能分析

本报告只读已脱敏的固定 REA 捕获文件 `evidence/module-03.json`、`module-04.json`、`module-05.json`，未连接浏览器或调用业务接口。覆盖 **15 + 2 + 6 = 23 个菜单入口**，分析初始 HTML、加载的 JavaScript 和已记录的请求事件；未进入新增/编辑表单，也未执行发布、删除、同步、导出或设备操作。

## 证据与判读方式

- **E03**：[module-03.json](evidence/module-03.json)，Evidence ID `ev_c590a872a43fe0d5c14d31c18cdcb66b904bb81b4e05b852730bf8dceb6eea00`。
- **E04**：[module-04.json](evidence/module-04.json)，Evidence ID `ev_217ee4e01474a60978df3b0f8593f64ec81bbe05d137d4ca0cfcaf8f1e1ebccf`。
- **E05**：[module-05.json](evidence/module-05.json)，Evidence ID `ev_c4d4036bc65a408c8041f833ce8889a39169173452dd7d6ae2a6a106c5d2ca2b`。

下文“静态支持”指源码有相关入口或分支；“候选接口”指代码声明的路径，未必被本次访问调用；“已观察请求”指 REA 网络事件实际记录了调用。行号按捕获响应正文 UTF-8 解码后原始行计算，不经格式化；压缩构建文件只含一行。所有 URL 均省略查询值，报告不包含业务记录、用户资料或鉴权值。

三个捕获整体均标记 `incomplete`、缺失部分 `events`，尽管 retained events 未丢弃（分别 6029、893、2129）；所以“未观察”只描述本次保留证据，不证明接口不存在或永不执行。三个场景还保留了页面错误事件（21、3、9）；这些限制意味着源码存在不能直接等同于界面完整可用。

## 配置管理（15 个入口）

### 1. 装修配置

静态支持按城市公司查询装修配置、新增/修改配置及选择后确认删除，列表实体包含配置 ID、城市公司、创建人与创建/修改时间，未采集具体配置内容或编辑表单校验。`queryList`、`updateQuestion`、`isDeleteQuestion` 分别指向候选查询 `/web-bus/pc/renovationConfigure/queryRenovationConfigureList`、编辑页面和删除 `/web-bus/pc/renovationConfigure/deleteRenovationConfigureById`，本次列表 `delayLoad: true` 且未观察主查询。

证据：E03，响应正文事件 684；[decorationConfig.js](https://o2o.unee.com.cn/web-bus/pc/html/decorationConfig/js/decorationConfig.js) 第 5、29、95、149–179、246–295 行。

### 2. 图片管理

静态支持按城市公司、服务中心和使用位置维护图片配置，包含新增、详情、修改和批量删除，删除前校验已选择记录并二次确认。`goAdd/goDetail/goUpdate/deleteConfPicture` 对应页面跳转和候选 `/web-cust/pc/confManagement/delteConfPicture`，主查询候选为原样拼写的 `/web-cust/pc/confManagement/quryConfPicture`，本次延迟列表未查询。

证据：E03，事件 854；[imgConfList.js](https://o2o.unee.com.cn/web-cust/pc/html/confManagement/js/imgConfList.js) 第 5、59–103、175–243 行。

### 3. 门设备管理

静态支持查询、新增/修改、批量导入、导出、删除和查看管理范围，设备模型覆盖厂商、门类型、设备 ID、MAC、物理地址及固件字段；这些是列定义，并非设备实际值。`importExcel/exportData/view/update/dele` 关联候选 `/web-bus/doorEquip/exportData`、`/web-bus/doorEquip/deleteData` 和相应表单/范围页，主查询 `/web-bus/doorEquip/doorEquipListQuery` 本次未观察，`delayLoad` 为真。

证据：E03，事件 1176；[doorEquipList.js](https://o2o.unee.com.cn/web-bus/pc/html/DoorEquipmentManagement/js/doorEquipList.js) 第 4–55、89–168、259–326 行。

### 4. 消息模板

静态支持维护模板使用位置、类型、标题及是否生效，状态 `1000` 显示为“是”，其他状态显示为“否”；查询需服务中心，删除需选择记录并确认。查询 `/web-bus/template/templateListQuery` 和删除 `/web-bus/template/deleteTemplate` 均为候选，详情/新增跳转 `templateView.html`；本次列表延迟且未观察主查询。

证据：E03，事件 1430；[templateList.js](https://o2o.unee.com.cn/web-bus/pc/html/templateManage/js/templateList.js) 第 12–48、91–129、145–220 行。

### 5. 问卷配置

静态支持问卷与模板的新增、修改、复制、启用/停止、删除、问卷链接、二维码和消息推送，操作受权限、管控范围及状态影响，源码区分草稿/待启用、启用等状态分支并保存生效/失效/停止时间。主查询 `/web-bus/pc/questionsConfigList` 未观察且列表延迟；复制 `/web-bus/quesBaseInfoController/copyQuesBaseInfo`、停止 `/web-bus/pc/stopStatus` 和创建二维码 `/web-bus/pc/ques/createQuestionsQR` 是候选，实际只观察初始化管控类型和项目二维码配置查询等辅助请求。

证据：E03，事件 1704；[questionsConfigList.js](https://o2o.unee.com.cn/web-bus/pc/html/questionsConfig/js/questionsConfigList.js) 第 5、109–148、296–338、382–420、650–771、899–902、993–1024 行；辅助请求事件 1766、1803 为 `/web-bus/quesQrCodeInfoController/qrCodeManageListQuery`，HTTP 200。

### 6. 评价二维码管理

静态支持按互动点位、粘贴地点、项目和状态查询二维码，查看/修改/删除、导出和二维码下载，修改及删除按钮还要求状态 `1000` 且有对应权限。主列表 `/web-bus/quesQrCodeInfoController/qrCodeListQuery`、删除 `/web-bus/quesQrCodeInfoController/deleteData`、图片下载 `/web-bus/quesQrCodeInfoController/downImg` 为候选，本次延迟列表未查询，实际加载了类型与状态字典。

证据：E03，事件 1988；[qrCodeList.js](https://o2o.unee.com.cn/web-bus/pc/html/scanEvaluate/qrCode/js/qrCodeList.js) 第 17–29、60–83、103–208、276–340、497–513 行。

### 7. 手机开门推送配置

静态支持配置推送发起方、业务类别、推送业务及有效期，包含新增、查看、修改、删除；修改/删除列按钮同时判断操作权限与创建者身份。主列表候选 `/web-bus/pc/pushManageController/query` 在本次延迟列表中未观察；实际调用的是初始化选项 `/web-bus/pc/pushManageController/queryConfig`（HTTP 200），删除候选另属 `/web-bus/DoorPagePushManageController/deleteCustAppPagePush`。

证据：E03，事件 2238；[push_manager_list.js](https://o2o.unee.com.cn/web-bus/pc/html/openDoor/js/push_manager_list.js) 第 17、23–34、40–71、100–144、261–287 行；初始化请求/响应事件 2312、2314。

### 8. 电梯管理

静态支持电梯新增/修改/删除、批量导入和导出，关联楼栋、单元、顺序、控制单元、主控/访客板 MAC、固件及楼层映射字段，新增流程检查服务中心。主查询候选 `/web-bus/CustElevatorManageController/queryCustElevatorManage` 本次未观察且 `delayLoad` 为真，删除和导出候选分别为同控制器 `/deleteCustElevatorManage`、`/exportData`；实际设备控制效果未验证。

证据：E03，事件 2501；[elevator_manage.js](https://o2o.unee.com.cn/web-bus/pc/html/elevatorManage/js/elevator_manage.js) 第 9–58、90–169、195–233、292 行。

### 9. 抵扣券导入

静态支持券码导入、查询、导出、启用和解锁，实体包含企业、券码、金额、导入时间及“未启用/已启用/已使用/已锁定”；启用仅接受“未启用”，解锁仅接受“已锁定”，两者最终提交“已启用”。虽然 grid 写有 `delayLoad: true`，初始化明确调用 `queryList()`，本次已观察 `/web-cust/deductionVoucher/selectList` 返回 HTTP 200，修改状态 `/web-cust/deductionVoucher/updateStatusToValid` 和导出 `/web-cust/deductionVoucher/exportData` 仍是未执行候选。

证据：E03，事件 2745；[deductionVoucherList.js](https://o2o.unee.com.cn/web-cust/pc/html/deductionVoucher/js/deductionVoucherList.js) 第 2–20、52–97、183–198、210–286、309–328 行；实际请求/响应事件 2802、2830。

### 10. 报告台岗位管理

静态支持岗位新增、修改、查询和批量删除，字段包括岗位名称、职责、备注与引用项目数；删除前拒绝被项目引用的岗位并要求确认。尽管 grid 延迟，初始化显式 `queryList()`，实际主查询 `/web-cust/postPool/selectList` 返回 HTTP 200，删除 `/web-cust/postPool/delPost` 是未执行候选。

证据：E03，事件 2991；[postPoolList.js](https://o2o.unee.com.cn/web-cust/pc/html/report/js/postPoolList.js) 第 2–9、38–74、174–209 行；实际请求/响应事件 3046、3071。

### 11. 报告台基础配置管理

静态支持按平台、城市、项目查询岗位配置，新增、删除、查看岗位详情和述职报告；代码还保留已审核/未审核筛选，但“启动测评”按钮分支被注释，不能算作已启用功能。主列表候选 `/web-cust/baseConfig/selectList` 本次未观察，grid 延迟且仅在返回标记存在时自动查询，删除候选 `/web-cust/baseConfig/delBaseConfig` 未执行。

证据：E03，事件 3195；[baseConfigList.js](https://o2o.unee.com.cn/web-cust/pc/html/report/js/baseConfigList.js) 第 2、9–40、70–138、235–276 行。

### 12. 质检员点位管理

静态支持质检点位新增、查询、配置服务标准、删除和置为失效，状态字典为 `1000=有效`、`9999=失效`，删除处理代码识别“有质检记录不可删除”的服务端失败原因。主查询 `/web-cust/pc/inspection/confList` 本次未观察且延迟，删除 `/web-cust/pc/inspection/deleteInspectionById`、失效 `/web-cust/pc/inspection/invalidInspectionById` 是未执行候选。

证据：E03，事件 3433；[inspeConfList.js](https://o2o.unee.com.cn/web-cust/pc/html/inspectionManagement/js/inspeConfList.js) 第 4–45、122–156、159–205、212–229 行。

### 13. 空置房配置

静态支持按服务中心与日期查询空置房配置、新增/修改及选择后确认删除，查询函数同时要求表单有效和服务中心已选择。主查询候选 `/web-bus/vacantRoomConfigureByPC/queryVacantRoomConfigureList` 本次未观察且延迟，返回页面标记可触发查询；删除候选 `/web-bus/vacantRoomConfigureByPC/deleteVacantRoomConfigureById` 未执行。

证据：E03，事件 3672；[vacantRoomConfigureByPC.js](https://o2o.unee.com.cn/web-bus/pc/html/vacantRoomConfigure/js/vacantRoomConfigureByPC.js) 第 50–88、170–209、215–245、322、376–378 行。

### 14. 缴费二维码管理

静态支持按平台、城市、服务中心多选筛选支付二维码，显示支付能力和二维码预览，提供单个/批量下载，批量下载要求先选择二维码。实际已观察 `/cent-cust/paymentQrCodeConfig/queryPaymentQrCodeConfigList` 返回 HTTP 200，`/downloadQrCodeByConfigId` 和 `/batchDownload` 仅为同控制器的 blob 下载候选；组件未使用传统 `delayLoad`。

证据：E03，事件 4832；[chunk-8b555334.ef7d5111.js](https://o2o.unee.com.cn/un-pc-fronted/js/chunk-8b555334.ef7d5111.js) 第 1 行；主请求/响应事件 4897、4901。

### 15. 角色清单导出

静态支持按平台、城市、服务中心查询员工项目角色列表并导出，表格包含项目编码、员工工号和角色，选中行使用“服务中心 ID + 系统用户 ID”组成身份键，导出按钮受显示权限控制。实际只捕获 `/web-bus/RoleListExportController/v3/pageList` 请求，未保留对应响应，不能确认列表加载成功；同控制器 `/export` 是 blob 导出候选，导出函数根据是否选中行构建范围，未执行导出。

证据：E03，事件 6012；[chunk-1a726ed1.62a92388.js](https://o2o.unee.com.cn/un-pc-fronted/js/chunk-1a726ed1.62a92388.js) 第 1 行；主请求事件 6025。

## 客户管理（2 个入口）

### 16. 客户管理

静态支持按房号、客户或手机号检索客户及房产关系，新增/修改、解除客户房产关系、查询历史房产和同步关系，显示逻辑区分户主与租户有效期；HTML 要求公司、服务中心和对应检索输入。源码注释明确取消默认查询，本次未观察业务检索，`yhqueryList/khqueryList/searchByContact` 的候选分别为 `/web-cust/mobile/queryServiceyh`、`/web-cust/mobile/queryServicekh`、`/web-cust/mobile/queryByContact`，解除/同步关系候选为 `/web-cust/custManage/delCustServ`、`/web-cust/o2o/syncCustHourseRel`。

证据：E04，事件 555、651；[CustomerList.html](https://o2o.unee.com.cn/web-cust/pc/html/Customers/CustomerList.html) 第 42–78 行；[CustomerList.js](https://o2o.unee.com.cn/web-cust/pc/html/Customers/js/CustomerList.js) 第 131–145、198–217、307–323、358–367、441–447、545–551、649–658、667、726、749–764 行。

### 17. 房产管理

静态支持按服务中心、楼栋和房号查询房产，展示面积、房产类型、入伙日期，并按权限进入使用人管理或查看；前端表单校验要求服务中心，填写房号时还检查先选楼栋。主列表候选 `/web-cust/pc/queryhourselist` 本次未观察且 `delayLoad` 为真，实际 `/web-cust/mobile/queryld` 返回 HTTP 200 属楼栋辅助加载，不能算作房产列表查询。

证据：E04，事件 801；[houseTable.js](https://o2o.unee.com.cn/web-cust/pc/html/Customers/js/houseTable.js) 第 12–62、66–95、133–173 行；[HourseList.html](https://o2o.unee.com.cn/web-cust/pc/html/Customers/HourseList.html) 第 58 行（事件 711）；楼栋请求/响应事件 866、891。

## 运营中心（6 个入口）

### 18. 公告公示

静态支持公告查询、新增、详情/编辑、评论、删除、导出以及置顶/取消置顶，实体含标题、分类、阅读数、发布方式、审核信息、失效时间、状态与打回原因，编辑跳转根据权限与状态 `1100/1000` 分支判断。主查询候选 `/web-bus/pc/procla/pcList` 本次未观察且延迟，删除 `/delProcla`、置顶 `/topProcla`、导出 `/exportData` 为同 `/web-bus/pc/procla` 控制器的未执行候选。

证据：E05，事件 613；[proclaList.js](https://o2o.unee.com.cn/web-bus/pc/html/procla/js/proclaList.js) 第 5、65–70、213–268、333–351、606–666、700–720 行。

### 19. 广告管理

静态支持广告新增、详情、修改、上下架、置顶/取消、删除、操作日志、二维码下载和第三方广告获取，操作显示依广告状态、位置及权限分支变化；上/下架预检分别由 `adOn/adOff` 请求 `/web-bus/adonoff/onCheck`、`/offCheck` 后打开处理页。主查询候选 `/web-bus/advertising/advertisingListQuery` 本次未观察且延迟，`/advertisingLower`、`/AdvertisingUpper`、`/deleteAdvertising`、`/downloadQRZip` 及 `/web-bus/mobile/thirdParty/syncThirdAdData` 均为未执行候选。

证据：E05，事件 995、991；[advertisingListLiger.js](https://o2o.unee.com.cn/web-bus/pc/html/admanage/js/advertisingListLiger.js) 第 40–241、295、471–475、540–625、645–709 行；[adonfPre.js](https://o2o.unee.com.cn/web-bus/pc/html/admanage/js/adonfPre.js) 第 1–14、47–56 行。

### 20. 便民电话

静态支持便民电话新增、详情/维护和选择后确认删除，字段包括单位、类别、电话号码，以及物品和存放地点，类别来自字典。主查询 `/web-cust/fastTelephone/telephoneListQuery` 和删除 `/web-cust/fastTelephone/deleteTelephone` 是候选，本次列表延迟未查询；`telephoneView.html` 被用作新增/详情入口，编辑表单具体校验未采集。

证据：E05，事件 1227；[telephoneList.js](https://o2o.unee.com.cn/web-cust/pc/html/fastTelephone/js/telephoneList.js) 第 12–52、157–211、315、376–388 行。

### 21. 房产交易

静态支持房产交易条目新增、修改与删除，列表字段涵盖编号、类型、客户、联系方式、户型、面积、价格及备注，删除先检查选中记录再确认。`addHouseSell/goToModify/deleteSell` 关联表单页面及删除候选 `/web-bus/pc/serv_delete_house_sell`，主查询 `/web-bus/pc/qry_house_sell_list` 本次未观察且延迟。

证据：E05，事件 1484；[houseSellList1.js](https://o2o.unee.com.cn/web-bus/pc/html/houseSell/js/houseSellList1.js) 第 6–82、116–151、262–299 行。

### 22. 社区活动

静态支持活动新增/修改、删除、发布、下架、置顶/取消置顶、评论、报名相关查看和二维码/数据导出，状态明确为 `10草稿/20待审核/30已打回/40已审核/50已发布/60已下架`；修改/删除/发布等分支还检查发起方、报名结束时间、订单数和评价数。主查询 `/web-odm/pc/qry_community_activity_list` 本次未观察且延迟，`/web-odm/pc/undercarriage`、`/isTop`、`/isNotTop` 是操作候选，服务端响应处理会再次限制非“已发布”操作。

证据：E05，事件 1824；[communityActivityList.js](https://o2o.unee.com.cn/web-odm/pc/html/communityActivity/js/communityActivityList.js) 第 5–87、197–275、305–399、522–530、600–680 行。

### 23. 议事大厅

静态支持社区议事/投票的新增、详情、修改、审核、删除、结束、投票结果、二维码及数据导出，状态为 `10草稿/20待审核/30已发布/40已结束`，按钮还受操作权限、创建者与组织/服务范围判断。主列表 `/web-cust/pc/discuss/queryDiscussList` 本次未观察且延迟，实际 `/web-cust/pc/discuss/checkUserPriv` 返回 HTTP 200 是权限初始化；状态变更 `/updateDiscussStatus`、状态复核 `/queryDiscussStatus`、二维码 `/makeQrCode` 为同控制器的候选，导出候选是 `/web-cust/pc/discussExport/excelExprort`。

证据：E05，事件 2020；[discuss_list.js](https://o2o.unee.com.cn/web-cust/pc/html/discuss/js/discuss_list.js) 第 66–94、178–222、259–335、368–417、511–619、646–662 行；权限请求/响应事件 2089、2117。

## 初始页是否实际查询主业务列表

| 入口 | 主列表初始化策略与保留网络事实 |
|---|---|
| 装修配置、图片管理、门设备管理、消息模板、问卷配置、评价二维码管理 | 静态 `delayLoad: true`；本次未观察对应主列表请求。问卷二维码配置/字典查询不等同于问卷业务列表。 |
| 手机开门推送配置、电梯管理、报告台基础配置管理、质检员点位管理、空置房配置 | 静态 `delayLoad: true`；本次未观察对应主列表请求。推送 `queryConfig` 是初始化选项；基础配置与空置房存在返回页面后查询分支。 |
| 抵扣券导入、报告台岗位管理 | 静态 `delayLoad: true`，但 ready 显式 `queryList()`；主列表请求及 HTTP 200 响应均已观察。 |
| 缴费二维码管理 | Vue 构建组件；主列表请求与 HTTP 200 已观察。 |
| 角色清单导出 | Vue 构建组件；只观察主列表请求，无保留响应，成功与否未知。 |
| 客户管理 | 非传统 grid，源码明确取消默认查询；本次未观察房号/客户/手机号检索请求。 |
| 房产管理 | 静态 `delayLoad: true`；未观察主列表，仅观察楼栋辅助查询。 |
| 公告公示、广告管理、便民电话、房产交易、社区活动、议事大厅 | 静态 `delayLoad: true`；本次未观察各自主列表。议事权限初始化与字典请求不能算作业务列表加载。 |

合计：**20 个入口的传统列表源码设置 `delayLoad: true`，其中 2 个又显式初始化查询；23 个入口中，19 个未观察主业务检索，3 个主列表请求有 HTTP 200 响应，1 个仅有主列表请求**。这只是初始页捕获覆盖，HTTP 200 不证明业务记录完整或业务语义成功；尚未验证查询按钮操作、表单字段完整校验、状态变更结果、后端授权和导出内容。
