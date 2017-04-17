## 数据集介绍 {#_2}

RussellCloud为个人用户提供数据云服务，用于管理、分享数据集，不用再下载数据集到本地，实现随时随地调用数据集的「美好愿望」，同时，你也可以在「探索」模块中找到感兴趣的数据集进行探索挖掘。

## 操作方式 {#_2}

1. 任务调用数据

```
#在不同模式的任务中引用数据集
$ russell run --data <data_id> <command>

$ russell run --mode jupyter --data <data_id>
#创建成功后引用数据集作为输入数据出现在项目所在目录下input文件夹中
```

   2. 任务输出数据

```
#任务创建时会在项目目录下创建output文件夹，任务结束时自动将output文件夹中的数据导入数据云
#通过 info 指令获取output_id（即输出数据集的id），<run_id>指任务ID
$ russell info <run_id>

# 通过 output 指令直接从浏览器打开任务输出数据集，可以直接下载或者预览
$ russell output <run_id>
```

   3. 数据集操作

```
#数据集初始化
russell data init <data_name>

#数据集上传
russell data upload

#查看数据集
russell data output <data_id>
```



