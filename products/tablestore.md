
データ耐久性99.99999999%（10个9）
SLA: 99.9%
强一致性
 - 表格存储保证数据写入强一致，并保证数据 3 副本均写入磁盘且数据最终将在所有存储位置中保持一致

TTLあり

[读/写吞吐量](https://help.aliyun.com/document_detail/27284.html)
  - CU （Capacity Unit）
    * 1 单位读能力表示从数据表中读一条 4 KB 数据
    * 1 单位写能力表示向数据表写一条 4 KB 数据。
    * 预留读/写吞吐量あり

Table Store Stream → Lambda 連携

最多可设置 4 个主键，主键的配置及顺序一旦设置便不可修改。

VPCのバインド

[キーの設計](https://help.aliyun.com/document_detail/27356.html)
  - ゼロ埋めと「,」の利用
