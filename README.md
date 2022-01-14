
## How to start

```
git clone https://github.com/cuchoco/pytorch_faster_rcnn.git

cd pytorch_faster_rcnn && mkdir data
```

-----

## Prepare data 

* **PASCAL_VOC 07+12**: Please follow the instructions in [py-faster-rcnn](https://github.com/rbgirshick/py-faster-rcnn#beyond-the-demo-installation-for-training-and-testing-models) to prepare VOC datasets. Actually, you can refer to any others. After downloading the data, creat softlinks in the folder data/.

```

├── data
│   ├── VOCdevkit2007
│   └── pretrained_model
│       └── resnet101_caffe.pth

```


## coco api make

```
cd data
git clone https://github.com/pdollar/coco.git 
cd coco/PythonAPI
make
```

