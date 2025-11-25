## Week 17 — Crossroads, First Monster Encounter, and Forced Escape

### Overview
This week focused on everything that happens **immediately after the fruit-collection scene**:
- Building the **crossroads** (left/right split)
- Implementing the **first monster encounter**
- Triggering the **big monster trap**
- Forcing the girl to **escape back to the crossroads**
- Important: at this stage, the player still has **no skills** — she can only defend/heal or run.

---

### 1. Crossroads Scene
<img width="1920" alt="28" src="https://git.arts.ac.uk/user-attachments/assets/9e5c833e-6e8f-4bdb-bcb7-162604d8fb0b" />
<img width="1920" alt="29" src="https://git.arts.ac.uk/user-attachments/assets/920e66b3-e278-465a-81b9-b924719204df" />
<img width="1920" alt="30" src="https://git.arts.ac.uk/user-attachments/assets/bb1bac92-61fe-4ea5-ac1c-3644cd9d2176" />

After turning in the collected fruit, the girl and the Hero arrive at a stone monument:

- Stone text:  
  - *“Girl goes left.”*  
  - *“Hero goes right.”*  
- Player is forced to take the left path.
- The environment is narrow and monochrome, with a sense of being “sent off alone again.”

**Implementation notes:**
- New `Crossroads` scene in Unity.
- Signpost object with trigger + UI text.
- Left path → leads into the first monster encounter.
- Right path → locked with an invisible collider and a “You can’t go there.” message.

---

### 2. First Monster Encounter
<img width="1920" alt="32" src="https://git.arts.ac.uk/user-attachments/assets/d44bdd18-117f-4450-8ccc-2ce98a6f2941" />
<img width="1920" alt="33" src="https://git.arts.ac.uk/user-attachments/assets/150f99f5-8535-482b-9dca-713367fec9bb" />


On the left path, the girl encounters **a smaller monster**:

- She has **no attack skills**.
- Available actions: `Defend`, `Heal`, or `Wait`.
- This encounter is unwinnable by design:
  - Defend only reduces damage.
  - Heal barely keeps her alive.
  - There is no way to defeat the monster.

**Goal:**
Let the player **feel** that she is structurally underpowered and functionally expendable.

---

### 3. Big Monster Trap
![34](https://git.arts.ac.uk/user-attachments/assets/54efae48-1fdd-41b1-8f65-708ef14dc5ec)

After barely surviving the first encounter, the scene escalates:

- A **larger monster** appears and captures the Hero (off-screen or in a parallel scene).
- The player cannot see or control the Hero.
- The narrative implies:
  - The girl was sent as a decoy.
  - The “real narrative” happens elsewhere.

Technical side:
- Triggered by exiting the combat zone.
- Cutscene plays showing:
  - A large roar
  - Screen shake
  - Noise distortion

---

### 4. Forced Return to Crossroads
<img width="1920" alt="35" src="https://git.arts.ac.uk/user-attachments/assets/1a6b713d-c5cf-4ab0-956c-441c78a7e639" />

The girl has no valid combat options.

- She is forced to **run back** toward the crossroads.
- The camera pulls back or narrows field-of-view to emphasize retreat.
- When reaching the crossroads, she has **no guidance**:
  - Hero is missing
  - Monument text remains the same
  - Player is left in a state of “What now?”

This is where the **skill-learning arc** will later begin in the following weeks.

---

### EEG Notes (Observation Only)
- This week’s content is expected to produce:
  - Moderate beta activation at the first monster.
  - Higher activation when the big monster appears and the girl has no solution.
  - Stronger sense of helplessness rather than empowerment (no skills yet).

---
Note: Due to the large number of scripts, it was difficult to paste them all, so they have all been merged into the complete game folder. From now on, I will only write about the difficulties and challenges encountered in completing the scripts.

---

## 1. Small Monster Encounter: Making an Unwinnable Fight “Feel Intentional”

### ❌ Challenge
The small monster fight is intentionally unwinnable because:
- The girl has no attack skills
- The design wants the player to feel powerless

But unwinnable fights can accidentally feel:
- Buggy  
- Unfair  
- Badly designed

### ✔ Solution
- Added **telegraphed patterns** so the player sees the monster is “designed to win.”
- Added defensive actions:
  - Defend → reduces damage
  - Heal → slow and barely effective
- Combat log messages hint:
  - “Your actions have little effect.”
  - “It’s too strong.”

This reframes losing as narrative, not a mechanical failure.

---

## 2. Big Monster Trap: Building a Threat Without Visible Combat

### ❌ Challenge
The big monster never fully appears on-screen (budget + aesthetic choice).  
But it must feel:
- Bigger  
- Deadlier  
- More important  
- Capable of capturing the Hero instantly

Hard to convey without showing the monster clearly.

### ✔ Solution
- Used **sound design** instead of visuals:
  - Deep roars
  - Reverb-heavy thumps
  - High noise distortion
- Quick **silhouette flash** in noise field (0.2 seconds)
- Hero’s shout plays from a directional audio source
- Scene transitions abruptly to emphasize chaos

The player understands the threat without needing a fully animated creature.

---
