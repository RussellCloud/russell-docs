# 名画风格学习

这一小节中我们将会在 Russell Cloud 上示范名画风格学习（style transfer 又称风格迁移）的例子。

您将在个例子中学会：
- 创建 bash 模式下的任务。
- 使用 GPU 支持
- 查看和保存输出文件

---

目录：
<!-- toc -->

---

## 准备：
* [注册RussellCloud账号](http://russellcloud.com/#register)
* [在本地安装 cli 客户端](/get-started/install.md)
* Clone 项目文件，[Git地址](https://github.com/RussellCloud/Neural_Style)
```bash
# clone项目
$ git clone https://github.com/RussellCloud/Neural_Style
```
这里会有一个小坑，有关启动 bash 模式下的任务。当我们的项目需要执行 shell 脚本时，这个脚本的文本格式必须为Unix格式。如果你使用 Windows 环境克隆本项目，克隆的 shell 脚本为Dos格式，运行项目时会出现无法运行的情况。可以参考社区的帖子解决：[russell run在运行shell脚本时日志出现错误](http://forum.russellcloud.com/read.php?tid=7&fid=9)

## 复现过程：

### russell login 登录
```bash
# 使用russell login命令登录
$ russell login
```
输入y，网页登录后在网页端拷贝账户的Token，粘贴进终端，回车。如果你使用Windows的命令行，可能会出现粘贴不进的情况，请右键窗口粘贴。成功登录后输出：
```bash
Login Successful as XXX
```

### 新建项目
来到RussellCloud主页，进入控制台，新建一个项目。项目名 Neural_Style ，默认容器环境选择：`tensorflow-1.0:py2`。

![](/asserts/img/style-transfer-newproject.jpg)

### 初始化项目
你可以选择使用项目名初始化，也可以在项目概览上复制项目概览ID用 --id 参数初始化。
```bash
# 进入项目目录
$ cd Neural_Style

# 初始化项目
$ russell init --name Neural_Style
# 或使用russell init --id <项目概览ID>初始化
```
初始化成功输出：
```bash
Project "Neural_Style" initialized in current directory
```

### 启动项目
初始化完成后我们用russell run命令运行，项目文件已经准备好了一个shell脚本，只需要指定一个content_img/video和一个style_img的图片路径就可以生成了。为了启动 GPU 支持，我们在命令中加入 `--gpu` 参数。
```bash
# russell run 运行项目下shell脚本生成
$ russell run "bash stylize_image.sh ./image_input/lion.jpg ./styles/kandinsky.jpg" --gpu  --data bf9f524a384c4a69a021f0cf122815ec:model
```
约2分钟时间，任务运行完成。

### 查看输出文件并下载
现在我们的输出文件及查看日志在网页端即可完成，打开我们的控制台，找到刚刚运行的任务。点击“运行日志”查看日志：

![](/asserts/img/style-transfer-logs.jpg)

点击“输出”查看输出：

![](/asserts/img/style-transfer-result.jpg)

然后右键将我们的图片另存到我们想要的位置。