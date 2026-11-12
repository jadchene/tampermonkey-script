# Tampermonkey Scripts

English | [简体中文](./README.zh-CN.md)

Personal userscripts for cleaner Google and Zhihu pages, plus an optional script that blocks common WebRTC APIs.

## Scripts

| Script | Runs on | What it does |
| --- | --- | --- |
| [beautify4google](./beautify4google) | `google.com`, `google.com.hk`, and their subdomains | Hides selected ads, sidebars, and footer elements; widens and centers search results; adds hover shadows. |
| [beautify4zhihu](./beautify4zhihu) | `zhihu.com` and its subdomains | Hides selected ads, navigation links, sidebars, content covers, reward areas, and the AI assistant panel; widens the main content area. |
| [Disable WebRTC IP Leak](./Disable%20WebRTC%20IP%20Leak) | HTTP and HTTPS pages where userscripts can run | Attempts to disable common WebRTC APIs at page startup. |

## Install

1. Install [Tampermonkey](https://www.tampermonkey.net/) in your browser and allow it to run userscripts on the intended sites.
2. Open a script from the table above, select **Raw**, and copy the entire file.
3. In the Tampermonkey dashboard, create a new script, replace the default code, and save.
4. Reload a matching page. Install and enable only the scripts you need.

The files have no `.user.js` extension, so use the manual installation steps above. To update a manually installed script, copy the latest file contents into its editor and save again.

## WebRTC behavior

The WebRTC script targets `RTCPeerConnection`, `webkitRTCPeerConnection`, `mozRTCPeerConnection`, and `RTCDataChannel` in the page window at `document-start`.

Blocking these APIs can break browser voice/video calls, screen sharing, and peer-to-peer transfers. Disable the script for sites that need those features, then reload the page.

This is a page-level restriction, not a guarantee against every IP leak. Its effectiveness depends on browser and userscript execution behavior; it does not replace browser privacy or proxy settings.

## Troubleshooting

- **Nothing changes:** confirm the script is enabled, the URL matches its scope, and Tampermonkey has permission to run on the site; then reload.
- **Content disappears or the layout breaks:** temporarily disable the relevant script. The Google and Zhihu scripts hide elements with CSS, including some normal page controls. Website updates and layout experiments can make selectors outdated.
- **Calls or screen sharing stop working:** disable the WebRTC script for that site and reload.

## License

[MIT](./LICENSE)
