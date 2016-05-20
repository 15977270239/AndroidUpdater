# android-app-update

使用DownloadManager来进行版本更新的完整方案策略

项目基本功能如下:

1, 一般在app中, 检测版本更新是在主界面中启动一个service其检测.
   如果需要更新则开始下载, 然后在通知栏显示下载通知.

2, 因为我们使用的是Android自带的DownloadManager模块来下载的, 我们通过通知栏知道, 该模块属于系统自带,
   它已经帮我们处理了下载失败重新下载, 断点续传等功能.

3, 如果下载成功后, 会通知我们的Receiver, 然后我们启动安装界面.

4, 如果用户取消安装, 用户下次进入我们的程序, 我们去检测下载任务是否已经下载完成, 如果没有下载完成, 走下载逻辑;
   如果已经下载成功了, 则`检测本地apk与当前程序的包名是否相同、版本号是否大于当前程序`, 如果都满足则使用本地下载好的apk, 进入安装界面.


---------------


PS :  很多网上的教程, 1-3的步骤, 第4步没有去考虑.


未来要做的事情, 把更新提示框加进去, 然后生成aar, 方便开发者使用.
