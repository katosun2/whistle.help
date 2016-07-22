# 快速上手
按[上述方法](install.html)安装好whistle后，用Chrome浏览器打开配置页面: [http://local.whistlejs.com](http://local.whistlejs.com/)

如图[Rules](webui/rules.html)，whistle的Rules配置页面有一个默认分组`Default`，用户也可以通过上面的菜单栏按钮`Create`、`Edit`、`Delete`分别创建、重命名、删除自定义分组，whistle先在选中的用户自定义分组中从上到下依次匹配，然后再到`Default`中匹配(如果`Default`分组被启用的情况下)。

点击页面上方菜单栏的`Create`按钮，新建一个名为`test`的分组，并按下面例子输入对应的规则配置。

1. 设置hosts

	
	指定[www.ifeng.com](http://www.ifeng.com/)的ip:
	
		www.ifeng.com 127.0.0.1
		
	指定[www.ifeng.com](http://www.ifeng.com/)的ip和端口，把请求转发到本地8080端口，这个在平时开发中可以用来去掉url中的端口号:
	
		# www.ifeng.com 127.0.0.1
		www.ifeng.com host://127.0.0.1:8080
		
2. 本地替换
	
	平时开发中经常会用到这个功能，把响应替换成本地文件内容。
	
		# Mac、Linux
		www.ifeng.com file:///User/xxx/test|/User/xxx/test/index.html
		
		# Windows的路径分隔符可以用`\`和`/`
		www.ifeng.com file://E:\xx\test|E:\xx\test\index.html
		
	[http://www.ifeng.com/](http://www.ifeng.com/)会先尝试加载`/User/xxx/test`这个文件，如果不存在，则会加载`/User/xxx/test/index.html`，如果没有对应的文件则返回404。
	
	http://www.ifeng.com/xxx会先尝试加载`/User/xxx/test/xxx`这个文件，如果不存在，则会加载`/User/xxx/test/index.html/xxx`，如果没有对应的文件则返回404。

3. 请求转发		
	
	[www.ifeng.com](http://www.ifeng.com/)域名下的请求都替换成对应的www.aliexpress.com域名

		www.ifeng.com www.aliexpress.com
		
	也可以用来去掉请求端口号：
	
		www.test.com 127.0.0.1:8080
		
	www.test.com的请求会自动转发到本地的8080端口，这个与配具有端口号的host的主要区别是前者会修改请求头的host字段，这个可能会导致请求被一些统一接入成转发到其它域名。
	
4. 注入html、js、css
	
	whistle会自动根据响应内容的类型，判断是否注入相应的文本及如何注入(是否要用标签包裹起来)。
	
		# Mac、Linux
		www.ifeng.com html:///User/xxx/test/test.html
		www.ifeng.com js:///User/xxx/test/test.js
		www.ifeng.com css:///User/xxx/test/test.css
		
				
		# Windows的路径分隔符可以用`\`和`/`
		www.ifeng.com html://E:\xx\test\test.html
		www.ifeng.com js://E:\xx\test\test.js
		www.ifeng.com css://E:\xx\test\test.css
		
	所有www.ifeng.com域名下的请求，whistle都会根据响应类型，将处理好的文本注入到响应内容里面。
	如是html请求，js和css会分别自动加上`script`和`style`标签后追加到内容后面。


5. 调试远程页面

	利用whistle提供的[weinre](rules/weinre.html)和[log](rules/log.html)两个协议，可以实现修改远程页面DOM结构及自动捕获页面js错误及console打印的信息，还可以在页面顶部或js文件底部注入指定的脚步调试页面信息。
	
	使用whistle的功能前，先把要相应的系统代理或浏览器代理指向whistle，如何设置可以参考：[安装配置](install.html)
	
	weinre：
	
		www.ifeng.com weinre://test
		
	配置后保存，打开[www.ifeng.com](http://www.ifeng.com/)，鼠标放在菜单栏的weinre按钮上会显示一个列表，并点击其中的`test`项打开weinre的调试页面选择对应的url切换到Elements即可。
	
	log:
	
		www.ifeng.com log://{test.js}
		
	配置后保存，鼠标放在菜单栏的weinre按钮上会显示一个列表，并点击其中的`test.js`项，whistle会自动在Values上建立一个test.js分组，在里面填入`console.log(1, 2, 3, {a: 123})`保存，打开Network -> 右侧Log -> Page，再打开[www.ifeng.com](http://www.ifeng.com/)，即可看到Log下面的Page输出的信息。
	
	
更多功能请参考：[协议列表](rules/index.html)