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

Presentation slides and the full project report are included in this repository.

---

## 📁 Dataset
**Normal Pancreas (CT-82 dataset)**
- 82 patients  
- High-quality manual pancreas labels  

**Chronic Pancreatitis (SIMS Hospital)**
- 14 labeled CT cases  
- 50 unlabeled CT cases  
  
<img width="992" height="506" alt="image" src="https://github.com/user-attachments/assets/3ec7081f-34ea-4c97-a41c-30a2ffb063a4" />


---

## 🧠 Segmentation Models

### SwinUNETR (final model)
- Hybrid Swin Transformer + UNETR architecture
<img width="608" height="266" alt="image" src="https://github.com/user-attachments/assets/ffaf5e86-150c-4090-8fa1-0b011bc26663" />
- Dice Score: **0.851**

### MedSAM (baseline)
- Dice Score: **0.79**

SwinUNETR showed better spatial understanding and segmentation accuracy and was used for downstream analysis.

---

## 🔧 Method Summary
1. **Preprocessing**  
   - HU windowing (WW: 400, WC: 40)  
   - Normalization and resizing  
<img width="839" height="399" alt="image" src="https://github.com/user-attachments/assets/949230af-9357-4c96-ace7-9c5c7eaf04ba" />

2. **Segmentation**  
   - SwinUNETR training and evaluation  
   - Dice-based validation  
   - Morphological postprocessing  
   - 3D visualization  
<img width="618" height="338" alt="image" src="https://github.com/user-attachments/assets/f3d9d88c-0d76-44c6-84b8-56c5bb9e662a" />

3. **Radiomics**  
   - Extracted features from segmented pancreas  
   - Examples: cluster prominence, entropy, contrast, IMC1, IMC2, homogeneity  

---

## 🔍 Key Radiomic Features
<img width="615" height="333" alt="image" src="https://github.com/user-attachments/assets/94198176-2094-4b87-846e-1bae09c79427" />

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
- Postprocessed segmentation masks showed clear pancreas boundaries with reduced noise  
- Extracted a comprehensive set of radiomic features (texture, intensity, shape) from the segmented pancreas  
- Segmentation + radiomics pipeline forms a strong base for downstream CP analysis

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
