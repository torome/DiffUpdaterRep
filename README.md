#DiffUpdaterRep


差量升级目的是解决没必要的资源文件下载，让用户更快速的安装应用。基于官方提供的Hbuilder项目的差量升级，需要打的版本差异包太多，开发人员的工作量比较大。此思路是做差量升级插件，当需要升级时，去掉无需更改的图片资源，添加新加的资源，替换同文件名资源，打成新的差量包。文件替换成功后，重启项目即可看到最新版本。

适合的需求是初期图片资源比较多，小版本迭代比较多，无需版本差异项的配置;支持安卓和iOS版本。

相关链接：

  插件开发：http://ask.dcloud.net.cn/docs/#//ask.dcloud.net.cn/article/66



1.LcUpdater:H Builder项目

2.LcUploaderAndroid:安卓离线打包项目

3 testzipfile: 用于测试差量升级的升级包，可以放到服务器测试下载

4 diffupdater.jar引用的jar包，可以配合离线打包引入的jar包一起使用。

5.LCUploaderiOS: iOS版本的离线打包项目

备注：iOS版本中，经测试，发现通过restart()重启项目，发现获取到的manifest.json中的版本号没有改变，这给升级带来了困扰。解决方案是将版本号缓存到本地，如果有新版本，则下载替换完成后，缓存新版本号到本地，问题解决，Android端也是参考此思路。
