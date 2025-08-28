# ISAC-Based UAV Parameter Estimation Using 5G NR Waveforms
SamsungEnnovateX Hackathon 2025

## Team Details
**Team Name:**
 TargetLock
**Members:**
- Sameer Gautam (24bcs10920)  
- Yash Sachan (24bcs11126)  
- Nishita Kumari (24bcs12125)  
- Priyanshu Choudhary (23bcs12648)

## Abstract
This project implements an Integrated Sensing and Communication (ISAC) framework to estimate UAV parameters—range, radial velocity, and direction of arrival (DoA)—using 5G NR OFDM waveforms at 28 GHz (mmWave). We synthesize realistic transmit/receive signals in MATLAB, propagate them through a 3GPP TR 38.901 channel (UMa LoS), and perform Range–Doppler processing and spatial spectrum analysis for DoA. We also generate a labeled dataset and features suitable for downstream machine-learning models. Artifacts include MATLAB simulation code, `.mat` datasets, and a Python-ready export for training in Google Colab.

## Introduction
Traditional radar and communication subsystems compete for spectrum and hardware resources. ISAC co-designs sensing and communication, enabling efficient spectrum reuse. This project demonstrates ISAC for UAV tracking in simulation using 5G NR-like OFDM signals, realistic channel effects, and array processing, and prepares data for ML-based estimators.

## Project Overview
**Problem Statement:**  
- Separate radar/communication systems increase complexity and spectrum usage.  
- UAV safety and airspace management require accurate, near-real-time estimation of range, velocity, and DoA in challenging channels.

**Proposed Solution:**  
- Generate 5G NR style OFDM at 28 GHz with QPSK, pilots, cyclic prefix.  
- Propagate through a 3GPP TR 38.901 UMa LoS channel with path loss, delay, and Doppler.  
- Use multi-antenna reception and spatial processing for DoA.  
- Build a synthetic dataset across diverse UAV kinematics for ML training.

## Technologies Used
- **Language/Tools:** MATLAB (primary), Google Colab (Python for ML)  
- **Key MATLAB Functions/Toolboxes:** IFFT/FFT, `pskmod`, `pwelch`, array steering and correlation; optional `rcosdesign` for pulse shaping  
- **Data Artifacts:** `isac_uav_dataset.mat`, `isac_python_data.mat` (Python-ready)

**Feature Extraction (per scenario):**  
  - Range features: cross-correlation peak/value and lag  
  - Velocity features: Doppler spectrum (FFT of correlation) and peak index  
  - Spatial features: sample covariance terms across Rx channels  
  - Power/phase summaries across channels  
  - Range: 100–1000 m  
  - Velocity: −50 to +50 m/s  
  - Azimuth: −60° to +60°  
  - SNR: 20 dB AWGN

**Feature Extraction (per scenario):**  
  - Range features: cross-correlation peak/value and lag  
  - Velocity features: Doppler spectrum (FFT of correlation) and peak index  
  - Spatial features: sample covariance terms across Rx channels  
  - Power/phase summaries across channels
**Labels:**
 `[range, velocity, azimuth]
<img width="1600" height="1009" alt="image" src="https://github.com/user-attachments/assets/13cf8af8-6d9c-4f6a-82fd-6d629d805a5d" />
**Visual Layout**
The frontend is a single, centered web page with a clean, modern design. It uses a soft gray background (#f3f4f6) and a white, rounded card in the middle that contains all the content. The card has a subtle shadow and a hover effect that makes it pop slightly.

Here's a breakdown of the key elements you will see:

Header: A large, bold heading that says "ISAC Parameter Prediction 📡" with a radar dish emoji. Below it is a smaller subtitle explaining the purpose of the app.

Input Form: A simple form with a text input field. The label above the field prompts you to enter 10 numbers separated by commas. The input field itself has a placeholder with an example format.

Prediction Button: A large, indigo-colored button with rounded corners and a slight shadow. The button's text says "Get Prediction."

Results Area: Initially hidden, this section appears after a successful prediction. It contains a "Prediction Results" heading and a gray, rounded container. Inside, it displays the predicted values for Range, Velocity, and Azimuth in a monospaced font to make them stand out.

Message Box: An alert box, also initially hidden, that appears to show either an error message (in red) or a success message (in green) depending on the outcome of the prediction request.

The overall design is fully responsive, meaning it will look good and be easy to use on both mobile phones and desktop computers.


