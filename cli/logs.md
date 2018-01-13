# russell logs

查看任务的运行日志。

## 查看帮助

```bash
russell logs --help
```

输出：

```
Usage: russell logs [OPTIONS] ID

  Print the logs of the run.

Options:
  -t, --tail int              output the last K lines, instead of all
                              available logs; If -f/--follow options is
                              provided, this option will be ignored
  -f, --follow                output appended data as the file grows
  -O, --output_document TEXT  Write documents to file
  --help                      Show this message and exit.
```

## 命令

```bash
russell logs [OPTIONS] ID
```

## 选项

| 选项 | 默认值 | 描述 |
| --- | --- | --- |
| ID | None | 任务ID |
| -t,--tail | None | 输出日志结尾的K行，如果指定了-f，本选项会被忽略，如果不指定本选项，默认获取当前日志已有的全部内容 |
| -f,--follow | False | 堵塞读取日志，直到运行任务结束所有日志输出 |
| -O,--output\_document | None | 如果指定了本参数，日志不会在控制台输出，二会下载到指定的路径 |

## 详情

项目代码中任何标准输出和标准错误都会输出到日志中。如果需要查看实时日志，必须确保您的日志刷出缓冲区。命令输出日志中还包括一些RussellCloud服务器任务调度信息。

示例：

1. 默认情况，直接输出当前已有的所有日志：

```bash
    russell logs 5b5e9b106d754b74acbe87c8e9618265
```

> 输出：

