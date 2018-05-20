# 快速启动 jupyter notebook
跟随本教程，在 RussellCloud 云服务器上快速启动 jupyter notebook。


## 准备工作

* [注册 RussellCloud 账号](http://russellcloud.com/#regist)
* [安装 *russell-cli* 终端工具](/get-started/install.md)
* [通过 *russell-cli* 登录账号](/login-cli.md)

---

## 快速开始
1. 访问 https://russellcloud.com/project/create 并创建一个项目。
![](/asserts/img/quick-start/quick-start-jupyter-notebook.png)

2. 在终端中，使用 RussellCloud CLI 初始化该项目（确保和上一步的名称相同）
``` bash
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

Setting up your instance and waiting for Jupyter notebook to become available ...

Path to jupyter notebook: https://russellcloud.com/RussellCloud/project/my_project/tasks/51a6697ecf594edf9fb259fc33bb53ed/notebook

    To view logs enter:
        russell logs 51a6697ecf594edf9fb259fc33bb53ed
        
```

# TODO: 从这里开始



### 第一步：网页创建项目

- 创建项目。进入个人主页，点击[创建项目]

![](/asserts/img/first_task_1.png)

- 给项目命名。这里我们取名为 *tf-mnist* 

![](/asserts/img/first_task_2.png)

- 获取项目ID。创建后自动跳转到新项目页，下图方框中即为新项目ID。本ID的作用是，**绑定本地项目与线上项目**。在本地上传代码时，此ID告诉了客户端，这些代码将传至的线上项目地址。

![](/asserts/img/first_task_3.png)


### 第二步：clone教程源码
打开终端，通过 git clone 下载教程源码

```
#clone项目代码
git clone https://github.com/RussellCloud/tensorflow-examples.git

#进入项目所在目录（这里我们进入第3章的代码目录）
cd tensorflow-examples/3_NeuralNetworks

```


![示意图](/asserts/img/first_task_4.png)


### 第三步：通过 russell-cli 操作



```
#绑定项目（也可以用 init --id <project_id>）
russell init --name tf-mnist

#运行启动指令
russell run "python mnist_cnn.py"

```

run之后的*<task_id>*是 run 返回的任务ID。**任务ID不同于项目ID**。

- 生成时间不同
    - 项目ID在网页创建项目的时候生成。
    - 任务ID在每一次run启动的时候生成。

- 使用情况不同
    - 项目ID一般只使用一次，用在初始化绑定项目。即建立本地项目与线上项目的联系时。
    - 任务ID可多次使用，查看项目状态、查看运行日志，都是用任务ID。
    - **在关停任务时，使用的是任务 ID**。即通过 `russell stop 任务ID`，关停任务。系统随之停止计时计费。


```
#查看项目状态 (别带上 < > )
russell status <task_id>

#查看运行日志（按ctrl-c退出,不会影响远程任务继续执行）
russell logs <task_id>
```

![](/asserts/img/first_task_5.png)

---




## 帮助我们完善文档
这篇文档以及剩下的文档，我们都有同步在 [GitHub](https://github.com/RussellCloud/russell-docs) 上。团队在尽力完善文档，但疏漏和不周难免存在。若你有什么新的想法或体验，欢迎 Pull Request，扩大你的影响力。

- 除此之外，你还可以通过 [issue](https://github.com/RussellCloud/russell-docs/issues/new?body=This%20issue%20is%20about%20<) 直接提交问题。
- 或者，在[这里](/faq/run-task.md)查看常见问题。

