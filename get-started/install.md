
# russell-cli安装

---

<!-- toc -->

---

## 基础安装

*russell-cli* 是基于Python的命令行工具，我们在终端通过它来进行 启动、监控任务或者上传数据集等操作。

目前大家可以直接通过 *pip* 安装 *russell-cli* ，该工具可以在 Windows、MacOs 以及 Linux 上运行并且兼容 *Python2.7* 和 *Python3.5*。

```bash
pip install -U russell-cli
```

现在，你可以通过 *help* 命令来查看支持的命令：

```bash
russell --help
```

更详细的命令说明可以在前往 [命令行工具](/cli.md) 查看。


---

## 遇到问题？

如果安装失败，请参考 [安装过程常见问题](/faq/install.md) 进行排查，仍未解决可 [联系我们](/contact-us.md) 。

### 小技巧

如果你在安装过程中遇到问题，可以考虑通过 *virtualenv* 创建一个虚拟环境以后再安装，这样可以避免几乎所有的包冲突问题。

（ 代价是 以后每次需要使用 *russell-cli* 时需要先 *source activate* 启动一下 ）。





