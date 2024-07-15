# MMPD-Dataset
MMPD Dataset is proposed in ECCV'2024 "When Pedestrian Detection Meets Multi-Modal Learning: Generalist Model and Benchmark Dataset".

Authors: [Yi Zhang](https://scholar.google.com/citations?hl=en&user=hzR7V5AAAAAJ), [Wang ZENG](https://scholar.google.com/citations?user=u_RNsOUAAAAJ&hl=en), [Sheng Jin](https://scholar.google.com/citations?user=wrNd--oAAAAJ&hl=en), [Chen Qian](https://scholar.google.com/citations?user=AerkT0YAAAAJ&hl=en), [Ping Luo](https://scholar.google.com/citations?user=aXdjxb4AAAAJ&hl=en), [Wentao Liu](https://scholar.google.com/citations?user=KZn9NWEAAAAJ&hl=en)

## Data Preparation

MMPD is built upon the 2D detection datasets, including
[COCO](http://cocodataset.org/),
[CrowdHuman](https://www.crowdhuman.org/),
[Object365](https://www.objects365.org/overview.html),
[LLVIP](https://bupt-ai-cz.github.io/LLVIP/),
[InOutDoor](http://adaptivefusion.cs.uni-freiburg.de/),
[STCrowd](https://github.com/4DVLab/STCrowd),
[PEDRo](https://github.com/SSIGPRO/PEDRo-Event-Based-Dataset),
[FLIR](https://adas-dataset-v2.flirconservator.com/#downloadguide),
[EventPed](https://drive.google.com/drive/folders/1tLACb8OIeHQTFQDUySbbVwBQcHplAr_J),
In order to use MMPD, please download images from the original dataset websites first,
then reorganize the data and use our provided annotation files 
[Google Drive](https://drive.google.com/file/d/1ly5j181GMpP9Rkx0weFamh7CqElL9FXh/view?usp=sharing) or [BaiDu Yun (Code: mmpd)](https://pan.baidu.com/s/1O4Hm44eBvwMflqizLlGUrQ) for training and testing.


After preparing images and annotations, the project should look like this:

```text
── mmpedestron_datasets
    │── mmpedestron_datasets_ann
        │   │-- crowdhuman_coco/annotation_train_full2coco_231020.json
        │   |-- LLVIP/ann_coco/LLVIP_coco_train_change_cat_id.json
        │   |-- PEDRo_events_dataset/coco_ann/pedro_train.json
        │   │-- ...
    │── mmpedestron_images
                │-- COCO
                │-- CrowdHuman
                │-- Object365
                │-- LLVIP
                │-- InOutDoor
                │-- STCrowd
                │-- ...
```
## Data Processing

Please obtain the data processing script from the following repo: [MMPedestron](https://github.com/BubblyYi/MMPedestron)

STCrowd Lidar2RGB
```shell
cd MMPedestron
python tools/datasets_converters/stcrowd_pointcloud2cam.py
```

PEDRo events dataset Event2RGB
```shell
cd MMPedestron
python tools/datasets_converters/multi_process_evs_handler.py
```

## Terms of Use

1. MMPD-dataset is **ONLY** for research and non-commercial use.
2. MMPD dataset consists of multiple existing public datasets ([COCO](http://cocodataset.org/), [CrowdHuman](https://www.crowdhuman.org/), [Object365](https://www.objects365.org/overview.html), [LLVIP](https://bupt-ai-cz.github.io/LLVIP/), [InOutDoor](http://adaptivefusion.cs.uni-freiburg.de/), [STCrowd](https://github.com/4DVLab/STCrowd), [PEDRo](https://github.com/SSIGPRO/PEDRo-Event-Based-Dataset), [FLIR](https://adas-dataset-v2.flirconservator.com/#downloadguide)), which are not our property. We do not own the copyright of the images. We are not responsible for the content nor the meaning of these images. 
3. MMPD dataset also contains one newly proposed dataset ([EventPed](https://drive.google.com/drive/folders/1tLACb8OIeHQTFQDUySbbVwBQcHplAr_J)). EventPed dataset is freely available for free non-commercial use, and may be redistributed under these conditions. The images and annotations of EventPed dataset belong to [SenseTime Research](https://www.sensetime.com). For commercial queries, please contact Mr. Sheng Jin (jinsheng13[at]foxmail[dot]com). We will send the detail agreement to you.


## Citation
```bibtex
@inproceedings{zhang2024when,
  title={When Pedestrian Detection Meets Multi-Modal Learning: Generalist Model and Benchmark Dataset},
  author={Zhang, Yi and Zeng, Wang and Jin, Sheng and Qian, Chen and Luo, Ping and Liu, Wentao},
  booktitle={European Conference on Computer Vision (ECCV)},
  year={2024},
  month={September}
}
```
