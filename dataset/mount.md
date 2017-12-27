# 挂载数据集

## russell run运行项目时挂载数据集

* 基本用法
```bash
russell run "command" --data data_id
```
command 是需要运行的命令
data_id 是数据集的 id ，**注意此处的 id 是要挂载数据集某个版本的 id **，不是数据集概览 id 。一个数据集可以有多个版本，版本 id 是上传完成后提示的  id ，也可以在数据集页面的版本标签下查看。


* 指定挂载目录
```bash
russell run "command" --data data_id
```
例如
```bash
russell run "python trainer.py" --data ee3da33467b04b4680ab31f523aeea6f:/data
```
这个例子会将数据集的内容挂载到 /input/data 下
如果未指定挂载目录，数据集将会挂载到 /input/DATA_NAME-VERSION目录下
DATANAME 是数据集名称， VERSION 是版本号，假如数据集名称是Poetry版本号是1，则会挂载到 /input/Poetry-1 目录下