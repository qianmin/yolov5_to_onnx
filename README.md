## 用法
①训练yolov5s.pt（官方教程）

② 安装onnx等requirements

``` python models/export.py --weights yolov5s.pt --img 640 --batch 1  ```




## 导出
根据[这篇博文](https://github.com/hpc203/yolov5-dnn-cpp-python)修改yolov5 repo，导出openCV dnn模块可读的onnx。  <br>
直接使用官方给出的脚本导出：<br>
 ``` !python models/export.py --weights yolov5s.pt --img 640 --batch 1  ```
 <br>
 
 ## 推理

 ```!python opencv_dnn_infer.py --imgpath data/images/bus.jpg```


opencv_dnn_infer.py修改自上面这位博主的[repo](https://github.com/hpc203/yolov5-dnn-cpp-python)，主要改动：
* 用numpy运算取代postprocess里的for循环，优化后处理。
* 对不同class分别执行nms，因为我抽出的这部分代码所属项目需要这么做。觉得没必要可以自己改postprocess2对应内容换回原版。





