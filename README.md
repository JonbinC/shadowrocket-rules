# Shadowrocket 远程规则

这两份配置不再维护手写域名清单；核心覆盖跟随 [blackmatrix7/ios_rule_script](https://github.com/blackmatrix7/ios_rule_script) 的原生 Shadowrocket 规则集更新。此仓库只维护**策略映射**到你的 3X-UI 节点名。

## 使用前提

先刷新 3X-UI 节点订阅，确保以下节点名存在：

- `上海阿里｜回国直连`
- `上海腾讯｜日本出口`

再在 Shadowrocket 的「配置」添加对应 `.conf` URL 并启用。不要同时启用两份配置。

## 配置

- `overseas-to-china.conf`：海外回国。中国大陆域名/IP、B站、腾讯视频、爱奇艺、网易云音乐 → `上海阿里｜回国直连`；其他流量直连。
- `china-to-global.conf`：中国大陆翻墙。广告拦截，中国大陆/局域网直连，全球服务和未知流量 → `上海腾讯｜日本出口`。

## 上游与边界

`ChinaMax` 规则集较大，换来更完整的域名/IP/应用覆盖。广告规则中少量 `URL-REGEX` 需要 MITM 才能生效；本配置不启用 MITM，因此不会解密 HTTPS。

此仓库不包含节点地址、订阅 token 或任何凭据。
