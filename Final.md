# SHE — A Game About Structural Bias, Emotional Suppression, and Awakening
### A narrative-driven experimental game exploring how **RPG systems silently reproduce gender bias**, told through constrained mechanics, fragmented visuals, and EEG-mapped emotional states.
<img width="1920" alt="1" src="https://git.arts.ac.uk/user-attachments/assets/6d21a18e-985b-4ddd-a622-83bac0624095" />

---
# 📌 Table of Contents
1. [Why I Created This Work](#1-why-i-created-this-work)  
2. [Technology Used](#2-technology-used)  
3. [Visual Style](#3-visual-style)  
4. [Game Structure & Mechanics](#4-game-structure--mechanics)  
5. [Narrative](#narrative)  
6. [EEG → TouchDesigner Mapping](#5-eeg--touchdesigner-mapping)  
7. [Testing Results](#6-testing)  
8. [Core Contribution](#7-core-contribution-of-the-work)  
9. [Limitations & Future Improvements](#8-limitations--future-improvements)  

# 1. Why I Created This Work

## The Core Question
How do games quietly reproduce gendered power structures—not only through story, but through mechanics?

In many RPGs, female characters are:
- weaker by design  
- emotionally supportive rather than agentic  
- narratively expendable  
- structurally silenced  

I wanted players to **feel**:
- being assigned tasks without choice  
- being excluded from the “main plot”  
- being underpowered  
- being denied speech  

This is not empowerment fantasy.  
It is about **seeing the invisible system** that shapes the character — and the player.

---

# 🛠️ 2. Technology Used

<img src="https://git.arts.ac.uk/user-attachments/assets/eb296a5d-ca23-467b-ac39-4d4eeb4d0e2a" />

| Component | Detailed Purpose |
|----------|------------------|
| **Unity** | Functions as the core game engine responsible for narrative logic, UI flow, scene transitions, input handling, collision systems, and all forced-choice mechanics. Unity manages the progression of emotional abilities (Mind, Eye, Mouth), controls cutscenes and dialogue gating, and ensures the player’s constrained movement and limited agency are structurally embedded into the gameplay. |
| **Muse EEG Headband** | Acts as a passive emotional-sensing device that captures real-time beta-wave activity (13–30 Hz) associated with cognitive tension, attention, emotional conflict, and stress responses. It does **not** influence gameplay; instead, it provides a live biometric mirror that reveals how players physiologically respond to moments of structural bias, forced choices, and narrative pressure. |
| **OSC Protocol** | Serves as the communication bridge for transmitting EEG data from the Muse headband to TouchDesigner. Provides a lightweight, low-latency real-time streaming pipeline capable of sending multi-channel beta-wave values at a stable rate. Ensures synchronized emotional visualization by maintaining consistent timing between in-game events and EEG fluctuations. |
| **TouchDesigner** | Performs real-time emotional visualisation based on incoming EEG data. It maps beta-wave intensity to cellular noise, fragmentation levels, monochrome–color transitions, spatial distortion, and dynamic audio filtering. TouchDesigner effectively externalizes the player’s internal emotional state, turning brainwave activity into a living, reactive visual environment. |


---

# 🎨 3. Visual Style

<img src="https://git.arts.ac.uk/user-attachments/assets/f97f51e9-ea55-42d2-8446-1a0c1b87958e" />

### Influences
- **Patchwork Girl** – collage body, nonlinear identity  
- **Cut-out Puppetry** – fragile, externally-controlled motion  

### Themes
- Fragmentation → Awakening → Integration  
- Monochrome Control → Color Autonomy  
- Noise as Emotional Turbulence  

---

# 🎮 4. Game Structure & Mechanics
![4](https://git.arts.ac.uk/user-attachments/assets/7572d67b-8255-496b-b596-60047fb4b220)

> The story follows a nameless girl who was born in a village where girls are sent to die in the hero’s story.
She is assigned tasks, forbidden to fight, excluded from the plot, and denied agency.

| Stage | Mechanic / What Happens | Player Effect / Emotional Experience |
|-------|--------------------------|--------------------------------------|
| **Fruit Collection (Basic)** | Player can only collect “allowed” fruits; forbidden items trigger denial; no combat allowed. | Produces a sense of obedience, restriction, and early-stage disempowerment. |
| **Fruit Collection (Upgraded)** | Introduces fake fruits, misleading layouts, moving hazards, partial visibility, and misdirection. | Creates confusion, cognitive dissonance, and heightened vulnerability. |
| **Crossroads** | Presents two paths but only allows the left route; the right path is blocked by narrative authority. | Reinforces structural limitation and the illusion of choice. |
| **Small Monster** | Combat encounter where the player cannot win; only defend/heal options exist; attacks are symbolic. | Communicates functional weakening, powerlessness, and systemic disadvantage. |
| **Big Monster Trap** | Hero is captured off-screen while player is excluded from the main conflict; forced retreat. | Demonstrates narrative exclusion and the girl's low priority in the story. |
| **Mind Ability** | Solving a fragmented word puzzle representing cognitive reconstruction and internal clarity. | Initiates cognitive awakening, self-awareness, and recognition of structural patterns. |
| **Eye Ability** | Reveals hidden traps, fake choices, invisible structures, and misleading pathways. | Shifts perception, enabling the player to “see” the system behind the narrative. |
| **Mouth Ability** | Allows the player to verbally reject false choices, commands, or biased narrative structures. | Grants agency through refusal, marking the beginning of narrative resistance. |
| **Four Paths** | Symbolic emotional routes: Thorny, Smooth, Curved, Dark; only the darkest path grants insight. | Encourages self-navigation and emotional confrontation; deepens thematic immersion. |
| **Bird Encounter** | Boss fight using verbal aggression; three waves of non-physical attacks; dodging required. | Produces emotional pressure, tension, and internal conflict, culminating in awakening. |
| **False Endings** | Three decorative endings that resemble closure but are invalid; no progression possible. | Forces confrontation with narrative systems and critiques deceptive “resolution.” |
| **Naming Scene** | The world becomes stable; player names the girl for the first time; final agency moment. | Restores subjectivity, autonomy, and identity through self-definition. |





## Narrative
> he story follows an unnamed girl born into a village where girls are destined to die inside someone else’s legend. At the age of eighteen, she is sent to “assist” the hero in defeating a monster—a ritual framed as destiny, though it functions as a systemic sacrifice. She has no real choice: even when the game presents her with questions, every path is predetermined. Her mother hands her a sealed letter “to be opened only in danger,” though the true danger is the narrative structure itself.
As the girl leaves the village, she quickly discovers that she is not the protagonist of this world. She cannot attack, cannot open treasure chests, cannot choose her direction, and cannot influence the plot. Her only task is to collect fruits for the hero—an activity controlled down to which items are permissible. Through design, she becomes a tool rather than a character.
At the crossroads, choice collapses into obligation. The girl encounters small monsters she cannot defeat and a major fight she is excluded from entirely. Eventually, she realizes that the story is not written for her survival. This realization triggers a slow awakening: she gains the ability to reconstruct words (Mind), perceive hidden structures (Eye), and ultimately speak refusal (Mouth).
In the Bird encounter, verbal attacks replace combat, forcing her emotional resilience rather than physical strength. After rejecting three false narrative endings, the girl breaks the frame of the story itself. The world finally stabilizes, shifting from monochrome to color.
The game ends with the first real act of agency she ever receives:
the player is asked to give her a name.
For the first time, she becomes a subject rather than a narrative instrument.

<img width="1920" alt="23" src="https://git.arts.ac.uk/user-attachments/assets/ccf29aac-5de8-457d-9d2c-eba01f0b25f0" />
<img width="1920" alt="28" src="https://git.arts.ac.uk/user-attachments/assets/47bdab7d-1998-44f0-8bdb-c3f7493c30c2" />
<img width="1920" alt="32" src="https://git.arts.ac.uk/user-attachments/assets/deddb8f5-6906-4222-bae0-be5984e93a08" />
<img width="1920" alt="6" src="https://git.arts.ac.uk/user-attachments/assets/c763041f-8a47-4636-95ea-b84004a715cc" />

![959e6f4feb946f174a27518f1ecd1161](https://git.arts.ac.uk/user-attachments/assets/c6224897-c567-4c7b-9aed-12de424ecfd2)
![8](https://git.arts.ac.uk/user-attachments/assets/f29bc8bd-b160-4aaf-9685-e5a254157d89)
![c6cfe4aa549548f2de68a09796e0ef63](https://git.arts.ac.uk/user-attachments/assets/7e052c09-30a5-4635-ba77-a87828dc6335)
![7](https://git.arts.ac.uk/user-attachments/assets/b89ea5fc-4a41-4444-a09c-34702d4ba458)
![38](https://git.arts.ac.uk/user-attachments/assets/6aed9529-58d8-45e1-b243-570524202d02)
![39](https://git.arts.ac.uk/user-attachments/assets/c5e35f15-c59c-45f4-9c2c-7f243a37f5a8)
<img width="1920" alt="41" src="https://git.arts.ac.uk/user-attachments/assets/849a90a0-03a8-445b-83c2-38ce1b4ad36b" />
<img width="1920" alt="43" src="https://git.arts.ac.uk/user-attachments/assets/0bfb24c0-8d35-4be3-b60f-e68f47d99dde" />





# 🧠 5. EEG → TouchDesigner Mapping

## 5.1 Data Pipeline
### Muse → OSC → TouchDesigner  
`oscin → select → filter → math → expression`
![b758f12e1c432789784a3daeb465ebe3](https://git.arts.ac.uk/user-attachments/assets/71b9b4c8-fb8a-4514-9795-604dd0218a20)

---

| Node | Detailed Function / Role in Pipeline |
|------|--------------------------------------|
| **oscin** | Receives raw OSC data streamed from the Muse EEG headband, specifically the `/muse/elements/beta_absolute` channel. Handles real-time incoming beta-wave values for all four sensors and establishes the foundation of the EEG → TD mapping chain. |
| **select** | Extracts only the relevant channels  that correspond to frontal-lobe beta activity, which is most strongly associated with attention, cognitive load, and mental conflict. Combines/averages them into a single channel `beta_raw` for stable emotional tracking. |
| **filter** | Smooths micro-spikes and short interruptions caused by blinking, jaw tension, head movement, or Muse signal jitter. Uses a moving-average window (8–12 samples) to produce a clean, stable emotional curve without losing temporal responsiveness. |
| **math (fit)** | Normalizes the raw beta amplitude into the consistent range **0.0 → 0.09** so that all players—regardless of individual EEG intensity—conform to the same emotional visual scale. Ensures visual/sound mapping remains consistent across tests. |
| **expression** | Converts the normalized continuous beta values into **five discrete emotional states (0–4)** used by the color, noise, and audio systems. This step enables symbolic interpretation (blue → purple → gray → orange → red) for final emotional visualization. |
---

### Color Mapping
![0510a9577e3cf3a03b6f2692fb409a4b](https://git.arts.ac.uk/user-attachments/assets/9c6df0eb-ef8d-4a68-b097-0f0be31a4f7b)
| Level | Beta Range | Color Output | Detailed Emotional Interpretation |
|-------|-------------|--------------|----------------------------------|
| **0 – Low Active** | 0.00–0.18 | **Blue** | Represents emotional suppression, detachment, low attention, and “freeze” responses. Typically seen when players feel powerless or disconnected (e.g., early fruit-collection stage). |
| **1 – Slightly Sub-active** | 0.18–0.36 | **Purple** | Indicates hesitation, early tension, light anxiety, or uncertainty. Often correlates with confusion in restricted-choice scenes or misdirection. |
| **2 – Normal** | 0.36–0.54 | **Gray** | Represents neutral, stable attention with neither stress nor calm dominance. Functions as the “baseline” emotional state during low-conflict traversal or puzzle recognition moments. |
| **3 – Active** | 0.54–0.72 | **Orange** | Shows rising conflict, emotional engagement, cognitive struggle, and narrative resistance. Frequently appears during Bird attacks, false endings, or revelation scenes. |
| **4 – Hyper Active** | 0.72–0.90 | **Red** | Marks emotional spikes: high alertness, fear, internal confrontation, or intense cognitive/emotional load. Often triggered at climactic turning points or moments of narrative contradiction. |

![e5da4bb325ad8451a4611f10fae8af6e](https://git.arts.ac.uk/user-attachments/assets/f9e3c6aa-32a5-4601-82a3-01a91f82c977)
![f65ebff2917393786f6ec7f4ca9ad8b6](https://git.arts.ac.uk/user-attachments/assets/f4038456-02b2-49b0-8e2e-53afc5039754)
![f943af0ebf40e0d5e6953cdd85c7ad30](https://git.arts.ac.uk/user-attachments/assets/a3cdb163-dc7c-4d34-92bf-eb9bbe9170e3)
![d15b7eb8d6ee92b52c09b05fbbc16a53](https://git.arts.ac.uk/user-attachments/assets/15cf018f-c896-4205-8408-42fc7fbe918b)
![aba2f5b691f3d59c1ae8807fce5ff263](https://git.arts.ac.uk/user-attachments/assets/b8ba1442-b966-414f-9514-c8782b0c17bd)



---
### Sound Mapping
![4cf498a6b9ee3a3ad5bf4a189d040135](https://git.arts.ac.uk/user-attachments/assets/53a5bbe5-ed21-41b7-ba78-87f681e17daa)
| Beta State | Output Behavior | Technical Implementation | Emotional Effect |
|------------|-----------------|---------------------------|------------------|
| **Low (0–1)** | Dull, muffled, weighted sound | Low-pass filter (cutoff < 300 Hz), reduced gain | Feels suppressed, muted, emotionally contracted; matches powerlessness. |
| **Normal (2)** | Silence / minimal tone | Volume ~0, no filter modulation | Represents neutrality, a pause or “breathing room” between emotional spikes. |
| **High (3–4)** | Sharp, bright, noisy audio bursts | High-pass filter (2–4 kHz), light distortion, gain boost | Conveys intensity, confrontation, fear, or emotional overload—especially during Bird waves or final refusal. |
---
### Brain Wave to transition
![d016286ae762734e53ad7aec3c58fca5](https://git.arts.ac.uk/user-attachments/assets/d1785c05-05b2-4ee4-8510-8891b85f46e5)
| Parameter | Expression | Extended Meaning / Visual Behavior |
|-----------|-------------|-------------------------------------|
| **Translate X** | `beta_norm * 0.3` | Controls horizontal drift of cellular noise. Slow drift in low states; becomes jittery and unstable in high beta states, visually encoding cognitive agitation. |
| **Translate Y** | `beta_norm * 0.4` | Vertical displacement. Adds layered turbulence; high beta produces rapid spatial instability, mirroring emotional escalation. |
| **Noise Amplitude** | `fit(beta_norm, 0, 0.9, 0.1, 1.0)` | Governs fragmentation intensity. Low = almost solid visuals. High = image tears apart, symbolizing emotional conflict or narrative breakdown moments. |
| **Displacement** | Driven directly by state level | Distorts the rendered scene based on emotional level. Light warping at low states; aggressive pixel/shape tearing under high emotional pressure (Bird encounter, refusal scenes). |

---
# 📊 6. TESTING
![924f1457d948cd5f2d06281f8cb6ffb1](https://git.arts.ac.uk/user-attachments/assets/a1237a77-0ae9-4582-8cc0-fc8935453dd1)
![7c640815af34a45c8b2c81cd159be72e](https://git.arts.ac.uk/user-attachments/assets/f0477d8a-6fac-4057-ae20-acaf3ae497cb)
![12302e907ab5d9e67759ae03c737dc30](https://git.arts.ac.uk/user-attachments/assets/79b91cf9-230d-4fe6-ad47-bd00656dab0e)
![e9eab8b24038a21789171579a265ff7e](https://git.arts.ac.uk/user-attachments/assets/28b14543-5fa1-472e-bd3a-dd38736cedfb)
![62e6ed5f6b7a080136854a1640bc5c82](https://git.arts.ac.uk/user-attachments/assets/033b4219-29bc-45f8-a4fc-80dea23a4161)
---
### Emotional Reactivity
| Group | EEG Pattern / Color Distribution | Behavioral Notes / Interpretation |
|--------|---------------------------------|----------------------------------|
| **Male Players** | Primarily **blue** (low activation) and **purple** (low–moderate tension). Only occasional transitions into gray, with very few spikes into orange or red. | Male testers generally showed lower emotional arousal and tended to approach the game analytically. Many interpreted the restricted mechanics as “game puzzles” rather than systemic oppression, resulting in flatter beta-wave variability. |
| **Female Players** | Frequent **orange** (active conflict) and **red** (high emotional load). More rapid transitions between color states. Sustained activation during forced-choice scenes, Bird encounter, and false endings. | Female testers exhibited stronger cognitive-emotional resonance with the protagonist. They reported tension, frustration, and empathy toward the girl's constrained situation. Their EEG traces showed more pronounced emotional peaks during moments of disempowerment or awakening. |
---
### Narrative Understanding
| Narrative Theme / Mechanic | Player Understanding Level | Notes on Player Interpretation |
|----------------------------|----------------------------|--------------------------------|
| **Structural bias** | **High** | Players quickly recognized that the girl was not treated as a protagonist and that the system itself perpetuates inequality. |
| **Forced compliance** | **High** | The fruit-collection tasks and crossroads restrictions were perceived as intentionally oppressive, not as “tutorial limitations.” |
| **Awakening arc** | **Strong** | Testers understood the significance of gaining Mind, Eye, and Mouth as metaphors for cognitive clarity, perception, and refusal. |
| **Bird as verbal violence** | **Very strong** | Nearly all players reported emotional discomfort and recognized the verbal attack waves as symbolic psychological pressure. |
| **False endings as system critique** | **Clear** | Testers recognized that the polished but meaningless endings represent narrative manipulation and lack of agency. |
| **Naming = reclaiming agency** | **Universal** | Every player interpreted the naming moment as the first genuine choice and a symbolic restoration of identity. |

---
# 🌟 7. Core Contribution of the Work 

> This project embeds feminist critique directly into its mechanics, allowing players to experience structural gender bias through constrained choices, weakened abilities, exclusion from main quests, and enforced obedience—producing understanding through lived play rather than instruction. EEG data never controls gameplay; instead, it mirrors the cognitive spikes and emotional turbulence generated by oppression, making internal tension visible. The visual system—cellular noise, collage textures, black-and-white suppression, and the gradual return of color—translates the girl’s inner struggle and awakening into a sensory language: the world stabilizes as agency emerges and fractures as narrative pressure intensifies. Narrative design centers on refusal as the core form of agency, where power comes not from leveling or combat but from recognizing manipulation and rejecting false choices; the Mouth ability is not an attack but an act of political awakening. Through its fusion of storytelling, physiological signals, and visual abstraction, the project becomes simultaneously an artwork, an emotional experiment, a narrative critique, and an instrument of affective resonance.

---


# ⚠️ 8. Limitations & Future Improvements 

1. **Narrative clarity vs intentional confusion**  
   Some players found early sections *too* confusing.  
   While this reflects the thematic goal (systemic ambiguity),  
   future iterations may add subtle environmental cues  
   so the metaphor remains readable without diminishing discomfort.

2. **Heart ability underdeveloped**  
   Compared to Mind, Eye, and Mouth,  
   the Heart ability was less perceptible in both mechanics and emotional impact.  
   Future work will integrate it more deeply into decision-making and narrative conflict.

3. **EEG variability across gender and individuals**  
   Male players produced lower beta activation overall, while female players spiked more frequently.  
   This suggests promising patterns but also indicates the need for:  
   - larger sample size,  
   - individual baseline calibration,  
   - potential normalization strategies to avoid over-fitting emotional conclusions.

4. **Limited audio dynamic range**  
   While effective, the current audio system mainly shifts between dull → silent → sharp.  
   Adding mid-layer textures may enrich emotional granularity.

5. **TouchDesigner visuals rely on beta only**  
   Using only beta waves simplifies the pipeline but ignores other emotional dimensions  
   such as relaxation (alpha) or internal conflict (theta).  
   Future versions may explore multi-band mapping while avoiding overcomplication.










 ---

 














































