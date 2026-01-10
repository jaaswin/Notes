
# TRANSISTOR 

## Definition

A **transistor** is a **three-terminal semiconductor device** that controls the flow of current or voltage and is used for **switching, amplification, signal modulation, and regulation**.

It is made using **semiconductor materials** like **silicon** or **germanium**, whose conductivity can be precisely controlled.

---

## Why Semiconductor?

Semiconductors sit between:

* Conductors (copper)
* Insulators (rubber)

Their conductivity can be changed by:

* Adding impurities (doping)
* Applying voltage
* Temperature change

This controllability is the soul of the transistor.

---

## Basic Functions of a Transistor

1. **Switching**
   ON or OFF control of current

2. **Amplification**
   Small input signal → large output signal

3. **Oscillation**
   Signal generation in communication circuits

4. **Regulation**
   Voltage and current control

---

# MAJOR TYPES OF TRANSISTORS

Transistors are broadly classified into **two main families**:

## 1. BJT (Bipolar Junction Transistor)

## 2. FET (Field Effect Transistor)

Let’s explore both in depth.

---

# 1. BIPOLAR JUNCTION TRANSISTOR (BJT)

### Why “Bipolar”?

Because **two types of charge carriers** take part:

* Electrons
* Holes

---

## Structure of BJT

A BJT has **three semiconductor regions**:

1. **Emitter (E)**
   Heavily doped
   Supplies charge carriers

2. **Base (B)**
   Very thin and lightly doped
   Controls the transistor

3. **Collector (C)**
   Moderately doped
   Collects charge carriers

---

## Types of BJT

### 1. NPN Transistor

### 2. PNP Transistor

---

### NPN Transistor (Most Common)

**Structure:**
N-type | P-type | N-type

**Working Principle:**

* Base-emitter junction forward biased
* Collector-base junction reverse biased
* Electrons flow from emitter to collector

A **small base current** allows a **large collector current**.

Used in:

* Amplifiers
* Switching circuits
* Microcontroller interfacing

---

### PNP Transistor

**Structure:**
P-type | N-type | P-type

**Working Principle:**

* Current flows from emitter to collector
* Base voltage must be lower than emitter

Used where:

* Negative voltage control is required
* Complementary circuits

---

## Modes of Operation of BJT

| Mode           | Condition                     | Application      |
| -------------- | ----------------------------- | ---------------- |
| Cut-off        | No base current               | OFF state        |
| Active         | Base-emitter forward biased   | Amplification    |
| Saturation     | Both junctions forward biased | ON state         |
| Reverse-active | Rare                          | Special circuits |

---

## BJT Current Relationship

[
I_E = I_B + I_C
]

Current gain:
[
\beta = \frac{I_C}{I_B}
]

This explains amplification.

---

# 2. FIELD EFFECT TRANSISTOR (FET)

### Why “Field Effect”?

Because **electric field** controls the current, not current itself.

---

## Advantages of FET over BJT

* Voltage controlled
* Very high input impedance
* Low power consumption
* Less heat

This makes FETs ideal for **modern electronics**.

---

## Types of FET

### 1. JFET (Junction FET)

### 2. MOSFET (Metal Oxide Semiconductor FET)

---

# JFET (Junction Field Effect Transistor)

### Terminals:

* Gate (G)
* Drain (D)
* Source (S)

### Working:

* Gate-source junction is reverse biased
* Voltage controls channel width
* Controls drain current

### Types:

* N-channel JFET
* P-channel JFET

Used in:

* Low-noise amplifiers
* Audio circuits

---

# MOSFET (Most Important Type)

MOSFETs dominate ICs and microcontrollers 🧠

---

## MOSFET Terminals

| Terminal | Role                        |
| -------- | --------------------------- |
| Gate     | Control voltage             |
| Drain    | Current input               |
| Source   | Current output              |
| Body     | Usually connected to source |

---

## Types of MOSFET

### Based on Mode of Operation

#### 1. Enhancement Mode MOSFET

* OFF by default
* Turns ON when gate voltage is applied

Most commonly used type.

#### 2. Depletion Mode MOSFET

* ON by default
* Turns OFF when gate voltage is removed

---

### Based on Channel Type

| Type             | Symbol                       |
| ---------------- | ---------------------------- |
| N-channel MOSFET | High speed, low resistance   |
| P-channel MOSFET | Used for high-side switching |

---

## MOSFET Working (Enhancement N-channel)

* Gate voltage applied
* Electric field forms a channel
* Current flows from drain to source
* No gate current flows

Perfect for PWM control.

---

## MOSFET vs BJT (Quick Comparison)

| Feature         | BJT      | MOSFET    |
| --------------- | -------- | --------- |
| Control         | Current  | Voltage   |
| Input impedance | Low      | Very high |
| Speed           | Moderate | Very high |
| Power loss      | More     | Less      |
| Use in MCU      | Limited  | Excellent |

---

# Special Types of Transistors

### Darlington Transistor

* Two BJTs combined
* Very high current gain

### Phototransistor

* Controlled by light
* Used in sensors

### Power Transistor

* Handles high current and voltage

### RF Transistor

* Used in high-frequency circuits

---

# Practical Applications

* Logic gates
* Amplifiers
* Motor drivers
* Switching regulators
* Communication systems
* Embedded systems projects

---

