## 环境配置 {#_2}

前面的示例中我们默认使用的是TensorFlow框架，事实上，RussellCloud支持目前几乎所有的主流深度学习框架，在 run 命令后加上 ” –env ” 指定对应的框架环境:

如果需要安装额外的python库，可以在项目根目录下新建russell\_requirements.txt文件，内部格式参考python项目中常见requirements文件的编写方式。

```
russell run --env <env_name> <command>
```

| 下面是目前支持的框架列表： |
| :--- |


| Framework | Env name \(–env parameter\) | Description |
| :--- | :--- | :--- |
| Tensorflow | tensorflow | Tensorflow 0.12.1 + Keras 1.2.2 on Python3. |
|  | tensorflow:py2 | Tensorflow 0.12.1 + Keras 1.2.2 on Python2. |
| Tensorflow 1.0 | tensorflow-1.0 | Tensorflow 1.0.0 + Keras 1.2.2 on Python3. |
|  | tensorflow-1.0:py2 | Tensorflow 1.0.0 + Keras 1.2.2 on Python2. |
| Theano | theano | Theano rel-0.8.2 + Keras 1.2.2 on Python3. |
|  | theano:py2 | Theano rel-0.8.2 + Keras 1.2.2 on Python2. |
| Keras | - | Use tensorflow or theano for the appropriate Keras backend |
| Caffe | caffe | Caffe rc4 on Python3. |
|  | caffe:py2 | Caffe rc4 on Python2. |
| Torch | torch | Torch 7 with Python 3 env. |
|  | torch:py2 | Torch 7 with Python 2 env. |
| PyTorch | pytorch | PyTorch 0.1.9 on Python 3. |
|  | torch:py2 | PyTorch 0.1.9 on Python 2. |
| Chainer \(beta\) | chainer | Chainer 1.21.0 on Python 3. |
|  | chainer:py2 | Chainer 1.21.0 on Python 2. |
| MxNet \(beta\) | mxnet:py2 | MxNet 0.9.3a on Python 2. |
| Kur | kur | Kur 0.3.0 on Python 3. |



