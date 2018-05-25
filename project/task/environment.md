## 环境配置 {#_2}

前面的示例中我们默认使用的是TensorFlow框架，事实上，RussellCloud支持目前几乎所有的主流深度学习框架，在 run 命令后加上 ” –env ” 指定对应的框架环境:

```
russell run --env <env_name> <command>
```

| 下面是目前支持的框架列表： |
| :--- |

| Framework | Env name (--env parameter)  |  Description              | 
| --------- | ------------------ | ------------------------ |-------------|
| Keras | keras      | Tensorflow 1.1.0 + keras 2.0.6 on Python3.5. |  |
|       | keras:py2  | Tensorflow 1.1.0 + keras 2.0.6 on Python2. |  |
| Tensorflow 1.4 | tensorflow-1.4  | Tensorflow 1.4.0 + Keras 2.0.8 on Python3.6. | 
|                | tensorflow-1.4:py2  | Tensorflow 1.4.0 + Keras 2.0.8 on Python2. | 
| Tensorflow 1.3 | tensorflow-1.3  | Tensorflow 1.3.0 + Keras 2.0.6 on Python3.6. | 
|                | tensorflow-1.3:py2  | Tensorflow 1.3.0 + Keras 2.0.6 on Python2. | 
| Tensorflow 1.2 | tensorflow-1.2  | Tensorflow 1.2.0 + Keras 2.0.6 on Python3.5. | 
|                | tensorflow-1.2:py2  | Tensorflow 1.2.0 + Keras 2.0.6 on Python2. | 
| Tensorflow 1.1 | tensorflow  | Tensorflow 1.1.0 + Keras 2.0.6 on Python3.5. | 
|                | tensorflow:py2  | Tensorflow 1.1.0 + Keras 2.0.6 on Python2. | 
| Tensorflow 1.0 | tensorflow-1.0  | Tensorflow 1.0.0 + Keras 2.0.6 on Python3.5. | 
|                | tensorflow-1.0:py2  | Tensorflow 1.0.0 + Keras 2.0.6 on Python2. | 
| Tensorflow 0.12 | tensorflow-0.12  | Tensorflow 0.12.1 + Keras 1.2.2 on Python3.5. | 
|                 | tensorflow-0.12:py2  | Tensorflow 0.12.1 + Keras 1.2.2 on Python2. | 
| PyTorch 0.3 | pytorch-0.3     | PyTorch 0.3.0 on Python 3. | 
|             | pytorch-0.3:py2 | PyTorch 0.3.0 on Python 2. | 
| PyTorch 0.2 | pytorch-0.2     | PyTorch 0.2.0 on Python 3. | 
|             | pytorch-0.2:py2 | PyTorch 0.2.0 on Python 2. | 
| PyTorch 0.1 | pytorch-0.1     | PyTorch 0.1.12 on Python 3. | 
|             | pytorch-0.1:py2 | PyTorch 0.1.12 on Python 2. | 
| Theano 0.8 | theano-0.8  | Theano rel-0.8.2 + Keras 1.2.2 on Python3.5. | 
|            | theano-0.8:py2  | Theano rel-0.8.2 + Keras 1.2.2 on Python2. | 
| Theano 0.9 | theano-0.9  | Theano rel-0.8.2 + Keras 2.0.3 on Python3.5. | 
|            | theano-0.9:py2  | Theano rel-0.8.2 + Keras 2.0.3 on Python2. | 
| Caffe | caffe  | Caffe rc4 on Python3.5. | 
|       | caffe:py2  | Caffe rc4 on Python2. | 
| Torch | torch | Torch 7 with Python 3 env. | 
|       | torch:py2 | Torch 7 with Python 2 env. | 
| Chainer 1.23 | chainer-1.23 | Chainer 1.23.0 on Python 3. | 
|              | chainer-1.23:py2 | Chainer 1.23.0 on Python 2. | 
| Chainer 2.0 | chainer-2.0 | Chainer 1.23.0 on Python 3. | 
|             | chainer-2.0:py2 | Chainer 1.23.0 on Python 2. | 
| MxNet | mxnet:py2 | MxNet 0.9.3a on Python 2. | 
| MxNet 1.0 | mxnet-1.0:py2 | MxNet 1.0 on Python 2. | 
| Kur | kur | Kur 0.3.0 on Python 3. |


除此之外下面这些数据科学常用的库也已经安装好了，在所有的环境中都可以直接使用：

```
h5py, iPython, Jupyter, matplotlib, numpy, OpenCV, Pandas, Pillow, scikit-learn, scipy, sklearn
```

如果需要安装额外的 python 库，可以在项目根目录下新建 `russell\_requirements.txt` 文件（内部格式参考 python 项目中常见 `requirements` 文件的编写方式），项目运行前会在环境中自动安装需要的库，但建议不要在这个过程中安装过多的库，有可能会造成安装超时，在 `jupyter` 任务中可以考虑启动 notebook 后再进行安装。

---

{% include "/contributing.md" %}
