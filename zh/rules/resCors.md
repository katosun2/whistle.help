# resCors

修改请求的[cors](https://developer.mozilla.org/zh-CN/docs/Web/HTTP/Access_control_CORS)，配置模式：

	pattern resCors://filepath
	
filepath为[Values](http://local.whistlejs.com/#values)里面的{key}或者本地文件:

	origin: * 
	methods: POST
	headers: x-test 
	credentials: true 
	maxAge: 300000

pattern参见[匹配方式](../pattern.html)，更多模式请参考[配置模式](../mode.html)，json格式参考[数据格式](../data.html)。

例子：

	www.ifeng.com resCors://{test-resCors.json}
	

test-resCors.json:

	origin: * 
	methods: POST
	headers: x-test 
	credentials: true 
	maxAge: 300000
