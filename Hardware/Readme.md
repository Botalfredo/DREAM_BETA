# Hardware Documentation

This folder contains all the hardware design files and documentation for the project :

- **DB_ELRS_R1_(ELRS_Receiver)**
- **DB_FC_R1_(Flight_Controleur)**

---

## DB_ELRS_R1_(ELRS_Receiver)

### Overview
This directory contains the design files for the ELRS radio receiver. The receiver is intended to provide a communication link for drone control using the ExpressLRS protocol.

### Status
- **Design:** Completed and fully documented.
- **Manufacturing:** Completed.
- **Testing:** Not yet tested.

### Contents
- **Schematics:** PDF electronics circuit diagrams.
- **PCB Layout Files:** Gerber files prepared for PCB fabrication.
---

## DB_FC_R1_(Flight_Controleur)

### Overview
This directory contains the design files for the flight controller, The flight controller has been tested and validated during initial flight trials.

### Status
- **Design:** Completed and validated through testing.
- **Manufacturing:** Completed.
- **Testing:** Successfully tested and operational.
- **Known Issues:** Corrections marked in orange on the schematic have not been applied to the Gerber files.

### Contents
- **Schematics:** Complete electrical diagrams of the flight controller. _Note:_ Some issues highlighted in orange in the schematic (indicating required corrections) have not been transferred to the PCB Gerber files.
- **PCB Layout Files:** Gerber files for manufacturing the flight controller. Ensure that the pending corrections from the schematic are addressed in future revisions.
---
