# Evaluating Monolingual and Multilingual Training in English-Hindi Speech Emotion Recognition Using MFCC-Based Recurrent Neural Networks

[![Conference](https://img.shields.io/badge/Proceedings-CMT%202026-blue.svg)](https://github.com/farhanwajid/mfcc-bilingual-ser-bilstm)
[![Framework](https://img.shields.io/badge/PyTorch%20%2F%20TensorFlow-yellow.svg)](#)
[![Status](https://img.shields.io/badge/Status-In%20Proceedings-brightgreen.svg)](#)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

Official implementation and evaluation benchmark for the paper **"Evaluating Monolingual and Multilingual Training in English-Hindi Speech Emotion Recognition Using MFCC-Based Recurrent Neural Networks"**, appearing in the *Proceedings of CMT 2026*.

---

## 📌 Abstract

Speech Emotion Recognition (SER) is a vital component for enhancing human-computer interaction (HCI). While classical and lightweight models often struggle to generalize across diverse linguistic domains, Mel-Frequency Cepstral Coefficients (MFCCs) coupled with recurrent sequence architectures remain standard low-compute acoustic baselines.

This study presents a controlled bilingual evaluation of monolingual (`EN -> EN`, `HI -> HI`) and multilingual pooling (`EN + HI -> EN / HI`) protocols across English (**RAVDESS**) and Hindi (**IESC**) datasets mapped to a unified 5-class space: *Angry, Sad, Happy, Fear, and Neutral*.

### Key Contributions & Findings:
- **Bidirectional Advantage:** The Bidirectional LSTM (Bi-LSTM) consistently outperforms unidirectional LSTM across both monolingual and multilingual protocols by capturing forward and backward temporal acoustic dynamics.
- **Robustness via Multilingual Pooling:** Training on bilingual pooled data (`EN + HI`) reduces performance variance across cross-validation folds and stabilizes class separation.
- **Experimental Rigor:** Evaluated with stratified 5-fold cross-validation and SMOTE feature-space balancing to prevent data leakage and mitigate class skew.

---

## 📊 Benchmark Results

### 1. Monolingual Benchmarks
| Dataset | Model | Test Accuracy | Macro F1 |
| :--- | :--- | :---: | :---: |
| **RAVDESS (English)** | MFCC + LSTM | 79.00% | 0.79 |
| **RAVDESS (English)** | MFCC + Bi-LSTM | **80.00%** | **0.80** |
| **IESC (Hindi)** | MFCC + LSTM | 90.00% | 0.90 |
| **IESC (Hindi)** | MFCC + Bi-LSTM | **91.00%** | **0.91** |

### 2. Multilingual Training Protocol (`Train: English + Hindi`)
| Evaluation Language | Model | Test Accuracy (Mean ± Std) | Macro F1 |
| :--- | :--- | :---: | :---: |
| **English** | MFCC + LSTM | 79.92% ± 0.0293 | 0.7861 |
| **English** | MFCC + Bi-LSTM | **84.72% ± 0.0266** | **0.8400** |
| **Hindi** | MFCC + LSTM | 80.63% ± 0.0579 | 0.8054 |
| **Hindi** | MFCC + Bi-LSTM | 78.42% ± 0.0859 | 0.7832 |
