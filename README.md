# Pytorch Implementation of Various Point Transformers

Recently, various methods applied transformers to point clouds: [PCT: Point Cloud Transformer (Meng-Hao Guo et al.)](https://arxiv.org/abs/2012.09688), [Point Transformer (Nico Engel et al.)](https://arxiv.org/abs/2011.00931), [Point Transformer (Hengshuang Zhao et al.)](https://arxiv.org/abs/2012.09164). This repo is a pytorch implementation for these methods and aims to compare them under a fair setting. Currently, all three methods are implemented, while tuning their hyperparameters.


## Classification
### Data Preparation
Download alignment **ModelNet** [here](https://shapenet.cs.stanford.edu/media/modelnet40_normal_resampled.zip) and save in `modelnet40_normal_resampled`.

### Run
Change which method to use in `config/config.yaml` and run
```
python train.py
```
### Results
Using Adam with learning rate 1e-3, decay 0.3 for every 50 epochs, train for 200 epochs; data augmentation follows [this repo](https://github.com/yanx27/Pointnet_Pointnet2_pytorch). We have the following result:
| Model | Accuracy |
|--|--|
| Hengshuang |  89.6|
| Menghao | 71.6 |
| Nico |  85.5 |

### Miscellaneous
Some code and training settings are borrowed from https://github.com/yanx27/Pointnet_Pointnet2_pytorch.
Code for [PCT: Point Cloud Transformer (Meng-Hao Guo et al.)](https://arxiv.org/abs/2012.09688) is adapted from the author's Jittor implementation https://github.com/MenghaoGuo/PCT.
