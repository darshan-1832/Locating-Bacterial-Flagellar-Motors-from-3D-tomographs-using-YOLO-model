# Locating-Bacterial-Flagellar-Motors-Using-Deep-Learning-Techniques


## 📌 Overview
The goal is to develop an algorithm to **identify the presence and location of flagellar motors** in **3D reconstructions of bacteria**. Automating this traditionally manual task will **accelerate the study of macromolecular complexes**, helping to:
- Answer **fundamental questions in molecular biology**  
- Improve **drug development**  
- Advance **synthetic biology**  

---

## 🔬 Introduction
The **flagellar motor** is a molecular machine that facilitates the **motility of many microorganisms**, playing a key role in:
- **Chemotaxis** (movement in response to chemical stimuli)
- **Pathogenesis** (the development of diseases)

🚀 **Cryogenic Electron Tomography (Cryo-ET)** enables imaging of these **nanomachines in near-native conditions**. However, **identifying flagellar motors in these 3D reconstructions (tomograms) is labor-intensive** due to:
- **Low signal-to-noise ratio**  
- **Variable motor orientations**  
- **Complex crowded intracellular environments**  

This project aims to **eliminate the human bottleneck** in the identification process by developing an **automated image-processing algorithm** to detect flagellar motors.

### 🖼️ What is a Tomogram?
A **tomogram** is a **3D image reconstructed from a series of 2D projection images**. The provided tomograms contain **bacteria flash-frozen in ice**, preserving their molecular structure.  

---

## 📊 Evaluation

### ✅ Evaluation Metric
The model is evaluated using a combination of:
1. **Fβ-score**  
2. **Euclidean distance**  

The objective is to determine whether a tomogram **contains a motor**, and if so, **accurately predict its location**.

### 📏 Classification Criteria
Let:
- **Ground truth location** = `y`
- **Predicted location** = `ȳ`
- **Threshold (τ)** = **1000 Angstroms**

The **classification** is determined based on **Euclidean distance**:  
- ✅ **True Positive (TP)**: If **|y−ȳ|₂ ≤ τ**, the prediction is within threshold.  
- ❌ **False Negative (FN)**: If **|y−ȳ|₂ > τ**, the prediction is outside the threshold.  

### 📌 Fβ-score  
The **Fβ-score** balances **precision and recall**, placing greater weight on recall when **β > 1**, and on precision when **β < 1**.  
For this challenge, we use **β = 2** (which emphasizes recall more than precision).

#### Formula:
![image](https://github.com/user-attachments/assets/fd340703-3372-4218-89d3-f44242d6cd73)


This metric ensures that **both the presence and location accuracy** of predicted motors are considered in the final score.

---

## 📚 Citation
Andrew Darley, Braxton Owens, Bryan Morse, Eben Lonsdale, Gus Hart, Jackson Pond, Joshua Blaser, Matias Gomez Paz, Matthew Ward, Rachel Webb, Andrew Crowther, Nathan Smith, Grant J. Jensen, TJ Hart, Maggie Demkin, Walter Reade, and Elizabeth Park.  
**BYU - Locating Bacterial Flagellar Motors 2025**  
🔗 [Kaggle Competition](https://kaggle.com/competitions/byu-locating-bacterial-flagellar-motors-2025), 2025. Kaggle.
