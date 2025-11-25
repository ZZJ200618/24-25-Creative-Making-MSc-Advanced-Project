## Week 15 — Muse EEG Input Testing (OSC Integration)

### Overview
This week focused on establishing a stable real-time data pipeline from the **Muse EEG headband → OSC → TouchDesigner**, and testing the responsiveness and stability of the beta-wave signal. Initial visual tests were also conducted to verify the mapping pipeline.

---

## 1. Establishing the Muse → OSC → TouchDesigner Realtime Stream

The first step was configuring the Muse EEG headset using **MuseLab** / **Muse Monitor** to broadcast EEG data as OSC messages.  
The output was streamed to the local machine using:

- **IP:** `127.0.0.1`
- **Port:** `5000`
- **Channel:** `/muse/elements/beta_absolute`

This provided four channels (TP9, AF7, AF8, TP10), updated at ~10–20 Hz depending on signal quality.



---

## 2. TouchDesigner Node Chain (Completed)

The following TD node chain was created and tested:


### **Node Functions Explained**

#### **1) `oscin`**
- Receives raw numeric data from Muse EEG  
- Subscribed to `/muse/elements/beta_absolute`

#### **2) `select`**
- Reduces incoming data to the desired channel  
- Typically: average of AF7 & AF8 for frontal beta  
- Created a single clean channel: `beta_raw`

#### **3) `filter`**
- Smooths noise, removes micro-spikes
- Parameters tested:  
  - Filter Width: **8–12 samples**  
  - Cut off sudden jumps produced by facial movement and minor artifacts

#### **4) `math (fit)`**
- Normalizes the beta values to **0–0.9**
- Output channel: `beta_norm`
- Used for continuous mapping (noise translation, intensity)

#### **5) `expression`**
- Converts normalized values into discrete segments:

0 = Low Active
1 = Sub-active
2 = Normal
3 = Active
4 = Hyper Active


- Output channel: `beta_level`

This will later be connected to the color-state logic (blue → purple → gray → orange → red).

---

## 3. Beta-Wave Stability Testing

A stability test was conducted under three conditions to understand the nature of the Muse beta signal:

### **(1) Sitting still, eyes open**
- Signal relatively low but stable  
- Fluctuates mainly between **0–1** (blue/purple)

### **(2) Light movement / walking in place**
- Beta values rise modestly  
- Fluctuates between **1–2** (purple/gray)

### **(3) Blinking / small facial motions**
- Causes short spikes due to EMG interference  
- Values can temporarily jump to **3–4**  
- Filter CHOP successfully suppresses most spikes

These tests confirmed that the normalized 0–0.9 range and 5-segment classification are valid.

---

## 4. First Visual Tests in TouchDesigner

To verify the full pipeline, a basic visualization prototype was created:
![e5da4bb325ad8451a4611f10fae8af6e](![f65ebff2917393786f6ec7f4ca9ad8b6](https://git.arts.ac.uk/user-attachments/assets/7b26934a-a762-4279-8f9c-c7cd588819a6)
https://git.arts.ac.uk/user-attachments/assets/7050554e-a7ce-4f88-adf0-074594635d45)
![d15b7eb8d6ee92b52c09b05fbbc16a53](https://git.arts.ac.uk/user-attachments/assets/3bf91240-683f-40d1-9ca6-7a2c4576cde2)
![aba2f5b691f3d59c1ae8807fce5ff263](https://git.arts.ac.uk/user-attachments/assets/c35c8585-6df3-4a7b-98c3-8a563c354f82)




### **Color-Block Test**
- A simple rectangle whose color changes based on `beta_level`
- Color mapping:

| Level | Color | Meaning |
|-------|--------|---------|
| 0 | Blue | low attention |
| 1 | Purple | slight activation |
| 2 | Gray | normal focus |
| 3 | Orange | increased arousal |
| 4 | Red | high alert / conflict |

### **Key Findings**
- Color changes responded instantly (under 0.1s latency)
- Blinking or micro-movements instantly produced orange/red flashes
- During calm focus, transitions stayed in blue/purple
- Confirms the system is ready for integration with noise-based visuals next week

---

