# 版本控制

RussellCloud在最开始设计的时候就加入了对版本控制的需求，通过实现版本控制，我们可以更好地追踪过去的版本修改记录，尽管当前实现的还比较粗陋（尚未支持 Git 协议），但已经满足基本的需求，至少复现过去的实验是没有问题的。

---

<!-- toc -->

---

## 如何提交一个版本

当前的客户端设计把项目的版本提交绑定在运行任务的过程中，即提交一个任务时，客户端将会根据配置上传当前项目目录下的文件并自动存入一个新的版本。（在未来的设计中，可能会将这个过程分离）

在提交版本时，需要特别注意的是，我们会对要上传的项目文件大小做出限制，当前最大上传大小为100M,超出上传的大小限制，客户端会提示：

```
Creating tar archive
compressed size: 135394533 Bytes
Code size too large to sync, please keep it under 100MB.
If you have data files in the current directory, please upload them 
separately using "russell data" command and remove them from here.
```


## 如何查看某个版本的项目代码

进入 项目-版本 ，选择一个版本，并点击右边的查看文件（只有当前版本状态是 valid 才会显示），即跳转文件浏览页面
![](/asserts/img/version_control_1.gif)


## 如何给项目的某个版本添加备注
在项目版本较多的情况下，为了便于以后我们回顾某个项目版本的变更，我们可以为项目的每个版本添加一个备注，具体操作步骤是进入 项目-版本 ，选择一个未备注过的版本，在备注一栏选择“添加备注”，在弹出备注输入框后，我们可以在里面键入备注信息，点击保存备注，即可完成备注操作。
![](/asserts/img/version_remark.gif)


## 如何删除项目的某个版本
进入 项目-版本 ，选择一个版本，并点击右边的删除版本图标，然后网页会弹出确认框，点击“立即删除”即可删除改项目版本。
![](/asserts/img/version_delete.gif)



