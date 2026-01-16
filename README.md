# Multimodal Growth Stage Prediction of Wheat Crop (Google Colab)

This repository contains a **Google Colab notebook** that implements a **multimodal time-series deep learning model** for predicting the growth stages of wheat crops using image, text, and numerical data over time.

📘 Open the Colab notebook here:  
https://colab.research.google.com/drive/1Sz9fYFG8nnG7MsXxovxpSIPWamHUzYhB

---

## 📌 Project Overview

Accurate prediction of crop growth stages is crucial for precision agriculture, irrigation planning, fertilization scheduling, and yield estimation. Traditional approaches rely on manual observation or single-modality data, which can be noisy or incomplete.

This project presents a **multimodal time-series framework** that integrates:
- **Visual data** (crop images),
- **Text embeddings** (metadata/descriptions), and  
- **Numerical agronomic features**  

to predict the wheat crop’s growth stage at each time step.

---

## 🎯 Project Objective

The main goal of this project is to **predict the wheat crop growth stage (4-class classification)** by learning both spatial and temporal patterns from multimodal data.

---

## 🚀 Key Contributions

- Built a **multimodal model** using:
  - **Vision Transformer (ViT) – Google Patch-224 model** for image embeddings  
  - **OpenAI’s CLIP** for text embeddings  
  - Numerical feature embeddings for structured data  

- Designed a **time-series prediction pipeline** using a sliding window approach:
  - Used embeddings from the **previous 5 time steps** to predict the **6th time step**.

- **Fine-tuned Stable Diffusion XL with LoRA** to generate **missing crop images**, ensuring data completeness and consistency.

- Trained an **LSTM-based temporal model**, as it performed better than:
  - Time Series Transformer  
  - Informer  
  - Bahdanau Attention mechanism  
  - Luong Attention mechanism  

- Achieved **83% prediction accuracy** on the **4-class crop growth stage classification task** using the full multimodal dataset.

---

## 🧠 Model Architecture

### 1️⃣ Feature Extraction
- **ViT (Google patch-224)** → Extracts deep visual embeddings from crop images  
- **CLIP embeddings** → Extracts semantic features from text  
- **Numerical embeddings** → Encodes structured agronomic variables  

These embeddings are concatenated to form a unified multimodal representation.

### 2️⃣ Time-Series Modeling
- A **sliding window of 6 time steps** is used:
  - First **5 steps → input**
  - 6th step → prediction target  

- A **Long Short-Term Memory (LSTM) network** is used to capture temporal dependencies, as it outperformed transformer-based models and attention mechanisms in this dataset.

### 3️⃣ Handling Missing Images
- Missing images were generated using a **LoRA fine-tuned Stable Diffusion XL model**, conditioned on structured prompts derived from numerical and textual features.

---


---

## 🛠 Technologies Used

| Component | Technology |
|------------|------------|
| Programming | Python |
| Environment | Google Colab |
| Image Encoder | Vision Transformer (ViT) – Google patch-224 |
| Text Encoder | OpenAI CLIP |
| Generative Model | Stable Diffusion XL + LoRA |
| Time-Series Model | LSTM |
| Libraries | PyTorch, NumPy, Pandas, Matplotlib |

---

## 📌 How to Run

### Option 1 — Run in Google Colab (Recommended)
1. Open the notebook in Colab  
2. Mount Google Drive  
3. Install required libraries  
4. Run all cells sequentially  
5. Check training metrics and predictions  

### Option 2 — Download and Run Locally
1. Click the notebook link  
2. Go to **File → Download → Download .ipynb**  
3. Open in Jupyter Notebook / VS Code  
4. Install dependencies and run all cells  

> **Note:** If GitHub does not render the notebook correctly, always download the **Raw .ipynb file** and open it locally.

---

## 📊 Results

- **Accuracy:** 83% on 4-class growth stage classification  
- **Temporal modeling:** LSTM outperformed transformer-based approaches  
- **Robustness:** Missing image generation improved multimodal consistency  

---

## 📬 Contact

If you have questions or want to collaborate:

- **Email:** arkadiptasaha04@gmail.com  
- **GitHub:** https://github.com/ArkadiptaSaha  

Contributions are welcome!

---

