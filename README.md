# Tampermonkey Scripts

个人使用的 Tampermonkey 用户脚本合集，主要用于网页样式精简、广告元素隐藏及 WebRTC 隐私防护。

## 脚本列表

| 脚本 | 适用网站 | 功能 |
| --- | --- | --- |
| [beautify4google](./beautify4google) | Google、Google 香港 | 隐藏广告、侧栏和底部元素，调整搜索结果宽度及居中布局，增加悬停效果 |
| [beautify4zhihu](./beautify4zhihu) | 知乎 | 隐藏广告、侧栏、视频回答、推荐内容和 AI 助手等元素，扩大主要内容区域 |
| [Disable WebRTC IP Leak](./Disable%20WebRTC%20IP%20Leak) | 所有网站 | 禁用页面中的常见 WebRTC API，降低 WebRTC 暴露本地或代理外 IP 的风险 |

## 安装方法

1. 在浏览器中安装 [Tampermonkey](https://www.tampermonkey.net/)。
2. 打开仓库中需要安装的脚本文件。
3. 点击右上角的 **Raw** 查看原始内容。
4. 复制全部代码。
5. 打开 Tampermonkey 管理面板，选择“添加新脚本”。
6. 替换编辑器中的默认内容并保存。

## 脚本说明

### beautify4google

适用于：

- `google.com`
- `google.com.hk`

主要功能：

- 隐藏搜索广告、右侧栏和底部区域
- 扩大搜索结果内容宽度
- 调整页面布局，使搜索结果居中
- 为搜索结果增加鼠标悬停阴影效果

### beautify4zhihu

适用于所有知乎页面。

主要功能：

- 隐藏侧栏和广告内容
- 隐藏视频回答、推荐搜索及部分商业内容
- 隐藏关注按钮、赞赏区域和 AI 助手面板
- 扩大首页、问题、搜索及个人主页的主要内容区域

### Disable WebRTC IP Leak

在所有网站加载开始阶段禁用以下 WebRTC API：

- `RTCPeerConnection`
- `webkitRTCPeerConnection`
- `mozRTCPeerConnection`
- `RTCDataChannel`

> [!WARNING]
> 启用后，可能导致网页视频通话、语音通话、屏幕共享、P2P 文件传输等依赖 WebRTC 的功能无法正常使用。  
> 该脚本只能阻止网页使用常见 WebRTC API，不能替代浏览器自身的隐私设置、防火墙或代理软件配置。

如果某个网站必须使用 WebRTC，可以在 Tampermonkey 中为该网站临时禁用此脚本。

## 注意事项

- 脚本依赖网页元素的 CSS 类名，网站改版后可能需要更新。
- Google 和知乎可能对不同账号、地区或页面启用不同布局，部分规则不一定始终生效。
- 建议按需启用脚本，出现页面显示异常时先临时关闭对应脚本进行排查。
- 本项目中的脚本主要用于个人使用，请根据自己的浏览器环境调整。
