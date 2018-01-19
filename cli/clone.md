# russell clone

将Russell远程仓库的项目克隆到本地目录。

## 查看帮助

```bash
russell clone --help
```

输出：

```
Usage: russell clone [OPTIONS] PROJECT_ID

  At present only support clone by id Clone remote project at the current
  dir.

Options:
  --help  Show this message and exit.
```

## 命令

```bash
russell clone [OPTIONS] PROJECT_ID
```

## 选项

## 详情

当前默认clone最新版本的代码，运行前请确认当前目录下没有与项目名同名的目录， 否则无法运行成功

实例：

```
$russell clone 2819a77485b24cdebd3a84a938d536af
```

输出:

```
Downloading the tar file to the current directory ...
Uncompressring the contents of the file ...
Cleaning up the compressed file ...
Project "tf-mnist" clone success
Project "tf-mnist" auto initialized in current directory
```

如果当前目录下已存在同步文件夹，会clone失败，如在上面运行的基础上，再次运行：

```
$russell clone 2819a77485b24cdebd3a84a938d536af
```

输出:

```
Clone ERROR! Directory/File Existed. Retry by changing name.
Project "5aa50663aa2845dab10ac87e47c4fcc9" clone failed
```

## 遇到更多问题？

如果您在使用过程中，发现终端有一些“意外”的输出，或者有其他的不愉快体验，请[联系我们](/contact-us.md)，帮助我们更好地改进产品、增强用户体验。