```
[2017-11-23 13:46:55] [INFO] | Task submitted successfully, queued for processing
[2017-11-23 13:46:55] [INFO] | Task start to be executed...
[2017-11-23 13:46:55] [INFO] | default_env: keras:py2, image: registry.cn-shanghai.aliyuncs.com/russellcloud/tensorflow:latest-py2 .
[2017-11-23 13:46:55] [INFO] | mkdir output
[2017-11-23 13:46:55] [INFO] | work_volume create successfully, mount dir: /workspace
[2017-11-27 12:36:02] [INFO] | Task is running now ~
################################################################################
Extracting /tmp/data/t10k-images-idx3-ubyte.gz
Successfully downloaded t10k-labels-idx1-ubyte.gz 4542 bytes.
Extracting /tmp/data/t10k-labels-idx1-ubyte.gz
Iter 1280, Minibatch Loss= 18114.056641, Training Accuracy= 0.32812
Successfully downloaded train-images-idx3-ubyte.gz 9912422 bytes.
Extracting /tmp/data/train-images-idx3-ubyte.gz
Successfully downloaded train-labels-idx1-ubyte.gz 28881 bytes.
Extracting /tmp/data/train-labels-idx1-ubyte.gz
Successfully downloaded t10k-images-idx3-ubyte.gz 1648877 bytes.
Iter 2560, Minibatch Loss= 9542.742188, Training Accuracy= 0.56250
Iter 3840, Minibatch Loss= 9782.160156, Training Accuracy= 0.64844
Iter 5120, Minibatch Loss= 6303.169922, Training Accuracy= 0.75000
Iter 6400, Minibatch Loss= 2990.343750, Training Accuracy= 0.83594
Iter 7680, Minibatch Loss= 6126.699219, Training Accuracy= 0.76562
Iter 8960, Minibatch Loss= 3960.538818, Training Accuracy= 0.81250
Iter 10240, Minibatch Loss= 3811.254395, Training Accuracy= 0.80469
Iter 11520, Minibatch Loss= 1279.536499, Training Accuracy= 0.92188
Iter 12800, Minibatch Loss= 4132.470703, Training Accuracy= 0.75781
Iter 14080, Minibatch Loss= 1617.436035, Training Accuracy= 0.89844
Iter 15360, Minibatch Loss= 1885.654297, Training Accuracy= 0.89062
Iter 16640, Minibatch Loss= 2519.239258, Training Accuracy= 0.87500
Iter 17920, Minibatch Loss= 855.256226, Training Accuracy= 0.90625
Iter 19200, Minibatch Loss= 1238.085693, Training Accuracy= 0.89844
Iter 20480, Minibatch Loss= 392.659027, Training Accuracy= 0.97656
Iter 21760, Minibatch Loss= 2368.198730, Training Accuracy= 0.85156
Iter 23040, Minibatch Loss= 427.726501, Training Accuracy= 0.95312
Iter 24320, Minibatch Loss= 1167.806152, Training Accuracy= 0.92969
Iter 25600, Minibatch Loss= 1091.727539, Training Accuracy= 0.92969
Iter 26880, Minibatch Loss= 1077.641724, Training Accuracy= 0.89062
Iter 28160, Minibatch Loss= 990.132996, Training Accuracy= 0.92969
Iter 29440, Minibatch Loss= 1191.703857, Training Accuracy= 0.91406
Iter 30720, Minibatch Loss= 811.717896, Training Accuracy= 0.93750
Iter 32000, Minibatch Loss= 726.563354, Training Accuracy= 0.96094
Iter 33280, Minibatch Loss= 1087.988037, Training Accuracy= 0.93750
Iter 34560, Minibatch Loss= 398.453003, Training Accuracy= 0.96875
Iter 35840, Minibatch Loss= 362.858459, Training Accuracy= 0.97656
Iter 37120, Minibatch Loss= 1161.823242, Training Accuracy= 0.91406
Iter 38400, Minibatch Loss= 23.459167, Training Accuracy= 0.99219
Iter 39680, Minibatch Loss= 191.411011, Training Accuracy= 0.97656
Iter 40960, Minibatch Loss= 1436.134033, Training Accuracy= 0.89062
Iter 42240, Minibatch Loss= 1187.610352, Training Accuracy= 0.89844
Iter 43520, Minibatch Loss= 241.973938, Training Accuracy= 0.97656
Iter 44800, Minibatch Loss= 4.120575, Training Accuracy= 0.99219
Iter 46080, Minibatch Loss= 256.512146, Training Accuracy= 0.96875
Iter 47360, Minibatch Loss= 870.189392, Training Accuracy= 0.92969
Iter 48640, Minibatch Loss= 1186.030640, Training Accuracy= 0.94531
Iter 49920, Minibatch Loss= 598.800415, Training Accuracy= 0.93750
Iter 51200, Minibatch Loss= 152.916763, Training Accuracy= 0.97656
Iter 52480, Minibatch Loss= 142.735229, Training Accuracy= 0.97656
Iter 53760, Minibatch Loss= 271.246948, Training Accuracy= 0.97656
Iter 55040, Minibatch Loss= 452.137726, Training Accuracy= 0.95312
Iter 56320, Minibatch Loss= 1293.763184, Training Accuracy= 0.92969
Iter 57600, Minibatch Loss= 570.845947, Training Accuracy= 0.96094
Iter 58880, Minibatch Loss= 560.895142, Training Accuracy= 0.93750
Iter 60160, Minibatch Loss= 103.327820, Training Accuracy= 0.97656
Iter 61440, Minibatch Loss= 291.725708, Training Accuracy= 0.93750
Iter 62720, Minibatch Loss= 416.025421, Training Accuracy= 0.94531
Iter 64000, Minibatch Loss= 485.168579, Training Accuracy= 0.94531
Iter 65280, Minibatch Loss= 173.749054, Training Accuracy= 0.98438
Iter 66560, Minibatch Loss= 442.136108, Training Accuracy= 0.97656
Iter 67840, Minibatch Loss= 285.199310, Training Accuracy= 0.96094
Iter 69120, Minibatch Loss= 574.883362, Training Accuracy= 0.93750
Iter 70400, Minibatch Loss= 610.286072, Training Accuracy= 0.93750
Iter 71680, Minibatch Loss= 350.221313, Training Accuracy= 0.97656
Iter 72960, Minibatch Loss= 469.742126, Training Accuracy= 0.96875
Iter 74240, Minibatch Loss= 356.809753, Training Accuracy= 0.95312
Iter 75520, Minibatch Loss= 48.085114, Training Accuracy= 0.98438
Iter 76800, Minibatch Loss= 122.642151, Training Accuracy= 0.98438
Iter 78080, Minibatch Loss= 354.253387, Training Accuracy= 0.96094
Iter 79360, Minibatch Loss= 526.759949, Training Accuracy= 0.95312
Iter 80640, Minibatch Loss= 1108.786865, Training Accuracy= 0.92188
Iter 81920, Minibatch Loss= 284.053314, Training Accuracy= 0.96094
Iter 83200, Minibatch Loss= 765.757324, Training Accuracy= 0.94531
Iter 84480, Minibatch Loss= 588.247803, Training Accuracy= 0.95312
Iter 85760, Minibatch Loss= 772.927917, Training Accuracy= 0.94531
Iter 87040, Minibatch Loss= 397.148987, Training Accuracy= 0.94531
Iter 88320, Minibatch Loss= 331.797729, Training Accuracy= 0.96875
Iter 89600, Minibatch Loss= 1135.337158, Training Accuracy= 0.93750
Iter 90880, Minibatch Loss= 349.096771, Training Accuracy= 0.94531
Iter 92160, Minibatch Loss= 192.557251, Training Accuracy= 0.97656
Iter 93440, Minibatch Loss= 438.485840, Training Accuracy= 0.96094
Iter 94720, Minibatch Loss= 405.391968, Training Accuracy= 0.96875
Iter 96000, Minibatch Loss= 696.918640, Training Accuracy= 0.94531
Iter 97280, Minibatch Loss= 614.973022, Training Accuracy= 0.95312
Iter 98560, Minibatch Loss= 644.320679, Training Accuracy= 0.92969
Iter 99840, Minibatch Loss= 275.512787, Training Accuracy= 0.96094
Iter 101120, Minibatch Loss= 542.054199, Training Accuracy= 0.95312
Iter 102400, Minibatch Loss= 357.655670, Training Accuracy= 0.97656
Iter 103680, Minibatch Loss= 263.928528, Training Accuracy= 0.96875
Iter 104960, Minibatch Loss= 526.952881, Training Accuracy= 0.97656
Iter 106240, Minibatch Loss= 210.429581, Training Accuracy= 0.97656
Iter 107520, Minibatch Loss= 145.280930, Training Accuracy= 0.96875
Iter 108800, Minibatch Loss= 889.954712, Training Accuracy= 0.93750
Iter 110080, Minibatch Loss= 267.018341, Training Accuracy= 0.98438
Iter 111360, Minibatch Loss= 126.925217, Training Accuracy= 0.96875
Iter 112640, Minibatch Loss= 110.727371, Training Accuracy= 0.96875
Iter 113920, Minibatch Loss= 359.462189, Training Accuracy= 0.97656
Iter 115200, Minibatch Loss= 196.406326, Training Accuracy= 0.96875
Iter 116480, Minibatch Loss= 45.307816, Training Accuracy= 0.97656
Iter 117760, Minibatch Loss= 151.861328, Training Accuracy= 0.96875
Iter 119040, Minibatch Loss= 323.700500, Training Accuracy= 0.93750
Iter 120320, Minibatch Loss= 48.079712, Training Accuracy= 0.98438
Iter 121600, Minibatch Loss= 378.871552, Training Accuracy= 0.96094
Iter 122880, Minibatch Loss= 0.079895, Training Accuracy= 0.99219
Iter 124160, Minibatch Loss= 174.654617, Training Accuracy= 0.96875
Iter 125440, Minibatch Loss= 237.100098, Training Accuracy= 0.98438
Iter 126720, Minibatch Loss= 320.379944, Training Accuracy= 0.97656
Iter 128000, Minibatch Loss= 268.691956, Training Accuracy= 0.97656
Iter 129280, Minibatch Loss= 555.880249, Training Accuracy= 0.95312
Iter 130560, Minibatch Loss= 142.087173, Training Accuracy= 0.97656
Iter 131840, Minibatch Loss= 211.274841, Training Accuracy= 0.96094
Iter 133120, Minibatch Loss= 315.713409, Training Accuracy= 0.96094
Iter 134400, Minibatch Loss= 564.462402, Training Accuracy= 0.95312
Iter 135680, Minibatch Loss= 62.472710, Training Accuracy= 0.95312
Iter 136960, Minibatch Loss= 58.676170, Training Accuracy= 0.99219
Iter 138240, Minibatch Loss= 299.196686, Training Accuracy= 0.96875
Iter 139520, Minibatch Loss= 190.612335, Training Accuracy= 0.95312
Iter 140800, Minibatch Loss= 85.633797, Training Accuracy= 0.98438
Iter 142080, Minibatch Loss= 185.101990, Training Accuracy= 0.98438
Iter 143360, Minibatch Loss= 58.654877, Training Accuracy= 0.99219
Iter 144640, Minibatch Loss= 208.146164, Training Accuracy= 0.97656
Iter 145920, Minibatch Loss= 140.436386, Training Accuracy= 0.97656
Iter 147200, Minibatch Loss= 73.716156, Training Accuracy= 0.98438
Iter 148480, Minibatch Loss= 263.519501, Training Accuracy= 0.96094
Iter 149760, Minibatch Loss= 39.185806, Training Accuracy= 0.99219
Iter 151040, Minibatch Loss= 298.738678, Training Accuracy= 0.96875
Iter 152320, Minibatch Loss= 221.323822, Training Accuracy= 0.96875
Iter 153600, Minibatch Loss= 260.786987, Training Accuracy= 0.96094
Iter 154880, Minibatch Loss= 119.939034, Training Accuracy= 0.96875
Iter 156160, Minibatch Loss= 91.964935, Training Accuracy= 0.99219
Iter 157440, Minibatch Loss= 31.657791, Training Accuracy= 0.98438
Iter 158720, Minibatch Loss= 311.707397, Training Accuracy= 0.96094
Iter 160000, Minibatch Loss= 374.835327, Training Accuracy= 0.96094
Iter 161280, Minibatch Loss= 11.804626, Training Accuracy= 0.99219
Iter 162560, Minibatch Loss= 726.179993, Training Accuracy= 0.94531
Iter 163840, Minibatch Loss= 311.699890, Training Accuracy= 0.97656
Iter 165120, Minibatch Loss= 45.144836, Training Accuracy= 0.98438
Iter 166400, Minibatch Loss= 224.419281, Training Accuracy= 0.96875
Iter 167680, Minibatch Loss= 194.260712, Training Accuracy= 0.96875
Iter 168960, Minibatch Loss= 4.430710, Training Accuracy= 0.99219
Iter 170240, Minibatch Loss= 42.810520, Training Accuracy= 0.97656
Iter 171520, Minibatch Loss= 97.054207, Training Accuracy= 0.97656
Iter 172800, Minibatch Loss= 81.921837, Training Accuracy= 0.96875
Iter 174080, Minibatch Loss= 152.696869, Training Accuracy= 0.99219
Iter 175360, Minibatch Loss= 140.990906, Training Accuracy= 0.98438
Iter 176640, Minibatch Loss= 188.690979, Training Accuracy= 0.97656
Iter 177920, Minibatch Loss= 54.187355, Training Accuracy= 0.96875
Iter 179200, Minibatch Loss= 193.618011, Training Accuracy= 0.98438
Iter 180480, Minibatch Loss= 73.453354, Training Accuracy= 0.98438
Iter 181760, Minibatch Loss= 62.365036, Training Accuracy= 0.98438
Iter 183040, Minibatch Loss= 129.584778, Training Accuracy= 0.99219
Iter 184320, Minibatch Loss= 105.896057, Training Accuracy= 0.97656
Iter 185600, Minibatch Loss= 109.627792, Training Accuracy= 0.96875
Iter 186880, Minibatch Loss= 108.050903, Training Accuracy= 0.97656
Iter 188160, Minibatch Loss= 183.186432, Training Accuracy= 0.99219
Iter 189440, Minibatch Loss= 45.477386, Training Accuracy= 0.97656
Iter 190720, Minibatch Loss= 129.498077, Training Accuracy= 0.96875
Iter 192000, Minibatch Loss= 274.199890, Training Accuracy= 0.96094
Iter 193280, Minibatch Loss= 278.135132, Training Accuracy= 0.98438
Iter 194560, Minibatch Loss= 10.363342, Training Accuracy= 0.98438
Iter 195840, Minibatch Loss= 76.943817, Training Accuracy= 0.99219
Iter 197120, Minibatch Loss= 110.401573, Training Accuracy= 0.98438
Iter 198400, Minibatch Loss= 61.524139, Training Accuracy= 0.98438
Iter 199680, Minibatch Loss= 0.000000, Training Accuracy= 1.00000
Optimization Finished!
Testing Accuracy: 0.972656
################################################################################
[2017-11-23 13:53:18] [INFO] | [stopped] Finishing execution in 375 seconds for Task
```

