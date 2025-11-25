#  Week8 Development Log  
## Focus: Narrative System Definition + Emotional Feedback Pipeline

---

# 1. Weekly Overview  
This week focused on translating the conceptual framework of *Fractured Script* into a structured development plan. I defined the narrative structure, emotional feedback system, projection workflow, and 3D body-fragment installation strategy. The goal was to establish a production-ready system blueprint integrating narrative design, biometric sensing, and audiovisual generation.

## Inspiration
The Bechdel test is a measure of the representation of women in film and other fiction. The test asks whether a work features at least two women who have a conversation about something other than a man. Some versions of the test also require that those two women have names.

Jackson's Patchwork Girl tells the story through illustrations of parts of a female body stitched together through text and image. The narrative of the story is divided into five segments, titled: "a Graveyard", "a Journal", "a Quilt", "a Story", and "& broken accents." These five sections each use a different structure and are written in a different style.

![WPS图片(1)](https://git.arts.ac.uk/user-attachments/assets/6a68c8f2-2c47-4323-963f-2462d0b23507)


---

# 2. Tasks Completed

## ✔ 2.1 Narrative Framework Extraction  
I formalised the **five-part fragmented-body narrative system**:

- **Chapter 1 – Eyes:** Woman exists only as visual presence  
- **Chapter 2 – Heart:** Emotional labour scripted for the male protagonist  
- **Chapter 3 – Hands:** Women allowed action but denied speech  
- **Chapter 4 – Mouth:** Dead-woman trope triggers male revenge arc  
- **Chapter 5 – Head:** (Implied) Narrative authority denied

Each chapter → mapped to **bias tropes**, **player intervention attempts**, and **emotion triggers** (anxiety, apathy, disgust, etc.).

---

## ✔ 2.2 Emotional Feedback System Formalised  
 I documented the 5-emotion system:

| Emotion | Color | Visual Form | Data Triggers |
|--------|--------|-------------|----------------|
| Anxiety | Red/Black flicker | inward crushing lines | ↑HR + Muse Beta + GSR spikes |
| Disgust | Acid green / violet | rotational cracks | GSR sharp peaks |
| Apathy | Gray-blue | low contrast blur | HR↓ + α↑ |
| Excitement | Yellow-orange | bursting particles | HR↑ + β↑ |
| Despair | Deep purple | sinking cracks | HR↓ + GSR↑ |

→ All mapped directly to TouchDesigner parameters (feedback loops, crack displacement, color ramps).

---

## ✔ 2.3 Installation Pipeline Breakdown  

### **Projection Surface**
- 3D-printed **female anatomical fragments** (eye, mouth, chest, hand, head).  
- Serve as both symbolic surfaces & narrative interfaces.

### **Projection Source**
- TouchDesigner generating abstract imagery (displacement, cellular noise, cracks).

### **Sound Design**
- Glitch synthesis  
- Granular fragmentation → “audio shards” representing emotional rupture

### **Monitoring Devices**
- Muse EEG  
- HR monitor (Polar)  
- GSR device (Shimmer / Grove)

I turned these into a system map: Sensor → TD parameter → Projection → Sculpture.

---

## ✔ 2.4 Interaction Logic Defined  

- User attempts to **repair** or **rewrite** the script  
- System **denies input** (override text, delete subtitles, freeze emotional responses)  
- Interactivity exposes the **illusion of agency**



