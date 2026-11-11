# 星海图大屏：指标分块、筛选与读取机制

## 证据范围

- 已观察页面：`/web-report/pc/html/viewport/viewport.html`。
- 场景 Evidence：`ev_fd14e31e863deaa274c4a5a04617a991386bb19b7e97b8fc4a2a887699ea5410`，文件 `evidence/supplement-viewport-scenario.json`（E1）；场景持续 5,108 ms，完整性标记 incomplete / missing_sections=events。
- 页面及脚本 Evidence：`ev_a061d81e147a52e6614d0b9f3dcaedda6874f3c6cf89e1a1e31a658e0f22fed8`，文件 `evidence/supplement-viewport-inspection.json`（E2）。
- 本章节仅离线读取这两份材料，未连接浏览器/API、选择组织/月度或执行钻取。没有在报告中展示运营指标、记录行、认证值、地图坐标或 Baidu AK 值。
- HTTP 200 是初始化读取观察；指标真实性、完整性、服务端聚合与权限覆盖并未因此得到验证。

## 分块功能与数据来源

源码 V：`https://o2o.unee.com.cn/web-report/pc/html/viewport/js/viewport.js`；行号来自 E2 `scripts.items[8].source.artifact.text`。

| 功能块 | 源码事实 | 位置 / 未知 |
| --- | --- | --- |
| 注册、在线、本月新增、活跃、留存 | `queryViewportUserInfo` 将 register_count、online_count、this_month_add_count、month_active_rate、month_retention_rate 直接写入对应 DOM。 | V L12–37；活跃/留存分母、在线判定、用户去重规则都在后端，未见前端计算。 |
| 项目覆盖 | `queryViewportProjectInfo` 显示 online_project_count、this_month_add_count、this_month_online_count、cover_org_count、cover_city_count。请求只含月份和 org_id，不传 service_id。 | V L40–61；“上线/覆盖”判定与组织层级归属未验证。 |
| 项目满意度 | `queryViewportScoreInfo` 使用 this_month_score1/2、score_percent1/2；负号驱动向下箭头，其他值向上，当前分数追加百分号；`roundEcharts` 以“事件评价/月度评价”画双环。 | V L64–105、L1053–1193；指标基准、样本量和变化比率计算未验证。 |
| 投诉量 | `queryViewportMatterInfo` 的 this_month_count1 与变化 count_percent1、序列 this_month_arr1/monthStr 生成卡片和曲线。 | V L108–150，curveEcharts1 L777–912；页面静态标签明确为投诉量，变化基准与事件去重未知。 |
| 入户维修 | 同一 matter 接口使用 this_month_count2、count_percent2、this_month_arr2/monthStr；第二曲线为入户维修。 | V L108–150，curveEcharts2 L915–1050；维修类型范围、计数和完成状态未知。 |
| 效率 | `queryViewportEfficiencyInfo` 将 efficiency_value1/2 和 max_efficiency_value1/2 传入仪表；仪表最大值也由服务器给出。 | V L154–178、L547–765；仪表1源码 name 为“接单响应及时率”，但 detail 单位写“小时”，存在标签/单位不一致，业务含义须另证。仪表2为“平均处理时长”。 |
| 公区报事来源 | `queryViewportMatterPublicInfoBySource` 用 list 中 matter_source 与 this_month_count；源码 code=1 显示“业主”，其他来源显示“员工”。 | V L180–266，pieEcharts1 L464–505；非1统一归员工是渲染事实，不能证明后端只有两类。 |
| 公区报事类型 | `queryViewportMatterPublicInfoByType` 将 matter_type 与 this_month_count 映射电梯、强电、消防、弱电、给排水、土建、杂项。 | V L268–462、L509–544；业务分类完整性和未知类型处理未验证。 |

前端仅做展示计算：曲线轴最大值取数组最大值乘 1.5（`getMaxData`，V L1262–1270）；曲线点由 monthStr 与相同序号的数组值配对（formatPointData，L769–775）。满意度双环把原分数缩放至 80% 的图形弧段，并补齐占位弧（L1055–1058），这是图形布局，不是重新计算满意度；饼图 tooltip 使用 ECharts 的 `{d}%`，真实计数仍来自服务器。

## 月份、组织和项目筛选及地图钻取