2. 输出尾部K=10行:

```
russell logs 5b5e9b106d754b74acbe87c8e9618265 -t 10
```

> 输出：

```
[2017-11-23 13:46:55] [INFO] | Task submitted successfully, queued for processing
[2017-11-23 13:46:55] [INFO] | Task start to be executed...
[2017-11-23 13:46:55] [INFO] | default_env: keras:py2, image: registry.cn-shanghai.aliyuncs.com/russellcloud/tensorflow:latest-py2 .
[2017-11-23 13:46:55] [INFO] | mkdir output
[2017-11-23 13:46:55] [INFO] | work_volume create successfully, mount dir: /workspace
[2017-11-27 12:36:02] [INFO] | Task is running now ~
################################################################################
Iter 190720, Minibatch Loss= 129.498077, Training Accuracy= 0.96875
Iter 192000, Minibatch Loss= 274.199890, Training Accuracy= 0.96094
Iter 193280, Minibatch Loss= 278.135132, Training Accuracy= 0.98438
Iter 194560, Minibatch Loss= 10.363342, Training Accuracy= 0.98438
Iter 195840, Minibatch Loss= 76.943817, Training Accuracy= 0.99219
Iter 197120, Minibatch Loss= 110.401573, Training Accuracy= 0.98438
Iter 198400, Minibatch Loss= 61.524139, Training Accuracy= 0.98438
Iter 199680, Minibatch Loss= 0.000000, Training Accuracy= 1.00000
Optimization Finished!
Testing Accuracy: 0.972656
################################################################################
[2017-11-23 13:53:18] [INFO] | [stopped] Finishing execution in 375 seconds for Task
```

