# VIDIT: Virtual Image Dataset for Illumination Transfer

We will release more content soon, and updates about future challenges, you can *watch* the repository if you would like to be notified!

:fire: **News-May20** :fire: VIDIT is used for the relighting challenge in the [AIM workshop](https://data.vision.ee.ethz.ch/cvl/aim20/), part of ECCV 2020. Check out the [relighting competition](https://competitions.codalab.org/competitions/24671) beginning May 13th 2020, it is made up of 3 tracks for [one-to-one](https://competitions.codalab.org/competitions/24671) and [any-to-any](https://competitions.codalab.org/competitions/24674) illumination transfer, and for [illumination estimation](https://competitions.codalab.org/competitions/24773).

#### [[VIDIT Paper](https://arxiv.org/abs/2005.05460)] 
#### [[ECCV AIM 2020 Paper](https://arxiv.org/abs/2009.12798)] - [[Supp.](https://github.com/majedelhelou/VIDIT/blob/master/AIM_2020_Relighting_Supp.pdf)] - [[Video](https://www.youtube.com/watch?v=Zn7R0fbXJZw)]

> **Abstract:** *Deep image relighting is gaining more interest lately, as it allows photo enhancement through illumination-specific retouching without human effort. Aside from aesthetic enhancement and photo montage, image relighting is valuable for domain adaptation, whether to augment datasets for training or to normalize input test data. Accurate relighting is, however, very challenging for various reasons, such as the difficulty in removing and recasting shadows and the modeling of different surfaces. We present a novel dataset, the Virtual Image Dataset for Illumination Transfer (VIDIT), in an effort to create a reference evaluation benchmark and to push forward the development of illumination manipulation methods. Virtual datasets are not only an important step towards achieving real-image performance but have also proven capable of improving training even when real datasets are possible to acquire and available. VIDIT contains 300 virtual scenes used for training, where every scene is captured 40 times in total: from 8 equally-spaced azimuthal angles, each lit with 5 different illuminants.*

## Content
VIDIT includes 390 different Unreal Engine scenes, each captured with 40 illumination settings, resulting in 15,600 images. The illumination settings are all the combinations of 5 color temperatures (2500K, 3500K, 4500K, 5500K and 6500K) and 8 light directions (N, NE, E, SE, S, SW, W, NW). Original image resolution is 1024x1024.

<p align="center">
  <img src="gifs/diagram.png" width="300px"/>
</p>


## Getting the AIM 2020 data
Note: *ground-truth test* data will remain private.

**Track 1** (1024x1024): [[Train](https://datasets.epfl.ch/vidit/AIM2020/AIM2020_track1_train.zip)] - [[Validation_Input](https://datasets.epfl.ch/vidit/AIM2020/AIM2020_track1_validation.zip)] - [[Validation_GT](https://datasets.epfl.ch/vidit/AIM2020/AIM2020_track1_validation_gt.zip)] - [[Test_Input](https://datasets.epfl.ch/vidit/AIM2020/AIM2020_track1_test.zip)]

**Track 2** (1024x1024): [[Train](https://datasets.epfl.ch/vidit/VIDIT_train.zip)] - [[Validation_Input](https://datasets.epfl.ch/vidit/AIM2020/AIM2020_track2_validation.zip)] - [[Validation_GT](https://datasets.epfl.ch/vidit/AIM2020/AIM2020_track2_validation_gt.zip)] - [[Test_Input](https://datasets.epfl.ch/vidit/AIM2020/AIM2020_track2_test.zip)]

**Track 3** (512x512): [[Train](https://datasets.epfl.ch/vidit/AIM2020/AIM2020_track3_train.zip)] - [[Validation_Input](https://datasets.epfl.ch/vidit/AIM2020/AIM2020_track3_validation.zip)] - [[Validation_GT](https://datasets.epfl.ch/vidit/AIM2020/AIM2020_track3_validation_gt.zip)] - [[Test_Input](https://datasets.epfl.ch/vidit/AIM2020/AIM2020_track3_test.zip)]

The images are downsampled by 2 for the competition track 3 to ease the computations:
`smallsize_img = cv2.resize(origin_img, (512, 512), interpolation=cv2.INTER_CUBIC)`

If you want to use VIDIT for other purposes, the training images are provided in full 1024x1024 resolution in the "Train" link of **Track 2** above. Also available for download from a Google Drive mirror here: [[Download](https://drive.google.com/open?id=1i_2lIXi-gXgIouDCYnfrdtY3wzTiH1E9)]


## Some associated solutions (pull request to add yours)
Results from the ECCV 2020 competition participants will be made available soon.

* Encoder-decoder latent space manipulation (A. Dherse, M. Everaert, and J. Gwizdala): [[Paper](https://arxiv.org/pdf/2006.02333.pdf)] - [[Code](https://github.com/martin-ev/2DSceneRelighting)]

* Norm-Relighting-U-Net (M. Afifi and M. Brown): [[Code](https://github.com/mahmoudnafifi/image_relighting)]

* (ECCVW2020) Deep relighting networks for image light source manipulation (L. Wang, Z. Liu, C. Li, W. Siu, D. Lun): [[Paper](https://arxiv.org/abs/2008.08298)] - [[Code](https://github.com/WangLiwen1994/DeepRelight)]

* (ECCVW2020) An ensemble neural network for scene relighting with light classification (Dong, L., Jiang, Z., Li, C.)

* (ECCVW2020) SA-AE for any-to-any relighting (Hu, Z., Huang, X., Li, Y., Wang, Q.)


## Citations
```bibtex
@article{elhelou2020vidit,
    title   = {{VIDIT}: Virtual Image Dataset for Illumination Transfer},
    author  = {El Helou, Majed and Zhou, Ruofan and Barthas, Johan and S{\"u}sstrunk, Sabine},
    journal = {arXiv preprint arXiv:2005.05460},
    year    = {2020}
}

@inproceedings{elhelou2020aim,
    title     = {{AIM} 2020: Scene Relighting and Illumination Estimation Challenge},
    author    = {El Helou, Majed and Zhou, Ruofan and S\"usstrunk, Sabine and Timofte, Radu and others},
    booktitle = {Proceedings of the European Conference on Computer Vision Workshops (ECCVW)},
    year      = {2020}
}
```


### Examples with varying direction
<p align="center">
<img src="gifs/A_directions.gif" width="200" /> 
<img src="gifs/B_directions.gif" width="200" />
<img src="gifs/C_directions.gif" width="200" /> 
<img src="gifs/D_directions.gif" width="200" />
</p>


### Examples with varying color temperature
<p align="center">
<img src="gifs/A_illuminants.gif" width="200" /> 
<img src="gifs/B_illuminants.gif" width="200" />
<img src="gifs/C_illuminants.gif" width="200" /> 
<img src="gifs/D_illuminants.gif" width="200" />
</p>
