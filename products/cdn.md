
## [功能优势](https://help.aliyun.com/document_detail/27103.html)

- 国内节点2000+, 海外节点500+, 单节点带宽40Gbps+

## [直播流媒体](https://help.aliyun.com/document_detail/109891.html)

- 当前支持 RTMP、HLS、FLV 三种格式直播内容加速

## [私有bucket回源授权](https://help.aliyun.com/document_detail/57653.html)

- 进行一次回源授权，即授权CDN对用户所有Bucket的只读权限，不只是对当前bucket授权
  - AliyunCDNAccessingPrivateOSSRole

## [回源SNI](https://help.aliyun.com/document_detail/111152.html)


## [自定义错误页面](https://help.aliyun.com/document_detail/27132.html)

- CDN HTTPS安全加速只支持 PEM 格式的证书
  * 其他格式需转换成 PEM格式
- 开启HTTP/2前，请确保HTTPS的证书已经配置成功。
- 配合使用cdn提供的refer防盗链功能，鉴权等功能，有效保护资源安全。

- アクセス制限
  * [防盗链](https://help.aliyun.com/document_detail/27134.html)
    * 防盗链功能支持<font color="red">黑名单或白名单机制</font>
  * [URL鉴权](https://help.aliyun.com/document_detail/85117.html)
    * A: ``http://DomainName/Filename?auth_key=timestamp-rand-uid-md5hash``
    * B: ``http://DomainName/timestamp/md5hash/FileName``
    * C: <br>Format1: ``http://DomainName/{<md5hash>/<timestamp>}/FileName`` <br> Format2: ``http://DomainName/FileName{&KEY1=<md5hash>&KEY2=<timestamp>}
    * [鉴权代码示例](https://help.aliyun.com/document_detail/85116.html)

- [日志下载](https://help.aliyun.com/document_detail/27142.html)
  * 日志文件延迟4小时，可以在日志管理模块查询到4小时之前的日志文件。
  * 日志文件按小时粒度分割
  * 支持 1月 的日志数据下载
    * 没有直接存到OSS的设置, 可以配合Function Compute的触发器/函数来执行
- [缓存](https://help.aliyun.com/document_detail/27140.html)
  * URL刷新(Max 2000URL) / 目录刷新(Max 100 个刷新请求)
  * URL预热(Max 500URL)
    * 原理：将指定的内容主动预热到CDN的L2节点上，用户 **首次访问即可直接命中缓存**，降低源站压力

- [变配流程](https://help.aliyun.com/document_detail/27273.html)
  * 流量和带宽间，流量/带宽 → 月结95带宽 : 第二自然日零点执行该变配
  * 月结95带宽 →　流量/带宽 : 下个自然月1日零点生效，月中不允许变更

- 计费方式
  * 基础服务(带宽/流量) + 增值服务
    * 带宽: 5mごとbandwidthのピーク値を集計 → 288値/日 → Max値
    * 增值服务:HTTPS加速/全站加速

- ヘルスチェック
  * 裏では(Layer4 prot80) 2.5s/回、3回利用不可の場合unhealtyと判断

- [缓存配置](https://help.aliyun.com/document_detail/27136.html)
  * ![atl](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5147/3383_zh-CN.png)

- CDN实时日志为实时采集的日志数据，日志数据 **延迟不超过3分钟**

- FAQ
  * (使用CDN加速的网站如何设置CORS访问)[https://help.aliyun.com/knowledge_detail/40112.html]
    * CDN控制台上设置的CORS等头部信息对整个加速域名生效，会覆盖掉源站设置的头部信息。<br>って、<font color="red">どうすればいい?</font>
  * (CDN设置某个目录或文件不缓存)[https://help.aliyun.com/knowledge_detail/40192.html]
    * 該当ディレクトリのcache expire時間を0にする
