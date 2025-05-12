
## FMS Band
> [!WARNING]  
> **This page is still under construction**

## Introduction
Hand gesture recognition is a vital component in the development of technologies such as prosthetics, exoskeletons, and virtual reality systems, offering intuitive and user-friendly control interfaces. However, the high cost of production, including expensive commercial software, create barriers to their accessibility, particularly for research and clinical cases. The armband design focuses on fitment for consistent sensor contact, accessibility through affordable components and open-source tools, and modularity for customization and integration with various systems. This manual aims to guide the process of constructing a low-cost, open-source Force Myography (FMG) device.

### FMG
This design uses FMG technology to detect radial muscle forces on the forearm, capturing patterns from hand gestures. The process relies on sensors picking up measurements that reflect the muscle activity that are later analyzed offline using a linear discriminant analysis (LDA) classifier to correlate the FMG (voltage) data with each hand gesture.

## Materials
| Item | Quantity | Cost Per Unit | Total Cost |
|------|----------|----------------|------------|
| FSR400 | 8 | $2.99 | $23.92 |
| Velcro Strap | 1 | $8.49 | $8.49 |
| Velcro Adhesive Tape | 1 | $8.99 | $8.99 |
| 30 AWG Flexible Cable | 1 | $12.99 | $12.99 |
| PCB Protoboard (×20) | 1 | $9.99 | $9.99 |
| ABS Resin | 1 | $44.09 | $44.09 |
| Copper Tape | 1 | $6.88 | $6.88 |
| PDMS Domes (x100) | 1 | $7.99 | $7.99 |
| 7.5 kOhm Resistors (x100) | 1 | $5.49 | $5.49 |
| Wiring Sheath | 1 | $7.63 | $7.63 |
| Hot Glue Sticks (x10) | 1 | $2.92 | $2.92 |
| Solder | 1 | $5.79 | $5.79 |
| Dupont Connectors | 1 | $12.99 | $12.99 |
| **Total Cost** | | | **$162.60** |

## Cradle/Sensor Design
The FMG band’s core components include FSR400 sensors integrated into a voltage divider which converts the resistance of the FSRs into measurable voltage signals based on the force applied. The mechanical design consists of 3D-printed resin cradles to hold the FSRs in place, adhesive polydimethylsiloxane (PDMS) domes for even force distribution (seen mounted on the sensors), and a Velcro strap for adjustability. The modular design allows for easy sensor replacement or integration of additional components as needed.

<img width="537" alt="Screenshot 2025-02-19 at 13 11 41" src="https://github.com/user-attachments/assets/e11b0ac1-9f9a-4b6b-ab90-5e9c5a8d20e4" />

> PDMS Dome, FSR400, and Sensor Cradle


### Cradle Construction

1. Print eight cradles using the `Real_Holder_V9.stl` provided.  
   > *Image to be added*

2. Place an FSR400 pressure sensor into each cradle and use super glue to secure the sensor in position.  
   > *Image to be added*

3. Carefully fit a PDMS dome to the sensing surface of each FSR, making sure there is full coverage over the active sensing region.  
   > *Image to be added*

4. Bend the FSR solder tabs at a 90° angle so they lay flat on the cradle.  
   > *Image to be added*

5. Solder the input and output wires to the solder tabs, and secure the connections with a thin layer of hot glue.
   > *Image to be added*

6. Mount the completed sensor units onto a Velcro base band for easy adjustment and modularity.  
   > *Image to be added*

## Circuit Design - Voltage Divider (VD)
Each FSR400 sensor is placed externally on the Velcro armband and connected to the circuit board through dedicated pin headers. One pin of the FSR is connected to an external +5V source, while the other pins are connected to a junction on the circuit board. In this junction, one end is linked to the 7.5 kΩ resistor and another to an output signal device, Sig0. The end of the resistor not connected to the pin junction is connected to GND. Sig0 is measured at the junction between the FSR and resistor and is sent to an external microcontroller through another set of dedicated pins.



<img width="569" alt="Screenshot 2025-03-10 at 13 00 32" src="https://github.com/user-attachments/assets/a80c65fa-925a-4efc-ae71-c7b879c54dba" />

> Single VD channel replicated 8 times across the board for each sensor


### Assembling the VD Circuit

1. Solder pin headers for Sig0, FSR400, GND, 5V onto the protoboard.

<img width="400" alt="Screenshot 2025-02-19 at 13 11 41" src="https://github.com/user-attachments/assets/b738faa4-5c97-477d-ac81-c4b283eb0c8e"/>
<img width="400" alt="Screenshot 2025-02-19 at 13 11 41" src="https://github.com/user-attachments/assets/5f1206dc-f7f6-4082-907f-d387d3648fc6"/>



2. Solder 7.5 kΩ resistors to the protoboard, leaving space between the resistors and the pin headers. Connect one end of each 7.5 kΩ resistor together to form a junction, then solder one end of that junction to GND.  

   <img width="300" alt="Screenshot 2025-02-19 at 13 11 41" src="https://github.com/user-attachments/assets/a0360afc-d4e6-4dad-934e-3db3ade64613"/>
   <img width="600" alt="Screenshot 2025-02-19 at 13 11 41" src="https://github.com/user-attachments/assets/01a0ea55-2bdc-4076-8c41-bfbe4191c678"/>


3. Create a junction between the resistors and the FSR400 leaving space for another wire to come in.

 <img width="300" alt="Screenshot 2025-02-19 at 13 11 41" src="https://github.com/user-attachments/assets/d184baf1-6f2b-4e9b-97d0-5607e473f088"/>
 <img width="600" alt="Screenshot 2025-02-19 at 13 11 41" src="https://github.com/user-attachments/assets/bcb9cf2e-1cca-423b-a06e-2f4178982906"/>




4. Create a junction between the FSR400 pin header, the Sig0 pin header, and the free end of a 7.5 kΩ resistor. One end of the wire should be in the junction while the other end should connect to the Sig0 pin header.

 <img width="300" alt="Screenshot 2025-02-19 at 13 11 41" src="https://github.com/user-attachments/assets/c582ac21-7143-4f64-912d-94c2ea2688de"/>
 <img width="500" alt="Screenshot 2025-02-19 at 13 11 41" src="https://github.com/user-attachments/assets/1709cc80-8568-45e6-9574-1f5faa0d99fa"/>

 
5. Connect one pin of the FSR400 header to +5V and one pin of the Sig0 header to GND.  
   > *Image to be added*




