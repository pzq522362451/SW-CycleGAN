# SW-CycleGAN

##Cycle consistency generative adversarial networks with Sliced Wasserstein distance

-  Tensorflow 2.X implementation
-  Inspired by Deshpande $et$ $al$. [sliced Wassetstein generator] (https://openaccess.thecvf.com/content_cvpr_2018/papers/Deshpande_Generative_Modeling_Using_CVPR_2018_paper.pdf), the sliced wasserstein distance (SWD) gains less computation and fast convergence than Wasserstein distance (WD). The code for SWD is shown in (https://github.com/ishansd/swg).
-  This repository contains reprodce of several experiments mentioned in the paper
-  Both unconditional and conditional SW-CycleGAN were verified with the MNIST handwritting dataset.
-  The implementation for CycleGAN using the MNIST dataset is shown in (https://github.com/MorvanZhou/mnistGANs)


## Requirements

- python 3.7.13
- Tensorflow == 2.8.2
- Numpy == 1.21.6
- Keras == 2.8.0

Note: All experiment were excecuted in Google colab with Tesla P100-PCIE-16GB GPU

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)]

![alt text](https://colab.research.google.com/assets/colab-badge.svg)
