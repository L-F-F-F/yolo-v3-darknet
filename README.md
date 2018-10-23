## yolo-v3-Window版
军事爱好者，源码摘自AlexeyAB大神的[yolo-v3](https://github.com/AlexeyAB/darknet)，Windows下的配置教程非常详细。这是在AlexeyAB大神的yolo-v3编译好，能运行基础上的样例。

测试样例，无代码。用于检测 Google Earth 中的飞机型号目标，训练图片均为 768*768，检测用图片最好也使用方形图片，训练集图片采集时放缩比例zoom=20，对应的 Google Earth 视线高度小于五百米，不宜过高。

* `bacckup/yolo-obj_32000_4_480_small.weights` 为训练32000轮后的权重文件。github上传文件大小限制100M，权重文件上传至[百度云](https://pan.baidu.com/s/1pdX9aof1MiosYxjx2SPjjA)（235MB），密码2o7a。
* `data/obj.data` 为相关文件信息，包含19类。
* `data/obj.names` 为19类飞机型号。
* `yolo-obj.cfg` 为模型配置文件。
* `tryTest/` 为2个图片样例，1个视频样例。

文件置于 `darknet-master\build\darknet\x64` 启动命令行

* `./darknet.exe detector test data/obj.data yolo-obj.cfg backup/yolo-obj_32000_4_480_small.weights tryTest/14-9.jpg` 测试图片样例

<center> ![](https://i.imgur.com/JGmdQp5.png) </center>
<center> ![](https://i.imgur.com/Wl4snx7.png) </center>
* `./darknet.exe detector demo data/obj.data yolo-obj.cfg backup/yolo-obj_32000_4_480_small.weights tryTest/3499-man.mp4` 测试视频样例
