# 挂载数据集

## russell run运行项目时挂载数据集

* **基本用法**
 使用 *- -data* 参数
 挂载之前你需要准备：
 * 需要挂载的数据集某个版本的id `<data_id>`。**注意不是数据集概览 id（创建数据集时的 id ）**，一个数据集可能有多个版本，版本 id 是上传完成后提示的 id ，也可以在数据集页面的版本标签下查看和复制。
 ![网页查看和复制数据集版本id](/asserts/img/dataset_mount_id1.png)
 * 挂载名称 `<mount_name>`

 **用法：**
 ```bash
 russell run <command> --data <data_id>:<mount_name>
 ```
 `<command>` 是运行的命令，这里的 *- -data* 参数会将 data_id 对应的数据集挂载到 `/input/<mount_name>` 目录下。如果未指定挂载名称，则会默认挂载到`/input/<dataset_name>-<version>目录下`。

 例如：
 ```bash
 russell run "python trainer.py" --data ee3da33467b04b4680ab31f523aeea6f:data
 ```
 这里会将数据集的内容挂载到 */input/data* 下，如果不指定挂载名称，对于这个数据集名称为 Poetry_Data 版本为 1 的数据集来说，会挂载到 */input/Poetry_Data-1* 目录下。

* **挂载多个数据集**

 **用法：**
 ```bash
 russell run <command> --data <data_id_1>:<mount_name_1> --data <data_id_2>:<mount_name_2> ......
 ```
 每个挂载的数据集前都需要加上 *- -data*参数。