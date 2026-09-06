# Cealing-Host 转换产物

由 GitHub Actions 自动转换生成

## 📦 文件说明

| 文件 | 用途 | 数量 |
| :--- | :--- | :--- |
| cealing-domains.yaml | Clash rule-provider 域名规则 | 221 条 |
| cealing-servername.txt | SNI 伪装域名参考列表 | 25 个 |
| cealing-hosts.txt | Clash DNS hosts 配置 | 192 条 |

## 🔧 使用方法

### 1. 域名规则（rule-provider）

```yaml
rule-providers:
  cealing-block:
    type: file
    url: https://raw.githubusercontent.com/XANGPIRENNN/clash-rule-generator/main/cealing-domains.yaml
    path: ./cealing-domains.yaml
    interval: 86400
    behavior: domain

rules:
  - RULE-SET,cealing-block,PROXY  # 走代理节点
```

### 2. DNS hosts（Clash 配置）

```yaml
dns:
  enable: true
  hosts:
    # 从 cealing-hosts.txt 复制内容到这里
```

### 3. SNI 伪装域名参考

`cealing-servername.txt` 中的域名可用于 Reality 节点的 `servername` 配置。
