# DLAProjects

## Requirements
Requirements to reproduce the results of "Lab1-CNNs.ipynb" :

```
pip install -r requirementsCNN.txt
```
and pytorch.

Requirements to reproduce the results of "Lab3-DRL.ipynb" : 

```
pip install -r requirementsDRL.txt
```
and pytorch.
 
To make the video recording possible it might also be required to run:
```
pip install moviepy --upgrade
```
and
```
#pip install ffmpeg --upgrade
```

## Lab1-CNNs

This laboratory is dedicated to trying to duplicate, on a smaller scale, the results of the ResNet paper:

> [Deep Residual Learning for Image Recognition](https://arxiv.org/abs/1512.03385), Kaiming He, Xiangyu Zhang, Shaoqing Ren, Jian Sun, CVPR 2016.

Deeper networks do not guarantee more reduction in training/validation loss or an increase in validation/testing accuracy.

The first section contains the results of training and evaluating MLPs with different depths on MNIST. Each depth is explored with three different runs with different random seeds (since "luck" could influence the outcome), their test accuracy, validation accuracy, validation loss and training loss are grouped together showing their mean and variance.

The second section contains the results of training and evaluating CNNs with different layer lists (how many blocks the CNN has for each type of "layer") on Cifar10.
The objective, once again, is to test how making CNNs deeper, with or without residual connections, affects their performances. Since CNNs are more stable and take more time training, there is only one run for each layer list.

Lastly, Grad-CAM, implemented following the math and instructions in the given paper, and some examples of its use with different Neural Networks and datasets. For each Neural Network I used different layers' features maps to compute Grad-CAM, exploring which were the saliency points of each image at different "depths" in the network.


## Lab3


