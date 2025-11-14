# Prognostication of Chronic Pancreatitis Using CT-Based Pancreas Segmentation

A deep learning and radiomics workflow for pancreas segmentation and chronic pancreatitis analysis.

Overview

This project focuses on segmenting the pancreas from CT scans and extracting radiomic features for the prognostication of Chronic Pancreatitis (CP).
The pipeline includes data preprocessing, pancreas segmentation using SwinUNETR, comparison with MedSAM, radiomic feature extraction, and classification.

This work was completed as part of my Dual Degree project at IIT Madras under the guidance of Prof. Ganapathy Krishnamurthi.

📁 Project Structure

Data Preprocessing

HU windowing (WW = 400, WC = 40)

Normalization & resampling

Visualization of preprocessed CT slices

Segmentation Model

SwinUNETR implementation (MONAI)

Comparison with MedSAM

Postprocessing (morphological ops, connected components)

3D visualization of predicted pancreas

Radiomics

Feature extraction from segmented regions

Key radiomic features for CP prognostication

Classification

Feature-based ML classification for normal vs. chronic pancreatitis

📊 Dataset

Normal Pancreas (CT-82 dataset):

82 CT scans with high-quality manual labels

Chronic Pancreatitis (SIMS Hospital):

14 labeled cases

50 unlabeled cases (potential for SSL)

🧠 Segmentation Models
SwinUNETR (final model)

Hybrid of Swin Transformer + UNETR

Dice Score: 0.851

MedSAM (baseline)

Dice Score: 0.79

SwinUNETR was selected due to better spatial understanding and performance on pancreas anatomy.

🔍 Radiomic Feature Extraction

Extracted features include:

Texture: contrast, entropy, correlation

Cluster-based: cluster shade, cluster prominence, cluster tendency

Homogeneity: homogeneity 1 & 2

Information-based: IMC1, IMC2

Intensity-based: energy

These features were used for downstream ML classification of CP vs. normal pancreas.

🧩 Methodology Summary

Data acquisition (CT-82 + SIMS Hospital)

Preprocessing using HU windowing

Training SwinUNETR for segmentation

Model evaluation using DSC

Postprocessing to clean segmentation masks

3D visualization of pancreas structure

Radiomic feature extraction

Feature-based ML classification

📈 Results

SwinUNETR achieved 0.851 DSC

Successful extraction of discriminative radiomic features

Pipeline demonstrates potential for early CP prognostication

📌 Future Work

Semi-supervised learning using unlabeled SIMS data

Larger multi-institutional dataset

Integration of clinical metadata

Improved feature selection and evaluation

Potential extension to multimodal prediction

🙏 Acknowledgements

Special thanks to Prof. Ganapathy Krishnamurthi and Dr. Vel Murugan for their guidance and mentorship during this project.
