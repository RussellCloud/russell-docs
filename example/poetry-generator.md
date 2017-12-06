## 唐诗生成（待补充完整）

## 使用RNN生成唐诗

### 复现过程：

前提：
* 使用邀请码在官网进行注册
* [在本地安装 cli 客户端](http://docs.russellcloud.com/get-started/install.html)
* 在cli客户端通过login登录

第一步：在官网创建项目
点击 项目创建页 创建项目，默认环境选：keras (注意不要选 kera:py2 )


第二步：绑定本地项目

```
#clone项目代码
git clone https://github.com/RussellCloud/poetry_generator.git

#进入项目目录
cd poetry_generator

#创建项目
russell init --name poetry_generator
```

第二步：训练模型（可跳过，直接使用在下一步使用预先训练好的model）

```
#运行模型训练代码并引用数据云上已经准备好的数据集
russell run "python trainer.py" --data ee3da33467b04b4680ab31f523aeea6f

#查看训练日志
russell logs <run_id>

#由于封测期间暂未采用GPU机器，因此训练需要一个晚上的时间
#训练结束后通过info命令获取项目输出output_id
russell info <run_id>

#通过output命令在浏览器中查看或下载输出文件
russell output <run_id>

```
![](https://pic1.zhimg.com/50/v2-ef8d369322831ae7201a2b59be69aa0c_hd.jpg)

现在可以直接浏览输出的模型目录：[训练好的模型](http://dl.russellcloud.com/RussellCloud/dataset/poetry_generator-output/4/)


第三步：使用预训练模型生成诗词

```
# 运行诗词生成代码并引用上一步中生成的模型数据
# <output_id>是上一步训练过程中通过info命令获取到的id
# 如跳过上一步，可直接使用预先训练好model的数据集：f030014be22b4965987d5b45f7093711

russell run "python gen_poetry.py" --data <output_id>

#从日志中查看生成的诗词
russell logs <run_id_2>

#顺利结束
```

![](https://pic1.zhimg.com/50/v2-3eb37d35e94e39045b0936510c7e22c4_hd.jpg)
