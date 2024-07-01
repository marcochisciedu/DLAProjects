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
pip install ffmpeg --upgrade
```

Requirements to reproduce the results of "Lab4-OOD.ipynb" :

```
pip install -r requirementsOOD.txt
```
and pytorch.


## Lab1-CNNs

This laboratory is dedicated to trying to duplicate, on a smaller scale, the results of the ResNet paper:

> [Deep Residual Learning for Image Recognition](https://arxiv.org/abs/1512.03385), Kaiming He, Xiangyu Zhang, Shaoqing Ren, Jian Sun, CVPR 2016.

Deeper networks do not guarantee more reduction in training/validation loss or an increase in validation/testing accuracy.

The first section contains the results of training and evaluating MLPs with different depths on MNIST. Each depth is explored with three different runs with different random seeds (since "luck" could influence the outcome), their test accuracy, validation accuracy, validation loss and training loss are grouped together showing their mean and variance.

The second section contains the results of training and evaluating CNNs with different layer lists (how many blocks the CNN has for each type of "layer") on Cifar10.
The objective, once again, is to test how making CNNs deeper, with or without residual connections, affects their performances. Since CNNs are more stable and take more time training, there is only one run for each layer list.

Lastly, Grad-CAM, implemented following the math and instructions in the given paper, and some examples of its use with different Neural Networks and datasets. For each Neural Network I used different layers' features maps to compute Grad-CAM, exploring which were the saliency points of each image at different "depths" in the network.


## Lab3-DRL

This laboratory is focused on getting more advanced versions of Deep Reinforcement Learning algorithms up and running. Deep Reinforcement Learning is **hard**, and getting agents to stably train can be frustrating and requires quite a bit of subtlety in analysis of intermediate results. We will start by implementing `REINFORCE` on the [Cartpole environment](https://gymnasium.farama.org/environments/classic_control/cart_pole/).

In the first section `REINFORCE` is tested on the Cartpole environment using the standard baseline while changing the temperature and gamma.
Since training the policy is stochastic, for each setting I performed the policy training 5 times with 5 different seeds to be able to replicate the experiments. The 5 runs are aggregated together showing their mean and variance.

The second section contains the results of the experiments with `REINFORCE` on Cartpole using different kinds of baselines (no baseline, standard baseline and a Value Net as a baseline). I also experimented with changing the number of layers of the Policy and Value Nets and with much longer runs with two of the best settings (standard baseline and ValueNet) to see if their performance gap was due to the number of training episodes.
Once again, for each setting I performed the policy training 5 times with 5 different seeds to be able to replicate the experiments.

Lastly, solving the OpenAI CarRacing-v2 environment. Using Deep Q Learning to train an agent that is able to solve that environment, approximating the q value function with a CNN that takes in input a stack of grayscale frames of the game.

## Lab4-OOD

The goal of this laboratory is to develop a methodology for detecting OOD samples and measuring the quality of OOD detection. It also includes some experiments incorporating adversarial examples during training to make models more robust to adversarial attacks.

The first section is dedicated to building a simple OOD detection pipeline using an ID (CIFAR10) and OOD datasets (Fake Data and CIFAR100) and implementing some performance metrics to evaluate OOD detection (ROC and PR curves).

Inside the second section there are some experiments with enhancing a base model to be (more) robust to adversarial attacks. After implementing and testing Fast Gradient Sign Method (FGSM), using various epsilons, it is used to augment the model training with adversarial examples. To conclude, it is tested whether the augmented model is more (or less) robust to OOD samples using the OOD detection pipeline and metrics previously implemented.