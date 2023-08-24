# SimMatch: Semi-supervised Learning with Similarity Matching (CVPR2022)

### News!!! We have recently released our SimMatchV2, please see more details in [paper](https://arxiv.org/abs/2308.06692) and [code](https://github.com/mingkai-zheng/SimMatchV2)

This repository contains PyTorch evaluation code, training code and pretrained models for SimMatch. Most of the code in this repository is adapted from [here](https://github.com/amazon-research/exponential-moving-average-normalization).

For details see [SimMatch: Semi-supervised Learning with Similarity Matching](https://arxiv.org/abs/2203.06915) by Mingkai Zheng, Shan You, Lang Huang, Fei Wang, Chen Qian, and Chang Xu

![SimMatch](img/framework.png)

## CIFAR10/100
This repository is based on ImageNet dataset, We also provide the training code and logs for cifar10/100, please download it from [this link](https://drive.google.com/file/d/1S59Eyt2klV02xW4FS46Mcir4L2jsIjeR/view?usp=sharing).


## Reproducing
To run the code, you probably need to change the Dataset setting (ImagenetPercentV2 function in dataset/imagenet.py), and Pytorch DDP setting (dist_init function in util/dist_utils.py) for your server environment.

The distributed training of this code is based on slurm environment, we have provided the training scrips in script/train.sh

We also provide the pre-trained model. 

|          |Arch | Setting | Epochs  | Accuracy | Download  |
|----------|:----:|:---:|:---:|:---:|:---:|
|  SimMatch | ResNet50 | 1% | 400  | 67.2 % | [simmatch-1p.pth](https://drive.google.com/file/d/1N-i7QwAyUuc862jm_nZLCKJL2cJCvbbD/view?usp=sharing) |
|  SimMatch | ResNet50 | 10% | 400  | 74.4 % | [simmatch-10p.pth](https://drive.google.com/file/d/1Eeeqxixr9JtbrUmFDgRcf-tCWbPGnt2o/view?usp=sharing) |

If you want to test the pre-trained model, please download the weights from the link above, and move them to the checkpoints folder. The evaluation scripts also have been provided in script/train.sh


## Citation
If you find that SimMatch interesting and help your research, please consider citing it:
```
@InProceedings{Zheng_2022_CVPR,
    author    = {Zheng, Mingkai and You, Shan and Huang, Lang and Wang, Fei and Qian, Chen and Xu, Chang},
    title     = {SimMatch: Semi-Supervised Learning With Similarity Matching},
    booktitle = {Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition (CVPR)},
    month     = {June},
    year      = {2022},
    pages     = {14471-14481}
}

@article{zheng2023simmatchv2,
  title={SimMatchV2: Semi-Supervised Learning with Graph Consistency},
  author={Zheng, Mingkai and You, Shan and Huang, Lang and Luo, Chen and Wang, Fei and Qian, Chen and Xu, Chang},
  journal={arXiv preprint arXiv:2308.06692},
  year={2023}
}
```
