
- CDN 回源暂不支持 SNI。
- CDN HTTPS安全加速只支持 PEM 格式的证书
  * 其他格式需转换成 PEM格式
- 开启HTTP/2前，请确保HTTPS的证书已经配置成功。
- 配合使用cdn提供的refer防盗链功能，鉴权等功能，有效保护资源安全。

- アクセス制限
  * [防盗链](https://help.aliyun.com/document_detail/27134.html)
    * 防盗链功能支持<font color="red">黑名单或白名单机制</font>
  * IP黑名单https://help.aliyun.com/document_detail/85117.html
  * [URL鉴权](https://help.aliyun.com/document_detail/85117.html)
    * A: ``http://DomainName/Filename?auth_key=timestamp-rand-uid-md5hash``
    * B: ``http://DomainName/timestamp/md5hash/FileName``
    * C: <br>Format1: ``http://DomainName/{<md5hash>/<timestamp>}/FileName`` <br> Format2: ``http://DomainName/FileName{&KEY1=<md5hash>&KEY2=<timestamp>}``
- [日志下载](https://help.aliyun.com/document_detail/27142.html)
  * 日志文件延迟4小时，可以在日志管理模块查询到4小时之前的日志文件。
  * 日志文件按小时粒度分割
  * 支持 1月 的日志数据下载
- [缓存](https://help.aliyun.com/document_detail/27140.html)
  * URL刷新(Max 2000URL) / 目录刷新(Max 100 个刷新请求)
  * URL预热(Max 500URL)
