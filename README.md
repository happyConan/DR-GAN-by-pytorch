# DR-GAN-by-pytorch
# [Disentangled Representation Learning GAN for Pose-Invariant Face Recognition](http://cvlab.cse.msu.edu/project-dr-gan.html)

- authors: Luan Tran, Xi Yin, Xiaoming Liu
- CVPR2017: http://cvlab.cse.msu.edu/pdfs/Tran_Yin_Liu_CVPR2017.pdf
- Pytorch implimentation of DR-GAN (updated version in "Representation Learning by Rotating Your Faces")
- Added a pretrained ResNet18 to offer a feature loss in order to improve Generator's performance.

## Requirements
- python 3.x
- pytorch
- torchvision
- numpy
- scipy
- matplotlib
- pillow

## How to use

### Single-Image DR-GAN

1. Modify model function at base_options.py to define single model.
    - Data needs to have ID and pose lables corresponds to each image.
    - If you don't have, default dataset is CFP_dataset. Modify dataroot function at base_options.py.


2. Run train.py to train models
      - Trained models and Loss_log will be saved at "DR_GAN/snapshot/Single" by default
      - You can also use tensorboard to watch the loss graphs in real-time.
      > python train.py
      > tensorboard --logdir=/home/zhangjunhao/logs

3. Generate Image with arbitrary pose
      - Change the "save_path" in base_model.py.
      - Specify leaned model's filename by "--pretrained_G" option in base_options.py.
      - generated images will be saved at specified result directory.
      > python test.py


### Multi-Image DR-GAN

1. Modify model function at base_options.py to define multi model.
    - Data needs to have ID and pose lables corresponds to each image.
    - If you don't have, default dataset is CFP_dataset. Modify dataroot function at base_options.py.


2. Run train.py to train models
      - Trained models and Loss_log will be saved at "DR_GAN/snapshot/Single" by default
      - You can also use tensorboard to watch the loss graphs in real-time.
      > python train.py
      > tensorboard --logdir=/home/zhangjunhao/logs

3. Generate Image with arbitrary pose
      - Change the "save_path" in base_model.py.
      - Specify leaned model's filename by "--pretrained_G" option in base_options.py.
      - generated images will be saved at specified result directory.
      > python test.py