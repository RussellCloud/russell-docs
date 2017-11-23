# 安装过程可能遇到的问题

---

<!-- toc -->

---

## 权限问题

* pip install 过程中直接报出 “Permission denied” 或者 “Access is denied” 之类的错误

    * 检查是否有管理员权限，尝试在 pip 前面加上 sudo：即 

```bash
sudo pip install -U russell-cli
```

* 如果在已经有管理员权限的情况下安装一些依赖包时出现“operation not permitted”等一大串红色错误

    * 可能是因为部分依赖库已安装产生冲突，可采取忽略已安装库的方式解决，即：

```
sudo pip install -U russell-cli --ignore-installed
```



## 依赖问题

* 在安装过程中可能会出现依赖库安装报错或者在运行过程中遇到“\*\*\* not installed”

    * 这种情况可以单独安装该依赖库处理，即：

```
sudo pip install -U ***
```

* 如果在linux系统中遇到“Python.h: No such file or directory”类似的问题

    * 直接安装python-dev包即可：

```
sudo apt-get install python-dev
```

---

## 遇到其他的问题？

* 请您先仔细check FAQs，尝试可能的解决方案；
* 如果仍未解决，您可以在GitBook的讨论页面（[点击这里跳转](https://www.gitbook.com/book/w821881341/russellcloud/discussions)）寻找是否已经有类似的问题，并查看是否已经解决；
* 如果没有找到类似的问题，您可以在该页面创建一个话题，描述你所遇到的问题，我们会尽快帮助您解决。



