
DNS(CNAME) → WAF → ECS
DNS(CNAME) → WAF → SLB → ECS

[放行WAF回源IP段](https://help.aliyun.com/document_detail/45254.html)

![alt](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/15547/15331809027576_zh-CN.png)

- 购买Web应用防火墙后，把域名解析到Web应用防火墙提供的CNAME地址上，并配置源站服务器IP，即可启用Web应用防火墙。启用之后，您网站所有的公网流量都会先经过Web应用防火墙，恶意攻击流量在Web应用防火墙上被检测过滤，而正常流量返回给源站IP，从而确保源站IP安全、稳定、可用。
- 支持负载均衡：以集群方式提供服务，多台机器负载均衡，支持多种负载均衡策略。
- 清洗服务可用性高达99.99%。
- 网站域名正式接入WAF防护后，您可以使用X-Forwarded-For的方式来获取访问者真实IP。
- <font color="red">MX记录和CNAME记录是互斥的</font>。如果您的网站域名必须保留MX记录，可以通过使用A记录指向WAF的IP来接入WAF防护。通过对WAF分配的CNAME地址使用Ping命令可以获取所分配的WAF IP，然后将A记录类型的解析记录中的记录值修改为该WAF IP。
<br>说明：如果您采用A记录方式将网站域名接入WAF防护，WAF将无法进行故障集群调度和故障bypass操作。
- WAF支持最多20个源站IP
- 添加源站IP后，您需要指定负载均衡算法：IP hash、轮询。
  * 使用IP HASH时，如果源IP不够分散，可能会出现负载不均。

- [Web应用攻击防护](https://help.aliyun.com/document_detail/43440.html)
  * 模式: 防护/预警
    * 防护:发现攻击后直接阻断. 预警:发现攻击后只告警，不阻断
  * 防护规则策略: 宽松/正常/严格

- [恶意IP惩罚](https://help.aliyun.com/document_detail/58035.html)
  * Malicious IP Penalty
- [精准访问控制](https://help.aliyun.com/document_detail/42780.html)
- [防敏感信息泄露](https://help.aliyun.com/knowledge_detail/53966.html)
  * 防敏感信息泄露通过检测响应页面中是否带有身份证号、手机号、银行卡号等敏感信息，发现敏感信息匹配命中后，根据所设置的匹配动作进行告警或者过滤敏感信息。其中，敏感信息过滤动作以*号替换敏感信息部分，从而达到保护敏感信息的效果。

- [风险预警报表](https://help.aliyun.com/document_detail/48707.html)
  * <font color="red">风险预警提供基于阿里云大数据分析和攻击溯源能力的黑客画像功能</font>。该功能对在您的网站进行过踩点、扫描、攻击等恶意行为的黑客进行标识和记录，标记出的黑客都是现实中具有真实身份的个人或组织。
