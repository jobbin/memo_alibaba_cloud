- NAS 提供 99.999999999% 的数据可靠性
- NAS 文件存储提供良好的协议兼容性，支持 NFS 和 SMB 协议方案

## [存储类型](https://help.aliyun.com/document_detail/61136.html)
 - 容量型 Capacity / 性能型 Performance / 极速型 Extreme

## [管理文件系统数据访问权限](https://help.aliyun.com/document_detail/27534.html)
- 在文件存储 NAS 中，权限组是一个白名单机制，通过向权限组添加规则，来允许指定的 IP 或网段访问文件系统，并可以给不同的IP或网段授予不同级别的访问权限
- 读写权限: 只读、读写
- 用户权限
  - 不限制 root 用户 (no_squash)
  - 限制 root 用户 (root_squash)
  - 限制所有用户 (all_squash)

## [跨 VPC 挂载阿里云文件存储 NAS](https://help.aliyun.com/document_detail/108665.html)

![alt](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/132139/155652958139613_zh-CN.png)

## [NAS性能测试](https://help.aliyun.com/document_detail/95501.html)