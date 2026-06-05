# Digital Voice Filtering in the Presence of Additive Noise 🎙️📉

This repository contains the implementation of a digital signal processing system designed to improve voice signals contaminated with additive noise. It was developed as a final project for the Digital Signal Processing course at the Faculty of Engineering, UNAM.

The project addresses the recovery of speech intelligibility in noisy environments by designing and applying digital filters, evaluating mathematical performance through error metrics before and after filtering.

## 📋 Project Description

The system takes an original voice recording and introduces two types of noise files:
* **Gaussian White Noise:** Distributed across the spectrum.
* **60 Hz Tone:** Simulating electromagnetic interference.

From these files, two noisy signal scenarios are generated:
* **Case A (Moderate Noise):** Signal-to-Noise Ratio (SNR) of 10.0 dB.
* **Case B (Severe Noise):** Signal-to-Noise Ratio (SNR) of 0.0 dB.

## ⚙️ How It Works

The complete processing pipeline consists of the following steps:

1. **Initialization and Loading:** The audio signals are loaded and automatically resampled to a target frequency of 16000 Hz.
2. **Low-pass FIR Filter:** Designed and applied to attenuate the white noise. It utilizes a Hamming window with a cutoff frequency of 3400.0 Hz.
3. **IIR Notch Filter:** Designed by hand to eliminate the 60.0 Hz tone, utilizing a quality factor of Q = 30.0. 
4. **Metrics Analysis:** The system calculates error metrics, specifically Mean Squared Error (MSE) and SNR, before and after the filtering process.

## 🛠️ Technologies and Libraries

The project is developed in a Jupyter Notebook named `Colab_PDS_E6_PHA_SMA.ipynb` using Python libraries such as:
* `numpy`
* `scipy` (`scipy.signal`, `scipy.io.wavfile`)
* `matplotlib.pyplot`
* `IPython.display`

## 🚀 Steps to Reproduce

To test this code, please follow these steps:

### Option 1: Google Colab
1. Upload the `Colab_PDS_E6_PHA_SMA.ipynb` file to Google Colab.
2. Run the initial configuration cells. 
3. When prompted, upload the three required audio files: `voz_original.wav`, `ruido_blanco.wav`, and `ruido.wav`.
4. Execute the remaining cells to listen to the original and filtered audio files and view the time and frequency analysis graphs.

### Option 2: Local Environment
1. Clone this repository to your local machine.
2. Ensure the audio files (`voz_original.wav`, `ruido_blanco.wav`, `ruido.wav`) are in the same current directory as the notebook.
3. Install the required dependencies (`numpy`, `scipy`, `matplotlib`, `ipython`).
4. Run the notebook using Jupyter.

## 👨‍💻 Authors
* **Pozos Hernández Angel**
* **Silverio Martínez Andrés**
* *Facultad de Ingeniería, UNAM*
