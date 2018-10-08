
# [产品概述](https://help.aliyun.com/document_detail/27414.html)

![Queue](http://docs-aliyun.cn-hangzhou.oss.aliyun-inc.com/assets/pic/27414/intl_en/1489471777368/Screen%20Shot%202017-03-14%20at%202.09.01%20PM.png)
消息服务提供了两种模型：
 - 队列模型
   * 队列模型支持一对一发送和接收消息
 - 主题模型
   * 主题模型支持一对多发布和订阅消息，并且支持多种消息推送方式。

队列模型特性
  - 普通队列、延迟队列、优先级队列等多种队列模式
  - 确保某条消息在取出之后的特定时间段内，无法被其他消费者获得。
  - 在消息有效期内，确保消息至少能被成功消费一次

主题模型简介
  - 提供一对多的发布订阅以及消息通知功能
    * 推送到用户指定 HttpServer
    * 推送到用户指定的 Queue（用户可以从该 Queue 拉取消息）
    * 推送到邮件（组）
    * 推送到短信（列表）(仅中国地区)
    * WebSocket方式推送（即将支持）
    * 移动推送（计划支持）

![Topic](http://docs-aliyun.cn-hangzhou.oss.aliyun-inc.com/assets/pic/27414/intl_en/1489473774057/Screen%20Shot%202017-03-14%20at%202.42.35%20PM.png)

# [产品优势](https://help.aliyun.com/document_detail/27416.html)

消息三份拷贝，可靠性 99.99999999%(10个9)
服务可用性高达99.9%

## [消息服务 MNS 和消息队列 MQ 产品对比](https://help.aliyun.com/document_detail/27437.html)

MSQ
- 支持长轮询
- 消息优先级
- Pull，Push

[OSS 事件通知](https://help.aliyun.com/document_detail/52996.html)

[Queue推送](https://help.aliyun.com/document_detail/27434.html)

最佳实践
  - [广播拉取消息模型](https://help.aliyun.com/document_detail/34483.html)
  - [长轮询（LongPolling）](https://help.aliyun.com/document_detail/34478.html)
  - [严格保序队列]()
