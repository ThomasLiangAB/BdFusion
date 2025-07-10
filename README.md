# BdFusion: Bi-directional Visual-LiDAR Fusion for Resilient Place Recognition
<p align="center">
Anbang Liang, Zhipeng Chen*, Wen Xiong, Yu Yin, Dejin Zhang, Qingquan Li
</p >
<p align="center">
  <a href=" ">Overview</a > •
  <a href="#key-features">Key Features</a > •
  <a href="#Network Architecture">Network Architecture</a > •
  <a href="#datasets">datasets</a > •
  <a href="#results">Results</a > •
</p >
<p align="center">
<img src="images/Fig1.jpg" width="50%"/>
</p >

This repository contains the official authors implementation associated with the paper "BdFusion: Bi-directional Visual-LiDAR Fusion for Resilient Place Recognition".

---

## 📢 Note
- **[2025.07]**  Paper under review.
- **[TODO]**  Code and Dataset will be released only after the paper is accepted.
---

## Overview

BdFusion is a novel attention-based visual-LiDAR fusion method for resilient place recognition in complex environments. Our approach leverages bi-directional attention mechanisms to exploit complementary features between 2D images and 3D point clouds, achieving state-of-the-art performance on multiple benchmarks.

####    Key Contributions:

1. **Bi-directional Attention Module**: Explicit cross-modal feature interaction and enhancement by mining complementary features between 2D textures and 3D structures
2. **Multi-scale Fusion Network**: Comprehensive optimization of feature representation and fusion process using spatial and channel attention
3. **SZU Dataset**: A large-scale dataset covering 20km+ trajectories in complex urban and underground scenarios

---

## Key Features

- ✅ **Robust Performance**: Maintains high accuracy in challenging conditions (low light, textureless, repetitive structures)
- ✅ **Real-time Processing**: 64 FPS on single GPU, suitable for online SLAM applications
- ✅ **Flexible Architecture**: Compatible with various visual and LiDAR feature extractors
- ✅ **Comprehensive Evaluation**: Tested on Oxford RobotCar, KITTI, and custom SZU datasets
---

## Network Architecture

This section provides an overview of the network structure used in DeepTurbid.

- **Network Diagram:**  
<p align="center">
<img src="images/Fig2.jpg" width="100%"/>
</p >

*More detailed network configuration and parameters will be available upon open-source release.*

---

## Datasets
- [Oxford RobotCar Dataset](https://robotcar-dataset.robots.ox.ac.uk/)
- [KITTI Odometry Dataset](http://www.cvlibs.net/datasets/kitti/eval_odometry.php)
- [SZU Dataset] (Coming soon!)

- **SZU Dataset Overview:**  
  The SZU datasets traverse over 20km and include 10 trajectories around the campus of Shenzhen University (SZU), and covers various complex underground and urban scenes (low-light, low-textured, homogeneous structured scenes, etc.).
<p align="center">
<img src="images/Fig6.jpg" width="50%"/>
</p >

---

## Results

### Quantitative Results


### Qualitative Results

<p align="center">
  < img src="assets/qualitative_results.png" alt="Qualitative Results" width="90%"/>
</p >



---

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

<p align="center">
  <b>Star ⭐ this repo if you find it useful!</b>
</p >
