## YOLO_tensorflow
  '''
            #给最后fn层得到的结果赋予解释性即可.reshape即可.
            #从这个代码就可以看出来,所有的cv的核心思想都一样,都是通过深度网络自身调节的这个功能,
            #不给与任意的人工参与,让他自己学,所谓的参数2,参数7这些东西,其实都是虚拟的,
            #现实中网络只会傻算,给一个图片,直接通过网络得到最后的一堆参数,他不会懂这些参数到底表示
            #的是图片的哪一个cell,然后对于每一个cell应该赋予多大的边框来框物体.
            #这些东西都是没有的. 而经过学习这些东西为什么都有了呢??
            #这就是类似fater rcnn里面的逻辑,都是通过逆向传导来获得的这些学习性质.
            #这些只是我们认为的设计成划分cell,划分边框.计算机一开始瞎算一堆,然后经过反复的纠错
            #这里面就体现了loss _function里面我们必须写好,写出所有我们要学的性质.
            #这样计算机就会慢慢地学会.用神经网络来讲就是那些神经元经过反复刺激,他们的权重会收敛
            #导致最后神经网络会跟我们想的一样.当然是理论上.实际上收敛到哪里都不一定,跟训练数据也有关
            #这就导致了神经网络可以解释性很差,不知道这个东西的结果准确率除了概率意义上的精确度
            #以外,没法给一个数学上的准确解释.只能加大训练量和训练集的复杂性,让计算机多学.
Tensorflow implementation of [YOLO](https://arxiv.org/pdf/1506.02640.pdf), including training and test phase.

### Installation

1. Clone yolo_tensorflow repository
	```Shell
	$ git clone https://github.com/hizhangp/yolo_tensorflow.git
    $ cd yolo_tensorflow
	```

2. Download Pascal VOC dataset, and create correct directories
	```Shell
	$ ./download_data.sh
	```

3. Download [YOLO_small](https://drive.google.com/file/d/0B5aC8pI-akZUNVFZMmhmcVRpbTA/view?usp=sharing)
weight file and put it in `data/weight`

4. Modify configuration in `yolo/config.py`

5. Training
	```Shell
	$ python train.py
	```

6. Test
	```Shell
	$ python test.py
	```

### Requirements
1. Tensorflow

2. OpenCV
