# SW-CycleGAN

## Cycle consistency generative adversarial networks with Sliced Wasserstein distance

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

Note: All experiment were excecuted in Google colab with Tesla P100-PCIE-16GB GPU ![alt text](https://colab.research.google.com/assets/colab-badge.svg)


## File discription

## Usage

## Model description

## Results on unconditional CycleGAN
### t-SNE
### MNIST visualization 
### Learning curve

## Results on conditional CycleGAN
### t-SNE


<div align=center>
<img src="https://github.com/pzq522362451/SW-CycleGAN/blob/main/Results/tsne_wd.png" width="360" height="360"><img src="https://github.com/pzq522362451/SW-CycleGAN/blob/main/Results/tsne_swd.png" width="360" height="360">
</div>


### MNIST visualization 

The results with swd is shown bellow:
![image](https://github.com/pzq522362451/SW-CycleGAN/blob/main/Results/swd.png)

The results with wd is shown bellow:
![image](https://github.com/pzq522362451/SW-CycleGAN/blob/main/Results/wd.png)

### Learning curve
<div align=center>
  
| First Header  | generator loss| discriminator loss | cycle consistency loss |
| ------------- | ------------- |   -------------    | -------------          |
| Wasserstein loss  | <img src="https://github.com/pzq522362451/SW-CycleGAN/blob/main/Results/gloss_wd.jpg" width="200" height="120"> |<img src="https://github.com/pzq522362451/SW-CycleGAN/blob/main/Results/dloss_wd.jpg" width="200" height="120">|<img src="https://github.com/pzq522362451/SW-CycleGAN/blob/main/Results/cycloss_wd.jpg" width="200" height="120">|
| Sliced Wasserstein loss  | <img src="https://github.com/pzq522362451/SW-CycleGAN/blob/main/Results/gloss_swd.jpg" width="200" height="120">  |<img src="https://github.com/pzq522362451/SW-CycleGAN/blob/main/Results/dloss_swd.jpg" width="200" height="120"> |<img src="https://github.com/pzq522362451/SW-CycleGAN/blob/main/Results/cycloss_swd.jpg" width="200" height="120"> |
  
</div>

## Ackonwledgements
This work is partially financed by Portuguese funds through FCT – Foundation for Science and Technology, I.P., through IDMEC, under LAETA, project UIDB/50022/2020. This work has been carried out under the High Performance Computing Chair - a R&D infrastructure based at the University of Évora, endorsed by Hewlett Packard Enterprise (HPE), and involving a consortium of higher education institutions (University of Algarve, University of Évora, New University of Lisbon, and University of Porto), research centres (CIAC, CIDEHUS, CHRC), enterprises (HPE, ANIET, ASSIMAGRA, Cluster Portugal Mineral Resources, DECSIS, FastCompChem, GeoSense, GEOtek, Health Tech, Starkdata), and pub- lic/private organizations (Alentejo Tourism-ERT, KIPT Colab).
