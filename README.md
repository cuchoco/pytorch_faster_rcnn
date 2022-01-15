Faster RCNN Pytorch
=======
This repo is duplication of [jwyang/faster-rcnn.pytorch](https://github.com/jwyang/faster-rcnn.pytorch)    
C/C++ code(nms, roi pool,align) are removed and easier to study.   
Python 3.8.5   
Ubuntu 20.04.1 LTS (and Window10)

***
## How to start

```bash
git clone https://github.com/cuchoco/pytorch_faster_rcnn.git

cd pytorch_faster_rcnn && mkdir data

pip install -r requirements.txt
```

## Prepare data & pretrained network

* **PASCAL_VOC 07+12**: Please follow the instructions in [py-faster-rcnn](https://github.com/rbgirshick/py-faster-rcnn#beyond-the-demo-installation-for-training-and-testing-models) to prepare VOC datasets.  
Actually, you can refer to any others. After downloading the data, creat softlinks in the folder data/.

```
├── data
│   ├── VOCdevkit2007
│   └── pretrained_model
│       └── resnet101_caffe.pth
```

We used two pretrained models in our experiments, VGG and ResNet101.   
You can download these two models from:

* VGG16: [Dropbox](https://www.dropbox.com/s/s3brpk0bdq60nyb/vgg16_caffe.pth?dl=0), [VT Server](https://filebox.ece.vt.edu/~jw2yang/faster-rcnn/pretrained-base-models/vgg16_caffe.pth)

* ResNet101: [Dropbox](https://www.dropbox.com/s/iev3tkbz5wyyuz9/resnet101_caffe.pth?dl=0), [VT Server](https://filebox.ece.vt.edu/~jw2yang/faster-rcnn/pretrained-base-models/resnet101_caffe.pth)

Download them and put them into the data/pretrained_model/

---
## coco api make
- linux
```bash
cd data
git clone https://github.com/pdollar/coco.git 
cd coco/PythonAPI
make
```

- window
```bash
cd data
git clone https://github.com/philferriere/cocoapi
python setup.py build_ext --inplace

lib/model/utils/config.py

374  # yaml_cfg = edict(yaml.load(f))
375  yaml_cfg = edict(yaml.safe_load(f))
```
and replace lib/pycocotools with data/cocoapi/PythonAPI/pycocotools

---
## Train

```bash
python trainval_net.py 
```
