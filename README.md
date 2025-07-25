# License-Plate-Detection

License Plate Detection Using Deep Learning and YOLO Algorithm.

> **_NOTE:_**  Click on the images to view the full-size.
---

**(Train YOLO v5 on a Custom Dataset)**
[<img src="/runs/detect/yolov5-l/f4015d33-vlcsnap-00225.jpg" width="500"/>](/runs/detect/yolov5-l/f4015d33-vlcsnap-00225.jpg)
[<img src="/runs/detect/yolov5-l/f9217ea6-C0013.MP4_frame_0.jpgf9217ea6-C0013.MP4_frame_0.jpg" width="500"/>](/runs/detect/yolov5-l/f9217ea6-C0013.MP4_frame_0.jpg)
[<img src="/runs/detect/yolov5-l/ff1cafc3-C0003.MP4_frame_6250.jpg" width="500"/>](/runs/detect/yolov5-l/ff1cafc3-C0003.MP4_frame_6250.jpg)
[<img src="/runs/detect/yolov5-l/fc260a75-vlcsnap-00220.jpg" width="500"/>](/runs/detect/yolov5-l/fc260a75-vlcsnap-00220.jpg)
[<img src="/runs/detect/yolov5-l/ffbd3aa4-C0004_2.MP4_frame_0.jpg" width="500"/>](/runs/detect/yolov5-l/ffbd3aa4-C0004_2.MP4_frame_0.jpg)

## Installation

```sh
# Clone the License-Plate-Detection Repository
git clone https://github.com/aligh993/License-Plate-Detection

# Navigate to the Cloned Directory
cd License-Plate-Detection

# Install Required Packages
pip install -r requirements.txt
```

> **_NOTE:_**  For **Quick Start** you can use *[`Main.ipynb`](/Main.ipynb "Main.ipynb")*.
---

## Dataset

Put the labeled dataset **`license_plate_dataset`** you downloaded from [**Google Drive**](https://B2n.ir/yn5201) in **`./License-Plate-Detection/Dataset/`**

**`dataset.yaml`** file's for the address and information of dataset (such as train/test/validation image address, class name and number of classes) is in the main directory of the project.

## Train

Train model on the License Plate Dataset .Pre Trained Models download automatically from the latest YOLOv5 release, but you can download manually YOLOv5 Pre Trained Model **`yolov5l.pt`** you downloaded from [**Ultralytics YOLOv5**](https://github.com/ultralytics/yolov5/releases/download/v7.0/yolov5l.pt) and put it in **`./pre_trained_model/`**

```
# fine-tuning on a pre-trained model of yolov5
python ./train.py --img 640 --batch 16 --epochs 60 --data ./dataset.yaml --weights ./pre_trained_model/yolov5l.pt --cache
```

## Test

Test model on the dataset. Put the weight **`best.pt`** you downloaded from [**Google Drive**](https://drive.google.com/drive/folders/140Nr6HFVJaci0K97u8OU10fCotNgWMoy) in **`./runs/train/yolov5-l/weights/`**

```
# after train, it gives you weight of train and you can use it for tests.
python ./detect.py --source ./test_images/ --weight ./runs/train/yolov5-l/weights/best.pt
```

## Validate

Validate model on the dataset. Put the weight **`best.pt`** you downloaded from [**Google Drive**](https://drive.google.com/drive/folders/140Nr6HFVJaci0K97u8OU10fCotNgWMoy) in **`./runs/train/yolov5-l/weights/`**

```
python ./val.py --data ./dataset.yaml --weights ./runs/train/yolov5-l/weights/best.pt
```

## wandb

to have mAP, loss, confusion matrix, and other metrics, sign in www.wandb.ai.

```
pip install wandb
```

## Clone License-Plate-Detection Repository

```
git clone https://github.com/aligh993/License-Plate-Detection
cd License-Plate-Detection
pip install -r requirements.txt
```

## Contributing

1. Fork it (<https://github.com/aligh993/License-Plate-Detection>)
2. Create your feature branch (`git checkout -b feature/fooBar`)
3. Commit your changes (`git commit -am 'Add some fooBar'`)
4. Push to the branch (`git push origin feature/fooBar`)
5. Create a new Pull Request
