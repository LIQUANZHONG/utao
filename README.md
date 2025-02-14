## 电视端看电视直播和解决爱奇艺等平台投屏问题
**专为电视投影等大屏设备设计的一个第三方浏览器 可绕过某些平台限制 让用户在电视上更便捷和低成本的观看视频**
###  官网 [utao.tv](https://www.utao.tv)
- 天下苦秦久矣  望不再有平台霸权
### **一、解决哪些痛点？**
1. **投屏限制**：许多平台（如爱奇艺）要求开通电视端会员才能投屏高清内容，而油桃TV通过内置浏览器直接访问视频网站，用普通会员账号即可在电视播放1080P视频。
2. **会员分级收费**：无需额外购买电视版会员，手机/PC端会员可直接在电视端使用。
3. **操作适配**：适配电视端常规遥控操作，支持全屏播放、选集、倍速等操作。
4. **可看电视直播**：同时适配了CCTV和各大地方台直播

### **二、核心功能**
- **直接访问网页版视频平台**：如爱奇艺、腾讯视频、B站、优酷等，适配扫码登录账号后可直接观看。
- **自动全屏播放**：进入视频页面自动全屏，减少操作步骤。
- **遥控器友好**：适配方向键、确认键等基础操作，支持进度调整、清晰度切换。
- **免费无广告**：软件本身不收费，也无插入广告（但视频平台自身的广告可能存在）。
- **基于浏览器插件机制实现**： 故后续也可方便兼容谷歌插件 用浏览器插件或Electron 可实现PC主机连接电视后便捷操作

### **三、适用场景**
- 家里有智能电视或盒子（安卓系统），想省去电视端会员费用。
- 习惯用手机/PC会员，但希望大屏观看，不愿受投屏限制。

![首页](img/home.jpg)
![demo](img/demo.jpg)
### **四、局限**
- 如今视频为了防盗链和迭代是越做越复杂 腾讯和爱奇艺平台在性能不好的机器上会卡
- 爱奇艺和腾讯页面请求数过多 会卡 平台如何优化是个大问题
- 测试平台流畅度 央视网==百视通》芒果》优酷》西瓜》哔哩》》爱奇艺》腾讯
- 此方案需要一定的电视或盒子性能 版本最好安卓9及其以上
- 安卓4浏览器内核版本低 百视通和江苏地方台一些兼容问题是打不开的

### 已知难点问题
- 火狐版在我的天猫魔盒上 CCTV直播有声音问题 西瓜视频打不开  腾讯视频声音不自动
- x5浏览器内核 安卓4下 基本只能看直播和央视频 其他平台都有些兼容问题 比如百视通会报错 江苏卫视提示没有replaceAll()

### 开源代码说明
1. android/x5 为内核版本为X5浏览器实现
2. web/tv-web 为主要逻辑代码 基于火狐插件实现 适配简化版实现在X5浏览内核/webview内核上
3. android/gecko 为火狐版实现 基本等同与火狐插件
### 特别声明
1. 适配平台均为正规正版资源发行平台  不得代码被修改适配不正规平台
2. 由于某些既存的规定 这软件不会收费 也不会商业化 除非不合理规定不再存在 
### 如何开发迭代
1. 由于基于火狐插件开发 故参考[火狐插件开发](https://developer.mozilla.org/zh-CN/docs/Mozilla/Add-ons/WebExtensions/Build_a_cross_browser_extension)
2. 项目根目录 执行web-ext run 每次执行是个全新浏览器 每个平台无法自动播放 需手动处理下 可以进爱奇艺平台(iqiyi.com)跳出登录二维码后按Q进主页
3. 爱奇艺和腾讯页面请求数过多 会卡 平台如何优化是个大问题
### todolist
- UI待优化(>-<)
- 兼容火狐内核 实现机制是火狐插件 但开发中优先了X5 已经不兼容了 后续再兼容火狐
- 搜索还未实现 对应的移动端网页或该应用内遥控器搜索实现
- 通用版浏览器飞鼠实现 不过肯定不能遥控器一点一点按 也太难用了

### ps 为何叫油桃
优酷+桃厂 企鹅加不进去了(>-<)


### Star History

[![Star History Chart](https://api.star-history.com/svg?repos=VonChange/utao&type=Date)](https://star-history.com/#VonChange/utao&Date)
