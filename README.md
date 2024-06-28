# Interpretable Self-Supervised Learning Library（ISSLlib)

A Interpretable Self-Supervised Learning Library. This repo collects the official implementations of works done by [Yisen Wang](https://yisenwang.github.io/) and his students.


This repository includes a PyTorch implementation of the NeurIPS 2023 paper [Identifiable Contrastive Learning with Automatic Feature Importance Discovery](https://arxiv.org/abs/2310.18904) 
and the ICLR 2024 paper [Non-negative Contrastive Learning](https://arxiv.org/pdf/2403.12459), which are two new self-supervised learning methods that can obtain interpretable features.


## Installation

First clone the repo.

Then use:
```
pip3 install .[dali,umap,h5] --extra-index-url https://developer.download.nvidia.com/compute/redist
```




## Training

Taking SimCLR on CIFAR-10 as an example, we pretrain the model with following commands
```bash
python3 main_pretrain.py \
    # path to training script folder
    --config-path scripts/pretrain/cifar/ \
    # training config name
    --config-name simclr.yaml

```

For Non-negative contrastive learning, we pretrain the model with following commands


```bash
python3 main_pretrain.py \
    # path to training script folder
    --config-path scripts/pretrain/cifar/ \
    # training config name
    --config-name ncl.yaml

```



For Tri-factor contrastive learning, we pretrain the model with following commands


```bash
python3 main_pretrain.py \
    # path to training script folder
    --config-path scripts/pretrain/cifar/ \
    # training config name
    --config-name tricl.yaml

```


**NOTE:** We can change the argument (loss_type) in the scripts (e.g., scripts/pretrain/cifar/simclr.yaml) to pretrain the model with different methods (xent represents simclr, tri represents tri-SimCLR, ).





After that, for offline linear evaluation on selected dimensions, follow the examples in `scripts/linear`.

---

## Citing this work
If you find the work useful, please cite the accompanying papers:
```
@inproceedings{
zhang2023tricontrastive,
title={Identifiable Contrastive Learning with Automatic Feature Importance Discovery},
author={Qi Zhang and Yifei Wang and Yisen Wang},
booktitle={NeurIPS},
year={2023},
}
```

```
@inproceedings{
wang2024nonnegative,
title={Non-negative Contrastive Learning},
author={Yifei Wang and Qi Zhang and Yaoyu Guo and Yisen Wang},
booktitle={ICLR},
year={2024},
}
```




## Acknowledgement

Our codes borrows the implementations of SimCLR in the solo-learn repository: https://github.com/vturrisi/solo-learn
