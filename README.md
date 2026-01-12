# rules-mrs
Automated TXT to MRS converter for Mihomo rules

3. **获取 MRS 文件**：
   - 直接下载：https://github.com/你的用户名/项目名/raw/main/[filename].mrs
   - CDN 代理（推荐）：https://cdn.jsdelivr.net/gh/你的用户名/项目名@main/[filename].mrs

## 在 Mihomo 配置中使用

对于每个 MRS，在 `config.yaml` 的 `rule-providers` 中引用（类型需匹配判断结果）：

```yaml
rule-providers:
  adblock-rules:  # 来自 filter.txt
    type: http
    behavior: domain
    format: mrs
    url: "https://cdn.jsdelivr.net/gh/你的用户名/项目名@main/filter.mrs"
    path: ./filter.mrs
    interval: 86400
  geoip-rules:  # 来自 geoip.txt
    type: http
    behavior: ipcidr
    format: mrs
    url: "https://cdn.jsdelivr.net/gh/你的用户名/项目名@main/geoip.mrs"
    path: ./geoip.mrs
    interval: 86400
