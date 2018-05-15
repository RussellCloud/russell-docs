# russell init
初始化一个RussellCloud项目。

## 查看帮助

```bash
russell init --help
```
输出：
```
Usage: russell init [OPTIONS]

  Initialize new project at the current dir.

      russell init --name test_name

  or

      russell init --id 151af60026cd462792fa5d77ef79be4d

Options:
  --id TEXT    Remote project id to init
  --name TEXT  Remote project name to init
  --help       Show this message and exit.
```

## 命令
```bash
russell init --id PROJECT_ID
```
或者
```bash
russell init --name PROJECT_NAME
```

## 选项

|可选项|默认值|描述|
|---|---|---|
|--id|False|项目id|
|--name|False|项目名|

两个可选项必须选择至少一个，同时选择两个则`--id`优先。


## 详情
该命令将使用所给参数初始化当前文件夹。请确保所输入的id或者name是在RussellCloud上已经存在的，并且该id所对应的项目是当前登录用户的，或者您拥有一个名叫name的项目。

该命令将在当前文件夹下创建一个`.russellexpt`文件，和一个`.russellignore`文件。您可以编辑`.russellignore`文件，当您运行任务时，这些文件将不会被上传。

如果需要初始化一个数据集，您需要使用[russell data init](/cli/data.md)命令。

例如：
1. 使用id
```bash
russell init --id 50e216f7467546e4b8ea1167ce38a185
```
输出：
```
Project "tinyflow" initialized in current directory
```

2. 使用name
```bash
russell init --name tinyflow
```
输出：
```
Project "tinyflow" initialized in current directory
```

## 遇到更多问题？

如果您在使用过程中，发现终端有一些“意外”的输出，或者有其他的不愉快体验，请[联系我们](/contact-us.md)，帮助我们更好地改进产品、增强用户体验。

