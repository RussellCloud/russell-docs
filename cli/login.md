# russell login
登录RussellCloud服务器：在本机存储登录凭证。


## 帮助
```bash
russell login --help
```
输出：
```
Usage: russell-dev login [OPTIONS]

  Log into Russell via Auth0.

Options:
  --token  Just enter token
  --help   Show this message and exit.
```

## 命令
```bash
russell login
```

## 选项

|可选项|默认值|描述|
|---|---|---|
|--token|False|若指定该项，将不打开浏览器使用token登录。注意：仅v0.5.5以上版本支持。|
|--username|False|RussellCloud用户名，若指定，必须包含--password项|
|--password|False|RussellCloud密码|

## 描述
在使用russell-cli工具运行任何其他命令之前，必须首先登录。默认情况下，您会从打开的RussellCloud官网上获取登录所需要的token：从官网复制token并粘贴到命令行中，即可完成登录。

例如：

1. 默认：

```
Authentication token page will now open in your browser. Continue? [Y/n]:
```
- 若输入Y并回车，或者直接回车：
```
Please copy and paste the token here:
```
粘贴token后，你可以看到类似如下输出，并退出回到交互式终端。
```
Login Successful as RussellCloud
```

- 若输入n并回车：
```
Please input your username:
Please input your password:
Login Successful as RussellCloud
```


2. 使用--token选项:

```bash
$ russell login --token
Please copy and paste the token here:
Login Successful as RussellCloud
```


## 认证token¶
RussellCloud使用JWT认证。您的token将会被存储到~/.russellconfig文件中。默认的token有效期为【X】天，在此之后您需要重新登录。

## 遇到更多问题？

如果您在使用过程中，发现终端有一些“意外”的输出，或者有其他的不愉快体验，请[联系我们](/contact-us.md)，帮助我们更好地改进产品、增强用户体验。

