# BdFusion: Bi-directional Visual-LiDAR Fusion for Resilient Place Recognition
<p align="center">
Anbang Liang, Zhipeng Chen*, Wen Xiong, Yu Yin, Dejin Zhang, Qingquan Li
</p >
<p align="center">
  <a href=" ">Overview</a > •
  <a href="#key-features">Key Features</a > •
  <a href="#installation">Installation</a > •
  <a href="#usage">Usage</a > •
  <a href="#results">Results</a > •
  <a href="#citation">Citation</a >
</p >
<p align="center">
<img src="images/Fig1.jpg" width="80%"/>
</p >


---

## 📢 Note
- **[2025.07]**  Paper under review.
- **[TODO]**  Code and Dataset will be released only after the paper is accepted.

## Overview

BdFusion is a novel attention-based visual-LiDAR fusion method for resilient place recognition in complex environments. Our approach leverages bi-directional attention mechanisms to exploit complementary features between 2D images and 3D point clouds, achieving state-of-the-art performance on multiple benchmarks.
<p align="center">
![Fig1](https://github.com/user-attachments/assets/980520fa-15c9-44b5-b950-4d35dede6187)
</p >

### 🎯 Key Contributions

1. **Bi-directional Attention Module**: Explicit cross-modal feature interaction and enhancement by mining complementary features between 2D textures and 3D structures
2. **Multi-scale Fusion Network**: Comprehensive optimization of feature representation and fusion process using spatial and channel attention
3. **SZU Dataset**: A large-scale dataset covering 20km+ trajectories in complex urban and underground scenarios

## Key Features

- ✅ **Robust Performance**: Maintains high accuracy in challenging conditions (low light, textureless, repetitive structures)
- ✅ **Real-time Processing**: 64 FPS on single GPU, suitable for online SLAM applications
- ✅ **Flexible Architecture**: Compatible with various visual and LiDAR feature extractors
- ✅ **Comprehensive Evaluation**: Tested on Oxford RobotCar, KITTI, and custom SZU datasets

## Installation

### Requirements
- Python 3.8+
- PyTorch 1.10+
- CUDA 11.0+
- Other dependencies: `numpy`, `opencv-python`, `open3d`, `tqdm`

### Setup

```bash
# Clone the repository
git clone https://github.com/your-username/BdFusion.git
cd BdFusion

# Create conda environment
conda create -n bdfusion python=3.8
conda activate bdfusion

# Install PyTorch (adjust CUDA version as needed)
conda install pytorch==1.10.0 torchvision==0.11.0 cudatoolkit=11.3 -c pytorch

# Install other dependencies
pip install -r requirements.txt
```

## Usage

### Data Preparation

Download datasets:
- [Oxford RobotCar Dataset](https://robotcar-dataset.robots.ox.ac.uk/)
- [KITTI Odometry Dataset](http://www.cvlibs.net/datasets/kitti/eval_odometry.php)
- [SZU Dataset](link-to-your-dataset) (Coming soon!)

Organize data as follows:
```
data/
├── oxford/
│   ├── 2014-05-06-12-54-54/
│   ├── 2014-05-06-13-09-52/
│   └── ...
├── kitti/
│   ├── sequences/
│   └── poses/
└── szu/
    ├── seq01/
    ├── seq02/
    └── ...
```

### Training

```bash
# Train on Oxford RobotCar dataset
python train.py --config configs/oxford.yaml

# Train on KITTI dataset
python train.py --config configs/kitti.yaml

# Train on SZU dataset
python train.py --config configs/szu.yaml
```

### Evaluation

```bash
# Evaluate on test set
python evaluate.py --config configs/oxford.yaml --checkpoint checkpoints/bdfusion_best.pth

# Generate visualization
python visualize.py --config configs/oxford.yaml --checkpoint checkpoints/bdfusion_best.pth
```

### Pre-trained Models

| Dataset | AR@1 | AR@1% | Download |
|---------|------|-------|----------|
| Oxford RobotCar | 98.25% | 99.32% | [model](link) |
| KITTI | 90.87% | 92.41% | [model](link) |
| SZU | 92.02% | 94.69% | [model](link) |

## Results

### Quantitative Results

<table>
<tr>
<td>

#### Oxford RobotCar Dataset
| Method | AR@1 | AR@1% | AP |
|--------|------|-------|-----|
| NetVLAD | 58.52% | 73.57% | 60.31% |
| PointNetVLAD | 63.88% | 81.29% | 69.04% |
| MinkLoc++ | 96.72% | 99.10% | 90.56% |
| AdaFusion | 98.18% | 99.21% | 92.33% |
| PRFusion | 98.23% | 99.24% | 92.45% |
| **BdFusion (Ours)** | **98.25%** | **99.32%** | **93.07%** |

</td>
<td>

#### KITTI Dataset
| Method | AR@1 | AR@1% | AP |
|--------|------|-------|-----|
| NetVLAD | 47.96% | 65.13% | 51.25% |
| PointNetVLAD | 60.83% | 76.82% | 62.58% |
| MinkLoc++ | 83.58% | 87.15% | 82.39% |
| AdaFusion | 89.05% | 90.46% | 87.61% |
| PRFusion | 90.35% | 91.87% | 88.92% |
| **BdFusion (Ours)** | **90.87%** | **92.41%** | **89.30%** |

</td>
</tr>
</table>

### Qualitative Results

<p align="center">
  < img src="assets/qualitative_results.png" alt="Qualitative Results" width="90%"/>
</p >

### Ablation Study

| Configuration | AR@1 | Runtime (ms) |
|--------------|------|--------------|
| w/o BDA | 89.36% | 3.55 |
| w/o IFA | 95.54% | 5.08 |
| w/o PFA | 97.19% | 5.32 |
| **Full Model** | **98.25%** | 6.78 |

## Network Architecture

<p align="center">
  < img src="assets/architecture.png" alt="Network Architecture" width="90%"/>
</p >

The BdFusion network consists of three main components:
1. **Feature Extraction**: Parallel CNN branches for image and point cloud features
2. **Bi-directional Attention**: Cross-modal feature enhancement
3. **Adaptive Fusion**: Channel attention-based feature fusion

## Citation

If you find this work useful in your research, please consider citing:

```bibtex
@article{liang2025bdfusion,
  title={BdFusion: Bi-directional Visual-LiDAR Fusion for Resilient Place Recognition},
  author={Liang, Anbang and Chen, Zhipeng and Xiong, Wen and Meng, Fanyi and Yin, Yu and Zhang, Dejin and Li, Qingquan},
  journal={ISPRS Journal of Photogrammetry and Remote Sensing},
  year={2025},
  publisher={Elsevier}
}
```

## Acknowledgments

This work was supported by:
- National Key Research and Development Program of China (Grant 2022YFB3904601)
- Shenzhen Science and Technology Program (Project No.KCXFZ20240903093000002)
- Natural Science Foundation of Guangdong Province (Grant No.2025A1515010216)

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Contact

For questions and collaborations, please contact:
- Anbang Liang: [email]
- Zhipeng Chen: chenzp1990@szu.edu.cn

---

<p align="center">
  <b>Star ⭐ this repo if you find it useful!</b>
</p >
