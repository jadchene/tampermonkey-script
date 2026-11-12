# Tampermonkey Scripts

[English](./README.md) | 简体中文

自用用户脚本合集，用于精简 Google 和知乎页面，并提供可按需启用的 WebRTC API 禁用脚本。

## 脚本列表

| 脚本 | 适用范围 | 功能 |
| --- | --- | --- |
| [beautify4google](./beautify4google) | `google.com`、`google.com.hk` 及其子域名 | 隐藏部分广告、侧栏和底部元素，扩大并居中搜索结果，增加悬停阴影。 |
| [beautify4zhihu](./beautify4zhihu) | `zhihu.com` 及其子域名 | 隐藏部分广告、导航链接、侧栏、内容封面、赞赏区域和 AI 助手面板，扩大主要内容区域。 |
| [Disable WebRTC IP Leak](./Disable%20WebRTC%20IP%20Leak) | 允许用户脚本运行的 HTTP 和 HTTPS 页面 | 尝试在页面加载开始时禁用常见 WebRTC API。 |

## 安装

1. 在浏览器中安装 [Tampermonkey](https://www.tampermonkey.net/)，并允许其在目标网站运行用户脚本。
2. 打开上表中的脚本文件，点击 **Raw**，复制完整内容。
3. 在 Tampermonkey 管理面板中新建脚本，替换默认代码并保存。
4. 刷新适用的页面。按需安装和启用脚本即可。

仓库文件没有 `.user.js` 扩展名，请使用上述手动安装方式。更新手动安装的脚本时，将最新文件内容复制到对应脚本的编辑器中，再次保存。

## WebRTC 行为

WebRTC 脚本在 `document-start` 阶段，尝试禁用页面窗口中的 `RTCPeerConnection`、`webkitRTCPeerConnection`、`mozRTCPeerConnection` 和 `RTCDataChannel`。

禁用这些 API 可能影响网页语音或视频通话、屏幕共享和点对点传输。需要使用这些功能时，请为对应网站停用该脚本并刷新页面。

这属于页面层面的限制，不能保证阻止所有 IP 泄漏。实际效果取决于浏览器和用户脚本的执行方式，不能替代浏览器隐私设置或代理配置。

## 常见问题

- **没有变化：**确认脚本已启用、网址符合适用范围，且 Tampermonkey 获准在该网站运行，然后刷新页面。
- **内容消失或布局异常：**临时停用对应脚本。Google 和知乎脚本通过 CSS 隐藏元素，其中也包含部分正常页面控件；网站改版或布局实验可能导致选择器失效。
- **通话或屏幕共享不可用：**为该网站停用 WebRTC 脚本并刷新页面。

## 许可证

[MIT](./LICENSE)
