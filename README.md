# clash-rules
自用clash规则集

## 文件

| 文件 | 用途 | Clash 配置 |
|---|---|---|
| `direct.list` | 强制直连的域名 | `RULE-SET,direct,🏠 私有网络` |
| `proxy.list` | 强制走节点的域名 | `RULE-SET,proxy,🚀 节点选择` |

两个文件都是 `behavior: classical`、`format: text`，一行一条规则，写法同 Clash 的 rules。

```yaml
rule-providers:
  direct: {type: http, behavior: classical, format: text, url: "https://raw.githubusercontent.com/doveppp/clash-rules/main/direct.list", path: ./ruleset/direct.txt, interval: 86400}
  proxy: {type: http, behavior: classical, format: text, url: "https://raw.githubusercontent.com/doveppp/clash-rules/main/proxy.list", path: ./ruleset/proxy.txt, interval: 86400}

rules:
  - RULE-SET,direct,🏠 私有网络
  - RULE-SET,proxy,🚀 节点选择
```
