Nginx+PHP 一键包

嘛，从Whuihuan那儿fork了这个仓库，发现有点小问题，没法正常的一撸到底，稍稍修改了一下。
README我就参照我的喜好写了。。
这是一个Openshift架设Nginx+PHP5.3+Zend Guard Loader的一键包。

文件夹

=.openshift //openshift默认的文件夹

==action_hooks //主程序位置

==tmpl //配置模版位置

=php //网站根目录

文件及作用

===build //编译主程序

===build_nginx //Nginx编译主程序

===build_php //PHP编译主程序

===common //用于重启时输出路径

===deploy //部署应用程序配置

===start //启动程序

===stop //停止程序



使用方法

请首先创创建一个Openshift的应用，类别为"Do-It-Yourself"。

如果你已经配置好了命令行工具rhc，可以通过命令

rhc app create zendphp diy-0.1

创建程序，zendphp为应用名，可以换成自己喜欢的；diy-0.1为应用类别，以官方给出的列表中的名称为准。

1.将本程序放至"app-root/repo/"目录。

2.进入".openshift"文件夹中的"action_hooks"目录。

3.执行"chmod 6755 build deploy start stop"赋予文件权限，然后执行"./build"开始编译。

4.等待编译完成，耗时一个小时左右。如果要离开电脑，请保证电脑不会进入休眠状态。

5.编译完成后，执行"./deploy"部署程序配置。

6.执行"./start"开始运行Nginx+PHP环境。

7.打开应用地址，若出现雅黑探针界面，说明安装成功。


常见问题

Q.Nginx无法启动，原因：端口被占用。
A.在程序里本结束了ruby的进程，也许出现意外并未结束，可输入命令"killall ruby"来结束进程，再尝试启动即可。
