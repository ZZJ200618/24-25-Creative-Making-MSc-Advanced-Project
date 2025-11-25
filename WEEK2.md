# Common Vision Bias  
**An Interactive Installation Using TouchDesigner + Muse EEG for Gendered Emotional Analysis**

Common Vision Bias explores how people of different genders produce distinct physiological and emotional reactions when watching the same set of socially charged images. The installation uses **Muse (EEG + HR)** as the primary biometric device, converting real-time emotional responses into audiovisual output in TouchDesigner.

This project reveals that “watching” is not neutral—our gaze is shaped by gender, memory, social bias, and cultural experiences.

---

##  Week 2 Progress Summary

This week’s work focused on **selecting the emotional sensing instrument**, **designing the two-zone installation layout**, and **analyzing gendered representation through the Bechdel Test**.

---

## 1. Emotion Sensor Evaluation — Choosing Muse

After comparing multiple devices (Polar H10, PPG sensors, smartwatches), I decided to adopt **Muse (Muse 2 / Muse S)** as the main emotional sensing device.

### ✔ Why Muse?

| Feature | Benefit to Project |
|--------|--------------------|
| **EEG (Alpha/Beta/Theta)** | Detects subtle emotional differences beyond heart rate, including tension, cognitive conflict, empathy, suppression |
| **Heart Rate (PPG)** | Provides stable arousal data for audiovisual mapping |
| **Breath + Micro-movements** | Helps interpret calmness, anxiety, and viewer tension |
| **OSC Compatibility** | Easily sends data to TouchDesigner for real-time visuals |
| **Gendered watching analysis** | EEG reveals subconscious reactions that heart rate alone cannot show |

Muse grants access to emotional layers essential to themes like **surveillance gaze, beauty discipline, gender stereotypes, and transgender representation**.



## 3. Bechdel Test Reflection (Week 2 Insight)

During research this week, the **Bechdel Test** resurfaced as a critical lens for selecting visual stimuli.
## **What is the Bechdel Test?**
The Bechdel Test is a simple but influential metric used to evaluate gender representation in films, literature, and visual media. A work passes the test only if it includes:

1. **At least two named female characters**,  
2. **Who talk to each other**,  
3. **About something other than a man**.

Although minimal, this test exposes how frequently women in media lack depth, agency, or narrative autonomy.

---

### **What Social Biases Does the Test Reveal?**

Despite its simplicity, the Bechdel Test highlights several structural gender biases:

- **Women as supporting tools**, not narrative subjects  
  → Female characters often exist only to assist male arcs or emotional growth.

- **Reduction of women to relationships with men**  
  → Women rarely have their own motivations, goals, or internal worlds.

- **Male-centered storytelling as default**  
  → Media frequently assumes male experience as universal and female experience as secondary.

- **Emotional labor expected from female characters**  
  → Women often appear as caregivers, love interests, sacrifices, or “initiators” for a male plot, not as full agents.

- **Invisible diversity**  
  → Women of color, queer women, and trans women are even less represented, revealing intersecting biases.

These patterns align with broader social norms where women are expected to be:
- objects of the gaze (the “male gaze”),  
- passive recipients of power,  
- symbols rather than subjects.

---

## 5. System Workflow (Muse → TouchDesigner)

```mermaid
flowchart LR
    A[Participant watches imagery] --> B[Muse EEG + HR]
    B --> C[OSC / BLE Stream]
    C --> D[TouchDesigner Processing]
    D --> E{Visual Output}
    D --> F{Audio Output}
    E --> G[Projection Zone]
    F --> G
