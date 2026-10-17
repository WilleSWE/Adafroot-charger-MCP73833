# MCP73833 Li-Po/Li-Ion Charger (REV 1B)

A highly flexible Li-Po and Li-Ion battery charger built around the Microchip **MCP73833** IC. 
<img width="1188" height="972" alt="image" src="https://github.com/user-attachments/assets/b372d752-499c-401d-9506-0a31937f3168" />
<img width="1054" height="836" alt="image" src="https://github.com/user-attachments/assets/00af7e2c-1e55-4624-9166-5cdbe79dbdd1" />


This board features a selectable charging current via a 2x5 pin header, allowing you to quickly switch between preset currents using a standard 2.54mm jumper shunt. It also includes two configurable THT slots for any custom current limit under 1000mA.

## Key Features
- **USB-C Powered:** Input via a 6-pin USB-C plug (USB4125-GF).
- **Universal Battery Output:** Features JST-PH (2.0mm), JST-ZH (1.5mm), and PicoBlade (1.25mm) connectors to fit almost any hobby battery.
- **Dedicated LED Indicators:** Clear status lights for **Power Good (PG)**, **STAT1 (Charging)**, and **STAT2 (Complete)**.
- **Built-in Storage:** A handy 1x2 header to store your jumper pin when not in use.
- **On-Board Cheat Sheet:** A complete LED status truth table silkscreened directly onto the back of the PCB.

## Charging Current Calculation
The charging current is set by the though-hole resistors R4 R8 R9 R10 R11.
Formula is also available to google, but:
Charging current (mA) = 1000 / Rprog (KΩ)
For example, 10 KΩ resistor gives charging speed of 100mA. 
Meanwhile 20Ω is 50mA
And, 1 KΩ would be the physical limit of the charging IC ( 1 Amp ), so don't go lower than 1 kohm! *(Or you will let out the magic smoke, and you can only do that **once**)*

### Default Jumper Configurations:
- **50mA:** 20 kΩ resistor
- **100mA:** 10 kΩ resistor
- **213mA:** 4.7 kΩ resistor
- **1000mA:** 1 kΩ resistor
- **Spare 2 aka R11:** Open THT slot for any custom current under 1000mA (Minimum 1 kΩ).

## Bill of Materials (BOM)

### SMD Components (0603 & IC)
- **1x** MCP73833-FCI/UN (MSOP-10 package)
- **2x** 10 µF Ceramic Capacitors (0603)
- **2x** 5.1 kΩ Resistors (0603) – *For USB-C CC pins, so not exactly required but recommended*
- **3x** LEDs (0603) – *Red for PG, Blue for STAT1, Green for STAT2 is what i used*
- **3x** ~330 Ω Resistors (0603) – *Current limiting for LEDs*

### Connectors & THT Components
- **1x** USB-C Receptacle (GCT USB4125-GF or compatible 6-pin)
- **3x** JST 2-pin Battery Connectors (1.25mm, 1.5mm, 2.0mm pitch.) (Although, remember to only plug in one battery at a time! The plugs are connected together so differently charged batteries would try to even out without a limit on the current. Or cause a fire)
- **1x** 2x5 (or 2x 1x5) Female Pin Header (2.54mm pitch)
- **1x** 1x2 Female Pin Header (2.54mm pitch) – *Jumper storage*
- **1x** 2.54mm Jumper/Shunt
- **Up to 6x** THT Axial Resistors (Choose values based on desired mA, minimum 2 required for basic operation)

