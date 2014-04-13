<div class="js-commit-preview">
    <div id="readme" class="blob instapaper_body">
        <div class="markdown-body">
            Nginx+PHP 一键包
            <P>
            这个一键包已经改过了,不能用于在openshift建立PHP+Zend环境,反之我正在努力的将其打造为MinecraftPE服务器.所以请不要使用这个环境在openshift部署,一旦导致出现问题,后果自负.
            </p>
            <p>
                嘛，从Whuihuan那儿fork了这个仓库，发现有点小问题，没法正常的一撸到底，稍稍修改了一下。README我就参照我的喜好写了。。
            </p>
            <p>
                这是一个Openshift架设Nginx+PHP5.3+Zend Guard Loader的一键包。
            </p>
            <p>
                文件夹
            </p>
            <blockquote formatblock="1" style="margin: 0.8em 0px 0.8em 2em; padding: 0px 0px 0px 0.7em; border-left: 2px solid rgb(221, 221, 221);">
                <p>
                    =.openshift //openshift默认的文件夹
                </p>
                <p>
                    ==action_hooks //主程序位置
                </p>
                <p>
                    ==tmpl //配置模版位置
                </p>
                <p>
                    =php //网站根目录
                </p>
            </blockquote>
            <p>
                文件及作用
            </p>
            <blockquote formatblock="1" style="margin: 0.8em 0px 0.8em 2em; padding: 0px 0px 0px 0.7em; border-left: 2px solid rgb(221, 221, 221);">
                <p>
                    ===build //编译主程序
                </p>
                <p>
                    ===build_nginx //Nginx编译主程序
                </p>
                <p>
                    ===build_php //PHP编译主程序
                </p>
                <p>
                    ===common //用于重启时输出路径
                </p>
                <p>
                    ===deploy //部署应用程序配置
                </p>
                <p>
                    ===start //启动程序
                </p>
                <p>
                    ===stop //停止程序
                </p>
            </blockquote>
            <p>
                使用方法
            </p>
            <p>
                请首先创创建一个Openshift的应用，类别为"Do-It-Yourself"。
            </p>
            <p>
                如果你已经配置好了命令行工具rhc，可以通过命令
            </p>
            <blockquote formatblock="1" style="margin: 0.8em 0px 0.8em 2em; padding: 0px 0px 0px 0.7em; border-left: 2px solid rgb(221, 221, 221);">
                <p>
                    rhc app create zendphp diy-0.1
                </p>
            </blockquote>
            <p>
                创建程序，zendphp为应用名，可以换成自己喜欢的；diy-0.1为应用类别，以官方给出的列表中的名称为准。
            </p>
            <p>
                1.将本程序放至"app-root/repo/"目录。
            </p>
            <p>
                2.进入".openshift"文件夹中的"action_hooks"目录。
            </p>
            <p>
                3.执行
            </p>
            <blockquote formatblock="1" style="margin: 0.8em 0px 0.8em 2em; padding: 0px 0px 0px 0.7em; border-left: 2px solid rgb(221, 221, 221);">
                <p>
                    chmod 6755 build deploy start stop
                </p>
            </blockquote>
            <p>
                赋予文件权限，然后执行
            </p>
            <blockquote formatblock="1" style="margin: 0.8em 0px 0.8em 2em; padding: 0px 0px 0px 0.7em; border-left: 2px solid rgb(221, 221, 221);">
                <p>
                    ./build
                </p>
            </blockquote>
            <p>
                开始编译。
            </p>
            <p>
                4.等待编译完成，耗时一个小时左右。如果要离开电脑，请保证电脑不会进入休眠状态。
            </p>
            <p>
                5.编译完成后，执行
            </p>
            <blockquote formatblock="1" style="margin: 0.8em 0px 0.8em 2em; padding: 0px 0px 0px 0.7em; border-left: 2px solid rgb(221, 221, 221);">
                <p>
                    ./deploy
                </p>
            </blockquote>
            <p>
                部署程序配置。
            </p>
            <p>
                6.执行
            </p>
            <blockquote formatblock="1" style="margin: 0.8em 0px 0.8em 2em; padding: 0px 0px 0px 0.7em; border-left: 2px solid rgb(221, 221, 221);">
                <p>
                    ./start
                </p>
            </blockquote>
            <p>
                开始运行Nginx+PHP环境。
            </p>
            <p>
                7.打开应用地址，若出现雅黑探针界面，说明安装成功。
            </p>
            <p>
                常见问题
            </p>
            <p>
                Q.Nginx无法启动，原因：端口被占用。A.在程序里本结束了ruby的进程，也许出现意外并未结束，可输入命令"killall ruby"来结束进程，再尝试启动即可。
            </p>
        </div>
    </div>
</div>
