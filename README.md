# Prognostication of Chronic Pancreatitis Using CT-Based Pancreas Segmentation

A deep learning and radiomics pipeline for pancreas segmentation and chronic pancreatitis analysis.  
Project completed as part of my Dual Degree at **IIT Madras**, supervised by **Prof. Ganapathy Krishnamurthi**.

---

## 📌 Overview
This project develops a workflow to segment the pancreas from CT scans and extract radiomic features for the prognostication of **Chronic Pancreatitis (CP)**.  
The pipeline includes:

- CT preprocessing with HU windowing  
- Pancreas segmentation using **SwinUNETR**  
- Comparison with **MedSAM**  
- Postprocessing and 3D visualization  
- Radiomics feature extraction  
- Feature-based ML classification  

Presentation slides and the full project report are included in this repository.

---

## 📁 Dataset
**Normal Pancreas (CT-82 dataset)**
- 82 patients  
- High-quality manual pancreas labels  

**Chronic Pancreatitis (SIMS Hospital)**
- 14 labeled CT cases  
- 50 unlabeled CT cases  
- Useful for semi-supervised extensions

---

## 🧠 Segmentation Models

### SwinUNETR (final model)
- Hybrid Swin Transformer + UNETR architecture  
- Dice Score: **0.851**

### MedSAM (baseline)
- Dice Score: **0.79**

SwinUNETR showed better spatial understanding and segmentation accuracy and was used for downstream analysis.

---

## 🔧 Method Summary
1. **Preprocessing**  
   - HU windowing (WW: 400, WC: 40)  
   - Normalization and resizing  

2. **Segmentation**  
   - SwinUNETR training and evaluation  
   - Dice-based validation  
   - Morphological postprocessing  
   - 3D visualization  

3. **Radiomics**  
   - Extracted features from segmented pancreas  
   - Examples: cluster prominence, entropy, contrast, IMC1, IMC2, homogeneity  

4. **Classification**  
   - Radiomic features used for ML-based CP vs. normal classification

---

## 🔍 Key Radiomic Features
- Cluster Prominence  
- Cluster Shade  
- Cluster Tendency  
- Contrast  
- Correlation  
- Entropy  
- Energy  
- Homogeneity (1 & 2)  
- IMC 1 / IMC 2  

These features capture shape, texture, and intensity properties of the segmented pancreas.

---

## 📈 Results
- SwinUNETR achieved **0.851 DSC**, outperforming MedSAM  
- Segmentation + radiomics pipeline successfully extracts meaningful differences between normal and CP cases  
- Provides a foundation for early CP prognostication

---

## 🚀 Future Work
- Semi-supervised learning using unlabeled SIMS data  
- Larger, multi-institutional dataset  
- Integration of clinical variables  
- Improved feature selection  
- End-to-end multimodal prognostication models  

---

## 🙏 Acknowledgements
Special thanks to **Prof. Ganapathy Krishnamurthi** and **Dr. Vel Murugan** for guidance and feedback throughout the project.
