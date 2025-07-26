# License-Plate-Detection

License Plate Detection Using Deep Learning and the YOLO Algorithm.

> **_NOTE:_**  Click on the images to view them full-size.
---

*(Train YOLO v5 on a Custom Dataset)*

[<img src="/runs/detect/yolov5-l/f4015d33-vlcsnap-00225.jpg" width="300"/>](/runs/detect/yolov5-l/f4015d33-vlcsnap-00225.jpg)
[<img src="/runs/detect/yolov5-l/fc260a75-vlcsnap-00220.jpg" width="300"/>](/runs/detect/yolov5-l/fc260a75-vlcsnap-00220.jpg)
[<img src="/runs/detect/yolov5-l/f9217ea6-C0013.MP4_frame_0.jpg" width="300"/>](/runs/detect/yolov5-l/f9217ea6-C0013.MP4_frame_0.jpg)
[<img src="/runs/detect/yolov5-l/fe54e4a7-C0007_2.MP4_frame_9250.jpg" width="300"/>](/runs/detect/yolov5-l/fe54e4a7-C0007_2.MP4_frame_9250.jpg)
[<img src="/runs/detect/yolov5-l/ff1cafc3-C0003.MP4_frame_6250.jpg" width="300"/>](/runs/detect/yolov5-l/ff1cafc3-C0003.MP4_frame_6250.jpg)
[<img src="/runs/detect/yolov5-l/ffbd3aa4-C0004_2.MP4_frame_0.jpg" width="300"/>](/runs/detect/yolov5-l/ffbd3aa4-C0004_2.MP4_frame_0.jpg)

## Installation

```bash
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

```
https://B2n.ir/yn5201
```
Place the labeled dataset, **`license_plate_dataset`**, you downloaded from [**Google Drive**](https://B2n.ir/yn5201) into **`./License-Plate-Detection/Dataset/`**.

**`dataset.yaml`** file, which contains the address and information for the dataset (such as train/test/validation image addresses, class names, and number of classes), is located in the main directory of the project.

## Train

Train the model on the License Plate Dataset. Pre-trained models download automatically from the latest YOLOv5 release. Alternatively, you can manually download the YOLOv5 Pre-trained Model **`yolov5l.pt`** from [**Ultralytics YOLOv5**](https://github.com/ultralytics/yolov5/releases/download/v7.0/yolov5l.pt) and place it in **`./pre_trained_model/`**.

```bash
# Fine-tuning on a Pre-trained model of yolov5
python ./train.py --img 640 --batch 16 --epochs 60 --data ./dataset.yaml --weights ./pre_trained_model/yolov5l.pt --cache
```

## Test

Test the model on the dataset. Place the weight **`best.pt`** you downloaded from [**Google Drive**](https://drive.google.com/drive/folders/140Nr6HFVJaci0K97u8OU10fCotNgWMoy) into **`./runs/train/yolov5-l/weights/`**.

```bash
# After training, this will provide the trained weights that you can use for testing.
python ./detect.py --source ./test_images/ --weight ./runs/train/yolov5-l/weights/best.pt
```

## Validate

Validate the model on the dataset. Place the weight **`best.pt`** you downloaded from [**Google Drive**](https://drive.google.com/drive/folders/140Nr6HFVJaci0K97u8OU10fCotNgWMoy) into **`./runs/train/yolov5-l/weights/`**.

```bash
# After training, this will provide the trained weights that you can use for validating.
python ./val.py --data ./dataset.yaml --weights ./runs/train/yolov5-l/weights/best.pt
```

## wandb

To view mAP, loss, confusion matrix, and other metrics, sign in at www.wandb.ai.

```bash
pip install wandb
```

## Contributing

1. Fork it (<https://github.com/aligh993/License-Plate-Detection>)
2. Create your feature branch (`git checkout -b feature/fooBar`)
3. Commit your changes (`git commit -am 'Add some fooBar'`)
4. Push to the branch (`git push origin feature/fooBar`)
5. Create a new Pull Request
