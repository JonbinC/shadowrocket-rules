# 彼岸 · Beyond — 远程规则

**推荐全部用 `vpn.mdtero.com` 镜像**（国内可达，不直连 GitHub）。

## 先分清你在哪

| 你人在 | 客户端 | 用什么 |
|--------|--------|--------|
| **国内**翻墙 | Clash Meta | `/c-...` 订阅 |
| **国内**翻墙 | 小火箭 | 节点 `/s-...` + `https://vpn.mdtero.com/rules/china-to-global.conf` |
| **海外**回国 | Clash Meta | 把 `/c-` 改成 `/co-` |
| **海外**回国 | 小火箭 | 节点 `/s-...` + `https://vpn.mdtero.com/rules/overseas-to-china.conf` |

## 节点名（与订阅一致，只会出现你开通的节点）

- 🇺🇸 美西 · LA 直连
- 🇯🇵 东京 · 直连
- 🇯🇵 东京 · IX
- 🇯🇵 东京 · IX 备用
- 🇺🇸 美西
- 🇸🇬 新加坡
- 🇨🇳 回国 · 阿里
- 🇨🇳 回国 · 腾讯

规则里不写死节点名，开通哪些节点都不会报错：

- 小火箭：走 App 首页**当前选中的节点**。国内随便选一个海外节点；海外回国请选 **回国 · 阿里 / 腾讯**。
- Clash `/c-`：`PROXY` 分组包含你开通的全部节点，默认第一个。
- Clash `/co-`：`🇨🇳 回国` 分组默认阿里，可切腾讯；没开回国节点时为直连。

## 规则来源

规则全部直接使用 GitHub 上的成熟规则集，不做自定义：小火箭用 [blackmatrix7/ios_rule_script](https://github.com/blackmatrix7/ios_rule_script)，Clash 用 [Loyalsoldier/clash-rules](https://github.com/Loyalsoldier/clash-rules)，由 `vpn.mdtero.com` 每日同步镜像。请用**规则模式**，不要开「全局代理」。

## 小火箭步骤

1. 强制刷新节点订阅  
2. 配置 → 添加对应 conf → 启用，底部选「配置」

## Timeout

回国节点测延迟常走 Google，Timeout 不代表挂了。
