## FMS Band

> [!WARNING]
> **This page is still under construction**


### Introduction
Hand gesture recognition is a vital component in the development of technologies such as prosthetics, exoskeletons, and virtual reality systems, offering intuitive and user-friendly control interfaces. However, the high cost and dependency on expensive software of commercially available solutions create barriers to their accessibility, particularly for research and clinical cases. The design focuses on fitment for consistent sensor contact, accessibility through affordable components and open-source tools, and modularity for customization and integration with various systems.This manual aims to guide the process of constructing a low-cost, open-source Force Myography (FMG) device.  


### FMG
This design uses FMG technology to detect radial muscle forces on the forearm, capturing patterns from hand gestures. The process relies on sensors picking up measurements that reflect the muscle activity that are later analyzed offline using a linear discriminant analysis (LDA) classifier to correlate the FMG (voltage) data with each hand gesture.


### Materials
| Item  | Quantity | Cost Per Unit  | Total Cost |
| ------------- | ------------- |------------- | ------------- |
| FSR400  | 8  | $2.99 | $23.92  |
| Velcro Strap | 1 | $8.49 | $8.49  |
| Velcro Adhesive Tape | 1 | $8.99 | $8.99  |
| 30 AWG Flexible Cable | 1 | $12.99 | $12.99  |
| PCB Protoboard (×20) | 1 | $9.99 | $9.99  |
| ABS Resin | 1 | $44.09 | $44.09  |
| Copper Tape | 1 | $6.88 | $6.88  |
| PDNS Domes (x100) | 1 | $7.99 | $7.99  |
| 7.5 kOhm Resistors (x100) | 1 | $5.49 | $5.49  |
| Wiring Sheath | 1 | $7.63 | $7.63  |
| Hot Glue Sticks (x10) | 1 | $2.92 | $2.92 |
| Solder | 1 | $5.79 | $5.79  |
| Dupont Connectors | 1 | $12.99 | $12.99 |
| Total Cost | | | $162.60 |


### Cradle/Sensor Desgin
The FMG band’s core components include FSR400 sensors integrated into a voltage divider which converts the resistance of the FSRs into measurable voltage signals based on the force applied. The mechanical design consists of 3D-printed resin cradles to hold the FSRs in place, adhesive polydimethylsiloxane (PDMS) domes for even force distribution (seen mounted on the sensors), and a Velcro strap for adjustability. The modular design allows for easy sensor replacement or integration of additional components as needed. 


<img width="537" alt="Screenshot 2025-02-19 at 13 11 41" src="https://github.com/user-attachments/assets/e11b0ac1-9f9a-4b6b-ab90-5e9c5a8d20e4" />








