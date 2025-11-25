## Week 16 — Basic Fruit Collection Stage (Core Mechanics Completed)

### Overview
This week focused on building the **first functional version** of the fruit-collection stage.  
The goal was to establish the logic, player limitations, item rules, and level flow **without aesthetic polish**.

---

## 1. Core Interaction Rules Implemented

### Allowed items:
- **grey fruit** (task objective)

### Forbidden items:
- **Yellow fruit**
- **Treasure chest**

### Player limitations:
- Cannot attack  
- Cannot open treasure  
- Can only pick up grey fruit  
- Must collect **all task fruit** to pass the stage  

---

## 2. Scene Layout (Basic Version)
![36](https://git.arts.ac.uk/user-attachments/assets/af4798eb-0ae8-4cb6-97a9-5ff8076c5c8d)

The layout is intentionally simple:

- Straight linear path  
- Minimal environmental decoration  
- Few obstacles  
- Fixed left/right boundaries  
- grey fruits positioned visibly along the route  

This version focuses on **clarity**, not difficulty.

---

## 3. Unity Implementation Summary

### Scripts Completed:
- `FruitCollectable.cs`
- `FruitManager.cs`
- `PlayerMovement.cs`
- `UIManager.cs`

### Basic Flow:
Player enters area
    → Collect red fruit
    → Attempt forbidden item → UI "Denied"
    → After all grey fruit collected → LevelComplete()

## 4. Key Upgrades Compared to Basic Version

### **A. Increased Difficulty**
![37](https://git.arts.ac.uk/user-attachments/assets/77172da5-e597-4fd4-86cd-2491c46fccf5)

- More complex path structure  
- Narrower corridors  
- Moving obstacles added  
- Fruits placed in misleading positions  

### **B. Early “perception dissonance”**
- Some fruits *look* orange but are actually forbidden  
- Some “safe” items appear dangerous  
- This introduces **trial-and-error learning**

### **C. Hidden warnings**
- Visual flickers  
- Slight noise distortion  
- Hinting the player to “start seeing patterns”  
(Preluding the Eye ability to be learned later)

## Challenges Encountered During Scripting (Fruit Stage Development)

During the development of both the **basic** and **upgraded** fruit-collection stages, several technical and design challenges emerged. These challenges shaped how the scripts were structured and how the player experience evolved.

---

### 1. Distinguishing Allowed vs. Forbidden Items in Real-Time

One of the first challenges was ensuring that:
- Red fruits can be collected smoothly,
- Yellow fruits and chests cannot be collected,
- And **fake red fruits** (in the upgraded version) look identical but behave differently.

**Problem:**  
Unity’s `OnTriggerEnter2D()` fires for all items, so early on all items behaved the same.

**Solution:**  
Introduce a `FruitType` enum and assign logic per type:

```csharp
public enum FruitType { Allowed, Forbidden, FakeAllowed }


---



