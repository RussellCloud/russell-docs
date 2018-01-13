# 使用 RNN 生成唐诗
这一例子中我们将会在 RussellCloud 上示范如何用 RNN 生成唐诗（poetry_generator）。

您将在这个例子中学会：
- 如何使用已有数据集训练自己的模型
- 如何使用自己训练的模型

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

## 训练模型：

### 新建项目

点击[项目创建页]创建名为`Poetry_Generator`的项目，默认环境选：`keras` (注意不要选 kera:py2 )

![](/asserts/img/poetry-generator-newproject.png)

### 初始化项目

你可以选择使用项目名初始化，也可以在项目概览上复制项目概览ID用 --id 参数初始化。

```bash
# 进入项目目录
$ cd poetry-generator

# 初始化项目
$ russell init --name Poetry-Generator
# 或使用russell init --id <项目概览ID>初始化
```

### 启动训练模型任务

使用 russell run 命令启动一个任务训练我们的唐诗生成模型。这里我们需要挂载一个唐诗的数据集到`/input/data`下，所以我们指定挂载名为`data`。唐诗数据集的 ID 为：ee3da33467b04b4680ab31f523aeea6f。

```bash
# 运行模型训练代码并引用数据云上已经准备好的数据集
$ russell run "python trainer.py" --data ee3da33467b04b4680ab31f523aeea6f:data

# 查看训练日志
$ russell logs <run_id> 

# 如果未使用GPU机器，则训练需要一个晚上的时间，GPU可以将训练缩短到几十分钟
# 训练结束后通过info命令获取项目输出output_id
$ russell info <run_id>

```

现在可以直接浏览输出的模型目录：[训练好的模型](http://russellcloud.com/RussellCloud/dataset/poetry_generator_model/versions)


## 使用训练的模型生成诗词
仍然使用我们这个项目，但是这次运行的是生成代码
```
# 运行诗词生成代码并引用上一步中生成的模型数据
# <output_id>是上一步训练过程中通过info命令获取到的id
# 如跳过上一步，可直接使用预先训练好model的数据集：f030014be22b4965987d5b45f7093711

russell run "python gen_poetry.py" --data f030014be22b4965987d5b45f7093711:model

#从日志中查看生成的诗词
russell logs <run_id_2>

#顺利结束
```

