# russell run
在RussellCloud上运行你的项目。

## 查看帮助
```bash
russell run --help
```
输出：
```
Usage: russell run [OPTIONS] [COMMAND]...

  Run a command on Russell. Russell will upload contents of the current
  directory and run your command remotely. This command will generate a run
  id for reference.

Options:
  --gpu / --cpu                   Run on a gpu instance
  --data TEXT                     Data source id to use
  --mode [job|jupyter|serve]      Different russell modes
  --env [caffe|caffe:py2|chainer|chainer:py2|keras|keras:py2|kur|mxnet:py2|pytorch|pytorch:py2|tensorflow|tensorflow-1.0|tensorflow-1.0:py2|tensorflow:py2|theano|theano:py2|torch|torch:py2]
                                  Environment type to use
  -m TEXT                         Message to commit
  --help                          Show this message and exit.
```

## 命令
```bash
russell run [OPTIONS] [COMMAND]
```

## 选项

|可选项|默认值|描述|
|---|---|---|
|--gpu/--cpu|cpu|如果指定，则在所指定的实例类型上运行任务|
|--data <ID:mount>||ID指定挂载的数据集，mount指定挂载的目录。注：mount仅v0.5.5以上版本支持|
|--mode[job&#124;jupyter&#124;serve]|job|指定任务的运行模式，默认行为是执行所指定的命令|
|--no-open||输出jupyter模式的url，而不是直接打开浏览器。注：仅v0.5.5以上版本支持|
|--env[...]|keras:py3|指定项目任务的运行环境，[支持的环境列表](/project/task/environment.md)|
|--m<message_str>||任务描述|
|command||所运行的命令，任务入口|

## 描述

该命令将上传CLI所追踪的代码文件到RussellCloud服务器，然后执行你的命令。你可以通过[status](/cli/status.md)命令查看任务进度，通过[logs](/cli/logs.md)命令查看任务日志。


例如：
1. 使用gpu + tensorflow环境

```bash
russell run --env tensorflow --gpu "python mnist_cnn.py"
```

输出：
```
Creating project run. Total upload size: 129.1KiB
Syncing code ...
RUN ID                            NAME                       VERSION
--------------------------------  -----------------------  ---------
5b5e9b106d754b74acbe87c8e9618265  RussellCloud/tinyflow:2          2


    To view logs enter:
        russell logs 5b5e9b106d754b74acbe87c8e9618265
```

### **russell_requirements.txt**

Russell对多种多样的深度学习框架使用标准的Docker镜像。如果您需要额外的Python依赖，您可以在项目文件夹下的`russell_requirements.txt`中指定。


### Jupyter notebook
Russell支持在服务器端以Jupyter/iPython模式运行。

### Serve
Russell可以将模型发布为线上REST-api接口。仅v0.6.0以上版本支持。


## 遇到更多问题？

如果您在使用过程中，发现终端有一些“意外”的输出，或者有其他的不愉快体验，请[联系我们](/contact-us.md)，帮助我们更好地改进产品、增强用户体验。

