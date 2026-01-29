Amplitude Modulation (AM) – Detailed Explanation

Amplitude Modulation is one of the earliest and simplest ways humans taught electricity to speak 📻. In AM, the strength of a high-frequency carrier wave is shaped by the message signal, while the carrier’s frequency and phase stay steady, like a calm clock ticking in the background.


---

1. What is Amplitude Modulation?

Amplitude Modulation (AM) is a process in which the amplitude of a carrier signal is varied in proportion to the instantaneous value of the message signal, while the carrier frequency remains constant.

One-line exam definition

> In amplitude modulation, the amplitude of the carrier wave is varied according to the message signal.




---

2. Basic Signals in AM

a) Message Signal

Low-frequency signal (voice, music)

Frequency range: 20 Hz to 20 kHz

Cannot travel long distances


b) Carrier Signal

High-frequency sinusoidal signal

Frequency in kHz or MHz range

Provides efficient radiation


c) Modulated Signal

Resultant signal after modulation

Contains carrier + sidebands



---

3. Mathematical Representation

Carrier signal

c(t) = A_c \cos(2\pi f_c t)

Message signal

m(t) = A_m \cos(2\pi f_m t)

AM wave

s(t) = A_c \left[1 + m \cos(2\pi f_m t)\right] \cos(2\pi f_c t)

Where:

 = carrier amplitude

 = carrier frequency

 = message frequency

 = modulation index



---

4. Modulation Index (m)

The modulation index tells how deeply the carrier is modulated.

m = \frac{A_m}{A_c}

Conditions

m < 1 → Under-modulation

m = 1 → 100% modulation (ideal)

m > 1 → Over-modulation ❌ (distortion)


📌 Over-modulation causes envelope distortion and information loss.


---

5. Frequency Spectrum of AM

An AM signal contains three frequency components:

1. Carrier frequency 


2. Upper Sideband (USB) → 


3. Lower Sideband (LSB) → 



Bandwidth of AM

\text{Bandwidth} = 2 f_m


---

6. Power Distribution in AM

Total transmitted power:

P_t = P_c \left(1 + \frac{m^2}{2}\right)

Where:

 = carrier power


Important Observation

Carrier alone carries no information

Sidebands carry all the information

Power efficiency is low ❌



---

7. Types of AM

1. Conventional AM (DSB-LC)

Carrier + both sidebands transmitted

Used in AM broadcasting


2. DSB-SC (Double Sideband Suppressed Carrier)

Carrier suppressed

Better power efficiency


3. SSB (Single Sideband)

Only one sideband transmitted

Very efficient ✔️

Used in aviation and military communication


4. Envelope Modulation

Simple detection method

Used in conventional AM receivers



---

8. Generation of AM

Low-Level Modulation

Modulation occurs at low power

Requires linear amplifier


High-Level Modulation

Modulation at final power stage

Used in transmitters


Common circuits:

Transistor modulator

Square-law modulator

Collector modulation



---

9. Detection of AM (Demodulation)

Envelope Detector

Diode + capacitor + resistor

Recovers original message

Works only for m ≤ 1


Synchronous Detector

Used for DSB-SC and SSB

Requires carrier recovery



---

10. Advantages of AM

✔ Simple transmitter and receiver
✔ Low-cost implementation
✔ Large coverage area


---

11. Disadvantages of AM

❌ Poor noise immunity
❌ Low power efficiency
❌ Large bandwidth compared to information rate


---

12. Applications of AM

AM radio broadcasting 📻

Aviation communication ✈️

Marine communication 🚢

Emergency communication systems



---

13. Comparison with FM (Short)

Feature	AM	FM

Noise immunity	Poor	Excellent
Bandwidth	Low	High
Circuit complexity	Simple	Complex
Audio quality	Average	High



---

14. Short Exam Notes

AM varies amplitude, not frequency

Bandwidth = 2 × message frequency

Modulation index determines signal quality

Over-modulation causes distortion



---
