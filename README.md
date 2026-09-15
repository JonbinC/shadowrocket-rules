# Shadowrocket 远程规则

核心域名/IP 跟随 [blackmatrix7/ios_rule_script](https://github.com/blackmatrix7/ios_rule_script)。本仓库只维护**策略映射**到 3X-UI 节点名。

## 先分清你在哪

| 你人在 | 客户端 | 用什么 | 不要用 |
|--------|--------|--------|--------|
| **国内**（翻墙） | Clash Meta | 面板 Clash 订阅 `/c-...`（已内嵌国内向规则） | 不要把「回国」当默认节点 |
| **国内**（翻墙） | 小火箭 | 节点订阅 `/s-...` + 本仓库 `china-to-global.conf` | 不要用 `overseas-to-china.conf` |
| **海外**（回国） | 小火箭 | 节点订阅 `/s-...` + 本仓库 `overseas-to-china.conf` | 不要开「全局」硬选回国；不要用 Clash 默认规则指望回国 |
| **海外**（回国） | Clash Meta | 手动选「回国」节点访问国内站，或自建回国规则 | 面板 Clash 默认是**国内翻墙向**（CN→直连），不适合海外回国 |

人在海外却启用了「国内翻墙」规则时：国内域名会被 **DIRECT**（当地直连），选「回国」节点也进不去国内站。

## 小火箭步骤

1. 刷新 3X-UI 节点订阅，并删除旧节点。需要至少有：
   - `上海阿里｜回国直连`
   - `上海阿里｜日本出口`
2. 小火箭 → 配置 → 添加对应 `.conf` 的 raw URL → 启用。
3. **底部选「配置」**（不要「全局」）。两份配置不要同时启用。

### 配置 URL

- 海外回国：  
  `https://raw.githubusercontent.com/JonbinC/shadowrocket-rules/main/overseas-to-china.conf`
- 国内翻墙：  
  `https://raw.githubusercontent.com/JonbinC/shadowrocket-rules/main/china-to-global.conf`

## 策略说明

- `overseas-to-china.conf`：中国大陆域名/IP、B站、腾讯视频、爱奇艺、网易云、微信 → `上海阿里｜回国直连`；其余 **直连**。
- `china-to-global.conf`：广告拒绝；中国大陆/局域网直连；全球与未知流量 → `上海阿里｜日本出口`。

## 关于「回国节点 Timeout」

小火箭测延迟常走 Google。回国出口访问 Google 会被墙，**延迟球 Timeout 不代表节点挂了**。以百度/淘宝/微信能否打开为准。

## 上游与边界

`ChinaMax` 体积较大但覆盖完整。广告规则里少量 `URL-REGEX` 需 MITM；本配置不启用 MITM。

本仓库不含节点地址、订阅 token 或凭据。
