# 使用 RNN 生成唐诗
这一例子中我们将会在 RussellCloud 上示范如何用 RNN 生成唐诗（poetry_generator）。

您将在这个例子中学会：
- 如何使用已有数据集训练自己的模型
- 输出模型为数据集便于以后操作使用
- 使用输出的中间模型

---

目录：
<!-- toc -->

---

## 准备：

* [注册 RussellCloud 账号](http://russellcloud.com/#register)
* [在本地安装 cli 客户端](/get-started/install.md)
* Clone 项目文件，[Git地址](https://github.com/RussellCloud/poetry_generator)
```bash
# clone项目
$ git clone https://github.com/RussellCloud/poetry_generator
```
* 登录 cli 工具
```bash
# 使用russell login命令登录
$ russell login
```

## 项目准备：

### 新建项目

点击[项目创建页]创建名为`Poetry_Generator`的项目，默认环境选：`tensorflow-0.12` (注意不要选 tensorflow-0.12:py2 )

![](/asserts/img/poetry-generator-newproject.png)

### 初始化项目

你可以选择使用项目名初始化，也可以在项目概览上复制项目概览ID用 --id 参数初始化。

```bash
# 进入项目目录
$ cd poetry-generator

# 初始化项目
$ russell init --name Poetry-Generator
# 或使用russell init --id <项目概览ID>初始化
$ russell init --id XXX
```

## 训练模型

### 启动训练模型任务

使用 russell run 命令启动一个任务训练我们的唐诗生成模型。这里我们需要挂载一个唐诗的数据集到`/input/data`下，所以我们指定挂载名为`data`。唐诗数据集的 ID 为：ee3da33467b04b4680ab31f523aeea6f。

```bash
# 运行模型训练代码并引用数据云上已经准备好的数据集
$ russell run "python trainer.py" --data ee3da33467b04b4680ab31f523aeea6f:data --gpu
# 如果未使用GPU机器，则训练需要一个晚上的时间，使用--gpu参数可以使用GPU机器，将训练缩短到三十分钟
```

此代码在训练过程中并没有什么日志输出，但是你可以通过查看主页上的任务运行状况来了解其是否正确运行。如果运行出现问题，一般会在3分钟之内就结束，你需要检查任务日志查找和解决问题。这里也能看到 GPU机器 和 CPU机器 的运行速度差别。

![](/asserts/img/poetry-generator-running.png)

### 输出训练模型

输出训练模型为数据集与查看输出文件类似，都是通过查看网页上运行任务的“输出”一栏来输出。这里输出为一个新建的数据集`poetry-generator-model`。

![](/asserts/img/poetry-generator-outputmodel1.png)

![](/asserts/img/poetry-generator-outputmodel2.png)

你可以直接浏览我们示例输出的模型：[训练好的模型](http://russellcloud.com/RussellCloud/dataset/poetry_generator_model/versions)


## 使用训练的模型生成诗词

### 启动诗词生成任务

我们仍然使用这个上传好的项目，但这次运行的是生成代码，而且挂载的也换成了我们刚才生成的模型数据集。已经训练好的模型数据集版本ID：`f030014be22b4965987d5b45f7093711`

```bash
# 运行诗词生成代码并引用上一步中生成的模型数据，你可以将ID替换为自己生成的模型版本ID，注意：一定不要将版本ID与概览ID混淆
$ russell run "python gen_poetry.py" --data f030014be22b4965987d5b45f7093711:model
```

### 查看输出的诗词

这个生成诗词代码是直接输出在日志中，所以我们要通过任务ID获取日志，当然你也可以在网站的任务界面直接看日志。

```bash
#从日志中查看生成的诗词
$ russell logs <run_id>
```

运行结果：

![](/asserts/img/poetry-generator-result.png)