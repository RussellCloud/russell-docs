# 运行任务过程可能遇到的问题

---

<!-- toc -->

---

## 日志

- 创建cli模式任务后，任务日志中为什么会一直查看不到任务执行日志？

>1. 首先，需要确认任务的启动命令执行正常时会有日志输出 (比如在本地试运行)；
>
>2. 其次，如果是通过 「python ***.py」的方式启动任务，请尝试添加 `-u` 参数（使用这个参数 会强制 stdin, stdout 和 stderr变为无缓冲的，会立刻输出出来，而不是等缓冲区满了才会打印数据），如下：

```
russell run "python -u test.py"
```

---

### 数据集

- 使用「--data」参数挂载数据集以后，启动任务报错：id对应资源不存在（如下图）

![](/asserts/img/error_not_found_id.png)

>run 的时候出现这个报错几乎可以确定是因为 id 的错误使用，这里需要强调的是 `--data`后面接的 id 是数据集具体版本的id（并非数据集id，该 id 仅使用于 data init），需要从数据集的版本列表获取，如下图：

![网页查看和复制数据集版本id](/asserts/img/dataset_mount_id1.png)


- 在挂载了数据集的 `jupyter` 任务中，为什么在notebook中找不到挂载的数据集？

>挂载的数据集访问目录是在 `/input/****/` 下面，而 notebook 是在 `/workspace/` 下面，所以你无法在notebook中查看到这个目录；
>
>但这个目录是切实可以访问的，你可以通过代码访问到，也可以新建一个 `terminal` 直接访问查看。



# 遇到其他的问题？

* 请您先仔细check FAQs，尝试可能的解决方案；
* 如果仍未解决，您可以在GitBook的讨论页面（[点击这里跳转](https://www.gitbook.com/book/w821881341/russellcloud/discussions)）寻找是否已经有类似的问题，并查看是否已经解决；
* 如果没有找到类似的问题，您可以在该页面创建一个话题，描述你所遇到的问题，我们会尽快帮助您解决。


---

{% include "/contributing.md" %}