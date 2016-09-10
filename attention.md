# 注意事项
1. 没有[开启https拦截](webui/https.html)的https、websocket的请求或者通过HTTPS代理过来的socket请求，由于无法获取代理内容的协议或者本身代理内容没有协议，方便配置时区分，whistle把这些请求的协议看成`tunnel:`，所有这里请求只能支持域名匹配、正则匹配和形如下面的路径匹配：

		tunnel://host
		tunnel://host/
		tunnel://host:port
		tunnel://host:port/
2. HTTPS代理也可以代理socket请求，前提对该请求不能[开启https拦截](webui/https.html)，可以在代理头部新增`x-whistle-policy: tunnel`，这时whistle对该HTTPS代理的请求不会[开启https拦截](webui/https.html)，即使whistle本身[开启https拦截](webui/https.html)。
3. 还有一些遇到过的问题可以查看：[常见问题](questions.html)
4. 用户反馈见：[用户反馈](fallback.html)