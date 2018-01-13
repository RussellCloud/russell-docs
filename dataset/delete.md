# 删除数据集

---

<!-- toc -->

---

## 删除数据集的指定版本
### 通过网页删除

* 访问网页：
```
   URL:  http://russellcloud.com/<user>/dataset/<dataset_name>/versions
```
* 在上面找到要删除的版本，在右侧点击垃圾箱图标，会弹出确认弹窗，点击“立即删除按钮”即可删除该版本的数据集

### 通过命令行删除

* 从数据集版本界面获复制版本ID

```
   URL:  http://russellcloud.com/<user>/dataset/<dataset_name>/versions
```

![](/asserts/img/dataset_mount_id1.png)

* 使用命令行按版本ID删除

```
    russell data delete <version_id>
```

![](/asserts/img/delete_dataset_2.png)


## 删除整个数据集

* 打开数据集设置界面，点击删除数据集


```
   URL:  http://russellcloud.com/<user>/dataset/<dataset_name>/setting
```

![](/asserts/img/delete_dataset_3.png)