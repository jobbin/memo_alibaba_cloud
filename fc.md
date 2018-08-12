
- formatted pattern : account_id.service_endpoint
  * Internet: accountId.region.fc.aliyuncs.com
  * Intranet: accountId.region-internal.fc.aliyuncs.com

- 料金
  * 调用次数费用 + 执行时间费用 + 公网流量费用

- [触发器列表](https://help.aliyun.com/document_detail/74707.html)
  * 函数计算支持 HTTP 触发器，配置 HTTP 触发器的函数可以通过 HTTP 请求触发执行。

- pathの取得
  * Pythonの場合: os.environ['FC_FUNC_CODE_PATH']
