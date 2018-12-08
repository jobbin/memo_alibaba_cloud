![slb](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/4091/1537429265936_zh-CN.png)

提供5Gbps的防DDOS攻击能力

## [基础架构](https://help.aliyun.com/document_detail/27544.html)
提供四层（TCP协议和UDP协议）和七层（HTTP和HTTPS协议）的负载均衡服务。
- 四层采用开源软件LVS（Linux Virtual Server）+ keepalived的方式实现负载均衡
- 七层采用Tengine实现负载均衡
  * Tengine是由淘宝网发起的Web服务器项目，它在Nginx的基础上，针对有大访问量的网站需求，添加了很多高级功能和特性。

### [绑定EIP](https://help.aliyun.com/document_detail/86105.html)

可以为专有网络类型的SLB实例绑定一个EIP

## [监听介绍](https://help.aliyun.com/document_detail/85943.html)
HTTP
- 基于Cookie的会话保持
- 使用X-Forward-For获取源地址

## [健康检查介绍](https://help.aliyun.com/document_detail/85958.html)
负载均衡健康检查使用的地址段是100.64.0.0/10(阿里云保留地址)

七层监听的检查机制
- 向后端ECS的内网IP+【健康检查端口】+【检查路径】发送HTTP HEAD请求
![七层监听的检查机制](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/4137/15326195972543_zh-CN.png)

TCP监听健康检查机制
- 向后端ECS的内网IP+【健康检查端口】发送TCP SYN数据包 → 后端返回SYN+ACK数据包
![TCP监听健康检查机制](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/4137/15326195972549_zh-CN.png)

UDP监听健康检查
- 向后端ECS的内网IP+【健康检查端口】发送UDP报文
- 如果后端ECS相应端口未正常监听，则系统会返回类似返回 port XX unreachable的ICMP报错信息; 反之不做任何处理。
![UDP监听健康检查](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/4137/15326195972566_zh-CN.png)

<font color="red">只有HTTP和HTTPS监听支持关闭健康检查。UDP和TCP监听无法关闭健康检查。</font>

### [配置访问控制策略组](https://help.aliyun.com/document_detail/85978.html)

可以针对不同的监听配置不同的访问控制策略（白名单或黑名单）








.