- `getYearAndMonth` 默认浏览器本月，用“YYYY年MM月”填 data_month，并生成包含本月的连续 12 个月选项（V L1197–1231）；`doSelClick` 更新该字段并重新查询全部 7 类指标（L1233–1246）。这是源码机制，本次没有实际切换月份。
- 地图和模糊查询共用 `/web-report/pc/viewport/getOrginOrService`，源码函数名保持 Orgin 拼写。组织输入候选传 org_name/parm；项目候选传 org_id/service_name（地图源码 M L53–72；下拉辅助 `common.js initAutoCompSel2` L29–173）；候选 name 和 ID 分开存。
- 地图 M：`https://o2o.unee.com.cn/web-report/pc/html/viewport/baiduMap.js`。`orgMaker` 初始化组织点；组织点点击设置 org_id/org_name，切换到项目选择、调用 serviceMaker 和 queryDateByMap(org_id)；项目点点击调用 queryDateByMap(org_id, project ID)；悬停显示名称提示（M L75–144）。
- `queryDateByMap` 保存选中范围到 org_ids/service_ids，再刷新全部指标（V L1249–1258）。未选范围时各请求把 org_id/service_id 转为源码哨兵 `-1`，实际后端对哨兵的范围解释未验证；项目覆盖接口始终只接受 org_id。
- `searchButton` 是返回全局地图动作：清空组织/项目选择、恢复组织点、调用 queryDateByMap()（M L40–49）。当前证据证明组织→项目的指标范围钻取候选，不证明能从指标卡直接打开业务明细。
- 地图数据字段包含坐标及 ID/NAME，代码将坐标转为 Marker；本报告不展示点位或坐标值。地图渲染和地理准确性未额外核验。

## 实际读取请求

来自 E1 的事务；所有 query 参数列表为空，body 字段名按原样保留。

| transaction / response sequence | method / status | 路径 | body 参数名称 |
| --- | --- | --- | --- |
| request-21 / 233 | POST / 200 | `/web-report/pc/viewport/queryViewportUserInfo` | data_month, org_id, service_id |
| request-22 / 190 | POST / 200 | `/web-report/pc/viewport/queryViewportProjectInfo` | data_month, org_id |
| request-23 / 226 | POST / 200 | `/web-report/pc/viewport/queryViewportScoreInfo` | data_month, org_id, service_id |
| request-24 / 357 | POST / 200 | `/web-report/pc/viewport/queryViewportMatterInfo` | data_month, org_id, service_id |
| request-25 / 234 | POST / 200 | `/web-report/pc/viewport/queryViewportEfficiencyInfo` | data_month, org_id, service_id |
| request-26 / 193 | POST / 200 | `/web-report/pc/viewport/queryViewportMatterPublicInfoBySource` | data_month, org_id, service_id |
| request-27 / 211 | POST / 200 | `/web-report/pc/viewport/queryViewportMatterPublicInfoByType` | data_month, org_id, service_id |
| request-30 / 242 | GET / 200 | `/web-report/pc/viewport/getOrginOrService` | not_exposed |

POST 正文为 captured；GET 的 not_exposed 不能严格证明没有正文。请求收取顺序不等于指标之间的因果链；本次只观察首次初始化，没有覆盖筛选后的响应或刷新后的范围。可复用无值索引：`derived-viewport/request-index.json`。

## 自动刷新及其静态限制

V L1–9 在 ready 时先初始化月份并查询全部指标，随后对满意度、投诉/维修、效率、公区来源和公区类型设置 5 分钟 interval；用户信息和项目覆盖没有对应 interval。

这些 interval 调用查询函数时**没有传 org_ids/service_ids**，而这些函数的空参数分支会转为 `-1` 范围，源码没有在查询函数中回读选中的全局范围。因此，组织/项目筛选后下一次定时刷新可能让部分卡片回到默认范围，同时其他两块保留旧范围；这是静态范围传递缺口，本次观察不到 5 分钟后刷新，尚未复现用户可见影响。月份字段则每次查询都会读取当前 data_month。

`findMaker` 还包含 `if(mdata.color="green")` 的赋值形式（M L169–173），与比较意图不同；这里只记录静态不一致，不声称地图选择错误已复现。图表每次 `echarts.init` 后 setOption，当前源码未见这些函数内的网络重试、取消、错误展示或更新时间水印，不能据此断言整体系统没有这些机制。

## 身份和待验证清单

| source | E2 script index / SHA-256 |
| --- | --- |
| M baiduMap.js | 0 / `b9e32f2ec54e5cd8ecf13bb124310f08152851e62dd62efdf2de6efee59d6b73` |
| V viewport.js | 8 / `1e6550d4795e22908f0756afe327c5d7b9985e79ce33e71385e5bb97cb41d07f` |
| viewport/js/common.js | 6 / `a08bdf743c743636e42bbf565815804d3af98dbfc9fc2bd2c2b5d1984ec48754` |

已回答：初始化读接口、参数名、8 组可见业务信息的前端绑定、筛选/地图范围机制、图形计算与定时刷新源码。

未验证：实际组织/月度/项目切换、5 分钟刷新、数据权限范围、指标统计口径/分母/去重、投诉维修状态与完结口径、响应指标单位、留存/活跃公式、图表与后台账本一致性、坐标准确性及后端代码。真实运营数字不属于本报告展示内容。
