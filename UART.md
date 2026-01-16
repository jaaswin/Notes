UART (**Universal Asynchronous Receiver/Transmitter**) is one of the most widely used serial communication protocols in embedded systems and microcontroller-based designs. It enables **full-duplex**, **asynchronous** data exchange between two devices using simple hardware and minimal wiring.

---

## 1. What is UART?

UART is a **hardware communication protocol** that converts **parallel data** from a processor into **serial data** for transmission and converts received serial data back into parallel form.
It is called *asynchronous* because it does **not require a shared clock signal** between the transmitting and receiving devices.

---

## 2. Basic Features of UART

* **Asynchronous communication** (no clock line)
* **Full-duplex** communication (data can be sent and received simultaneously)
* Uses **serial data transmission**
* Simple hardware interface
* Widely used for **debugging, GPS, Bluetooth, GSM, sensors**, etc.

---

## 3. UART Hardware Lines

A basic UART system uses **two main signal lines**:

1. **TX (Transmit)** – Sends data
2. **RX (Receive)** – Receives data

Optional lines:

* **GND** – Common ground (must be shared)
* **RTS (Request to Send)** and **CTS (Clear to Send)** – Used for hardware flow control

> Minimum requirement: **TX, RX, and GND**

---

## 4. UART Communication Principle

Since UART has no clock signal, both devices must agree on communication parameters **before data transfer** begins.

### Key Parameters:

* **Baud Rate** (speed of communication, e.g., 9600, 115200 bps)
* **Number of data bits** (usually 5–9 bits, commonly 8)
* **Parity bit** (error checking: None, Even, Odd)
* **Stop bits** (1 or 2)

These settings must be **identical on both devices**.

---

## 5. UART Data Frame Format

A UART transmission consists of a **frame** with the following parts:

```
| Start Bit | Data Bits | Parity Bit (optional) | Stop Bit(s) |
```

### 1. Start Bit

* Always **LOW (0)**
* Signals the beginning of data transmission
* Alerts the receiver to start sampling

### 2. Data Bits

* Usually **8 bits**
* Transmitted **LSB (Least Significant Bit) first**

### 3. Parity Bit (Optional)

* Used for simple error detection
* Types:

  * **Even parity**
  * **Odd parity**
  * **No parity**

### 4. Stop Bit(s)

* One or two **HIGH (1)** bits
* Indicates the end of the data frame

---

## 6. Timing and Baud Rate

The **baud rate** defines how fast bits are transmitted.

Example:

* Baud rate = **9600**
* Bit time = **1 / 9600 ≈ 104 µs per bit**

The receiver samples the incoming data based on this timing.
A small mismatch (±2–3%) is usually tolerated.

---

## 7. UART Communication Process (Step-by-Step)

1. TX line remains HIGH when idle
2. Transmitter sends a LOW start bit
3. Data bits are sent sequentially
4. Parity bit is added (if enabled)
5. Stop bit(s) are sent
6. Line returns to idle HIGH state

---

## 8. UART Flow Control

Flow control prevents data loss when the receiver cannot process data fast enough.

### 1. Hardware Flow Control

* Uses **RTS/CTS** signals
* Reliable but requires extra wires

### 2. Software Flow Control

* Uses special characters like **XON/XOFF**
* No extra wires, but slower

---

## 9. Advantages of UART

* Simple and easy to implement
* Requires only two wires
* No clock synchronization issues
* Widely supported by microcontrollers
* Suitable for low-speed communication

---

## 10. Disadvantages of UART

* Limited speed compared to SPI or I²C
* No built-in addressing (only point-to-point)
* Not ideal for multi-device communication
* Error detection is minimal (parity only)

---

## 11. Applications of UART

* Microcontroller debugging (serial monitor)
* GPS modules
* Bluetooth modules (HC-05, HC-06)
* GSM/GPRS modules
* Communication between microcontrollers
* PC serial communication (USB-to-UART)

---

## 12. UART vs Other Protocols

| Feature    | UART   | SPI  | I²C    |
| ---------- | ------ | ---- | ------ |
| Clock      | No     | Yes  | Yes    |
| Speed      | Medium | High | Medium |
| Addressing | No     | No   | Yes    |
| Wires      | 2      | 4+   | 2      |
| Duplex     | Full   | Full | Half   |

---

## 13. Summary

UART is a **simple, reliable, and widely used serial communication protocol** for point-to-point data transfer. Its asynchronous nature makes it easy to use without complex timing hardware, making it ideal for embedded systems, debugging, and communication with peripheral modules.

---
