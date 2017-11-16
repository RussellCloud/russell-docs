## 模式介绍 {#_2}

1. Cli 模式：（默认模式）以提交任务的形式从终端启动深度学习任务，常用于模型训练过程；
2. Jupyter 模式：在Jupyter Notebook的网页环境下调试项目，常用于数据探索、模型调试；
3. Serve 模式：（开发中）

## 启动方式 {#_2}

```
# Cli模式 (<command>指启动命令)
$ russell run <command>

# Jupyter模式
$ russell run --mode jupyter

# Serve模式（待补充）
```



## 注意 {#_2}

1. 在CLI模式下，如果command中包含python运行代码，建议加上 -u，以避免输出缓冲问题，如下：

```
$ russell run "python test.py"
# 这种方式启动可能会导致日志无法同步输出（因为python解释器的log buffer）

$ russell run "python -u test.py"
# 加上 -u 可以避免这个问题
```



