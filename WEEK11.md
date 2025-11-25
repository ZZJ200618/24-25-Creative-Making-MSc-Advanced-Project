## Week 11 — System Architecture Design

### Goals for This Week
- Draw and finalize the complete system architecture connecting  
  **Unity (Narrative Logic) → Muse EEG → OSC → TouchDesigner (Visual/Audio Output)**  
- Plan the entire data flow for beta-wave processing  
- Define how beta values influence visuals and audio  
- Finalize the visual style direction: collage, fragmentation, cellular noise, monochrome structure
![0baa4845e62a97ef8651cc23f63527b9](https://git.arts.ac.uk/user-attachments/assets/12afe211-3d22-4c33-a8e6-877093b4cd38)


---

### 1. System Architecture (Completed)

This week centered on formalizing the full technical structure linking the narrative engine, biosignal input, and audiovisual rendering system.

**Final System Structure:**

- **Unity** controls narrative progression, task triggers, ability unlocks, and branching logic.
- **Muse EEG** provides real-time beta-band data as a *passive observation* of attention/arousal.
- **OSC** streams raw data from Muse to TouchDesigner.
- **TouchDesigner** transforms the beta stream into dynamic visual and audio feedback.

---

### 2. Data Flow Planning (Beta-Wave Processing)

The beta-wave data pipeline was fully defined this week.  
The goal: convert raw EEG into both continuous and discrete mapping signals.

#### **(1) Raw Input**
- Source: `/muse/elements/beta_absolute`
- Captured via:  
  `oscin → select`
  ![0a091a69548dff526d1f98997aca51e4](https://git.arts.ac.uk/user-attachments/assets/29d7a4a2-a6cc-4922-9f49-9bf1fd610854)



#### **(2) Normalization (0–0.9)**
- Processing chain: `filter → math (fit)`
- Output: `beta_norm` ∈ **0.00–0.90**
- ![b758f12e1c432789784a3daeb465ebe3](https://git.arts.ac.uk/user-attachments/assets/e8b5dd54-56bf-45f6-845d-622d851a9e95)
- Used for continuous changes:
  - noise translation  
  - noise speed  
  - audio intensity  


#### **(3) Segmentation into Five Levels (0–4)**  
Used for discrete color states and event-driven feedback.

0 = Low Active (Blue)
1 = Slightly Sub-active (Purple)
2 = Normal (Gray)
3 = Active (Orange)
4 = Hyper Active (Red)


**Expression implemented:**
```python
if(val < 0.18, 0,
    if(val < 0.36, 1,
        if(val < 0.54, 2,
            if(val < 0.72, 3, 4))))

---


