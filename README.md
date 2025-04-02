## FMS Band

> [!WARNING]
> **This page is still under construction**


## Introduction
Hand gesture recognition is a vital component in the development of technologies such as prosthetics, exoskeletons, and virtual reality systems, offering intuitive and user-friendly control interfaces. However, the high cost and dependency on expensive software of commercially available solutions create barriers to their accessibility, particularly for research and clinical cases. The design focuses on fitment for consistent sensor contact, accessibility through affordable components and open-source tools, and modularity for customization and integration with various systems.This manual aims to guide the process of constructing a low-cost, open-source Force Myography (FMG) device.  


### FMG
This design uses FMG technology to detect radial muscle forces on the forearm, capturing patterns from hand gestures. The process relies on sensors picking up measurements that reflect the muscle activity that are later analyzed offline using a linear discriminant analysis (LDA) classifier to correlate the FMG (voltage) data with each hand gesture.


## Materials
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


## Cradle/Sensor Desgin
The FMG band’s core components include FSR400 sensors integrated into a voltage divider which converts the resistance of the FSRs into measurable voltage signals based on the force applied. The mechanical design consists of 3D-printed resin cradles to hold the FSRs in place, adhesive polydimethylsiloxane (PDMS) domes for even force distribution (seen mounted on the sensors), and a Velcro strap for adjustability. The modular design allows for easy sensor replacement or integration of additional components as needed. 


<img width="537" alt="Screenshot 2025-02-19 at 13 11 41" src="https://github.com/user-attachments/assets/e11b0ac1-9f9a-4b6b-ab90-5e9c5a8d20e4" />


> PDMS Dome, FSR400, and Sensor Cradle construction




## Circuit Design - Voltage Divider (VD)
Each FSR400 sensor is placed externally on a separate device (the velcro armband) and connected to the circuit board through dedicated pin headers. One pin of the FSR is connected to an external +5V source, while the other pins are connected to a junction on the circuit board. In this junction one end is linked to the 7.5 kΩ resistor and another to the Sig0. The end of the resistor not connected to the pin junction is connected to ground. The output signal (Sig0) is measured at the junction between the FSR and resistor and is sent to an external microcontroller through another set of dedicated pins. This setup allows for modularity and easy sensor replacement while still providing an analog voltage output that varies based on applied force.



<img width="569" alt="Screenshot 2025-03-10 at 13 00 32" src="https://github.com/user-attachments/assets/a80c65fa-925a-4efc-ae71-c7b879c54dba" />


> Single VD channel replicated 8 times across the board for each sensor


### Assembling the VD Circuit
Solder pins for the output voltage node (Sig0), FSR400, and Source connection to the protoboard
> image of the pins 


Solder all 7.5 kΩ resistors with enough room between it and the pins to create a junction


> Image to be added


Create a junction that connects one end of all the resistors and bring that connection to ground


> Image to be added


Use one pin from Sig0 and connect to ground 
Use one pin from FSR400 and connect to +5v


> Image to be added


Create a junction between the FSR400 pin header, Sig0 pin header, and the 7.5k resistor
Solder a wire from Sig0 pin header and the resistor that connect to the FSR400 pin header 


> Image to be added









