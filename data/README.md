---
license: cc-by-nc-4.0
language:
- en
size_categories:
- 1K<n<10K
---

This repository contains the **VX-S3DIS** dataset, presented in [RESSCAL3D++](https://arxiv.org/abs/2410.02323), an indoor scene dataset which accurately mimics the behavior of a resolution-scalable 3D sensor. The presented dataset is the first dataset leveraging resolution scalable point streams. It is build upon the S3DIS dateset and comprises a total of 7031 samples derived from 168 distinct rooms within the S3DIS dataset. The dataset includes annotations for 11 different classes: floor, wall, column, window, door, table, chair, sofa, bookcase, board, and clutter.

The data is distributed as ply files where all information is encoded in the vertex attributes. Please see DATA.md for details about the data.

If you use this data, please cite the [RESSCAL3D++](https://arxiv.org/abs/2410.02323) paper along with the S3DIS paper.

```
@inproceedings{royen2024resscal3d++,
title={RESSCAL3D++: Joint Acquisition and Semantic Segmentation of 3D Point Clouds},
author={Royen, Remco and Pataridis, Kostas and van der Tempel, Ward and Munteanu, Adrian},
booktitle={2024 IEEE International Conference on Image Processing (ICIP)},
pages={3547--3553},
year={2024},
organization={IEEE}
}
```

```
@inproceedings{armeni20163d,
title={3d semantic parsing of large-scale indoor spaces},
author={Armeni, Iro and Sener, Ozan and Zamir, Amir R and Jiang, Helen and Brilakis, Ioannis and Fischer, Martin and Savarese, Silvio},
booktitle={Proceedings of the IEEE conference on computer vision and pattern recognition},
pages={1534--1543},
year={2016}
}
```