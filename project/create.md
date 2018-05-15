# 新建项目

---

<!-- toc -->

---

### 项目：概念解读
在 RussellCloud ，项目的概念与 *Github* 的 *Repository* （仓库）类似，在 版本仓库 的基础上加入了对 *任务* 的管理，同样的，你也可以查看甚至 [fork](/project/fork.md) 其他用户的公开项目。

---


## 新建项目


### 网页入口

<br />

* （登录后）导航栏右上角「+」号

![](/asserts/img/create_project_1.png)

<br />

* （登录后）个人主页-项目栏—列表右上角

![](/asserts/img/create_project_2.png)

<br />
<br />

### 填写信息

点击 [新建项目](http://russellcloud.com/project/create) 后进入创建页，填写 项目名、项目描述（可选），并选择 权限、默认容器环境。

> 项目名只能由 字母、数字、-（中划线）、_（下划线）组成，不超过 31 位；
> 
> 权限：公开项目为所有人可见，且项目数量不受限；私有项目只有创建者可见，且项目数量有限制（免费账户不能创建私有项目）；
> 
> 默认容器环境：执行 run 运行任务时，如果不明确指定 env（即运行环境），则默认为当前项目的默认容器环境；

![](/asserts/img/create_project_3.png)

<br />

### 补充 README 描述
如果你使用过GitHub 的话应该知道 README.md 的用法，同样的，RussellCloud 支持自动加载 README，你只需要在项目目录下创建 README.md 并按照 MarkDown 规范（与 github 一致）写入内容，在你下一次 run 时，README文件就会自动上传并在 [项目页-描述] 模块中加载。

（小建议：如果需要插入视频或者图片，建议使用第三方图床链接，不要把资源放在项目目录中，推荐教程：[截图快速上传到七牛](http://www.cnblogs.com/harlanc/p/6923500.html)）

```
#在项目目录下绑定项目（也可以用 init --id <project_id>,注意不需要 <> ）
russell init --name <project_name>

#...在项目目录中创建README.md并输入内容(略)...

#执行一次任务将会自动上传
russell run "ls"

```
这时打开项目页，就能看到描述中已经加载最新的README内容

<br />
<img width=80% src="../asserts/img/create_project_4.gif"/>
<br />

> (原文：https://help.github.com/articles/about-readmes/)
>
> A README is often the first item a visitor will see when visiting your repository.
> README files typically include information on:
>
> What the project does
>
> Why the project is useful
>
> How users can get started with the project
>
> Where users can get help with your project
>
> Who maintains and contributes to the project
