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
* `--CycleGAN`: THe model we build the CycleGAN. It is a class and based on Keras.
* `--GAN_Utils`: Functions about how to save the model and how to produce synthetic examples.
* `--InstanceNormalization`: Instance Normalization implemetation based on Keras
* `--NN_Utils`:Build model structures include squeeze-and-excitation mechanism, CNN, ResNet, Modified ResNet, the discriminator and generator (both in conditional and unconditional cases).
* `--Set_seed`: Set random seeds for reproducible implementation.
* `--Utils_MNIST`: Downlaod and preprocessing MNIST dataset.
* `--swd_tf2`: The sliced Wasserstein distance implementation in tensorflow 2.0.
* `--t-SNE_Utils`: t-SNE package for 2-D visualization.
* `--Main`: The main file to run these pexperiments.

## Implementation details
- The overall experiments include swd,wd,swd-sem and wd-sem are included in Run Main.ipynb. Directly using this file can get the results. Note that users should change the directory to successfully run this code.
-Hyperparameter settings: Adam optimizer is used with learning rate of `2e-4` in both the generator and the discriminator;The batch size is `32`, total iteration is 10,000. LABDA (Weight of cycle consistency loss) is `10`. Random projection in SWD is `32`.

## Usage
The script with `.ipynb` contains all the experiments (four scenarios: wd/swd/wd-sem/swd-sem).

## Model description
<div align=center>
  
|  Architecture | Description|
| ------------- | ------------- |
|<img src="https://github.com/pzq522362451/SW-CycleGAN/blob/main/Results/cyclegan_1.jpg" width="250" height="110">|The first part of CycleGAN receives a domain 𝐴 image <br>together with a label 𝑦𝐵 ∈ {1, 2, ..., 9} at the generator G12 <br>to generate the corresponding 𝑦𝐵 domain image. Generated domain 𝐵 <br>images will compare with real domain 𝐵 images in the discriminator D12. <br>At the same time, generated domain 𝐵 images and labels 𝑦𝐴 will be sent to <br>the other generator G21 to reconstruct domain 𝐴 images.|
<img src="https://github.com/pzq522362451/SW-CycleGAN/blob/main/Results/cyclegan_2.jpg" width="250" height="110">|The second part of CycleGAN receives a domain 𝐵 image <br>together with a label 𝑦𝐴 ∈ {0, 0, ..., 0} at the generator G21 <br>to generate the corresponding 𝑦𝐴 domain image. Generated domain 𝐴 <br>images will compare with real domain 𝐴 images in the discriminator D21. <br>At the same time, generated domain 𝐵 images and labels 𝑦𝐵 will be sent to <br>the other generator G12 to reconstruct domain 𝐵 images.|

</div>


## Results on conditional CycleGAN
### t-SNE

<div align=center>
  
|   | wd|swd|
| ------------- | ------------- |------------- |
| t-SNE| <img src="https://github.com/pzq522362451/SW-CycleGAN/blob/main/Results/tsne_wd.png" width="320" height="320">|<img src="https://github.com/pzq522362451/SW-CycleGAN/blob/main/Results/tsne_swd.png" width="320" height="320"> |

</div>


### MNIST visualization 

The results with swd is shown bellow:
![image](https://github.com/pzq522362451/SW-CycleGAN/blob/main/Results/swd.png)

The results with wd is shown bellow:
![image](https://github.com/pzq522362451/SW-CycleGAN/blob/main/Results/wd.png)

### Learning curve
<div align=center>
  
| Loss type  | Generator loss| Discriminator loss | Cycle consistency loss |
| ------------- | ------------- |   -------------    | ------------- |
| Wasserstein loss  | <img src="https://github.com/pzq522362451/SW-CycleGAN/blob/main/Results/gloss_wd.jpg" width="200" height="120"> |<img src="https://github.com/pzq522362451/SW-CycleGAN/blob/main/Results/dloss_wd.jpg" width="200" height="120">|<img src="https://github.com/pzq522362451/SW-CycleGAN/blob/main/Results/cycloss_wd.jpg" width="200" height="120">|
| Sliced Wasserstein loss  | <img src="https://github.com/pzq522362451/SW-CycleGAN/blob/main/Results/gloss_swd.jpg" width="200" height="120">  |<img src="https://github.com/pzq522362451/SW-CycleGAN/blob/main/Results/dloss_swd.jpg" width="200" height="120"> |<img src="https://github.com/pzq522362451/SW-CycleGAN/blob/main/Results/cycloss_swd.jpg" width="200" height="120"> |
  
</div>

## Ackonwledgements
This work is partially financed by Portuguese funds through FCT – Foundation for Science and Technology, I.P., through IDMEC, under LAETA, project UIDB/50022/2020. This work has been carried out under the High Performance Computing Chair - a R&D infrastructure based at the University of Évora, endorsed by Hewlett Packard Enterprise (HPE), and involving a consortium of higher education institutions (University of Algarve, University of Évora, New University of Lisbon, and University of Porto), research centres (CIAC, CIDEHUS, CHRC), enterprises (HPE, ANIET, ASSIMAGRA, Cluster Portugal Mineral Resources, DECSIS, FastCompChem, GeoSense, GEOtek, Health Tech, Starkdata), and pub- lic/private organizations (Alentejo Tourism-ERT, KIPT Colab).
