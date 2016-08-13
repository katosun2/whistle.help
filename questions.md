# 常见问题

1. 为什么[http://local.whistlejs.com](http://local.whistlejs.com/)无法访问？

	没有启动whistle或者配置代理，具体操作请参考[安装启动](install.html)

2. 为什么**Network**上看不到请求？

	没有用Chrome浏览器访问[http://local.whistlejs.com](http://local.whistlejs.com/)，或者是请求没有代理到指定的whistle，如何配置代理请参考[安装启动](install.html)

3. 手机或平板如何抓包请求？

	需要配置代理，且可能要关闭防火墙或者设置运行远程访问本地指定端口，具体参考[安装启动](install.html)

4. 为什么设置的规则对https请求不生效？

	需要安装根证书及开启https拦截，具体参考[https](webui/https.html)
	
	PS: Firefox自带根证书列表，需要系统根证书对Firefox不生效，需要对Firefox单独安装根证书。

5. 如何查看错误信息？

	如果是请求出错，可以在Network里面的Request或Response的Text里面看到，有些请求会把异常作为响应内容直接输出到界面；如果是内部运行出现的非致命性异常，可以在Network -> Log -> Server里面看到；如果是导致程序crash的异常，日志信息会写在命令行启动的目录的`whistle.log`文件。