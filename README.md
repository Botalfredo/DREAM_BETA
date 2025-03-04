# DREAM_BETA

![Flight Controller](Images/1.jpg)

DREAM_BETA is an open source project dedicated to designing and developing a flight computer for FPV drones. The board is created to run the BetaFlight firmware.

---

## Project History

DREAM_BETA evolved from earlier personal. Starting with the LEVEL project in 2021, which focused on building flight controllers for various aerial vehicles, the concept matured through iterations like DREAM_ALPHA. DREAM_BETA represents the next step: adapting the flight controller design to meet modern FPV software.

---

## Repository Structure

The repository is organized as follows:

- **DREAM_BETA**
  - **Hardware**
    - **DB_ELRS_R1_(ELRS_Receiver)** – Design files for the ELRS radio receiver *(designed and fabricated, not yet tested)*
    - **DB_FC_R1_(Flight_Controller)** – Design files for the flight controller *(tested and validated; schematic corrections highlighted in orange have not been applied to the Gerber files)*
  - **Firmware/**
    - `config.h` – Configuration file with pin declarations and board-specific settings
    - `betaflight_4.5.0_STM32F405_DREAM_BETA.hex` – Precompiled BetaFlight firmware for the flight controller
  - **Images/**
    - `1.jpg` – Photo of the flight controller prototype

---

## Embedded Functionalities
✅ – Tested and confirmed to work
🟨 – Not yet tested
- **BetaFlight Firmware Support** ✅

- **Microcontroller STM32F405** ✅

- **IMU ICM42688p** ✅

- **Black Box W25Q128** ✅

- **Barometer DSP368** ✅

- **USB C** ✅  

- **OSD MAX7456**  ✅

- **GPS Interface** 🟨 
 
- **Magnetometer Interface** 🟨  

---

## Open Source Commitment

DREAM_BETA is released under an open source license. All design files, firmware, and documentation are freely available for anyone interested from the project.

---