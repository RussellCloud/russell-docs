# russell output
russell-cli提供一组命令实现在终端内对数据集进行管理。

## 查看帮助 --help

您可通过键入`$ russell status --help`命令查看使用帮助。 

```
Usage: russell status [OPTIONS] [ID]

  View status of all or specific run. It can also list status of all the
  runs in the project.

Options:
  --help  Show this message and exit.
```

## 选项

## 详情

1. 查看任务状态
执行命令：
```bash
russell status 50e216f7467546e4b8ea1167ce38a185
```

您可以看到类似这样的输出：
```
RUN ID                            CREATED         STATUS      DURATION(s)  NAME      INSTANCE      VERSION
--------------------------------  --------------  --------  -------------  --------  ----------  ---------
50e216f7467546e4b8ea1167ce38a185  51 seconds ago  running               0  tinyflow  cpu                 1
```
 
- DURATION 任务在云端实际运行的总时长，所谓“按秒计费”是依据这个标准的。任务在运行中，这里显示的DURATION将一直是0。


## 遇到更多问题？

如果您在使用过程中，发现终端有一些“非正常”的输出，或者有其他的不愉快体验，请[联系我们](/contact-us.md)，帮助我们更好地改进产品、增强用户体验。




