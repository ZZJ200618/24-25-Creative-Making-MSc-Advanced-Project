## Week 19 — The Bird Encounter: Combat Avoidance + Vocal Conflict

### Overview
This week implemented the Bird sequence — the first antagonist that uses **language violence** instead of physical damage.

---

## 1. Bird Combat System
The structure:
- Player cannot attack
- Bird shouts gender-biased lines (“NPC misogyny”)
- Three waves of projectiles/attacks to dodge
- After surviving 3 waves, the girl screams → unlocks “Mouth” ability
![7](https://git.arts.ac.uk/user-attachments/assets/a7950755-4acf-42e0-9388-486f4d118a5f)

---

## 2. Technical Implementation
- Unity projectile system (sinusoidal flight paths)
- Dodge detection via collider triggers

---

## 3. “Mouth” Ability Unlock
- Enables:
  - short-range sound bursts  
  - rejecting scripted choices  
  - confronting narrative constraints  

This is the first time the girl *speaks*.

---

## 4. EEG Considerations
- Marked as high-intensity region  
- Expect frequent orange/red zones (beta > 0.54)

---
## Bird Encounter — Script Challenges

The Bird encounter is the first major “boss moment” in the narrative, but unlike traditional RPG combat, the Bird does not deal physical damage — it deals *verbal violence* and symbolic attacks. This required a very different scripting approach and created several challenges.

---


## False Endings

After the Bird sequence, the game presents three styled endings:

- Each one looks “complete” but is structurally wrong:
  - Hero-centered resolution
  - Sacrifice ending
  - Return-to-normal ending

The key design:

- Clicking them does not lead to a satisfying resolution.
- The **correct action** is to **refuse** them using the newly acquired Mouth ability.

---

## True Ending & Naming
![38](https://git.arts.ac.uk/user-attachments/assets/55e4efde-444d-4680-b15b-4781e0fcf710)
![39](https://git.arts.ac.uk/user-attachments/assets/5f7dd68e-4b30-45c7-954b-53af35190cd9)
![40](https://git.arts.ac.uk/user-attachments/assets/ec049063-5783-4dd6-b455-7931e7997fad)

When the player refuses all endings:

- The monochrome world shifts gradually to color.
- Overlay text reveals:
  > “The monster and the hero never existed.  
  > They were only fears and scripts inside your mind.”

## EEG Tagging

Important segments flagged:

- Bird conflict (verbal violence + dodging)
- Moment of rejecting the false endings
- Color-transition sequence


These regions are intended for later comparison between:

- emotional arousal
- narrative understanding
- gender-based response differences

