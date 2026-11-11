# 页面专用脚本内容缺口核查

9 份原始模块采集中有 381 条脚本响应内容未取得，涉及 44 个不同路径。排除公共库和通用界面工具后，有 0 条页面目录脚本内容缺口；未归属脚本为 0 条。

## 页面目录脚本缺口

| 菜单ID | 模块 | 功能 | 页面专用脚本 | HTTP | 内容未取得原因 |
| --- | --- | --- | --- | --- | --- |

评价二维码管理 menu_id=5121 的 `/web-bus/pc/html/scanEvaluate/qrCode/js/viewer_default.js` 位于页面目录，但相同路径被装修配置、问卷配置、广告管理及评价二维码管理四个菜单 HTML 引用。已有 request-124、request-328 的 200 响应版本只定义包装 window.Viewer 的 initViewer 图片预览函数，属共享界面初始化工具。request-390 的 304 响应内容仍然未取得，不能用其他事务内容声明其字节一致；缺口保留在 JSON 的独立条目中。

## 原因与公共库范围

380 条未取得内容是 HTTP 304 的 body-read-failed；1 条是 HTTP 404 的 request-failed。304 表示缓存校验响应，REA 未取得这些事务的缓存内容，不表示浏览器没有执行相应脚本。380 条具体错误信息均为 `response.body: Response body is unavailable for redirect responses`；另 1 条为 `net::ERR_ABORTED`（`/pc/js/jquery.placeholder.js`）。

公共库与通用工具共 381 条：jQuery 及插件、LigerUI、artDialog、My97DatePicker、niceValidator、viewerjs，以及 esmp_base、common、taskCommon、日期格式化、表格高度调整、进度和通用表格工具。dateFormat 与 resetTableHeight 虽位于 work 目录，HTML 引用证实它们跨菜单共用。

排除目录中的共享图片预览初始化工具后，没有发现专属业务脚本未取得内容的记录。这只针对已观察到的脚本响应，不证明动态脚本或整个系统源码完整。完整逐事务路径、原因、来源及 HTML 引用菜单ID见 [结构化缺口核查](/Volumes/MOVESPEED/Projects/uni-rea/does/page-script-gaps.json)。本核查没有使用其他 URL 或共享库内容填补原始事务的缺口。

## 评价二维码补采的实际目标

定向补采进入 `/sso/login.html` 登录页，module_3_open 失败，后续评价二维码步骤均取消。页面检查 `ev_82209f9d27dee9e2a2ca98f34a8b59563029f6bb01ad727c2f7d87365741cda6` 属于登录页，不是二维码页面；它没有返回 viewer_default 匹配脚本不能证明目标脚本不存在，也没有弥补原始二维码事务的内容缺口。原九模块证据与统计保持独立。

## 星海图和消息通知的内联脚本

星海图 HTML 的 151 字符内联脚本定义 goReport，以显式 http 协议、当前 hostname 和 port 拼接 `/web-report/pc/html/viewport/viewport.html`，再调用 window.open。这里只确认静态导航字面路径，没有打开目标或执行代码。

消息通知 HTML 的 110 字符内联脚本通过 document.write 声明 `./js/noticeList.js?v=` 加随机数。原 src 枚举遗漏了该动态加载声明，现在单列静态加载候选并关联 module-09 的 request-363 实际脚本请求 `/portal/notice/js/noticeList.js`。已分析捕获内容，不执行内联脚本；逐段摘要与 HTML Evidence 来源见 [功能分析 JSON](/Volumes/MOVESPEED/Projects/uni-rea/does/features-analysis.json) 的 inline_script_observations。
