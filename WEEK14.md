# Week 14 — Unity → TouchDesigner Attack Signal Integration  
### Dev Log (Based on “MIDI, Audio, and Spout in Unity using Keijiro Plugins and TouchDesigner”)

## 1. Overview  
This week I focused on extending the workflow demonstrated in the tutorial  
**“MIDI, Audio, and Spout in Unity using Keijiro Plugins and TouchDesigner”**  
to support a new type of data stream:  
**Unity attack events (Attack Signals) sent into TouchDesigner for real-time visual triggering.**

The goal was to build a structured communication path:

```
Unity (Attack Event)
        ↓ OSC
TouchDesigner (Signal In)
        ↓
Visual Response / Effect Trigger
```

---

## 2. Communication Method  
Following the architecture pattern in the tutorial, I evaluated several options for transporting Unity → TD data.

| Method | Pros | Cons |
|-------|------|------|
| **OSC** | Low latency, well supported, ideal for event signals | Requires plugin |
| UDP Socket | Flexible | Manual parsing |
| WebSocket | Overkill | High latency |
| Spout | Video only | Not suitable for events |

**Chosen method: OSC (Open Sound Control)**  
It matches the tutorial’s modular design style and works natively in TouchDesigner.

---

## 3. Unity Implementation  
### Attack Event → OSC message

Created a dedicated Unity script for sending an OSC pulse whenever the attack action is triggered.

```csharp
using extOSC;
using UnityEngine;

public class AttackEventSender : MonoBehaviour
{
    public OSCTransmitter transmitter;

    void Update()
    {
        if (Input.GetMouseButtonDown(0))
        {
            transmitter.Send("/attack", 1);
        }
    }
}
```

Key points:

- `/attack` is used as the OSC address.
- A single pulse value (`1`) represents the event.
- TouchDesigner handles smoothing, shaping, or visual mapping.

---

## 4. TouchDesigner Implementation  
### Receiving Attack Signal

1. Added **OSC In CHOP**  
2. Set port to match Unity  
3. Mapped input channel to TD parameters

To refine the event signal:

- **Trigger CHOP** → Converts pulse into an envelope  
- **Math CHOP** → Normalization  
- **LFO / Lag CHOP** → Optional smoothing

Example visual mappings:

- Driving the amplitude of Noise TOP  
- Triggering a Feedback reset  
- Flash intensity in GLSL  
- Burst in particle systems  

---

## 5. Issues Encountered  

### Problem 1 — Multiple Trigger Events  
Caused by using `GetMouseButton()` instead of `GetMouseButtonDown()`.

**Solution:** Change to `GetMouseButtonDown` for one-shot detection.

---

### Problem 2 — OSC Not Received  
Blocked by Windows firewall.

**Solution:** Whitelist Unity output port.

---

### Problem 3 — Pulse Too Short  
Raw `1 → 0` signal was visually weak.

**Solution:** Use TD Trigger CHOP to generate a smooth attack envelope.

---

## 6. Results  
By following the structure demonstrated in the original tutorial, the final workflow mirrors its modular, signal-based design:
![857501d4fc76d94b7f961fe7c69cc1a7](https://git.arts.ac.uk/user-attachments/assets/7df904da-b996-4bcd-b831-f518d7664823)

- Unity handles event generation  
- OSC transports lightweight, structured messages  
- TouchDesigner manages all visual mappings  

The system performs reliably with minimal latency and can be extended to additional gameplay signals.

---

