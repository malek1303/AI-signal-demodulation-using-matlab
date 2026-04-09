# Universal Neural Demodulator
### ECE342: Communication Systems & Signal Processing Final Project

This project implements a comprehensive communication system in MATLAB, comparing traditional signal processing techniques with a modern **1D-Convolutional Neural Network (CNN)** approach. The system is capable of modulating and demodulating six different schemes within a single unified framework.

##  Project Overview
The goal of this project was to design an AI model that acts as a "Universal Demodulator." Unlike traditional hardware-defined or software-defined radios that require specific algorithms for each modulation type, this system uses a single Neural Network to extract the original message signal from any noisy modulated carrier.

##  Modulation Schemes
The system supports the following techniques:
* **Amplitude Modulation (AM)**
* **Double Sideband Suppressed Carrier (DSB-SC)**
* **Single Sideband (SSB)**
* **Vestigial Sideband (VSB)**
* **Frequency Modulation (FM)**
* **Phase Modulation (PM)**

##  AI & Deep Learning Implementation
A **1D-CNN** was trained on a generated dataset of 3,000 samples. Each sample contains a randomized message frequency, modulation type, and SNR level (0dB to 30dB).

### Architecture:
* **Input Layer:** 1D Sequence input (Signal length: 501).
* **Convolutional Blocks:** Feature extraction layers to identify carrier patterns.
* **ReLU Activation:** Provides non-linearity for complex demodulation (FM/PM).
* **Fully Connected Regression:** Maps learned features back to the baseband message wave.

##  Performance Results
The AI model demonstrates significant superiority, particularly in non-linear modulation schemes.

| Modulation Type | Avg. Improvement (%) | Accuracy Gain (Factor) |
| :--- | :--- | :--- |
| **AM** | 83.67% | 26.76x |
| **DSB-SC** | 33.31% | 1.51x |
| **SSB** | 81.39% | 15.53x |
| **VSB** | 66.04% | 3.01x |
| **FM** | 95.05% | 171.10x |
| **PM** | 93.86% | 26.40x |

### Key Findings:
* **FM Superiority:** The AI achieved its highest gain in FM, outperforming conventional frequency extraction by a factor of 171x.
* **Generalization:** The model successfully learned to demodulate 6 different formats using the same weights, proving "Universal" capability.
* **Noise Suppression:** The CNN effectively learned to act as a dynamic, non-linear filter, outperforming static Butterworth implementations.

##  Installation & Usage
1.  Open MATLAB (Tested on R2024b ).
2.  Ensure **Deep Learning Toolbox** and **Signal Processing Toolbox** are installed.
3.  Open `ECE342_final_proj_modulation_techniques.mlx`.
4.  Run the sections sequentially to generate data, train the model, and view the performance audit.

---
**Author:** Malek  
**Academic Role:** Electronics and Communications Engineering Student  
**Leadership:** Head of Embedded Systems Committee, IEEE Student Branch