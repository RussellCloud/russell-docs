## 名画风格学习（cli） {#_2}

这一小节中我们将会在Russell Cloud上 示范 名画风格学习（style transfer）的例子 ，你可以在这个例子中学会如何创建 CLI 模式下的任务，数据集引用以及添加依赖，输出结果查看等操作。

```
$ russell run --gpu --env tensorflow:py2 --data 585ef99d05484d5f856d045cc5aa91dd "python -u evaluate.py --allow-different-dimensions --checkpoint input/wave.ckpt --in-path images/ --out-path output/"

$ russell status <task_id>

$ russell logs <task_id>
```



