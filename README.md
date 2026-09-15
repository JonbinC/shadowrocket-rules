# Shadowrocket / Clash 远程规则

核心域名/IP 跟随 [blackmatrix7/ios_rule_script](https://github.com/blackmatrix7/ios_rule_script) 与 [Loyalsoldier/clash-rules](https://github.com/Loyalsoldier/clash-rules)。  
**推荐用 `vpn.mdtero.com` 镜像**（国内可达，不直连 GitHub）。

## 先分清你在哪

| 你人在 | 客户端 | 用什么 |
|--------|--------|--------|
| **国内**翻墙 | Clash Meta | 面板 Clash 订阅：`/c-...` |
| **国内**翻墙 | 小火箭 | 节点 `/s-...` + 下面「国内翻墙」规则 URL |
| **海外**回国 | Clash Meta | 把订阅里的 `/c-` **改成 `/co-`**（其余路径不变） |
| **海外**回国 | 小火箭 | 节点 `/s-...` + 下面「海外回国」规则 URL |

## 规则 URL（走 vpn.mdtero.com）

### 小火箭

- 国内翻墙：`https://vpn.mdtero.com/rules/china-to-global.conf`
- 海外回国：`https://vpn.mdtero.com/rules/overseas-to-china.conf`

### Clash

- 国内：订阅原样 `/c-<token>/<subId>`（规则已镜像到本域）
- 海外：`/co-<token>/<subId>`（自动改成：中国流量 → `上海阿里｜回国直连`，其余直连）

GitHub raw 仍可用，但国内可能很慢：

- `https://raw.githubusercontent.com/JonbinC/shadowrocket-rules/main/china-to-global.conf`
- `https://raw.githubusercontent.com/JonbinC/shadowrocket-rules/main/overseas-to-china.conf`

## 小火箭步骤

1. 刷新节点订阅，确认有 `上海阿里｜回国直连`、`上海阿里｜日本出口`
2. 配置 → 添加对应 conf URL → 启用
3. 底部选「配置」（不要「全局」）

## 策略说明

- 海外回国：中国站/影音/微信 → `上海阿里｜回国直连`；其余直连
- 国内翻墙：中国/局域网直连；其余 → `上海阿里｜日本出口`

## 关于 Timeout

回国节点测延迟常走 Google，Timeout **不代表挂了**。以百度/微信为准。

本仓库不含节点地址或订阅 token。
