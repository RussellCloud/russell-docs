# data 命令组
russell-cli提供一组命令实现在终端内对数据集进行管理。

### 查看帮助 --help

您可通过键入`$ russell data` 或者 `$ russell data --help`命令查看使用帮助。


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


### 初始化 init

您可通过键入`$ russell data init --help`命令查看初始化的帮助文档。

>>下面是可能的帮助文档输出结果，不保证与实际输出完全一致，请以实际输出为准。

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

在RussellCloud官网中创建数据集后，您可以点击浏览器中【数据集\|概览\|基础信息】中的复制按钮获取数据集的唯一ID，然后键入

```bash
russell data init --id <dataset-id>
```

回车后您可以看到初始化的结果，可能像下面这样：

```
Data source "first-test" initialized in current directory

    You can now upload your data to Russell by:
        russell data upload
```

如果是其他的异常输出，可能是您输入的<dataset-id>存在于外太空，或者存在于婶婶的脑海里吧^\_^。严肃脸，请参照提示检查id是否输入错误，或者联系我们（请提交当前目录下的隐藏文件`.russelldata`）。

- 如果您觉得id实在是过于冗长，我们也支持使用数据集的名称进行初始化：
```bash
russell data init --name first-test
```


### 上传 upload

完成初始化后，可以键入：
```bash
russell data upload
```

我们将使出洪荒之力将您的数据集文件通过⚡️传送至云端。

如果一切顺利的话，您可能会看到这样的输出：

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

如果你修改了本地数据集文件，可以上传一个新版本，这将与之前上传的版本完全隔离。您可以在上传后看到版本号的变化。

```
compressing files...
Creating tar archive
compressed size: 145331 Bytes
Start uploading...
100% |########################################################################|
Upload finished
DATA ID                           NAME                         VERSION
--------------------------------  -------------------------  ---------
0cf470341d1c467194c2418c031e2934  RussellCloud/first-test:3          3

Upload finished, start extracting to data module

    To check data status enter:
        russell data status 0cf470341d1c467194c2418c031e2934
```

### 查看状态 status

在上传成功或者上传失败后，您可以复制输出中最后一行，形如`russell data status faecc90b11a5434394967f6cfa679ebb`，在终端中粘贴、回车后，你可以看到该id所对应数据集的上传状态。

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

## 遇到更多问题？

如果您在使用过程中，发现终端有一些“非正常”的输出，或者有其他的不愉快体验，请[联系我们](/contact-us.md)，帮助我们更好地改进产品、增强用户体验。




