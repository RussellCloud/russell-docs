# 安装过程可能遇到的问题



1. 权限问题

在pip install 过程中直接报出 “Permission denied” 或者 “Access is denied” 之类的错误

* 检查是否有管理员权限，尝试在 pip 前面加上 sudo：即 

```bash
sudo pip install -U russell-cli
```

如果在已经有管理员权限的情况下安装一些依赖包时出现“operation not permitted”等一大串红色错误

* 可能是因为部分依赖库已安装产生冲突，可采取忽略已安装库的方式解决，即：

```
sudo pip install -U russell-cli --ignore-installed
```



