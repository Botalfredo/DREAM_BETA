# Flight Computer Electronics Calculations

This document explains the key calculations performed during the design of the flight computer electronics.

---

## 1. Optimal Ferrite Value Calculations

### 1.1 Low-Pass Filter Model

Each ferrite bead is used in series with a decoupling capacitor (1 µF) to form a low-pass filter. The cutoff frequency \( f_c \) of this filter is given by:

$$
f_c = \frac{1}{2\pi \sqrt{L \cdot C}}
$$

where:
- **\( L \)** is the equivalent inductance of the ferrite.
- **\( C \)** is the decoupling capacitor (1 µF).

### 1.2 Target Frequencies

- **Digital Interference:**  
  Major interference arises from the STM32F405 microcontroller operating around **168 MHz** and its harmonics.

- **Analog Interference:**  
  Interference around **27 MHz** needs to be blocked to protect sensitive analog signals.

### 1.3 Calculation for a Cutoff Frequency of 168 MHz

For \( f_c = 168\,\text{MHz} \) and \( C = 1\,\mu\text{F} = 1 \times 10^{-6}\,\text{F} \), the required inductance is calculated by rearranging the formula:

$$
L = \frac{1}{(2\pi \cdot f_c)^2 \cdot C}
$$

Substituting the values:

$$
L = \frac{1}{(2\pi \cdot 168 \times 10^6)^2 \cdot 1 \times 10^{-6}} \approx 0.14\,\mu\text{H}
$$

An equivalent inductance of approximately **0.14 µH** for filtering out interference near 168 MHz.

### 1.4 Calculation for a Cutoff Frequency of 27 MHz

For \( f_c = 27\,\text{MHz} \) with the same capacitor value:

$$
L = \frac{1}{(2\pi \cdot 27 \times 10^6)^2 \cdot 1 \times 10^{-6}} \approx 3.5\,\mu\text{H}
$$

An inductance of approximately **3.5 µH** is suitable for blocking interference around 27 MHz.

### 1.5 Ferrite Selection

Ferrite beads are typically characterized by their impedance at a given frequency rather than their inductance. To ensure effective attenuation:
- A ferrite with an impedance of **100–600 Ω at 100 MHz** is recommended between GND and AGND.
- A similar impedance is advised between +5V and +VCAM.

---

## 2. Power Supply Calculations

The flight computer is designed to operate with input batteries ranging from 3S to 6S. Two key voltage rails are considered: 5V and 10V.

### 2.1 5V Power Supply

The 5V rail must be capable of delivering the required current (e.g., 2A for Mateksys or 3A for SpeedyBee designs). A step-down regulator such as the **TPS54302DDCR** is used for this purpose. For more details, refer to the [TPS54302 datasheet](https://www.ti.com/lit/ds/symlink/tps54302.pdf).

### 2.2 10V Power Supply

The 10V rail is designed to supply peripherals such as cameras and VTX units. A regulator is chosen to work with:
- A minimum input voltage of **11.1V** (typical for a 3S battery)
- A maximum input voltage of **28V** (compatible with a 6S battery)

### 2.3 Voltage Divider Calculation for the TPS54302 Regulator

The output voltage \( V_{OUT} \) is set using a voltage divider composed of resistors \( R_2 \) and \( R_3 \). The relationship is given by:

$$
V_{OUT} = V_{REF} \times \left(1 + \frac{R_2}{R_3}\right)
$$

where:
- \( V_{REF} = 0.596\,V \) is the reference voltage.
- \( R_2 \) is chosen to be **100 kΩ**.

To achieve \( V_{OUT} \approx 10\,V \), we solve for \( R_3 \):

$$
R_3 = \frac{R_2}{\left(\frac{V_{OUT}}{V_{REF}} - 1\right)}
$$

Substitute the values:

$$
R_3 = \frac{100\,k\Omega}{\left(\frac{10}{0.596} - 1\right)} \approx 5.96\,k\Omega
$$

A standard resistor value of **6 kΩ** is chosen, which yields an output voltage of approximately **10 V**.

---
