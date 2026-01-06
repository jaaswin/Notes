
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
PWM is like a quiet metronome hidden inside embedded systems 🎵⚙️. You rarely see it, but everything moves to its beat. Let’s tour the places where PWM lives and works.

---

## 1. Motor control (most common)

### DC motors

PWM controls **speed**.

* Low duty cycle → slow
* High duty cycle → fast

Used in:

* Line-following robots
* Fans
* Toy cars
* Conveyor belts

---

### Servo motors

PWM controls **position**.

* Pulse width decides angle
* Frequency fixed (50 Hz)

Used in:

* Robotic arms
* Pan-tilt cameras
* RC vehicles
* Smart door locks

---

### Stepper motor drivers

PWM controls **current** in motor coils.

Used in:

* 3D printers
* CNC machines
* Plotters

Here PWM is about torque and smooth motion.

---

## 2. LED and display control 💡

### LED brightness control

PWM adjusts brightness without changing color.

Used in:

* Indicator LEDs
* Street lights
* LCD backlight
* RGB LED strips

---

### Display contrast and backlight

PWM saves power while keeping displays readable.

Used in:

* Smartphones
* Embedded HMIs
* Automotive dashboards

---

## 3. Power management systems 🔋

### Battery charging

PWM controls charging current.

Used in:

* Solar chargers
* Power banks
* EV chargers

---

### SMPS and DC-DC converters

PWM regulates output voltage.

Used in:

* Power supplies
* Embedded boards
* IoT devices

PWM here decides efficiency and stability.

---

## 4. Audio and signal generation 🎧

### Audio output (Class-D amplifiers)

PWM encodes audio signals.

Used in:

* Embedded speakers
* Buzzers
* Alarms

Filtered PWM becomes sound.

---

### Tone and buzzer control

PWM generates frequency-based sounds.

Used in:

* Beepers
* Warning systems
* User feedback tones

---

## 5. Communication and timing 🕒

### Infrared (IR) communication

PWM modulates IR signals.

Used in:

* TV remotes
* IR sensors
* Proximity systems

---

### Signal encoding

PWM represents data in time.

Used in:

* Dimming protocols
* Sensor interfaces
* Custom communication links

---

## 6. Heating and power loads 🔥

### Heater control

PWM regulates heating elements.

Used in:

* Soldering stations
* Incubators
* Smart irons

---

### Power control of loads

PWM controls lamps, relays (via drivers), solenoids.

Used in:

* Industrial automation
* Smart appliances

---

## 7. Robotics and automation 🤖

PWM controls:

* Arm joints
* Wheel speed
* Gripper force
* Balance systems

Every movement is a timed pulse.

---

## 8. Automotive embedded systems 🚗

PWM is used in:

* Engine control units (ECU)
* Fuel injectors
* ABS systems
* Power steering
* Interior lighting

Automotive systems trust PWM because it is robust.

---

## 9. Sensor interfacing

PWM used as:

* Sensor output format
* Control signal for sensors

Used in:

* Ultrasonic sensors
* Gas sensors
* Flow meters

Time-based signals survive noise better.

---

## 10. Industrial control systems 🏭

PWM used in:

* Variable frequency drives
* PLC output modules
* Actuators

Here PWM runs machines that never sleep.

---

## 11. IoT and low-power devices 🌍

PWM helps:

* Reduce power consumption
* Control peripherals efficiently

Used in:

* Smart lights
* Wearables
* Home automation

---

## Summary table (exam-friendly)

| Area          | PWM role                    |
| ------------- | --------------------------- |
| Motors        | Speed, position, torque     |
| LEDs          | Brightness control          |
| Power         | Voltage, current regulation |
| Audio         | Signal generation           |
| Heating       | Power control               |
| Communication | Signal encoding             |
| Automotive    | Actuator control            |
| Robotics      | Motion control              |

---
