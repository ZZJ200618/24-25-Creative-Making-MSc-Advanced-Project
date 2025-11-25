## Week 10 — Pre-Production Research Summary
Before starting full production, this week was dedicated to consolidating all early-stage research: thematic study, narrative analysis, feminist theory references, technical feasibility studies (Unity, EEG, TouchDesigner), and the conceptual foundations that will drive the game.
| Research Area | Key Findings | Implications for Game Design |
|---------------|--------------|-------------------------------|
| **Feminist Narrative Research** | Female characters in RPGs are often voiceless, supportive, sacrificial, or mechanically weakened. | Gameplay must embody structural disempowerment: limited actions, forced tasks, loss of agency. |
| **Biased Narrative Structures** | Identified 5 core biases: functional weakening, emotional labor, instrumental sacrifice, visual gendering, loss of narrative agency. | These become the backbone of Choice / Evaluation / Judgment tasks that expose structural bias. |
| **Reference Work: *Patchwork Girl*** | Fragmented body, collage aesthetics, nonlinear structure, “female body as text.” | Visual identity uses collage, torn paper, cellular noise, fragmented UI, symbolic reconstruction. |
| **EEG (Beta-wave) Research** | Beta = attention, cognitive conflict; stable for passive observation; broader waves too noisy. | EEG used only as *observation*, not gameplay input. Beta mapped to color + noise intensity. |
| **TouchDesigner Research** | Cellular noise, LUT color shifts, displacement maps most suitable for real-time emotional visualization. | EEG controls abstract audiovisual states (fragmentation, noise movement, suppression/release). |
| **Technical Stack Feasibility** | Unity + Muse EEG + OSC + TouchDesigner is stable, low-latency, well-documented. | Final system architecture confirmed; data pipeline is reliable for narrative-linked visualization. |
| **Initial Narrative Framework** | Story arc: Birth → Forced tasks → Exclusion → Fruit stage → Crossroads → Monsters → Skills → Bird → False endings → Naming. | Narrative designed to gradually shift from disempowerment → perception → rejection → self-definition. |
| **Early Challenges** | Translating theory into mechanics, visual consistency, avoiding unfairness, balancing EEG noise, preserving ambiguity. | Solutions include perception-based skills, monochrome suppression, limited agency, and symbolic puzzles. |

This document summarizes the major findings and decisions from the pre-production research phase.

---

## 1. Feminist Narrative Research

### Key questions guiding the research:
- How are women traditionally positioned in RPG narratives?
- What forms of structural bias do female characters face?
- How can gameplay embody systemic constraint instead of merely describing it?

### Findings:
- Women are often **support roles, emotional laborers, or sacrifices**.
- They are frequently **voiceless**, denied subjectivity, framed as tools.
- RPGs reinforce a structure where:
  - Hero = male  
  - Assistant / healer / sacrifice = female  

This informed the idea of:
> A girl who *cannot act*, *cannot attack*, *cannot choose* — not because of mechanics, but because of narrative structure.

---

