## 泰坦尼克号乘客分析（Notebook） 

这一小节中我们将会在 Russell Cloud 上示范 kaggle 上面泰坦尼克号乘客死亡预测的例子。

您将在个例子中学会：
- 如何创建 notebook 模式下的任务。
- 如何添加依赖。
- 如何引用数据集。

---
### 复现过程：

前提：
* 使用邀请码在官网进行注册
* [在本地安装 cli 客户端](/get-started/install.md)
* 在 cli 客户端通过 login 登录

第一步：项目准备

#### 在官网创建项目
点击[项目创建页]创建名为`kaggle_titanic`的项目，默认环境选不变。


#### 绑定本地项目

```
# clone项目代码
git clone https://github.com/RussellCloud/kaggle_titanic.git
cd kaggle_titanic
russell init --name kaggle_titanic

# 数据集准备（下面步骤可跳过，直接使用数据集ID：b9cc2a3077454d8b80e37e1be521e265）
# 打开数据集所在目录
cd kaggle_titanic/data/

# 数据集初始化
russell data init --name titanic_data

# 数据集上传
russell data upload

# 上传成功后你将会获得数据集ID
```

第二步：启动项目

```
# 打开代码所在目录
cd code

# 由于本项目需要使用seaborn库进行数据可视化，因此在项目下创建russell_requirements.txt
echo "seaborn" >> russell_requirements.txt

# 绑定远程项目
russell init --name <project_name>

# 以jupyter模式启动，可能需要等待一小会，返回相应浏览器可访问的notebook链接
russell run --mode jupyter --data <data_id>:data
```

备注：jupyter模式下的任务不会自动关闭，使用stop命令主动结束，如下:

```
russell stop <run_id>
```



