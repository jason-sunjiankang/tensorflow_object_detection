# Tensorflow_object_detection
*Detect object with [tensorflow object detection api](https://github.com/tensorflow/models/tree/master/research/object_detection)*

## Dependence
* TensorFlow ≥1.6
* OpenCV 3.4
* Python 3

## Installation(tensorflow object detection)
>### windows10
>>1.下载tensorflow models模块，地址：https://github.com/tensorflow/models；

>>2.配置protobuf，下载protoc-3.5.0-win32.zip（https://github.com/google/protobuf/releases， 解压后将bin文件夹加入到系统环境变量；

>>3.安装tensorflow model 以及slim：

  >>>a.在models-master/research/目录下cmd运行：python setup.py install，安装model模块；
  
  >>>b.在models-master/research/目录下cmd运行：python object_detection/builders/model_builder_test.py测试，会报错ImportError: No module named nets；
  
  >>>c.进一步安装slim,在models-master/research/slim目录下cmd运行：python setup.py install；
  
>>4.配置path环境变量：包括models-master、research和slim三个文件夹的路径。

>### ubuntu 16.04

>>1.按照官方文档进行安装：[tensorflow object detection api installation](https://github.com/tensorflow/models/blob/master/research/object_detection/g3doc/installation.md)

## Get tfrecord
>1.新建data目录，如下所有相关数据可放在这个目录下；

>2.获取图像数据，放在data/；

>3.使用[labelImg](https://github.com/tzutalin/labelImg)给图像数据打标签，得到每张图像对应的xml文件；

>4.运行xml_to_csv.py将xml按照train和eval转成train.csv和eval.csv，得到训练列表和测试列表;

>5.运行generate_tfrecord.py将train.csv、eval.csv、images转化为train.record和eval.record，得到tensorflow测试和训练所需的数据；


## Trainning
>1.需要使用迁移学习来加速我们的训练过程，我们将使用[ssd_mobilenet_v1_coco](http://download.tensorflow.org/models/object_detection/ssd_mobilenet_v1_coco_2017_11_17.tar.gz)作为预训练模型来进行训练，放在自己新建的data/目录下；

>2.


>3.复制models-master/research/object_detection/samples/configs/下的ssd_mobilenet_v1_coco.config到自己新建的data/目录下，并做如下修改：num_classes: 90->num_classes: 1(如有n个类，则为n)，num_steps: 200000->num_steps: 100000(根据训练过程调整)，train_input_reader中


>4.在models-master/research/object_detection(tensorflow object detection api)路径下,执行下面的相关命令：

## Eval

## 实际运行测试
>1.将检查点文件导出为冻结的模型文件，在models-master/research/object_detection/目录下执行：

>2.运行.py。

## Dependence License
* MIT license
