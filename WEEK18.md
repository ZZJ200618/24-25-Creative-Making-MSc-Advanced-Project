## Week 18 — Ability Awakening Begins: Mind System & Word Reconstruction

### Overview
After the girl returns to the crossroads with **no clear instruction and no Hero**, the focus of this week was to:

- Introduce the **first ability: Mind**
- Implement the **word reconstruction puzzle**
- Connect this to the idea that the girl starts to think for herself for the first time

---

### 1. Triggering the Mind Ability

At the crossroads, when the player:
- Wanders without direction  
- Or interacts with the stone multiple times  

A new internal prompt appears:

> “If no one is going to tell you what to do…  
> maybe you have to decide what this all means.”

This triggers the **Mind** learning sequence.

---

### 2. Word Reconstruction Puzzle

The Mind ability is introduced via a puzzle where the girl must:

- Reassemble fragmented words or phrases into a meaningful sentence.
- These fragments represent:
  - broken narrative logic
  - half-finished commands
  - stereotypical RPG lines

**Implementation details:**
- Unity UI using `Canvas + GridLayoutGroup`.
- Draggable word fragments.
- Sentence validation through string matching.
- Feedback:
  - Incorrect attempt → subtle screen shake + glitch text.
  - Correct solution → short noise burst + grayscale world flicker.

---

### 3. Function of “Mind” in the System
![959e6f4feb946f174a27518f1ecd1161](https://git.arts.ac.uk/user-attachments/assets/41f14118-be7f-4749-a995-6ae3fa99bd29)


After solving the puzzle:

- **Mind ability unlocked**:
  - Internally: the girl gains cognitive clarity.
  - System-wise: flags future dialogue options as “questioned” instead of “accepted.”
- This does **not** yet give explicit gameplay powers like attack or seeing hidden paths.
- It mainly changes:
  - internal monologue
  - tone of future choices
  - the way UI text responds to commands

---

### EEG Considerations

- The Mind puzzle is marked as:
  - A likely **high-beta region** (cognitive load, problem solving).
  - Moment where attention is sharply focused.
- In TouchDesigner:
  - This segment will be time-labeled for later visual playback.

---
### ❌ Challenge
The puzzle must express:
- Cognitive awakening  
- Reassembling identity  
- Breaking narrative conditioning

But it must not:
- Be too hard  
- Stall progress  
- Frustrate players who aren’t puzzle-oriented

### ✔ Solution
- Reduced fragment count
- Provided subtle “magnetic” snapping between correct pieces
- UI highlights correct cluster connections
- Failure gives thematic feedback:
  - “This doesn’t feel right.”
  - “Try again.”

The puzzle then becomes symbolic, not academically difficult.

---



### 1. Four Paths Redesign
![c6cfe4aa549548f2de68a09796e0ef63](https://git.arts.ac.uk/user-attachments/assets/6be9f376-9f05-4a35-a726-803810c41d3d)

The crossroads now branches into:

- Thorny Path — painful progress, visible danger
- Smooth Path — low resistance, but emptiness
- Curved Path — confusing navigation and looping
- Dark Path — almost no visibility, unknown risk

The player can **choose any path**, but:

- Only the **Dark Path** leads to unlocking **Eye**.
- The others eventually loop back to the crossroads.

---

### 2. Eye Ability Unlock

When the player chooses to enter and persist in the Dark Path:

- Visuals become more unstable:
  - cellular noise intensifies
  - contrast drops
- Eventually, a key event triggers:
  - a flash of light  
  - UI: “You start seeing what was always there.”

**Eye ability effect:**
- Allows:
  - highlighting “fake” choices later (e.g. false endings)
  - subtle glow around traps
  - visual cues in otherwise monochrome scenes

---

### 3. Narrative Function

The difference from previous weeks:

- Before: player is under-guided and underpowered.
- Now: the player begins to gain tools to **perceive the structure**, not just survive inside it.

---

### EEG Notes

- Anticipated behavior:
  - Dark Path: anticipation + fear → higher beta
  - Looping on smooth/curved paths: frustration → moderate beta
- These sections will be useful for comparing:
  - “risk-taking” vs “safe route” behavior.

---



