# 快速上手
按[上述方法](install.html)安装好whistle后，用Chrome浏览器打开配置页面: [http://local.whistlejs.com](http://local.whistlejs.com/)

如图[Rules](webui/rules.html)，whistle的Rules配置页面有一个默认分组`Default`，用户也可以通过上面的菜单栏按钮`Create`、`Edit`、`Delete`分别创建、重命名、删除自定义分组，whistle先在选中的用户自定义分组中从上到下依次匹配，然后再到`Default`中匹配(如果`Default`分组被启用的情况下)。

点击页面上方菜单栏的`Create`按钮，新建一个名为`test`的分组，并按下面例子输入对应的规则配置。

> whistle支持域名、路径、正则三种[匹配方式](pattern.html)，如果不[开启HTTPS拦截](webui/https.html)，whistle无法获取请求的完整的请求url，对这部分请求只有域名匹配能完整支持，为了让规则对所有请求都生效请先[开启HTTPS拦截](webui/https.html)

1. 设置hosts

	whistle不仅完全兼容操作系统的hosts配置方式，也支持域名、路径、正则三种匹配方式，而且支持配置端口号。
	
	whistle支持以下几种配置模式：
	
		# 下面四种host配置方式等价
		pattern ip
		ip pattern
		pattern host://ip
		host://ip pattern
		
		# 加上端口号，匹配pattern的请求会访问ip下的port端口
		# 主要用途是去掉url中的端口号
		pattern host://ip:port
		host://ip:port pattern
		
		# 组合模式
		pattern ip1 ip2 ipN host://ip:port
		ip pattern1 pattern2 patternN
		host://ip:port pattern1 pattern2 patternN
		
	*其中，pattern请参考[匹配方式](pattern.html)*
		
	**例子：**
	
	指定[www.ifeng.com](http://www.ifeng.com/)的ip:
	
		www.ifeng.com 127.0.0.1
		
	指定[www.ifeng.com](http://www.ifeng.com/)的ip和端口，把请求转发到本地8080端口:
	
		# www.ifeng.com 127.0.0.1
		www.ifeng.com host://127.0.0.1:8080
		
2. 替换本地文件
3. 请求转发		
4. 注入html、js、css
5. 调试远程页面

	
更多功能请参考：[协议列表](rules/index.html)