- 服务 ( Service )
 * 函数计算资源管理的单位。服务下的所有函数共享一些相同的设置，例如服务授权、配置日志。同一服务下有多个函数，这些函数共享服务配置的资源( 例如日志库，服务角色等)。

- Runtime
  * nodejs6 / nodejs8
  * python2.7 / python3
  * php7.2
  * java8

- [为函数安装第三方依赖](https://help.aliyun.com/document_detail/74571.html)
- [事件处理函数](https://help.aliyun.com/document_detail/52633.html)
  * [event 对象格式说明](https://help.aliyun.com/document_detail/52633.html#event)
  * [context 对象格式说明](https://help.aliyun.com/document_detail/52633.html#context)
  * [callback 对象格式说明](https://help.aliyun.com/document_detail/52633.html#callback)

- [调用函数](https://help.aliyun.com/document_detail/52878.html)
  * 函数计算在每个账户粒度设置了并发执行限制，默认为100。
  * [重试机制](https://help.aliyun.com/document_detail/52878.html#h2-u91CDu8BD5u673Au52364)
    * 同步调用：同步调用的函数执行失败系统不会进行处理。您可以自行重试。  
    异步调用：如果您的函数异步调用失败，以下情况函数计算会自动重试。
    * 200: Max 2
    * Function Compute は自動的に制限されたイベントを最大 5 時間再試行します。再試行操作の間には、待ち時間があります。非同期イベントは、関数を呼び出すために使用される前にキューに入れられます。

- formatted pattern : account_id.service_endpoint
  * Internet: accountId.region.fc.aliyuncs.com
  * Intranet: accountId.region-internal.fc.aliyuncs.com

- 料金
  * 调用次数费用 + 执行时间费用 + 公网流量费用

- [触发器列表](https://help.aliyun.com/document_detail/74707.html)
  * 函数计算支持 HTTP 触发器，配置 HTTP 触发器的函数可以通过 HTTP 请求触发执行。
- [配置触发器和事件格式](https://help.aliyun.com/document_detail/70140.html)
  * HTTP触发器
    * URL:  <account_id>.<region>.fc.aliyuncs.com/<version>/proxy/<serviceName>/<functionName>/[action?queries]  
    例: 123456.cn-shanghai.fc.aliyuncs.com/2016-08-15/proxy/serviceName/functionName/action?hello=world
    * 可用CNAME绑定 [自定义域名](https://help.aliyun.com/document_detail/90763.html)
    * authType  
    anonymous: 无需授权，允许任何人访问。  
    function: HTTP请求Header需要包含 [签名](https://help.aliyun.com/document_detail/53252.html) 和时间戳。
  * [Timer触发器](https://help.aliyun.com/document_detail/68172.html)

- [配置 VPC 功能](https://help.aliyun.com/knowledge_detail/72959.html)
- [环境变量](https://help.aliyun.com/document_detail/69777.html)
  * pathの取得
    * Pythonの場合: os.environ['FC_FUNC_CODE_PATH']

- [挂载NAS访问](https://help.aliyun.com/document_detail/87401.html)
  * 多个函数可以共用一个NAS，实现文件共享

- [使用限制](https://help.aliyun.com/document_detail/51907.html)
- [计费方式](https://help.aliyun.com/document_detail/54301.html)
  * 总费用由=调用次数费用 + 执行时间费用 + 公网流量费用
