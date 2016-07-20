# 更新whistle

变更点请查看：[CHANGELOG](https://github.com/avwo/whistle/blob/master/CHANGELOG.md#-)

执行命令更新whistle(mac或linux用户，如果安装过程出现异常，请在命令行前面加`sudo`，如: `sudo npm install -g whistle`)：
	
	$ npm install -g whistle 
	# 或
	$ npm update -g whistle
	# 或
	$ npm install -g whistle --registry=https://registry.npm.taobao.org
	# 或
	$ npm update -g whistle --registry=https://registry.npm.taobao.org
	
	

npm默认镜像是在国外，有时候安装速度很慢或者出现安装不了的情况，如果无法安装或者安装很慢，可以使用taobao的镜像安装：

	$ npm install cnpm -g --registry=https://registry.npm.taobao.org
	
安装成功后，直接执行：

	$ cnpm install -g whistle
	
或直接执行：

	npm install whistle -g --registry=https://registry.npm.taobao.org
	
*mac或linux用户，如果安装过程出现异常，可以使用 `sudo cnpm install -g whistle`安装*

更新成功后，重启 `whistle` ：

	$ w2 restart
	
*mac或linux用户，如果启动过程出现读写文件权限异常，可以使用 `sudo w2 restart` 启动*

极端情况下可能出现端口占用的情况，遇到这种情况手动kill掉 `node` 或 `iojs` 的进程即可。