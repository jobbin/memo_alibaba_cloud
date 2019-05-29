
![alt](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/13979/4440_zh-CN.png)

- DNAT功能
  * 将一个公网IP映射给专有网络中的ECS。配置后，公网IP收到的数据将按照自定义的映射规则，转发给专有网络内的ECS实例。
- SNAT功能
  * 为专有网络中无公网IP的ECS实例提供访问互联网的代理服务
  * 以**交换机为粒度**进行SNAT规则配置

- 若某台持有公网IP的ECS实例（比如已经绑定了EIP）发起互联网访问时，会优先使用其持有的公网IP，而不会使用NAT网关的SNAT功能。

- [NAT网关规格](https://help.aliyun.com/document_detail/42757.html)

- SLA: 99.95%

# 制限
 - 一个VPC只能配置一个NAT网关
 - 一个NAT网关最多绑定20个EIP，可提交工单申请更多配额
 - 当VPC内无公网IP的ECS实例通过NAT网关访问公网上同一个目的IP和端口的带宽大于2Gbps时，建议您为NAT网关绑定4-8个公网IP并构建 [SNAT IP池](https://yq.aliyun.com/articles/533821)，避免单个公网IP的端口数量限制可能产生的丢包

# 最佳实践

 - [创建SNAT IP地址池](https://help.aliyun.com/document_detail/118491.html)
    * **OpenAPI Explorerで CreateSnatEntry を利用**

