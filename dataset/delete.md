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

## 帮助我们完善文档
这篇文档以及剩下的文档，我们都有同步在 [GitHub](https://github.com/RussellCloud/russell-docs) 上。团队在尽力完善文档，但疏漏和不周难免存在。若你有什么新的想法或体验，欢迎 Pull Request，扩大你的影响力。

- 除此之外，你还可以通过 [issue](https://github.com/RussellCloud/russell-docs/issues/new?body=This%20issue%20is%20about%20<) 直接提交问题。
- 或者，在[这里](/faq/run-task.md)查看常见问题。