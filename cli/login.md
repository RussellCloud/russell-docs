# russell login

登录RussellCloud服务器：在本机存储登录凭证。

## 查看帮助

```bash
russell login --help
```

输出：

```
Usage: russell login [OPTIONS]

  Log into Russell via Auth0.

Options:
  -t, --token          Just enter token
  -u, --username TEXT  Input username/email to login. If --token if provided,
                       this option will be ignored
  -p, --password TEXT  Input password to login. If password is not given it's
                       asked from the tty.If --token if provided, this option
                       will be ignored
  --help               Show this message and exit.
```

## 命令

```bash
russell login
```

## 选项

| 可选项 | 默认值 | 描述 |
| --- | --- | --- |
| -t/--token | False | 是否直接输入token,如果指定了本参数，会直接提示输入token完成登陆校验 |
| -u/--username | None | 指定使用用户名/邮箱进行登录，如果指定了使用token,本选项会被忽略 |
| -p.--password | None | 在指定了用户名后，可使用此选项指定密码完成登陆校验，如果不指定用户名，本选项会被忽略 |
| --help | False | 输出本命令的相关使用帮助信息 |

## 详情

在使用russell-cli工具运行任何其他命令之前，必须首先登录。默认情况下，您会从打开的RussellCloud官网上获取登录所需要的token：从官网复制token并粘贴到命令行中，即可完成登录。

例如：

1. 默认：

```
Authentication token page will now open in your browser. Continue? [Y/n]:
```

* 若输入Y并回车，或者直接回车：

  ```
  Please copy and paste the token here:
  ```

  粘贴token后，你可以看到类似如下输出，并退出回到交互式终端。

  ```
  Login Successful as RussellCloud
  ```

* 若输入n并回车：

  ```
  Login with your russell username/email and password. If you don't have a Russell account, head over to http://russellcloud.com to create one.
  Username/Email:RussellCloud
  Password:
  Login Successful as RussellCloud
  ```

* 使用--token选项:

```bash
$ russell login --token
Please copy and paste the token here:
Login Successful as RussellCloud
```

* 同时使用-u/--username,-p/--password选项:
  ```
  russell login -u RussellCloud -p my-password
  Login Successful as RussellCloud 
  ```
* 同时使用-u,-p会使密码在命令行明文出现，如果想以更安全的方式登陆，可以只使用-u/--username选项:

```
    russell login -u RussellCloud
    Password:
    Login Successful as RussellCloud
```



## 认证token¶

RussellCloud使用JWT认证。您的token将会被存储到~/.russellconfig文件中。默认的token有效期为 1 天，在此之后您需要重新登录。当使用用户名、密码的方式登陆时，会先通过用户校验取得token，再将token存储到~/.russellconfig文件中。token有效期同样为 1 天

## 遇到更多问题？

如果您在使用过程中，发现终端有一些“意外”的输出，或者有其他的不愉快体验，请[联系我们](/contact-us.md)，帮助我们更好地改进产品、增强用户体验。

