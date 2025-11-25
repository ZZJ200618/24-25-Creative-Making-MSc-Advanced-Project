## Week 3 Progress Overview

This week focused on two major directions:

1. **Designing the spatial layout for the installation** (based on Muse EEG + HR/SC data)  
2. **Conducting a literature-grounded analysis** of:
   - gender representation bias (Bechdel Test & extensions)
   - emotional physiology in media viewing (HRV, EEG)
   - feminist biofeedback art methodologies

These studies provide the theoretical backbone for the upcoming visual stimuli design and mapping logic in TouchDesigner.

---

## 1. Scene & Spatial Design (Updated for Week 3)

Based on the advisor’s feedback and supported by literature on media-induced emotion and psychophysiology, the installation now adopts a **two-zone structure**:

### **🔹 Zone A — Exposure / Viewing Zone (Stimulus Input)**
<img width="1920" alt="front" src="https://git.arts.ac.uk/user-attachments/assets/672a7be5-99a1-4e47-8791-b3b53205659a" />



Participants watch curated social video related to:
- gender stereotypes  
- surveillance gaze  
- body discipline  
- transgender representation  
- Bechdel Test–failing scenes  

**Justification from literature:**
- Psychophysiology research shows external sound/light alters HRV/EDA during media exposure, reducing validity
- HRV synchrony studies show that emotional arousal is highly sensitive to environmental
---

### **🔹 Zone B — Data Processing & TouchDesigner Mapping**
<img width="1920" alt="show" src="https://git.arts.ac.uk/user-attachments/assets/8e3a8307-38ae-4cac-b624-7b45831bdd76" />


Muse streams:
- EEG (Alpha/Beta/Theta)
- HR (PPG)
- Skin Conductance
- Breath Rate  

into TouchDesigner → converted into:
- particle systems  
- distortion fields  
- color gradients  
- glitch/ambient audio  

**Literature support:**
- EEG → audiovisual transformation creates intuitive “mirroring” of mental state
- Biofeedback art benefits from immediate, transparent mapping back to the participant  

---


## 2. Literature Review — Bechdel Test & Gender Bias
![edd6af393fb017ea26e5c93626698e1f](https://git.arts.ac.uk/user-attachments/assets/dd15643b-543d-43f8-b05b-c71efc37193e)
![448517b54a4fcdc4351597db65ce5a80](https://git.arts.ac.uk/user-attachments/assets/8b597bf0-374a-4678-9280-ee3fe4ab772b)

### **What the Bechdel Test Reveals**
Across media, the Bechdel Test exposes:
- Women’s lack of narrative agency  
- Dialogue economies dominated by men  
- Structural absence of female subjectivity  
- Women used chiefly as emotional/plot tools  

This aligns with broader research showing that gender inequality is:
- **subconscious**
- structured through **behavioural scripts**
- embedded in everyday social interaction

### **Advanced interpretations of the Bechdel Test**
Recent scholarship reframes the test as:
- a **network analysis of character relations** 
- a measure of **whose emotional world matters**
- a structural tool revealing **gendered power networks**  

This supports my installation’s core concept:
> “Watching is not neutral — it is structured by gendered histories of who is allowed to speak, feel, or be centered.”

---

## 🎞 3. Literature Review — Physiological Responses in Media Viewing

### 3.1 HRV Studies

![f4081db3042a7e8a5518e7ba5d845384](https://git.arts.ac.uk/user-attachments/assets/1ed1c982-289c-4322-b66f-527893a655b9)
![d7f7cd74656ab80bbaccb44b55532056](https://git.arts.ac.uk/user-attachments/assets/3a5dfc1e-1867-40ee-a13b-7fb46f157dae)


HRV synchrony can:
- identify emotionally arousing segments  
- predict viewer engagement  
- reflect group-level emotional coordination 

**Relevance:**
- Gendered HRV patterns may reveal different affective reactions to the same imagery  
- This supports your goal of comparing cross-gender emotional responses

---

### .2 Suspense & Emotional Tension
![068738234bd6ed5cbd4f188ab4f067f5](https://git.arts.ac.uk/user-attachments/assets/399a0753-58ec-4224-ad42-b1d3f1f5dd92)

Research shows:
- suspense increases HR, SCL (arousal)  
- repeated exposure reduces arousal but not necessarily enjoyment  
- emotional habituation can be measured physiologically 

---

### 3.3 EEG-Based Art & Biofeedback
![00dc11414ca4ceb061cc0fe318ea956b](https://git.arts.ac.uk/user-attachments/assets/c8c0a2d9-5b96-42fe-be8e-56e1e1b07cd6)
![dbf535ebbed231bccf07c01f2e06c41f](https://git.arts.ac.uk/user-attachments/assets/f8c6ebc6-eef8-4cf0-a268-bac8eacf7b47)
From Tokunaga (2013) and Gee (2023):
- EEG-based audiovisuals create intuitive awareness of internal state  
- Feminist biofeedback avoids normalizing or ranking emotions  
- Emotion should be represented as **situated, relational, context-dependent**  

---

## 4. How Literature Directly Informs Your Project

| Research Domain | Key Finding | How It Shapes Your Installation |
|----------------|-------------|--------------------------------|
| Bechdel Test & Gender Bias | Media systematically centers male narratives | Image dataset will include Bechdel-failing vs passing scenes for comparison |
| HRV Synchrony | Physiological signals synchronize during shared emotional moments | Enables cross-gender comparison of emotional peaks |
| EEG Sonification | Mapping must be intuitive and real-time | TouchDesigner will use immediate mapping from Muse signals |
| Feminist Biofeedback | Avoid normative comparisons | Data is compared *within* participant + *between* gender groups as social patterns |
| Suspense Studies | Arousal shifts predict emotional impact | Helps build stimuli sequences with clear emotional arcs |

---
