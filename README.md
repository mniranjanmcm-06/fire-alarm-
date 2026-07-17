# Fire Alarm System with Automatic Water Suppression

A low-cost fire detection circuit using a photodiode and a BC548 NPN transistor, built as a design project for the Bachelor of Engineering (ECE) program at The National Institute of Engineering, Mysuru.

## Overview

This project presents a simple, IC-free fire detection system that triggers a visual (LED) and audible (buzzer) alarm, along with an automatic water pump for fire suppression, when a light/heat anomaly indicative of fire is detected by a photodiode sensor.

The design was built under the explicit constraint of **not using any ICs or driver circuitry** — the entire detection and switching function is implemented using a single BJT (BC548) in a discrete transistor circuit.

## Circuit Design

**Components**
- 9V DC power supply
- BC548 NPN transistor (general-purpose BJT)
- Photodiode
- Resistors — 100 kΩ, 100 Ω
- 5V Buzzer
- LED (indicator)
- Mini 5V DC submersible water pump

**Configuration:** Common-collector (emitter-follower) — the buzzer, LED, and water pump are connected at the transistor's emitter, with the collector tied to Vcc.



## Working Principle

The photodiode is reverse-biased. As it detects light/fire, its reverse (photo) current increases proportionally with light intensity, raising the base drive to transistor Q1:

- **No fire detected:** Photodiode current is negligible → Q1 remains in cutoff → alarm outputs stay off.
- **Fire detected:** Rising photodiode current drives Q1 into conduction → emitter current flows through the buzzer, LED, and water pump, activating the alarm and suppression system.

Since the base drive is analog/proportional rather than a digital trigger, and no comparator or driver IC is used, Q1 operates as a proportional current amplifier moving between cutoff and its active region — rather than a hard-switching common-emitter configuration. This was a deliberate design trade-off to satisfy the "no ICs/drivers" project constraint while still achieving a functional ON/OFF alarm response.

## Prototype

Built and tested on a breadboard.

<img width="537" height="405" alt="image" src="https://github.com/user-attachments/assets/4f0113c7-d435-46c8-a25f-6ea60708d646" />


<img width="410" height="257" alt="image" src="https://github.com/user-attachments/assets/39c20480-6f9b-445f-9211-16c717f28c3e" />

*Breadboard prototype of the fire alarm and water suppression circuit*

**Total Prototype Cost:** ₹130
(Battery ₹30, DC Motor ₹50, Buzzer/LED/Resistor/Transistor/Photodiode ₹50)

## Testing & Verification
*VIDEO LINK:*
https://drive.google.com/drive/folders/1Xddc TXtZv7MGTfhnNiKatmt88JqC6Lec

The circuit was simulated to validate detection response, followed by physical prototype testing to confirm the alarm and pump activation on light/fire exposure.

## Conclusion

The fire alarm system based on the photodiode and BC548 transistor offers a simple, low-cost, IC-free solution for fire detection. It reliably triggers visual and audible alerts along with automatic water suppression, making it suitable for basic residential fire-safety applications. Future improvements could include additional sensors (smoke, heat) and IoT-based remote monitoring for broader, more sophisticated deployment.

## Contributors

- Niranjan M (4NI23EC049)
- B Manikanta (4NI23EC017)
- Veeresh C N (4NI23EC021)
- Mallikarjuna V R (4NI23EC053)

**Guided by:** Dr. Remya Jayachandran, Associate Professor, Dept. of ECE, NIE Mysuru
