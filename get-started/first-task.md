# 第一个任务
基于 *tensorflow* 框架的 CNN 手写数字识别

在本小节，我们将介绍如何使用 Russell Cloud，创建你的第一个深度学习项目。

我们使用的代码来自 Github：[RussellCloud/TensorFlow-Examples](https://github.com/RussellCloud/TensorFlow-Examples)。数据集MNIST在代码中自动完成下载。

---

<!-- toc -->

---

## 准备

* [注册 RussellCloud 账号](http://russellcloud.com/#regist)
* [安装 *russell-cli* 终端工具](/get-started/install.md)
* [通过 *russell-cli* 登录账号](/login-cli.md)

---

## 第一个任务


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


{% include "/contributing.md" %}