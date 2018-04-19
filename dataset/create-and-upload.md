# 新建数据集

---

<!-- toc -->

---

### 数据集介绍

RussellCloud为个人用户提供数据云服务，用于管理、分享数据集，不用再下载数据集到本地，实现随时随地调用数据集的「美好愿望」，同时，你也可以在「探索」模块中找到感兴趣的数据集进行探索挖掘。


## 创建数据集

### 网页入口

* （登录后）导航栏右上角「+」号

![](/asserts/img/create_dataset_1.png)

* （登录后）个人主页-项目栏—列表右上角

![](/asserts/img/create_dataset_2.png)

### 填写信息

点击 [新建数据集](http://russellcloud.com/dataset/create) 后进入创建页，填写 数据集名称、数据集描述（可选），并选择 权限。

> 数据集名称只能由 字母、数字、-（中划线）、_（下划线）组成，不超过 31 位；
>
> 权限：公开数据集为所有人可见，且数据集数量不受限；私有数据集只有创建者可见，且数据集数量有限制（免费账户不能创建私有数据集）。

![](/asserts/img/create_dataset_3.png)


## 上传数据集

> 数据集创建成功之后，您可以通过命令行上传数据集；
>
> 当前目录下的文件（包括子文件）都会被上传至数据集；
>
> 每次上传标记为一个新的版本，对应一个版本ID, 在项目中可以按版本使用数据集。
>
> 当前系统对上传的数据集大小做出限制，只能上传小于 20 GB的数据集,超出上传的大小限制，客户端会提示：
>
>```
Creating tar archive
compressed size: 6435394533 Bytes
Total size: 6435394533 . Data size too large to sync, please keep it under 5GB.
>```



* 打开数据集概览，粘贴数据集对应ID

![](/asserts/img/upload_dataset_1.png)

* 数据集初始化(在数据集所在目录下运行)
```
    russell data init --id <data_id>
```

![](/asserts/img/upload_dataset_2.png)


* 数据集上传(在数据集所在目录下运行)

> 参数说明：
>
> -m:  备注
>
> --nopack:  注明该数据集在传输前只能打包不能压缩（部分文字数据集不能压缩）

```
    russell data upload -m "test"
```

![](/asserts/img/upload_dataset_3.png)


* 查看数据集上传状态

> 上传数据集时，RussellCloud Cli会压缩打包您的数据并加密传输到RussellCloud的服务器中；
>
> 如果您的数据集较大，文件传输解压可能会有些耗时。

```
    russell data status <version_id>
```

![](/asserts/img/upload_dataset_4.png)

