# 安装whistle
安装启动whistle，需要以下四个步骤： **安装node**、**安装whistle**、**启动whistle**、**配置代理**。

### 安装node

如果你的机器上已经安装了 `v0.10.0` 及以上版本的node(**推荐安装最新的node版本**)，可以忽略此步骤。

windows或mac可以直接访问[https://nodejs.org/](https://nodejs.org/)点击页面中间的 **INSTALL** 按钮下载安装包，下载完毕后默认安装即可。

linux可以参考（推荐使用源码安装）：[http://my.oschina.net/blogshi/blog/260953](http://my.oschina.net/blogshi/blog/260953)

安装完node后，执行下面命令，查看当前node版本

	$ node -v
	v0.12.7

如果能正常输出node的版本号，表示node已安装成功。

### 安装whistle

执行npm命令 `npm install -g whistle`，开始安装whistle （**mac或linux用户，如果安装过程出现异常，可以使用 `sudo npm install -g whistle`安装，下面命令类同，如果max或linux用户执行命令过程出现异常信息，都在命令前面加个 `sudo`**）

	$ npm install -g whistle
	
npm默认镜像是在国外，有时候安装速度很慢或者出现安装不了的情况，如果无法安装或者安装很慢，可以使用taobao的镜像安装：

	$ npm install cnpm -g --registry=https://registry.npm.taobao.org
	
安装成功后，直接执行：

	$ cnpm install -g whistle
	
*mac或linux用户，如果安装过程出现异常，可以使用 `sudo cnpm install -g whistle`安装*


whistle安装完成后，执行命令 `whistle help` (`v0.7.0`及以上版本也可以使用`w2 help`)，查看whistle的帮助信息

	$ whistle help		

	  
	Usage: whistle <command> [options]
	
	
	Commands:

    run       Start a front service
    start     Start a background service
    stop      Stop current background service
    restart   Restart current background service
    help      Display help information

	Options:
	
	    -h, --help                                      output usage information
	    -d, --debug [debug]                             debug mode
	    -n, --username [username]                       login username
	    -w, --password [password]                       login password
	    -p, --port [port]                               whistle port(8899 by default
	)
	    -m, --middlewares [script path or module name]  express middlewares path (as
	: xx,yy/zz.js)
	    -u, --uipath [script path]                      web ui plugin path
	    -t, --timneout [ms]                             request timeout(36000 ms by
	default)
	    -s, --sockets [number]                          max sockets
	    -V, --version                                   output the version number
	    -c, --custom <custom>                           custom parameters ("node --h
	armony")

	
如果能正常输出whistle的帮助信息，表示whistle已安装成功。


### 启动whistle

执行如下命令启动whistle (`v0.7.0`及以上版本也可以使用`w2 start`)

	$ whistle start


*Note: 如果要防止其他机器访问配置页面，可以在启动时加上登录用户名和密码 `-n yourusername -w yourpassword`。*

重启whsitle (`v0.7.0`及以上版本也可以使用`w2 restart`)

	$ whistle restart

停止whistle (`v0.7.0`及以上版本也可以使用`w2 stop`)

	$ whistle stop

如果whistle无法启动，可以执行如下命令启动whistle可以打印出错误信息 (`v0.7.0`及以上版本也可以使用`w2 run`)

	$ whistle run

启动完whistle后，最后一步需要配置代理，并把代理指向whistle。

### 配置代理

######配置信息：

1. IP： 127.0.0.1(如果部署在远程服务器或虚拟机上，把ip改成对应服务器或虚拟机的ip即可)

2. 端口： 8899(默认端口为8899，如果端口被占用，可以在启动是通过 `-p` 来指定新的端口，更多信息可以通过执行命令行 `whistle help` (`v0.7.0`及以上版本也可以使用`w2 help`) 查看)

3. 勾选上 **对所有协议均使用相同的代理服务器**

######两种代理配置方式(任选其中一个，并把上面配置信息配置上即可)：

1. 直接配置系统代理：　


	1) [Windows](http://jingyan.baidu.com/article/0aa22375866c8988cc0d648c.html) 

	2) [Mac](http://jingyan.baidu.com/article/a378c960849144b3282830dc.html)

2. 安装浏览器代理插件 (**推荐**)

	1) 安装chrome代理插件： [whistle管理插件](https://github.com/avwo/whistle-for-chrome) 或者 [Proxy SwitchySharp](https://chrome.google.com/webstore/detail/proxy-switchysharp/dpplabbmogkhghncfbfdeeokoefdjegm)

	2) 安装firefox代理插件： [Proxy Selector](https://addons.mozilla.org/zh-cn/firefox/addon/proxy-selector/)
	

### 访问配置页面
启动whistle及配置完代理后，用**Chrome浏览器(由于css兼容性问题界面只支持Chrome浏览器)**访问配置页面 [http://local.whistlejs.com/](http://local.whistlejs.com/)或请求列表页面[http://local.whistlejs.com/index.html](http://local.whistlejs.com/index.html)，如果能正常打开页面，whistle安装启动完毕，可以开始使用。

*Note: 也支持直接用ip访问配置页面： [http://whistleServerIP:whistlePort/](http://127.0.0.1:8899)*


至此，whistle已经安装启动配置完毕，匹配方式、规则配置、ui操作、查看抓包数据、重发请求、构造请求等功能请参考：[使用方法](https://github.com/avwo/whistle/wiki)


有什么问题可以通过QQ群反馈： 462558941

