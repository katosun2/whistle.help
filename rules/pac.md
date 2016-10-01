# pac
设置pac脚本，配置模式：

	pattern pac://filepath
	
filepath为[Values](http://local.whistlejs.com/#values)里面的{key}或者本地文件，pattern参见[匹配方式](../pattern.html)，更多模式请参考[配置模式](../mode.html)。

例子：

	/./ pac://{test.pac}
	
test.pac:

	function FindProxyForURL(url,host) {
		return host == 'www.test.com' ? 'DIRECT'DIRECT : 'PROXY myproxy:80';
	}