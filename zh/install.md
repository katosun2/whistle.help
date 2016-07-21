# 安装whistle
安装启动whistle，需要以下四个步骤： **安装node**、**安装whistle**、**启动whistle**、**配置代理**。

### 安装node

whistle支持`v0.10.0`以上版本的Node，为获取更好的性能，推荐最新版本的Node。

如果你的系统已经安装了`v0.10.0`以上版本的Node，可以忽略此步骤，直接进入安装whistle的步骤，否则：

1. Windows或Mac系统，访问[https://nodejs.org/](https://nodejs.org/)，安装**LTS**版本的Node，默认安装即可。
2. Linux参考(推荐使用源码安装): 从Node官网[https://nodejs.org/en/download/](https://nodejs.org/en/download/)上下载最新版的**Source Code**(可以在Linux上用`wget`命令下载或者直接点击下载后上传到指定的Linux服务器)，解压文件(`tar xvf node-xxx`)后进入解压后的根目录(`node-xxx`)依次执行`./configure`、`./make`和`./make install`。


安装完node后，执行下面命令，查看当前node版本

	$ node -v
	v4.4.0

如果能正常输出node的版本号，表示node已安装成功(Windows系统可能需要重新打开cmd)。

### 安装whistle

Node安装成功后，执行如下npm命令安装whistle （**mac或linux的非root用户需要在命令行前面加`sudo`，如：`sudo npm install -g whistle`**）

	$ npm install -g whistle
	
	
	
npm默认镜像是在国外，有时候安装速度很慢或者出现安装不了的情况，如果无法安装或者安装很慢，可以使用taobao的镜像安装：

	$ npm install cnpm -g --registry=https://registry.npm.taobao.org
	
安装成功后，直接执行：

	$ cnpm install -g whistle
	
或者直接指定镜像安装：

	$ npm install whistle -g --registry=https://registry.npm.taobao.org
	

whistle安装完成后，执行命令 `whistle help` 或 `w2 help`，查看whistle的帮助信息

	$ w2 help		

	  
	  Usage: w2 <command> [options]


	  Commands:

	    run       Start a front service
	    start     Start a background service
	    stop      Stop current background service
	    restart   Restart current background service
	    help      Display help information

	  Options:

	    -h, --help                                      output usage information
	    -d, --debug                                     debug mode
	    -n, --username [username]                       login username
	    -w, --password [password]                       login password
	    -r, --rules [newRulesDir]                       the dirname of rules(rules by default)
    	-v, --values [newValuesDir]                     the dirname of values(values by default)
    	-c, --copy [copy]                               copy rulesDir|valuesDir to newRulesDir&newValuesDir(rules|values by default)
	    -p, --port [port]                               whistle port(8899 by default)
	    -m, --middlewares [script path or module name]  express middlewares path (as: xx,yy/zz.js)
	    -u, --uipath [script path]                      web ui plugin path
	    -t, --timneout [ms]                             request timeout(36000 ms by default)
	    -s, --sockets [number]                          max sockets
	    -V, --version                                   output the version number
	    -c, --command <command>                         command parameters ("node --harmony")

	
如果能正常输出whistle的帮助信息，表示whistle已安装成功。


### 启动whistle

执行如下命令启动whistle(最新版本的whistle支持三种等价的命令`whistle`、`w2`、`wproxy`):

	$ w2 start


*Note: 如果要防止其他人访问配置页面，可以在启动时加上登录用户名和密码 `-n yourusername -w yourpassword`。*

重启whsitle:

	$ w2 restart

停止whistle:

	$ w2 stop

调试模式启动whistle(主要用于查看whistle的异常及插件开发):

	$ w2 run

启动完whistle后，最后一步需要配置代理。

### 配置代理

######配置信息：

1. IP： 127.0.0.1(如果部署在远程服务器或虚拟机上，把ip改成对应服务器或虚拟机的ip即可)

2. 端口： 8899(默认端口为8899，如果端口被占用，可以在启动是通过 `-p` 来指定新的端口，更多信息可以通过执行命令行 `w2 help` (`v0.7.0`及以上版本也可以使用`w2 help`) 查看)

3. 勾选上 **对所有协议均使用相同的代理服务器**

######代理配置方式(把上面配置信息配置上即可)：

1. 直接配置系统代理：　


	1) [Windows](http://jingyan.baidu.com/article/0aa22375866c8988cc0d648c.html) 

	2) [Mac](http://jingyan.baidu.com/article/a378c960849144b3282830dc.html)

2. 安装浏览器代理插件 (**推荐**)

	1) 安装chrome代理插件： [whistle-for-chrome插件](https://github.com/avwo/whistle-for-chrome) 或者 [Proxy SwitchySharp](https://chrome.google.com/webstore/detail/proxy-switchysharp/dpplabbmogkhghncfbfdeeokoefdjegm)

	2) 安装firefox代理插件： [Proxy Selector](https://addons.mozilla.org/zh-cn/firefox/addon/proxy-selector/)
	
3. 移动端需要在`设置`中配置当前Wifi的代理
	

### 访问配置页面
启动whistle及配置完代理后，用**Chrome浏览器(由于css兼容性问题界面只支持Chrome浏览器)**访问配置页面 [http://local.whistlejs.com/](http://local.whistlejs.com/)，如果能正常打开页面，whistle安装启动完毕，可以开始使用。

*Note: 也支持直接用ip访问配置页面： [http://whistleServerIP:whistlePort+1/](http://127.0.0.1:8900)*

### 启动多个whistle
如果你想在同一台机器启动多个whistle，方便多个浏览器或者供多人使用，有两种方式：

1. 切换到不同的系统用户，在每个系统用户启动一个whistle代理服务(每个服务的端口号可以用命令行参数`w2 start -p xxxx`来指定)
2. 也可以通过切换规则目录和端口号的方式来解决

		w2 start -S newStorageDir -p newPort
		
		# 系统默认目录的配置拷贝到新的目录
		w2 start -S newStorageDir -c -p newPort
		
		# 也可以指定要拷贝的目录
		w2 start -S newStorageDir -c storageDir -p newPort
		
	*Note: 这种拷贝是覆盖式的，会替换原来的文件*
		


至此，whistle已经安装完毕，可以开始使用了。