3. 使用-f参数实时获取任务日志输出：

```
russell logs 5b5e9b106d754b74acbe87c8e9618265 -f
```

> 一个输出例子，此时控制台处于堵塞等待状态，正在等待日志服务器传输新的日志：

```
[2017-11-23 13:46:55] [INFO] | Task submitted successfully, queued for processing
[2017-11-23 13:46:55] [INFO] | Task start to be executed...
[2017-11-23 13:46:55] [INFO] | default_env: keras:py2, image: registry.cn-shanghai.aliyuncs.com/russellcloud/tensorflow:latest-py2 .
[2017-11-23 13:46:55] [INFO] | mkdir output
[2017-11-23 13:46:55] [INFO] | work_volume create successfully, mount dir: /workspace
[2017-11-27 12:36:02] [INFO] | Task is running now ~
################################################################################
Iter 190720, Minibatch Loss= 129.498077, Training Accuracy= 0.96875
Iter 192000, Minibatch Loss= 274.199890, Training Accuracy= 0.96094
Iter 193280, Minibatch Loss= 278.135132, Training Accuracy= 0.98438
Iter 194560, Minibatch Loss= 10.363342, Training Accuracy= 0.98438
Iter 195840, Minibatch Loss= 76.943817, Training Accuracy= 0.99219
Iter 197120, Minibatch Loss= 110.401573, Training Accuracy= 0.98438

```

4. 使用-O参数下载日志到本地：

```
russell logs 5b5e9b106d754b74acbe87c8e9618265 -O log.txt
```

> 输出：

```
Connecting to the server....
HTTP request sent, awaiting response...
Length: 20957418 Bytes 20.0MiB [application/octet-stream]
Downloading from server. Saving to log.txt....
[log.txt] Downloading... 20402.00 KB / 20466.00 KB 4.7MiB/s
log.txt saved. Total size: [20.0MiB/20.0MiB]
```

## 输出限制

目前控制台日志仅支持输出最大1024行日志，当超过1024行，控制台会输出以下信息：

```
--------------------------------------------------------------------------------
The log exceeds 1024 rows. To view complete log:
    1. In terminal, enter:
             russell logs 6dc0e8e05a7a4841844e24ac91f4b8c1 -O log.txt
    2. In browser,click the download button on the web page
--------------------------------------------------------------------------------
```

如果需要查看完整日志，请使用 -O 命令下载到本地进行查看。

## 遇到更多问题？

如果您在使用过程中，发现终端有一些“非正常”的输出，或者有其他的不愉快体验，请[联系我们](/contact-us.md)，帮助我们更好地改进产品、增强用户体验。

