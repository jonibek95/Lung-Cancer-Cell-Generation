# 🧬 Fake Lung Cancer Cell Generation using PGGAN

Implementation of synthetic lung cancer cell image generation using **Progressive Growing GAN (PGGAN)**.

---

## 📌 Overview

This repository presents a complete pipeline for generating **realistic synthetic lung cancer cell images** using PGGAN.

Because Whole Slide Images (WSIs) are extremely large and require expert annotations, this project focuses on:

- **Preparing WSIs**
- **Extracting annotated cancer patches**
- **Training PGGAN**
- **Generating high-quality fake cancer cells for data augmentation and research**

This work helps address the challenge of limited annotated medical datasets and provides a scalable solution for synthetic pathology image generation.

---

## 🚀 Pipeline Summary

### 1️⃣ Data Preparation
- Load gigapixel Whole Slide Images (WSIs)
- Use pathologist-provided annotations
- Organize image/label structure for preprocessing and extraction

---

### 2️⃣ Downscale & Preprocessing
WSIs are extremely large (gigapixel scale), so downscaling is applied.

Preprocessing includes:
- **Tissue detection**
- **Color normalization** (optional)
- **Artifact removal**
- **Filtering empty/background tiles**

---

### 3️⃣ Patch Extraction
- Crop high-resolution cancer regions from WSIs  
- Each patch captures meaningful histopathology patterns  
- These extracted patches form the training dataset for PGGAN  

<p align="center">
  <img src="images/preprocessing.png" width="650">
</p>

---

### 4️⃣ Fake Cell Generation (PGGAN)

PGGAN is used for its stability and ability to **progressively increase** image resolution during training.

Key features:
- Training grows from **4×4 → 8×8 → … → 256×256**
- Fade-in layers ensure stable GAN convergence
- Generates realistic **histopathology textures** and **nuclear structures**

---

### 5️⃣ Results

A comparison between **real lung cancer patches** and **PGGAN-generated synthetic images**:

<p align="center">
  <img src="images/results.png" width="670">
</p>

✔ **Real patches** – extracted from annotated WSIs  
✔ **Generated patches** – produced by the trained PGGAN generator  

Synthetic images show realistic tissue morphology, color distribution, and cellular structure.

---
