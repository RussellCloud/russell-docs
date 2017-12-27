# 运行任务


### 快速入门

```
 russell run  [OPTIONS] [COMMAND]
```

[OPTIONS] 运行参数主要包括以下选择：
- [机器类型](#机器类型---gpu-or---cpu): `--cpu` **or** `--gpu`
- [数据集](#数据集---data): `--data <id_of_datasource>:<mount_name_on_server>`
- [任务模式](#任务模式---mode): `--mode <mode_name>`
- [框架环境](#环境----env): `--env <environment_name>`
- [备注信息](#备注--m): `-m`
- [Tensorboard](#tensorboard): `--tensorboard`


[command]为启动命令，任务运行时首先执行该命令，仅在 cli 模式下有效，jupyter等其他模式不接受该参数；

---

<!-- toc -->

---

# 概念详解

运行任务是 RussellCloud 整个工作流中最核心的一步。任务提交后首先会更新项目代码，然后排入队列等待执行，当有可用计算资源时才会开始正式执行，执行时任务会把代码和数据集挂载到一起（具体挂载路径见下），放置在对应的深度学习框架环境下并配备指定的计算资源，然后执行启动命令或启动 jupyter 帮助用户完成训练任务。

整个流程的具体实现都取决于run时的运行参数，因此你的任务能否被正确顺利执行也完全取决于此。

## [OPTIONS]
### 机器类型 `--gpu` **or** `--cpu

你可以通过这个参数选择具体任务执行时的机器配置。目前提供两种选择：

|`russell run` 参数|机器类型|备注           |
|:------------|:--------------:|:---------------------|
|`--gpu`      |GPU             |GPU服务器|
|`--cpu`      |CPU             |CPU服务器|

具体机器配置参数参见[价格页](http://russellcloud.com/price).

    - 默认机器类型是 `--cpu`，也就是说如果你不加这个参数的话，你的任务就是运行在一台CPU服务器上；
    - 如果你在run的时候添加了多个机器配置参数且同时包含了GPU、CPU，则以GPU参数为准。

---

### 数据集 `--data`

目前 RussellCloud 中单个任务支持最多挂载 5 个数据集。run时每个`--data`后面对应一个数据集

```
--data <id_of_datasource>:<mount_name_on_server>
```


关于数据集挂载的更多内容，可以参考 [挂载数据集](/dataset/mount.md)

---

### 任务模式 `--mode`

RussellCloud 目前支持以下三种任务模式：

1. `--mode cli` (默认)
2. `--mode jupyter`
3. `--mode serve` （测试中）

下面是各个模式的介绍：

#### `--mode cli`

`cli` 是默认模式，所以在 `run` 的时候 **不需要** 显式指定，用更通俗的方式来表达，这其实就是`命令模式`。

当你通过这个模式启动一个任务时，当前目录的代码将会被上传，然后系统将会在实验环境下部署环境并将上传的代码放在/workspace目录下，接着在该目录执行启动命令。


#### `--mode jupyter`

这个模式可以帮助你创建一个 jupyter notebook 环境，当你使用`jupyter`模式启动一个任务时，你当前目录的代码将会被上传到云端，然后系统将在/workspace目录下创建一个jupyter notebook,并将访问链接返回给客户端。一般来说创建成功后客户端将会自行帮助你在浏览器打开notebook.

![](/asserts/img/run_task_02.png)

如果项目代码中包含 `.ipynb` 文件，在项目详情页-预览栏可以直接查看内容：

![](/asserts/img/run_task_01.png)

> jupyter 能用来做什么
> - 可用于创建一个交互式的开发网页，帮助你逐步调试模型算法；
> - 还可以用来连接任务环境的 terminal ，通过 terminal 你可以更自由地进行更多操作。

![](/asserts/img/run_task_03.png)


#### `--mode serve`

本模式正在测试中，暂不介绍

---

### 环境  `--env`

你可以通过这个参数指定具体的深度学习框架环境，目前可选的环境可以前往 [环境配置](./environment.md) 查看详细。注意对于不同 [机器配置](#机器类型---gpu-or---cpu) 来说，环境参数是没有区别的。

```
举几个例子

$ floyd run --env tensorflow-1.3 "python train.py"

$ floyd run --env theano-0.8 "python train.py"

$ floyd run --env pytorch-0.2 "python train.py"

```

---

### 备注 -m

通过 `-m` 参数你可以给对应版本（如果有新增版本的话）以及对应任务添加备注，启动后你可以在任务列表及版本列表看到备注信息，当你查看历史任务时，备注可以帮助你更好的区分各个任务。

Example:

```
$ russell run -m "reduce epoll to 100" "python train.py --epoch 100"
Creating project run. Total upload size: 66.2KiB
Syncing code ...
RUN ID                            NAME                                      VERSION
--------------------------------  --------------------------------------  ---------
ee13c7e306924ad3bc0d4af7428eb464  RussellCloud/train_passenger_predict:9          9

To view logs enter:
   russell logs ee13c7e306924ad3bc0d4af7428eb464
```

---

### Tensorboard

通过 `--tensorboard` 命令，你可以为 tensorflow 任务创建 Tensorboard。

---

## [COMMAND]

你应该在 `[COMMAND]` 位置写上启动命令。这条启动命令将在任务启动时在远程环境中执行，运行目录是 `/workspace`,
即代码所在目录，为了确保这条命令运行正常 ，你可以先在本地代码目录首先执行这条命令试试看能否运行成功。

另外，系统环境为ubuntu系统，因此请使用ubuntu的命令体系，比如`apt-get install`.

你可以在项目目录下先试试这些例子：

```bash
$ russell run "pwd"
```

```bash
$ russell run "ls"
```

```bash
$ russell run "python -v"
```

```bash
$ russell run "echo 'Hello, Russell!'"
```

如果你需要在启动命令中运行多条命令，这里有两种做法：

- 使用 && 连接两条命令；

```bash
$ russell run "bash my_setup_script.sh && python train.py"
```

- 在当前项目路径下创建一个 start_script.sh 并在其中编辑启动命令（注意不要命名为`run.sh`，避免和系统文件冲突）。

```bash
$ russell run "sh start_script.sh"
```

> 敲黑板：只有默认模式才接受启动命令～