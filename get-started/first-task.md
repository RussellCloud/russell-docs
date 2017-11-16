# 第一个任务

在这一小节，我们将使用 RussellCloud 快速创建一项 基于 tensorflow 框架的简单逻辑回归 实现手写数字识别，并让它迅速的运行在我们的计算云服务上，这里使用的是 Github 上的基础教程源码 [TensorFlow-Example](https://github.com/RussellCloud/TensorFlow-Examples) 以及 MNIST 数据集。

## 预先准备事项

* [注册 RussellCloud 账号](http://russellcloud.com/#regist)
* [安装 *russell-cli* 终端工具](/get-started/install.md)
* [通过 *russell-cli* 登录账号]()



### 第一步：项目准备

```
#clone项目代码
git clone https://github.com/RussellCloud/tensorflow-examples.git

#进入项目所在目录（这里我们进入第3章的代码目录）
cd tensorflow-examples/3_NeuralNetworks


#创建项目
russell create tf-boy
```

### 第二步：运行项目

```
#运行启动指令
russell run "python -u dynamic_rnn.py"

#查看项目状态
russell status <task_id>

#查看运行日志（按ctrl-c退出）
russell logs <task_id>
```



