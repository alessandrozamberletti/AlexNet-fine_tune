# AlexNet-fine_tune

Layer-wise AlexNet fine-tuning.

![AlexNet-fine_tune](./res/alexnet-fine_tune.gif)

```python
alex_net = AlexNet(dataset.num_classes, 'res/alexnet-caffemodel.npy')
alex_net.fit(X_train, X_val, y_train, y_val, freeze=True, epochs=1000, lr=0.001)
```
when ```freeze=True``` layer-wise fine-tuning is performed (see: [1](https://ieeexplore.ieee.org/abstract/document/7426826/), [2](https://github.com/duggalrahul/AlexNet-Experiments-Keras)).

## Instructions
Use the following dataset structure: ```data/class_{0,..,K}/image_{0,..,N}.jpg```.  
Run:
```console
$ python fine_tune.py
```
If the converted (source: [caffe-tensorflow](https://github.com/ethereon/caffe-tensorflow)) caffemodel (source: [BVLC](https://github.com/BVLC/caffe/tree/master/models/bvlc_alexnet))
is not in ```res/```, it will be downloaded from
[here](https://www.dropbox.com/s/ekgz9jtj1ybtxmj/alexnet-caffemodel.npy?dl=1).

## Dependencies
```console
$ python -V
Python 2.7.10
```

```console
$ python -c 'import tensorflow as tf; print(tf.__version__)'
1.8.0
```

## Resources
Original caffemodel and prototxt: [https://github.com/BVLC/caffe/tree/master/models/bvlc_alexnet]  
Caffe-tensorflow conversion project: [https://github.com/ethereon/caffe-tensorflow]  
Evaluation dataset: [https://www.kaggle.com/c/dogs-vs-cats]