## 2. Biased Narrative Structures (Disassembled)
![微信图片_20251122132207_981_17](https://git.arts.ac.uk/user-attachments/assets/47e2dd0a-6eef-41d4-afef-e4b7b7534314)

Based on readings from feminist game studies and narrative theory, five common bias structures were identified:

1. **Functional Weakening**  
   The female character is weaker or stripped of mechanics.

2. **Emotional Labor**  
   Expected to heal, comfort, support, not participate.

3. **Instrumental Sacrifice**  
   Girl’s injury/death advances the *hero’s* story.

4. **Visual Gendering**  
   Female characters designed as objects, not agents.

5. **Loss of Narrative Agency**  
   Story continues regardless of her decisions.

These became the backbone of the game’s **Choice / Evaluation / Judgment** task categories.

---

## 3. Reference Work: *Patchwork Girl*
![image](https://git.arts.ac.uk/user-attachments/assets/39c973b0-414f-48ef-954c-3ddde1429bfa)


Shelley Jackson’s *Patchwork Girl* influenced:
- Fragmented body aesthetics  
- Non-linear narrative stitching  
- “Female body as text”  
- Disassembled identity  

This directly shaped:
- Collage-based visual design  
- Fragmented UI  
- Cellular noise and torn-paper shapes  
- The idea of *becoming whole* only after rejecting the narrative

---

## 4. EEG Research (Beta-Wave Focus)
![b758f12e1c432789784a3daeb465ebe3](https://git.arts.ac.uk/user-attachments/assets/f27fdc5a-1c52-40b1-b916-f808f2d488a0)

### Why Beta Waves?
- Beta (13–30Hz) reflects:
  - attention
  - cognitive processing
  - conflict
- Practical: easiest to observe reliably with Muse sensor.

### Data handling:
- Normalize to 0–0.9
- Segment into five states (0–4)
- Use only as **passive observation**, not gameplay control

The conclusion:
> EEG should *reflect* the narrative experience, not influence it.

---

## 5. TouchDesigner Visual Research
![0baa4845e62a97ef8651cc23f63527b9](https://git.arts.ac.uk/user-attachments/assets/9e4e82eb-831d-48eb-a348-a12a78feb7d5)

Research explored:
- Cellular noise  
- Displacement mapping  
- Signal-driven color LUT  
- Fragmentation as metaphor  

Goals:
- Visualize internal emotional states  
- Reflect beta-wave spikes in color and noise  
- Maintain monochrome suppression until awakening arc

---

## 6. Technical Feasibility Research (Unity + TD + EEG)

### Unity
- Supports narrative scripting  
- Easy scene transitions  
- Suits linear + symbolic design

### Muse EEG → OSC
- Stable  
- Low latency  
- Good for observing cognitive shifts

### TouchDesigner
- Best tool for real-time visual metaphor  
- Strong noise system  
- Excellent for EEG-driven color states

Conclusion:
> The system architecture (Unity → Muse → OSC → TouchDesigner) is feasible and robust.

---

## 7. Narrative Framework (Early Draft)

From research, the narrative arc was conceptualized as:

1. **Birth & No Name**  
2. **Task assignment without choice**  
3. **Being excluded from the "main story"**  
4. **Forced dangerous tasks (fruit collection)**  
5. **Crossroads split (false choice)**  
6. **Small monster → loss → big monster trap**  
7. **Return in confusion**  
8. **Awakening of abilities (Mind / Eye / Mouth / Heart)**  
9. **Bird confrontation (verbal bias embodiment)**  
10. **False endings**  
11. **Refusal → True ending → Naming**

The story embodies research conclusions about structural bias.

---

## 8. Challenges Encountered in Early Research

### 1) Translating feminist theory into mechanics  
Difficult to avoid preachy or literal representation.  
Solution: embed structure into restrictions, not dialogue.

### 2) Deciding how much agency the player should have  
Too little = frustration  
Too much = breaks theme  
Solution: give “internal agency” (Mind/Eye) before “external capability”.

### 3) Balancing beta-wave interpretation  
EEG spikes must be meaningful, not random noise.  
Solution: heavy filtering + focusing on high-level states only.

### 4) Ensuring aesthetic cohesion  
Collage + noise + monochrome + narrative fragmentation  
Solution: created a unified moodboard combining all references.

### 5) Avoiding the trap of “female suffering as spectacle”  
Solution: ensure the *player* experiences structural constraint, not just the character.

---

## 9. Summary of Pre-Production Conclusions

- **The game’s theme is solid**: structural bias embodied through mechanics.  
- **The tech stack is validated**: Unity + Muse + TouchDesigner is feasible.  
- **The visual language is coherent**: collage, noise, fragmentation.  
- **The narrative arc is supported by research**: from constraint → awareness → self-naming.  
- **The EEG usage adds data-driven emotional mapping**,

