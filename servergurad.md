
[Agent说明](https://help.aliyun.com/document_detail/31778.html)
- 安骑士 Agent 每隔五个小时会主动向安骑士服务器端上报一次在线数据信息。
- 如果安骑士 Agent 没有按时上报在线信息，安骑士服务器端则在 12 小时后判定该服务器不在线，且在安骑士管理控制台中此服务器的保护状态显示为离线。
- 同一服务器上的同一漏洞只会在首次发现时为您推送告警信息。重大漏洞:多次推送告警信息

[软件漏洞](https://help.aliyun.com/document_detail/54567.html)
- Linux软件漏洞检查周期 2次/天
- 漏洞白名单, 如果将某个漏洞从白名单中移除，安骑士将恢复对该漏洞的检测，但无法恢复该漏洞的历史上报记录。

[基线检查](https://help.aliyun.com/document_detail/59003.html)
- 自动检测您服务器上的系统、数据库、账号配置存在的风险点，并针对所发现的问题项为您提供修复建议。

[异常登录](https://help.aliyun.com/document_detail/52786.html)
- 检测服务器上的登录行为，对于在非常用登录地的登录行为进行告警
- 企业版中可允许客户设置合法登录IP、合法登录时间、合法登录账号，在上述合法登录IP、合法登录事件、合法登录账号之外的登录行为均提供告警。
- 当某个IP被判定为异地登录行为，只会有第一次登录行为进行短信告警，如果该IP成功登录六次或六次以上时，安骑士默认将此IP的地点记录为常用登录地。

[网站后门](https://help.aliyun.com/document_detail/52788.html)
- 拥有定时查杀和实时防护扫描策略，支持检测常见的 PHP、JSP 等后门文件类型，并提供一键隔离功能。
- 检测周期 动/静态检测
- 处理木马文件: 隔离/恢复/忽略

[日志功能](https://help.aliyun.com/document_detail/60009.html)
- 仅企业版可用，企业版支持检索 30 天内的主机日志
- 将散落在各系统中的主机日志进行集中管理。
- 支持 TB 级数据检索，及 50 种逻辑条件

资产管理(仅企业版)
- [端口清点](https://help.aliyun.com/document_detail/60612.html)
  * 数据收集周期：每小时
- [进程管理](https://help.aliyun.com/document_detail/60613.html)
  * 数据收集周期：每小时
- 软件版本管理
  * 数据收集周期：可自定义
- [账号管理](https://help.aliyun.com/document_detail/60615.html)
  * 数据收集周期：每小时

[病毒云查杀](https://help.aliyun.com/document_detail/66555.html)
![alt](http://docs-aliyun.cn-hangzhou.oss.aliyun-inc.com/assets/pic/66555/cn_zh/1517627956202/2.png)

## Other

- 安骑士占用资源非常少，仅有50MB





.
