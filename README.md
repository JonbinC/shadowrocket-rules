# Shadowrocket / Clash 远程规则

**推荐全部用 `vpn.mdtero.com` 镜像**（国内可达）。

## 先分清你在哪

| 你人在 | 客户端 | 用什么 |
|--------|--------|--------|
| **国内**翻墙 | Clash Meta | `/c-...` 订阅（点评/美团已强制直连） |
| **国内**翻墙 | 小火箭 | 节点 `/s-...` + `https://vpn.mdtero.com/rules/china-to-global.conf` |
| **海外**回国 | Clash Meta | 把 `/c-` 改成 `/co-` |
| **海外**回国 | 小火箭 | 节点 `/s-...` + `https://vpn.mdtero.com/rules/overseas-to-china.conf` |

## 点评/美团说明

大众点评、美团域名常解析到**新加坡/香港 CDN**，不在中国 IP 库里。若走代理出口，国内版 App/网站会打不开。  
国内规则已把相关域名**强制直连**；请用**规则模式**，不要开「全局代理」。

## 小火箭步骤

1. 强制刷新节点订阅  
2. 配置 → 添加对应 conf → 启用，底部选「配置」

## Timeout

回国节点测延迟常走 Google，Timeout 不代表挂了。
