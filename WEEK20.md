## Week20 — Final Boss Sequence, Naming Ending, and TouchDesigner EEG Integration

This week focused on completing the entire final act of the game: the three false endings, the final (non-)boss confrontation, the naming sequence, and the integration of EEG-driven TouchDesigner visuals and audio mapping. This marks the first time the emotional architecture, narrative logic, and EEG visualization system operate together from start to finish.
<img width="1920" alt="41" src="https://git.arts.ac.uk/user-attachments/assets/3bbeb524-24ce-4000-9d5f-300df1c69394" />
![44](https://git.arts.ac.uk/user-attachments/assets/5c36405e-53b2-4e70-8541-e78461cc5b04)
![42](https://git.arts.ac.uk/user-attachments/assets/0546a7b8-8c51-4022-b89b-ac7b29b072f2)


---

# 1. Final Boss Design — A “Narrative Structure” Instead of a Monster

Unlike traditional RPGs, the final boss is *not* a creature.  
It is **the narrative system itself**:  
- Forced endings  
- Gender-biased tropes  
- Pre-scripted story paths  
- Player's lack of agency

The girl must pass tests of her mind, heart, eyes, and mouth to pass the test.

### Naming Sequence — The Only Player-Given Choice

After the world stabilizes:

Naming UI
Input field: “Give her a name.”
Soft breathing animation on the text
No background sound except low noise floor

Logic
No slurs, empty strings, or joke names allowed
Name saved to local file (optional)
The moment of naming finalizes the girl’s agency
Once the player names her:
The system fades to white
Music fades to a soft-toned hum
Ending logo appears
<img width="1920" alt="43" src="https://git.arts.ac.uk/user-attachments/assets/142458f1-e58d-4d0b-bafb-560cfb49b7b9" />

## Touchdesigner noise transition
Noise & Translation Mapping
The normalized beta value beta_norm drives:
(1) Cellular Noise Translate
tx = beta_norm * 0.3
ty = beta_norm * 0.4
![d016286ae762734e53ad7aec3c58fca5](https://git.arts.ac.uk/user-attachments/assets/5b347295-1bac-461e-b834-2db4a99f7305)
This creates:
subtle drift in low states
violent shaking in high states


