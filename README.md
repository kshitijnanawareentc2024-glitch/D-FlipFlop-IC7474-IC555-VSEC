# Implementation of D Flip-Flop (IC 74HC74) with IC 555 Clock Circuit

This repository contains the hardware implementation, schematic design, and activity report for the **Vocational Skill Enhancement Course (VSEC - Code: ET24305)** project[cite: 3].

---

## 📌 Project Overview
This project demonstrates a clocked **D Flip-Flop (IC 74HC74)** circuit driven by an **NE555 Timer** operating in astable mode to generate continuous clock pulses[cite: 4]. The circuit runs on a regulated +5V DC power supply using an **LM7805** voltage regulator[cite: 4, 7].

---

## ⚙️ Components Required
| Component | Type / Value | Quantity | Description |
| :--- | :--- | :---: | :--- |
| **Clock Generator** | NE555 Timer (DIP-8) | 1 | Generates periodic square-wave clock pulses in astable mode[cite: 4, 8] |
| **D Flip-Flop IC** | 74HC74 (DIP-14) | 1 | Dual positive-edge-triggered D-type flip-flop[cite: 4, 6] |
| **Voltage Regulator** | LM7805 | 1 | Regulates DC supply voltage down to +5 V[cite: 4, 7] |
| **Input Switch** | Push Button | 1 | Provides manual logic state to D input[cite: 4, 8] |
| **Status LEDs** | Red / Green LEDs | 3 | Visual indicators for CLK, Q, and Q̄ outputs[cite: 4, 8] |
| **Passive Components**| $R_A=3.9\text{ k}\Omega, R_B=68\text{ k}\Omega, C=10\mu\text{F}$ | Various | Astable timing resistors/capacitors & LED current limiters[cite: 4, 5] |

---

## ⚡ Circuit Operation
1. **Clock Signal Generation**: The NE555 timer operates in astable mode, producing a ~1 Hz continuous square-wave clock output at pin 3[cite: 4, 5, 8].
2. **Data Input ($D$)**: A push-button switch connected to pin 2 ($1D$) of the 74HC74 supplies logic HIGH ($1$) when pressed and logic LOW ($0$) when released via a pull-down resistor[cite: 7, 8].
3. **Edge Latching**: The 74HC74 samples input $D$ strictly on the **rising edge** of the clock pulse[cite: 4, 6, 8].
4. **Complementary Output Display**: Output $Q$ (pin 5) and complementary output $\bar{Q}$ (pin 6) drive separate LEDs to visually display stored bit states[cite: 4, 7, 8].

---

## 📊 Truth Table
| Clock Event | D Input | Q (Next State) | $\bar{Q}$ (Next State) | Description |
| :---: | :---: | :---: | :---: | :--- |
| Rising Edge (↑) | 0 | 0 | 1 | Reset State[cite: 8] |
| Rising Edge (↑) | 1 | 1 | 0 | Set State[cite: 8] |
| No Active Edge | X | $Q_{prev}$ | $\bar{Q}_{prev}$ | Retains previous state[cite: 8] |

---

## 📂 Project Resources
* **Full Report**: [`docs/Implementation_of_D_Flip_Flop_Using_IC555.pdf`](docs/)[cite: 3]
* **Hardware Circuit**: [`images/circuit_hardware.jpg`](images/)[cite: 1, 11]

---

## 🎓 Course Details
* **Course**: Vocational Skill Enhancement Course (VSEC)[cite: 3]
* **Course Code**: ET24305[cite: 3]
* **Academic Year**: 2026-27[cite: 3]
