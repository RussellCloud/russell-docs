# 快速启动 jupyter notebook
跟随本教程，在 RussellCloud 云服务器上快速启动 jupyter notebook。

---

<!-- toc -->

---

## 准备工作

* [注册 RussellCloud 账号](http://russellcloud.com/#regist)
* [安装 *russell-cli* 终端工具](/get-started/install.md)
* [通过 *russell-cli* 登录账号](/login-cli.md)

---

## 启动 Notebook
1. 访问 https://russellcloud.com/project/create 并创建一个项目。
![](/asserts/img/quick-start/quick-start-jupyter-notebook.png)

2. 在终端中，使用 RussellCloud CLI 初始化该项目（确保和上一步的名称相同）

``` 
$ russell init --name my_project
Project "my_project" initialized in current directory

```

3. 接着使用如下命令

```
$ russell run --mode jupyter 
Syncing code ...
compressing files...
creating F:\kuhung\Desktop\RC\for-docs\temp
Creating tar archive
compressed size: 167 Bytes
Start uploading...
close status: 31522###########################################################|

Upload finished
RUN ID                            NAME                         VERSION
--------------------------------  -------------------------  ---------
51a6697ecf594edf9fb259fc33bb53ed  RussellCloud/my_project:1          1
...

```

这一操作会在你的浏览器打开 Jupyter Notebook。该 notebook 运行在 RussellCloud 服务器端。


## 停止 Notebook
回到主页面，依次选择**项目-概览**栏目，找到正在运行的项目。如下图所示。

![](/asserts/img/quick-start/stop-jupyter-1.png)
![](/asserts/img/quick-start/stop-jupyter-2.png)

点击进入正在运行的项目，点击**停止项目**，即可立即停止 Notebook。
![](/asserts/img/quick-start/stop-jupyter-3.png)


---

{% include "../help-us.md" %}

