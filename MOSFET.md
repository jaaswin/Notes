# MOSFET Explained Clearly

## 1. What is a MOSFET?

**MOSFET** stands for:

> **Metal Oxide Semiconductor Field Effect Transistor**

A MOSFET is a **voltage-controlled electronic device** mainly used for:

- Switching
- Amplification
- Motor control
- LED control
- Power control
- Voltage regulation

### Main Idea

> A small voltage applied to the **Gate** controls the current flowing between the **Drain** and **Source**.

Think of a MOSFET as an **electronically controlled switch**.

---

# 2. MOSFET Terminals

A MOSFET has three main terminals:

```text
        Gate (G)
           │
           │
       ┌───────┐
       │       │
Drain ─│ MOSFET│
  (D)  │       │
       └───────┘
           │
        Source (S)
Terminal	Name	Function
G	Gate	Controls the MOSFET
D	Drain	Current terminal
S	Source	Current terminal

There is also a Body/Bulk terminal inside the MOSFET structure.

In many discrete MOSFETs, the Body is internally connected to the Source.

3. How Does a MOSFET Work?

The most important concept is:

Gate Voltage
     ↓
Electric Field
     ↓
Channel Changes
     ↓
Drain-Source Current Changes

The Gate is separated from the semiconductor by an insulating oxide layer.

Therefore:

Ideally, almost no DC current flows into the Gate.

This gives MOSFETs a very high input impedance.

4. MOSFET as a Switch

One of the most important applications of a MOSFET is switching.

For example, a microcontroller may need to control a motor.

The microcontroller cannot usually drive the motor directly.

Instead:

          +12V
            │
          Motor
            │
            D
        ┌───────┐
MCU ────┤   G   │
GPIO    │ MOSFET│
        └───────┘
            S
            │
           GND

When the MCU provides the appropriate Gate voltage:

MOSFET → ON
Motor  → ON

When the Gate voltage is removed:

MOSFET → OFF
Motor  → OFF

Therefore:

The microcontroller provides the control signal, while the MOSFET handles the load current.

5. Types of MOSFET

The two main channel types are:

N-Channel MOSFET
P-Channel MOSFET

MOSFETs can also be classified as:

Enhancement MOSFET
Depletion MOSFET
6. N-Channel MOSFET

N-channel MOSFETs use electrons as the main charge carriers.

They are very commonly used for:

Low-side switching
Motor control
LED switching
Power supplies
DC-DC converters

For an N-channel MOSFET:

VGS = VG - VS

Where:

VG = Gate voltage
VS = Source voltage
VGS = Gate-to-Source voltage

The MOSFET starts conducting when:

VGS > VGS(th)

where VGS(th) is the threshold voltage.

7. Important: Threshold Voltage

Threshold voltage is written as:

VGS(th)

It is the Gate-to-Source voltage at which the MOSFET begins to conduct a specified small current under the datasheet's test conditions.

Important Warning

Do not assume:

VGS(th) = Fully ON voltage

For example, if:

VGS(th) = 2V

it does NOT mean:

2V → MOSFET fully ON

It only means the MOSFET has started conducting under the specified test condition.

To determine whether the MOSFET is properly ON, check the datasheet for:

RDS(on)

at the actual Gate voltage you are using.

This is especially important when controlling a MOSFET from a:

3.3V microcontroller
8. P-Channel MOSFET

P-channel MOSFETs use holes as the main charge carriers.

They are commonly used for:

High-side switching
Power switching
Battery circuits

Compared with N-channel MOSFETs:

Feature	N-Channel	P-Channel
Main carriers	Electrons	Holes
Common use	Low-side switching	High-side switching
Typical resistance	Lower	Higher
Gate control	Positive relative to Source	Negative relative to Source
9. Enhancement MOSFET

Enhancement MOSFETs are normally OFF.

For example, an N-channel enhancement MOSFET:

Gate LOW
   ↓
MOSFET OFF

Apply a sufficiently positive Gate voltage:

Gate HIGH
   ↓
Channel forms
   ↓
MOSFET ON

Therefore:

Enhancement MOSFET = Normally OFF

Enhancement MOSFETs are very common in switching applications.

10. Depletion MOSFET

A depletion MOSFET behaves differently.

It is normally ON.

Applying the appropriate Gate voltage reduces the channel current and can eventually turn the device OFF.

Therefore:

Enhancement → Normally OFF
Depletion   → Normally ON

This is an important interview point.

11. MOSFET Operating Regions

MOSFETs have several operating regions.

For basic embedded hardware, understand these three:

Cutoff
Triode/Linear
Saturation
11.1 Cutoff Region

The MOSFET is OFF.

For an N-channel MOSFET:

VGS < VGS(th)

Approximately:

ID ≈ 0

Think:

Cutoff = OFF switch
11.2 Triode / Linear Region

The MOSFET conducts strongly and behaves approximately like a voltage-controlled resistance.

This is important when using the MOSFET as an ON switch.

A good switching MOSFET should have a low:

RDS(on)

Think:

Triode/Linear Region = ON switch
11.3 Saturation Region

In the MOSFET saturation region, the Drain current is primarily controlled by the Gate voltage.

This region is commonly used for:

Amplification
Analog circuits
Important

Do not confuse MOSFET saturation with BJT saturation.

They have different meanings.

12. Low-Side Switching

Low-side switching is very common in embedded systems.

Example: controlling an LED.

       +5V
        │
       LED
        │
     Resistor
        │
        D
      N-MOSFET
        S
        │
       GND

MCU GPIO ───── G
GPIO LOW
GPIO LOW
   ↓
VGS ≈ 0
   ↓
MOSFET OFF
   ↓
LED OFF
GPIO HIGH
GPIO HIGH
   ↓
VGS becomes positive
   ↓
MOSFET ON
   ↓
Current flows
   ↓
LED ON
13. Why Use a MOSFET with a Microcontroller?

Suppose a microcontroller GPIO can only safely supply a small current.

A motor may require much more current.

Do not connect:

MCU GPIO ─── Motor

Instead:

MCU GPIO
    │
    ↓
MOSFET Gate
    │
    ↓
MOSFET controls
    │
    ↓
Motor current

The MCU controls the MOSFET with a small signal.

The MOSFET controls the larger load current.

14. Important MOSFET Parameters

When selecting a MOSFET, always check the datasheet.

Important parameters include:

VDS
ID
VGS
VGS(th)
RDS(on)
Qg
15. VDS

VDS means:

Drain-to-Source Voltage

It is the voltage between Drain and Source.

For example:

VDS(max) = 30V

means the MOSFET has a specified maximum Drain-to-Source voltage rating of 30 V.

You should provide suitable voltage margin rather than operating continuously at the absolute maximum.

16. ID

ID means:

Drain Current

It represents the Drain current rating under specified conditions.

For example:

ID = 10A

However, do not assume the MOSFET can always carry 10 A in every circuit.

Actual current capability depends on:

Temperature
Package
PCB design
Cooling
RDS(on)
Operating conditions
17. RDS(on) ⭐⭐⭐⭐⭐

RDS(on) means:

Drain-to-Source ON Resistance

When a MOSFET is ON, it still has some resistance.

A lower:

RDS(on)

generally means:

Lower voltage drop
Lower power loss
Less heating
Power Loss

The approximate conduction power loss is:

P = I² × RDS(on)
Example

Suppose:

I = 2A
RDS(on) = 0.05Ω

Then:

P = I² × RDS(on)

P = 2² × 0.05

P = 4 × 0.05

P = 0.2W

So approximately:

Power loss = 0.2W

That power becomes heat.

18. VGS

VGS means:

Gate-to-Source Voltage

It is:

VGS = VG - VS

For an N-channel MOSFET:

Higher VGS
     ↓
Stronger channel
     ↓
Lower RDS(on)
     ↓
Higher current capability

The exact behavior depends on the particular MOSFET and its datasheet.

19. Gate Charge

Gate charge is represented by:

Qg

A MOSFET Gate behaves somewhat like a capacitor during switching.

When turning ON:

MCU / Gate Driver
       ↓
Charges Gate
       ↓
MOSFET turns ON

When turning OFF:

MCU / Gate Driver
       ↓
Discharges Gate
       ↓
MOSFET turns OFF

Gate charge becomes particularly important in:

High-frequency switching
PWM
Power converters
Motor control
20. MOSFET Body Diode

A practical MOSFET contains an intrinsic diode called the:

Body diode

It is important when controlling:

Motors
Relays
Solenoids
Inductive loads
Power converters

Inductive loads can produce voltage spikes when their current is suddenly interrupted.

Therefore, the current path and protection components must be designed correctly.

21. Gate Resistor

A resistor can be placed between the microcontroller and MOSFET Gate:

MCU GPIO ──[R]── Gate

A Gate resistor can help:

Limit peak Gate current
Reduce ringing
Control switching speed
Reduce electromagnetic interference

The exact value depends on the circuit and switching requirements.

22. Pull-Down Resistor

A pull-down resistor can be connected to the Gate:

MCU GPIO ───── Gate
               │
             [10kΩ]
               │
              GND

Why use it?

During MCU startup or reset, the GPIO may temporarily be floating.

The pull-down ensures:

GPIO floating
     ↓
Gate pulled LOW
     ↓
MOSFET OFF

This prevents an unwanted load from turning ON.

23. MOSFET vs BJT

This is a common interview question.

MOSFET	BJT
Voltage-controlled	Current-controlled
Gate controls current	Base controls current
Very high input impedance	Lower input impedance
Ideally almost no DC Gate current	Base requires current
Common in switching	Common in switching and amplification
Uses electric field	Uses current injection
Easy Memory Trick
MOSFET → Voltage controls current

BJT → Current controls current
24. MOSFET Applications in Embedded Systems

MOSFETs are commonly used for:

                 MOSFET
                    │
       ┌────────────┼────────────┐
       ↓            ↓            ↓
      LED         Motor        Relay
       │            │            │
       ↓            ↓            ↓
    Switching     Control     Switching

       ┌────────────┼────────────┐
       ↓            ↓            ↓
   Solenoid      Battery      Power
    Control      Protection   Switching

Other applications include:

PWM motor control
DC-DC converters
Load switching
Battery management
Power supplies
LED drivers
Reverse polarity protection
25. MOSFET in PWM Motor Control

MOSFETs are very important in PWM applications.

MCU
 │
 │ PWM
 ↓
MOSFET
 │
 ↓
Motor

The MCU rapidly switches the MOSFET:

ON → OFF → ON → OFF → ON → OFF

By changing the duty cycle:

Low duty cycle  → Lower average power
High duty cycle → Higher average power

Example:

20% PWM → Low average power
50% PWM → Medium average power
80% PWM → High average power

This is one of the most useful connections between:

Digital Electronics
        ↓
Microcontroller
        ↓
PWM
        ↓
MOSFET
        ↓
Motor / Load
26. Important Difference: Threshold Voltage vs Fully ON

This is a very common interview trap.

Suppose:

VGS(th) = 2V

You should NOT say:

"The MOSFET is fully ON at 2 V."

Correct understanding:

VGS(th)
   ↓
MOSFET starts conducting

For a MOSFET to work efficiently as a switch:

Choose appropriate VGS
        ↓
Check RDS(on)
        ↓
Check datasheet conditions

For a 3.3 V MCU, choose a MOSFET whose datasheet specifies suitable RDS(on) at a Gate voltage compatible with your MCU.

27. Simple Mental Model

Think of a MOSFET as an electronic water valve.

Gate voltage
     ↓
Controls the valve
     ↓
Controls current
     ↓
Drain → Source

But unlike a mechanical valve, the MOSFET uses an electric field to control the current.

28. Quick Summary
MOSFET
│
├── Full Form
│   └── Metal Oxide Semiconductor Field Effect Transistor
│
├── Terminals
│   ├── Gate
│   ├── Drain
│   └── Source
│
├── Main Types
│   ├── N-Channel
│   └── P-Channel
│
├── Operating Types
│   ├── Enhancement
│   └── Depletion
│
├── Important Parameters
│   ├── VDS
│   ├── ID
│   ├── VGS
│   ├── VGS(th)
│   ├── RDS(on)
│   └── Qg
│
└── Applications
    ├── Switching
    ├── Motor Control
    ├── LED Control
    ├── PWM
    ├── Power Supplies
    └── Battery Systems
