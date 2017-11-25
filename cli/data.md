# russell data
管理数据集。

|命令|描述|
|---|---|
|russell data init|初始化一个数据集|
|russell data upload|创建并上传一个新的数据集版本|
|russell data status|列出所有的数据集|
|russell data clone|克隆一个已存在的数据集|
|russell data delete|删除数据集|
|russell data output|查看数据集内容|

## 查看帮助
命令：
```bash
russell data --help
```
输出：
```
Usage: russell data [OPTIONS] COMMAND [ARGS]...

  Subcommand for data operations

Options:
  --help  Show this message and exit.

Commands:
  delete  Delete data set.
  init    Initialize a new data upload.
  output  Shows the output url of the run.
  status  Show the status of a run with id.
  upload  Upload data in the current dir to Russell.
```

## 初始化 russell data init
### 查看帮助
```bash
russell data init --help
```
输出：
```
Usage: russell data init [OPTIONS]

  Initialize a new data upload. After init ensure that your data files are
  in this directory. Then you can upload them to Russell. Example:

      russell data upload

Options:
  --id TEXT    Remote dataset id to init
  --name TEXT  Remote dataset name to init
  --help       Show this message and exit.
```
### 命令
```bash
russell data init --id DATASET_ID
```
或者
```bash
russell data init --name DATASET_NAME
```
这里的[DATA_ID]，在RussellCloud官网中创建数据集后，您可以点击浏览器中【数据集\|概览\|基础信息】中的复制按钮获取数据集的唯一ID。


### 选项

|选项|默认值|描述|
|---|---|---|
|--id||数据集ID|
|--name||数据集名称|

### 详情
RussellCloud会管理您的实验数据集，在运行项目的时候您可以使用这些数据集。初始化命令会初始化当前目录，track所有的文件和子文件夹。需要确保初始化参数的id和name是已经在官网创建的数据集。

如果数据集不存在，CLI会打开浏览器并跳转到创建数据集的页面。（v6.0.0以上版本支持）

示例：
```bash
russell data init --id 45a8b39ec0134f58becd7a4660312a3e
```
或者
```bash
russell data init --name first-test
```
输出：
```
Data source "first-test" initialized in current directory

    You can now upload your data to Russell by:
        russell data upload
```

## 上传 russell data upload
### 命令
完成初始化后，可以键入：
```bash
russell data upload
```

### 详情
该命令将当前目录下的内容作为已初始化的数据集的一个新版本——
我们将使出洪荒之力将您的数据集文件通过⚡️传送至云端。然后您可以在[run](/cli/run.md)命令中引用该数据集。

目前该命令还不支持`.russellignore`文件。

- **示例：**

如果上传一切顺利的话，您可能会看到这样的输出：
```
compressing files...
Creating tar archive
compressed size: 145334 Bytes
Start uploading...
100% |########################################################################|
Upload finished
DATA ID                           NAME                         VERSION
--------------------------------  -------------------------  ---------
faecc90b11a5434394967f6cfa679ebb  RussellCloud/first-test:2          2

Upload finished, start extracting to data module

    To check data status enter:
        russell data status faecc90b11a5434394967f6cfa679ebb
```

## 状态 russell data status
### 命令
```bash
russell data status [ID]
```

### 选项 

|选项|默认值|描述|
|---|---|---|
|ID||数据集ID|

### 详情

示例：
```bash
russell data status faecc90b11a5434394967f6cfa679ebb
```
输出：
```
DATA ID                           CREATED        STATE    DISK USAGE      NAME          VERSION
--------------------------------  -------------  -------  --------------  ----------  ---------
faecc90b11a5434394967f6cfa679ebb  2 minutes ago  valid    less than 1 MB  first-test          2
```

**请注意，这里的【DATA ID】不是初始化时所使用的ID。**

这里的STATE对应项如果是valid，说明该数据集上传成功，已经可以正常使用。

其他可能的状态：
- pending 未开始写文件
- uploading 上传中
- failed 上传失败

上传失败不用气馁，您可以尝试重新上传：`$ russell data upload`即可。如果连续多次上传失败，请联系我们^\_^。


## 输出 russell data output
### 命令
```bash
russell data output [OPTIONS] ID
```

### 选项
|选项|默认值|描述|
|---|---|---|
|--url, -u||只在终端打印URL，不打开浏览器|
|ID||数据集ID|

## 遇到更多问题？

如果您在使用过程中，发现终端有一些“非正常”的输出，或者有其他的不愉快体验，请[联系我们](/contact-us.md)，帮助我们更好地改进产品、增强用户体验。




