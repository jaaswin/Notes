
## What is PWM (Pulse Width Modulation)

**PWM** is a technique to control **power** or **signal information** by switching a digital signal **ON and OFF very fast**.

Instead of changing voltage smoothly (which digital systems hate), PWM changes **time**.

The voltage stays the same.
The **ON time** changes.

That single trick makes PWM powerful.

---

## Why PWM is needed

Microcontrollers like Arduino, Raspberry Pi Pico, ESP32 are **digital thinkers**.

They know:

* HIGH (1)
* LOW (0)

They do **not** naturally produce:

* 1.8 V
* 3.2 V
* 4.1 V

But motors and LEDs want **variable power**.

PWM is the translator between digital brains and analog reality 🌉

---

## Basic idea (visual imagination)

Imagine a switch connected to a bulb 💡

* Switch ON → bulb bright
* Switch OFF → bulb dark

Now flick the switch **very fast**:

* ON longer than OFF → bright
* ON and OFF equal → medium brightness
* ON very short → dim

Your eye cannot see the flicker.
It only sees **average brightness**.

That flicker pattern is PWM.

---

## Important PWM terms

### 1. Period (T)

Time for **one complete ON + OFF cycle**

Example:

* Period = 20 ms
* Frequency = 1 / T = 50 Hz

---

### 2. Frequency (f)

How many PWM cycles happen per second.

Examples:

* LED dimming → 500 Hz to 5 kHz
* DC motor control → 1 kHz to 20 kHz
* Servo motor → 50 Hz

Wrong frequency can cause:

* Noise
* Heating
* Jitter

---

### 3. Duty Cycle (D)

The **percentage of ON time** in one period.

[
\text{Duty Cycle} = \frac{T_{ON}}{T} \times 100
]

Examples:

* 0% → always OFF
* 25% → ON short, OFF long
* 50% → ON = OFF
* 100% → always ON

Duty cycle controls **power level** 🔋

---

## PWM waveform (mental picture)

```
HIGH  ┌───┐       ┌──────┐
      │   │       │      │
LOW ──┘   └───────┘      └──

25% duty      50% duty
```

Voltage is always full HIGH or LOW.
Only **width of pulse** changes.

---

## How PWM controls power

PWM does **not** reduce voltage.
It reduces **average voltage**.

[
V_{avg} = V_{max} \times \text{Duty Cycle}
]

Example:

* 5 V supply
* 50% duty cycle

[
V_{avg} = 5 \times 0.5 = 2.5 V
]

Motors and LEDs respond to this average effect.

---

## PWM in DC motor control

* Low duty → motor slow
* High duty → motor fast

Motor inertia smooths the pulses into continuous motion ⚙️

But:

* Too low frequency → jerky motion
* Too high frequency → driver heating

That’s why motor drivers have recommended PWM ranges.

---

## PWM in LED brightness control

PWM is preferred over voltage control because:

* Color remains constant
* High efficiency
* Less heat loss

Brightness ∝ Duty cycle
Frequency must be high enough to avoid flicker.

---

## PWM in servo motors (special case)

Servo motors **do not use duty cycle like motors**.

They use **pulse width**.

* Frequency fixed at **50 Hz (20 ms period)**
* Pulse width carries position info

| Pulse width | Angle |
| ----------- | ----- |
| 1 ms        | 0°    |
| 1.5 ms      | 90°   |
| 2 ms        | 180°  |

Here:

* ON time matters
* OFF time is ignored

Servo PWM is **signal PWM**, not power PWM 🎯

---

## PWM resolution

Resolution decides **how fine control is**.

Example:

* 8-bit PWM → 256 levels (0–255)
* 10-bit PWM → 1024 levels
* 16-bit PWM → very smooth control

Higher resolution = smoother motion, smoother brightness.

---

## How microcontrollers generate PWM

Internally they use:

* **Timers**
* **Counters**
* **Compare registers**

Process:

1. Timer counts up
2. When count < compare value → output HIGH
3. When count ≥ compare value → output LOW

This happens automatically in hardware, very precise ⏱️

---

## Limitations of PWM

✖ Creates electrical noise
✖ Needs filtering for analog use
✖ Wrong frequency causes problems
✖ Not ideal for sensitive analog circuits

---

## PWM vs Analog control (quick compare)

| PWM              | Analog     |
| ---------------- | ---------- |
| Digital friendly | Needs DAC  |
| Efficient        | Power loss |
| Noise present    | Cleaner    |
| Cheap            | Expensive  |

---

## Why PWM is everywhere

Because it is:

* Smart
* Cheap
* Efficient
* Flexible

PWM is time pretending to be voltage ⏳➡️⚡

---

