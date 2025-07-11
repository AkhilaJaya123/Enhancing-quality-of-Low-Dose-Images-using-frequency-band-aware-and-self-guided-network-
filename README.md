# Enhancing Quality of Low Dose CT Images Using Frequency Band-Aware and Self-Guided Network

This project implements a deep learning-based framework for improving the quality of low-dose CT (LDCT) images using a **Frequency-band-aware and Self-guided network (FreeSeed)**. It aims to reduce radiation exposure while maintaining high diagnostic image quality.

---

## 📌 Problem Statement

Reconstructing high-quality images from sparse-view CT scans introduces frequency-band-specific artifacts. This project proposes a dual-domain solution to enhance LDCT images while minimizing radiation risk using a deep neural network architecture.

---

## 🎯 Objectives

- Develop a **frequency-band-aware network** to remove structured artifacts from the frequency domain.
- Design a **self-guided network** to restore fine image details in the spatial domain.
- Compare the model’s performance against standard denoising approaches using metrics like **SSIM**, **PSNR**, and **CNR**.

---

## 🛠️ Methodology
![Architecture](Architecture)
### 1. FBP-Based Reconstruction
- Input NDCT images
- Generate sparse-view sinograms using Radon transform (e.g., 2°, 3° intervals)
- Apply **Filtered Back Projection (FBP)** to reconstruct LDCT images

### 2. FreeSeed Model
#### 🔹 FreeNet (Frequency Domain)
- Converts image to frequency domain via FFT
- Detects artifact-prone frequency bands using convolution and band-pass attention

#### 🔹 SeedNet (Spatial Domain)
- Refines the artifact-removed output to recover missing detail
- Enhances spatial clarity and reduces residual noise

### 3. Loss Functions
- **SSIM**, **MSE**, **MAE (L1 Loss)** used to train and validate model performance

---

## 📊 Results Summary

- **SSIM**: LDCT_2_degree outperformed LDCT_3_degree in structural preservation
- **PSNR**: Higher for LDCT_2_degree, indicating better noise removal
- **CNR**: Improved contrast retention with LDCT_2_degree
- **Histogram Matching**: High correlation and low divergence confirm fidelity of reconstructions

---

## 🧪 Dataset

- CT images from the **CT_train** dataset
- Images processed at 2° and 3° acquisition angles
- Input format: `.jpg`

---

## 🧰 Tools & Libraries

- Python
- NumPy, Pandas
- OpenCV
- Matplotlib
- PyTorch
- scikit-image
- Radon & iradon from scikit-image

---

## 📜 License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more details.


