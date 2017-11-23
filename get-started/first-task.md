# 第一个任务

在这一小节，我们将帮助你快速使用 RussellCloud 提交你的第一个深度学习任务 —— 通过基于 *tensorflow* 框架的CNN模型 实现手写数字识别，这里使用的是 Github 上的基础教程源码 [TensorFlow-Example](https://github.com/RussellCloud/TensorFlow-Examples) 以及 MNIST 数据集（在代码中下载）。

---

<!-- toc -->

---

## 准备

* [注册 RussellCloud 账号](http://russellcloud.com/#regist)
* [安装 *russell-cli* 终端工具](/get-started/install.md)
* [通过 *russell-cli* 登录账号](http://russellcloud.com/#login)

---

## 第一个任务


### 第一步：网页创建项目

进入个人主页点击 [创建项目] 

![](/asserts/img/first_task_1.png)

并且通过它创建一个项目，这里我们取名为 *tf-mnist* 

![](/asserts/img/first_task_2.png)

创建后自动跳转到新项目页，下图方框中即为新项目ID，可以在init时用到，注意和后面运行时的任务id区分

![](/asserts/img/first_task_3.png)


### 第二步：clone教程源码
打开终端，通过git clone下载教程源码

```
#clone项目代码
git clone https://github.com/RussellCloud/tensorflow-examples.git

#进入项目所在目录（这里我们进入第3章的代码目录）
cd tensorflow-examples/3_NeuralNetworks

```


![](/asserts/img/first_task_4.png)


### 第三步：通过 russell-cli 操作

注意后面的 *<task_id>* 就是 run 返回的 RUN ID

```
#绑定项目（也可以用 init --id <project_id>）
russell init --name tf-mnist

#运行启动指令
russell run "python mnist_cnn.py"

#查看项目状态 (别带上 < > )
russell status <task_id>

#查看运行日志（按ctrl-c退出,不会影响远程任务继续执行）
russell logs <task_id>
```

![](/asserts/img/first_task_5.png)

---

## 常见问题

1. 执行 *run* 时输出 *“Error: Task is submitted failed. Please retry after a while”*

回答：大部分情况下没有问题，过几秒重新 *run* 就行了，如果重复几次仍然出现问题，仍未解决可 [联系我们](/contact-us.md) 。

2. 执行 *logs* 时偶尔会中途断开，是不是任务挂掉了？

回答：当前设计的实时log服务与实际运行的任务是完全分离的，如果任务日志 10s 内没有新数据，实时log就会自动断开，避免不必要的资源浪费，你可以重新运行 *logs* 继续获取日志。 


### 更多问题？
如果遇到更多的问题，请参考 [运行过程常见问题](/faq/run-task.md) 进行排查，仍未解决可 [联系我们](/contact-us.md) 。







