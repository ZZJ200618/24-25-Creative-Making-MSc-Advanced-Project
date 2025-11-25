# Week 21— Final Playtest & Evaluation Results

## This week focused on running full end-to-end playtests of the complete game, including:
- the fruit collection stages (basic + upgraded),
- crossroads and monster sequences,
- skill-unlocking arc,
- Bird encounter,
- final false endings + true ending,
- TouchDesigner EEG color/sound mapping.

The goal was to evaluate narrative clarity, emotional response, EEG behavior, and the stability of the audiovisual system.

---

# 1. Test Procedure
![12302e907ab5d9e67759ae03c737dc30](https://git.arts.ac.uk/user-attachments/assets/826afa43-ede5-4241-92ca-e490cb6159e8)
![7c640815af34a45c8b2c81cd159be72e](https://git.arts.ac.uk/user-attachments/assets/e32b9a51-a9c1-4d13-bdfe-3aa11bab74c2)

## 1.1 Participants
- Total testers: small sample (mixed gender)
- Ages: early 20s
- Experience: most players familiar with RPGs

## 1.2 Testing Setup
- Unity game build (PC)
- Muse EEG headband (beta-wave only)
- OSC → TouchDesigner pipeline active
- TD window placed beside gameplay window for observation

## 1.3 Test Flow
Players completed the full sequence:
Fruit (basic)  → Crossroads →
Small Monster → Big Monster → Return → Skills →
Four Paths →  Fruit (upgraded)→Bird → False Endings → True Ending → Naming


Afterwards, they completed a short survey on:
- emotional response  
- narrative clarity  
- perceived agency  
- understanding of the theme  
- comfort/confusion levels  

---

# 2. Observations During Testing

![924f1457d948cd5f2d06281f8cb6ffb1](https://git.arts.ac.uk/user-attachments/assets/f4022939-ee78-405c-9151-ad9ed1127a81)

## 2.1 EEG Behavior Was More Reactive Than Expected
Originally, it was hypothesized that:
- only event-heavy scenes would spike beta (Bird, endings)
- neutral regions would remain in gray/blue

However:
- **Players showed frequent spikes outside “event scenes”**
- **Beta activity shifted rapidly**, producing many transitions:
  - Blue → Purple → Orange → Red jumping in short intervals

This indicates:
- The narrative structure itself creates emotional pressure  
- Not only discrete events cause tension  

---


Afterwards, they completed a short survey on:
- emotional response  
- narrative clarity  
- perceived agency  
- understanding of the theme  
- comfort/confusion levels  


## 2.2 Gender Differences in Beta Activation
A consistent trend appeared:

### Male testers
- Spent significantly more time in **blue/purple** ranges  
- Fewer red peaks  
- Described the story as “interesting but predictable”  
- Showed lower emotional arousal during false endings

### Female testers
- High frequency of **orange/red** activation  
- Stronger emotional response to:
  - bird’s verbal attacks  
  - forced-compliance scenes  
  - false ending rejection  
- Many described feeling:
  - angry
  - anxious
  - relieved at the naming scene

Although the sample is small, the pattern is consistent.
![10](https://git.arts.ac.uk/user-attachments/assets/193d99f3-9ba3-4c2c-90d2-ead6e76a4f56)
![11](https://git.arts.ac.uk/user-attachments/assets/4b76abdb-5f0e-4714-9d83-b092d38a0bfa)
![12](https://git.arts.ac.uk/user-attachments/assets/1392052d-051d-434e-95a7-232f289f43a7)
<img width="891" alt="13" src="https://git.arts.ac.uk/user-attachments/assets/87a68e32-34a1-4e3c-b01e-5f342b73689f" />
![14](https://git.arts.ac.uk/user-attachments/assets/98043c28-c0a6-4c8a-bf3a-8e67ab358fd5)
![15](https://git.arts.ac.uk/user-attachments/assets/9754bb5b-3bbc-4ecf-acc9-8b8f6fb74ef6)

---

# 3. Narrative Comprehension

### ✔ Most players fully understood the theme  
Especially after the final line (“The monster and the hero never existed”), players identified:
- structural oppression  
- biased narrative conventions  
- female character constraints  

### ✔ Players found the “skill awakening” arc meaningful  
However:
- Some felt the **Heart ability** was less evident  
- Eye and Mind were the strongest moments  
- Mouth (refusal mechanic) was the most memorable

### ✔ Confusion was intentional — but still reported
Players frequently commented:
- “I wasn’t sure what the game wanted me to do at first.”
- “The guidance was vague.”

This aligns with the design goal:
> making the player feel the same structural confusion the girl experiences.

---


# 4. Final Results Summary

| Category | Result |
|---------|--------|
| Narrative Comprehension | High |
| Emotional Resonance | Strong (esp. for female testers) |
| EEG Reactivity | Stronger & more chaotic than expected |
| Visual Coherence | Excellent |
| Audio Mapping | Effective & emotionally aligned |
| System Stability | Stable, no crashes |
| Confusion Level | Moderate (intentional) |
| Understanding of Theme | High |

---

# 5. Improvements for Final Build

### 🔧 Clarity tuning
- Add subtle hints for the four paths  
- Strengthen Heart-ability feedback  
- Reduce early-game confusion slightly  

### 🎨 Visual polish
- Add small ambient motion to the Crossroads  
- Increase contrast during the Dark path  

### 🔊 Audio refinement
- Smooth transitions between sound states  
- Subtle ambient hum in normal state (optional)

---

# ✔ Conclusion

The final test validates that:
- the emotional system works,
- the EEG mapping meaningfully reflects player tension,
- the color/noise/audio mapping is coherent,
- the narrative is well understood,
- and the final naming moment lands with emotional precision.

The game creates the intended experience:
**a critique of RPG gender bias expressed through player discomfort, constraint, and awakening.**


