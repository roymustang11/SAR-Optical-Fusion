# Fusion of Optical and SAR Data for LAI Estimation

This repository implements the methodology described in: **"Fusion of Optical and SAR Data Using Three Approaches for the Estimation of LAI With Modified Integral Equation Model"** (IEEE GRSL, 2024).

## 🌾 Research Overview
This study presents a comprehensive investigation of **Leaf Area Index (LAI)** estimation for wheat crops using **Sentinel-1 (SAR)** and **Sentinel-2 (Optical)** datasets. It introduces a novel derivation of the backscattering coefficient for the **Integral Equation Model (IEM)** at **VH polarization**.

### Core Methodology
* **SAR Modeling**: Water Cloud Model (WCM) integrated with a Modified IEM (Gaussian correlation function).
* **Optical Modeling**: PROSAIL Radiative Transfer Model (RTM).
* **Study Area**: Varanasi, India (Indo-Gangetic plain).
* **Fusion Strategy**: Deep Learning, Principal Component Analysis (PCA), and Nonlinear Regression.

## 📁 Repository Structure
* `/data`: Must contains in situ measurements (LAI , soil moisture, and surface roughness etc.).
* `/models`: Python implementation of the WCM, Modified IEM, and the Deep Learning sequential model.
* `/notebooks`: Analysis and visualization scripts for regenerating paper plots.

## 📊 Performance Summary
The deep learning fusion approach outperformed individual sensors and traditional fusion methods:

| Approach | $R^2$ | $RMSE$ ($m^2m^{-2}$) |
| :--- | :---: | :---: |
| Optical (PROSAIL) | 0.70 | 0.82 |
| SAR (VH Polarization) | 0.72 | 0.60 |
| PCA Fusion | 0.86 | 0.44 |
| **Deep Learning Fusion** | **0.91** | **0.38** |



## 🛠 Deep Learning Architecture
The optimized model was built using the **TensorFlow** library with the following sequential structure:
* **Input Layer**: ReLU activation.
* **Hidden Layer 1**: 64 units, ReLU activation, L2 regularization.
* **Hidden Layer 2**: 32 units, ReLU activation, L2 regularization.
* **Output Layer**: Linear activation.
* **Training**: 50 epochs with a 30% validation split.

## 📜 Citation
If you use this work, please cite:
```bibtex
@article{singh2024fusion,
  title={Fusion of Optical and SAR Data Using Three Approaches for the Estimation of LAI With Modified Integral Equation Model},
  author={Singh, Shubham Kumar and Prasad, Rajendra and Yadav, Suraj A. and Srivastava, Prashant K. and Singh, Gulab and Srivastava, Hari Shanker},
  journal={IEEE Geoscience and Remote Sensing Letters},
  volume={21},
  year={2024},
  publisher={IEEE}
}
