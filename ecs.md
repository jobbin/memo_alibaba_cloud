#

## ECS

インスタンスタイプ
![alt](http://docs-aliyun.cn-hangzhou.oss.aliyun-inc.com/assets/pic/25374/cn_zh/1518318731933/Image%202.png)

[突发性能实例](https://help.aliyun.com/document_detail/59977.html)

- [弹性块存储三副本技术](https://help.aliyun.com/document_detail/35108.html)
- [ECS 磁盘加密](https://help.aliyun.com/document_detail/59643.html)
 * 注意点あり:数据加密状态的转换

- 本地存储 → [操作本地盘实例对本地盘数据状态的影响](https://help.aliyun.com/document_detail/63138.html#h2-u64CDu4F5Cu672Cu5730u76D8u5B9Eu4F8Bu5BF9u672Cu5730u76D8u6570u636Eu72B6u6001u7684u5F71u54CD5)
- 内网
  * 目前只要是相同地域下，SLB、云数据库RDS、OSS与ECS之间都可以直接内网互通连接使用。
  * 目前阿里云的云服务器ECS内网间，非I/O优化的实例为千兆共享的带宽，I/O优化的实例为万兆共享的带宽，没有特殊限制。由于是共享网络，因此无法保证带宽速度是不变的。
- 专有网络的IP
  * 一个专有网络类型的ECS实例上最多只能分配一个公网IP，可以是PublicIP或弹性公网IP。  <font color="red">複数NICにpublic IPをつけるのが無理ってこと(?)</font>
  * 弹性公网IP（EIP）是可以单独申请，可以绑定到没有分配PublicIP的实例，也可以从实例上解绑，绑定到另外一个实例上，还可以单独释放。  <font color="red">予めpulicIPが付けたれているInstanceにはEIPを付けられないってこと(?)</font>
  * [网卡多队列](https://help.aliyun.com/document_detail/52559.html)  irqbalance服务(?), RPS特性(?)
- [DDoS基础防护](https://help.aliyun.com/document_detail/55256.html)
  * [流量清洗](https://help.aliyun.com/document_detail/28404.html)
  * [阿里云黑洞策略](https://help.aliyun.com/knowledge_detail/40032.html)

- [云助手](https://help.aliyun.com/document_detail/64601.html)


- クラウドディスク
  * システムディスク
      * ECSインスタンスと同様なライフサイクル
      * インスタンスがリリースされるとともにリリース
  * データディスク
      * ECSインスタンスと当時に作成される場合はインスタンスがリリースされるととともにリリース
      * 単特作成も可能
      * max 16 disks / instance
- [扩容系统盘](https://help.aliyun.com/document_detail/44986.html)
  * 更换系统盘后，您手动创建的快照不受影响，您仍可以用这些快照创建自定义镜像。
<br>如果您为旧的系统盘设置了自动快照策略，而且设置了<font color="red">自动快照随云盘释放，则自动快照策略不再适用于新的系统盘，而且旧系统盘的自动快照会自动删除</font>。
  * 不能修改系统盘的云盘类型
- [扩容数据盘_Linux](https://help.aliyun.com/document_detail/25452.html)
  * 挂载在实例上的数据盘，只有当实例处于 运行中 (Running) 或 已停止(Stopped) 状态时才可以扩容。扩容这种数据盘需要在控制台上重启实例后才能使扩容后的容量生效
  * 无论数据盘的状态是 待挂载 还是 使用中，都可以执行磁盘扩容操作。
  * 需要[登录实例扩容文件系统](https://help.aliyun.com/document_detail/25452.html#concept_z11_xsh_ydb__ResizeInInstance)
- [创建快照](https://help.aliyun.com/document_detail/25455.html)
  * 创建快照期间，操作磁盘不会影响快照中的数据。
- イメージ
  * スナップショート → カスタムイメージ
      * システムディスクのみ
      * 强烈建议您在制作自定义镜像前 umount Linux实例上挂载的所有文件系统，然后再对系统盘打快照并创建自定义镜像，否则有可能造成以该自定义镜像创建的ECS实例不能启动或使用。
  * ECSインスタンス　→　カスタムイメージ
      * システムディスク(a) + データディスク(b ~ z)
  * イメージのコピー: リージョン跨ぎの共有が可能に
  * イメージの共有: アカウント跨ぎの共有が可能に
  *
- SSH
  * 一台 Linux 实例只能绑定一个 SSH 密钥对

## Important
 - [ECS で SMTP(25番ポート)を使用する際の注意事項](https://jp.alibabacloud.com/help/doc-detail/49123.htm)
