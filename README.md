# 🧬 Instance Segmentation of Synthetic Biomedical Images with U-Net

This repository demonstrates a complete pipeline for **instance segmentation** of synthetic biomedical images using a **U-Net** architecture, a convolutional neural network originally designed for biomedical image segmentation.

I hope this project can be useful to you as a first glance at this type of neural network and instance segmentation tasks in biomedical imaging.

The goal is to detect and segment each "cell" (simulated blob) in an image by assigning a **unique label** to every instance. This task mimics real-world cell segmentation challenges often encountered in microscopy and biomedical research.

## 🔍 Project Overview

> 📌 *This project focuses on the **technical implementation** of the U-Net architecture. For a deeper understanding of the underlying theory, please refer to the original paper:*  
> **U-Net: Convolutional Networks for Biomedical Image Segmentation**  
> [https://arxiv.org/abs/1505.04597](https://arxiv.org/abs/1505.04597)

In this project, the final goal is to predict a good label and these is the different step:
The ultimate goal of this project is to accurately predict segmentation labels. Here are the main stages involved in achieving this goal:

- Generate synthetic cell-like images with instance-level ground truth.
- Add noise and vary complexity to simulate real-world imperfections.
- Build and train a U-Net model for pixel-wise instance segmentation.
- Evaluate the model using both quantitative metrics and qualitative visualizations.
- Test model generalization on differently generated test images.

## 🧪 Key Results

### ✅ Original Test Set Performance

- **F1 Score:** 0.96–0.98 (mean: **0.97**)
- **Cohen’s Kappa:** 0.96–0.98 (mean: **0.97**)

The model performs extremely well, achieving near-perfect segmentation on the original synthetic test set.

### 🔄 Generalization to Differently Generated Images

To assess robustness, we tested the model on a second set of images generated with a **different process**. While performance slightly decreased, results remained strong:

- **F1 Score:** 0.88–0.94 (mean: **0.91**)
- **Cohen’s Kappa:** 0.87–0.93 (mean: **0.90**)

🔍 Visualizations revealed an increase in **false positives** (shown in pink), suggesting the model occasionally confuses noise/outliers with real cells — yet overall predictions remain solid.

## 🧠 Model Architecture

We use a classic **U-Net** with:

- Convolutional + ReLU + BatchNorm layers
- Downsampling via max pooling
- Upsampling via transposed convolutions
- Skip connections for localization

📄 2025 Lucas
