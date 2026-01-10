

# DIODE – DETAILED EXPLANATION

## What is a Diode?

A **diode** is a **two-terminal semiconductor device** that allows **current to flow in only one direction** and blocks it in the opposite direction.

It acts like an **electrical check valve**
forward → allowed
reverse → blocked

---

## Why Diodes Exist

Electronic circuits need:

* Direction control of current
* AC to DC conversion
* Voltage protection
* Signal shaping

Diodes do these jobs silently, reliably, endlessly.

---

## Construction of a Diode

A diode is formed by joining:

* **P-type semiconductor**
* **N-type semiconductor**

This junction is called a **PN junction**.

### Terminals

| Terminal         | Name          |
| ---------------- | ------------- |
| Anode (P-side)   | Positive side |
| Cathode (N-side) | Negative side |

The cathode is usually marked with a **line** on the diode body.

---

## What Happens at the PN Junction?

When P and N materials join:

* Electrons from N move to P
* Holes from P move to N
* They recombine

This creates a region with no free charge carriers, called the **depletion region**.

It behaves like a natural barrier.

---

## Biasing of a Diode

A diode’s behavior depends on how voltage is applied.

---

## 1. Forward Bias

### Condition:

* Anode connected to positive
* Cathode connected to negative

### Result:

* Depletion region narrows
* Barrier potential reduces
* Current flows

### Forward Voltage Drop:

| Material        | Voltage |
| --------------- | ------- |
| Silicon diode   | ~0.7 V  |
| Germanium diode | ~0.3 V  |
| Schottky diode  | ~0.2 V  |

---

## 2. Reverse Bias

### Condition:

* Anode negative
* Cathode positive

### Result:

* Depletion region widens
* No current flows (ideally)

Only a very tiny **leakage current** exists.

---

## Breakdown of Diode

If reverse voltage exceeds a limit:

* Depletion region collapses
* Large current flows

This is called **breakdown**.

Two types:

* Zener breakdown
* Avalanche breakdown

Some diodes are designed to work here.

---

# V-I CHARACTERISTICS OF DIODE

The V-I curve shows diode behavior.

### Forward Region

* No current until threshold
* Sudden rise after cut-in voltage

### Reverse Region

* Very small current
* Sudden rise at breakdown voltage

---

# TYPES OF DIODES (DETAILED)

---

## 1. Rectifier Diode

### Purpose:

Convert AC to DC

### Used in:

* Power supplies
* Chargers
* Adapters

Handles high current and voltage.

---

## 2. Zener Diode

### Special Property:

Works in **reverse breakdown safely**

### Function:

Maintains constant voltage

### Used in:

* Voltage regulation
* Over-voltage protection

Example:
5.1 V Zener keeps output at 5.1 V.

---

## 3. LED (Light Emitting Diode)

### Special Property:

Emits light when forward biased

### Energy conversion:

Electrical → Light

### Uses:

* Indicators
* Displays
* Lighting

LED color depends on semiconductor material.

---

## 4. Schottky Diode

### Feature:

* Very low forward voltage drop
* Very fast switching

### Uses:

* High-speed circuits
* SMPS
* Logic level protection

---

## 5. Photodiode

### Feature:

* Produces current when light falls on it

### Uses:

* Light sensors
* Optical communication
* IR receivers

---

## 6. Laser Diode

### Feature:

* Emits coherent laser light

### Uses:

* Fiber optics
* Barcode scanners
* CD/DVD drives

---

## 7. Tunnel Diode

### Feature:

* Works on quantum tunneling
* Negative resistance region

### Uses:

* High-frequency oscillators

---

## 8. Varactor Diode

### Feature:

* Acts like a voltage-controlled capacitor

### Uses:

* RF tuning
* FM receivers

---

## 9. TVS Diode (Transient Voltage Suppressor)

### Feature:

* Protects against voltage spikes

### Uses:

* ESD protection
* Surge suppression

---

# Diode as a Rectifier

### Half-Wave Rectifier

* Uses one diode
* Converts half AC cycle

### Full-Wave Rectifier

* Uses two or four diodes
* Converts full AC cycle

Full-wave gives smoother DC.

---

# Practical Applications of Diode

* Power supplies
* Signal clipping and clamping
* Reverse polarity protection
* Free-wheeling diode in motors
* Logic circuits

---

## Important Exam Points

* Diode is **unidirectional**
* Forward bias conducts
* Reverse bias blocks
* Zener works in breakdown
* LED emits light
* Schottky has low voltage drop

---
