## 泰坦尼克号乘客分析（Notebook） {#_2}

这一小节中我们将会在Russell Cloud上 示范 kaggle 上面泰坦尼克号乘客死亡预测的例子 ，你可以在这个例子中学会如何创建 notebook 模式下的任务，数据集引用以及添加依赖等操作。

第一步：项目准备

```
# clone代码
$ git clone https://github.com/RussellCloud/kaggle_titanic.git

# 数据集准备（下面步骤可跳过，直接使用数据集ID：b9cc2a3077454d8b80e37e1be521e265）
# 打开数据集所在目录
$ cd kaggle_titanic/data/

# 数据集初始化
$ russell data init titanic_data

# 数据集上传
$ russell data upload

# 上传成功后你将会获得数据集ID
```

第二步：启动项目

```
# 打开代码所在目录
$ cd code

# 由于本项目需要使用seaborn库进行数据可视化，因此在项目下创建russell_requirements.txt
$ echo "seaborn" >> russell_requirements.txt

# 以jupyter模式启动，可能需要等待一小会，返回相应浏览器可访问的notebook链接
$ russell run --mode jupyter --data <data_id>
```

备注：jupyter模式下的任务不会自动关闭，使用stop命令主动结束，如下:

```
russell stop <run_id>
```



