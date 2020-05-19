# Yolo-Python



## Step 1: Install DarkNet Support

### Official Tutorial

* [click to read darknet offical tutorial](https://pjreddie.com/darknet/yolo/)

### Comiling with CUDA

* download base

```shell
git clone https://github.com/pjreddie/darknet
cd darknet
wget https://pjreddie.com/media/files/yolov3.weights
```

* change the first line of Makefile

```shell
CPU = 1
```

* make

```
make
```

* then test

```
./darknet -nogpu detect cfg/yolov3.cfg yolov3.weights data/dog.jpg
./darknet -i 1 detect cfg/yolov3.cfg yolov3.weights data/dog.jpg
```



## Step 2 : Yolo with Numpy 

* change [darknet/Makefile & darknet.py](https://github.com/FiftyWu/Yolo-Python/tree/master/darknet)

* change [src/image.c & image.h](https://github.com/FiftyWu/Yolo-Python/tree/master/src)

* make

```
make clean & make
```



## Step 3: Yolo-Python

```python
from DarknetTest import Detector


image = ''  	  # (image path or ndarray)
yolov3 = Detector(gpu=1,
                  cfg="/darknet/cfg/yolov3.cfg",
                  weights="/darknet/yolov3.weights",
                  data="/darknet/cfg/coco.data")
result, width_height = yolov3.detect_result(image)
```





