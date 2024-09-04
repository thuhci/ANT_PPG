# ANT_PPG
Open-Source PPG Dataset for Identity Authentication

## 📖Dataset Description
The former datasets primarily feature single-channel green light PPG signals and are collected from fingertip sensors. To address the limitations of these open-source datasets, such as their absence of activity labels, low sampling rates, and only single-channel PPG signals, we collected the ANT_PPG dataset approved by the Institutional Review Board (IRB) of Tsinghua University. This dataset includes three-channel(i.e., red, green, and infrared) PPG signals from 28 subjects engaged in 10 various activities(e.g., sitting still, standing still, and exercise) and was collected using two types of sensors.

The PPG data collection experiment is conducted by the ANT TIANJI Lab at a secure facility located on Beijing. This experiment will utilize PPG collection devices, such as the MAXREFDES280 smartwatch and GH3X2X\_EVK\_ALL chip, to collect PPG data under various physical conditions (sitting still, finger movements, hand movement while drinking water, standing still, standing with fist clenching, walking with arm swinging, and jumping). The collected PPG data is intended for evaluating and testing PPG-related algorithms.

## ⚙️Experiment Procedure
![image](https://github.com/user-attachments/assets/0a2a6f41-22c1-480c-9e7c-13b26b43a1b0)

## 🔍Dataset Samples
![image](https://github.com/user-attachments/assets/98ad4eb6-1e5c-45af-a932-2d5fad5db349)


## 🖥️Code to load Dataset
```
import numpy as np
import matplotlib.pyplot as plt
import os

# load PPG and label from .npy file
ppg_npy_path = '../data/ANT_Maxim_6sec_QI_500_posi_pairs.npy'
ppg = np.load(ppg_npy_path)
print(ppg.shape)
ppg = ppg[:9]
plt.figure(figsize=(40, 9))
for i in range(9):
    plt.subplot(3, 3, i + 1)  # Create a 3x3 grid of subplots
    for j in range(3):
        plt.plot(ppg[i, 0, j], label='PPG1-Channel ' + str(j))
        plt.plot(ppg[i, 1, j], label='PPG2-Channel ' + str(j))
    plt.legend(loc='upper right')
plt.tight_layout()
plt.savefig('../fig/ppg_pairs.png') 
```

## 🗝️ Dataset Download
The test dataset including 2000 PPG pairs with identity labels is open for benchmarking PPG Authentication algorithms. ([Download Link](https://pan.baidu.com/s/1RU1Go6AcO3UmfL5L2xfOEQ?pwd=xe3d))

The whole training dataset is accessible by application. (Please see [Data Release Agreement](https://github.com/thuhci/ANT_PPG/blob/main/ANT_PPG_Release_Agreement.pdf))

## 📄 Citation
Citation is coming soon.
