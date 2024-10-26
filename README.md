# DIY Simple Router UPS

## Description

Welcome to my DIY project where I've designed a custom Uninterruptible Power Supply (UPS) for my home network equipment. This solution is aimed at providing power during long outages (16-18 hours a day). Rather than using a commercial UPS from Aliexpress which consumed high current from 18650 cells—cells I wanted to reserve for a future power bank project for my laptop—I decided to create a UPS using generic, cost-effective components.

The primary goal of this project was to repurpose a collection of Li-polymer batteries of different sizes and various components purchased in bulk from Aliexpress, which I had never previously used.

![DIY UPS Setup](https://github.com/tornadox/diy-simple-router-ups/blob/main/UPS.png?raw=true)

### Design Overview

The circuit design is built to support two Ethernet switches (one operating at 5V, the other at 9V), alongside a router and an Optical Network Unit (ONU) that require 12V. Each Li-poly cell is paired with its own Battery Management System (BMS) and they are connected in parallel. While the total capacity is uncertain, I estimate it to be around 10Ah.

For voltage regulation, I employed LM2596 DC-DC converters, which theoretically can handle up to 3A; however, they tend to overheat (you can see more on this issue in [this video](https://www.youtube.com/watch?v=hBOJDlftKTU)). I utilized two LM2596 modules—one for charging and another for powering the devices when AC power is available, which also helps mitigate heat during charging times.

### Charging Solution

For the charging solution, I used TP4056 modules, which I had available. Each module is capable of charging at 1A. However, this slow charge rate meant they couldn't replenish the batteries sufficiently during the periodic 2-hour periods when electricity was present. To enhance the charging rate, I connected multiple TP4056 modules in parallel, allowing for a 2A charging capacity. There’s potential to add even one more, although heat management remains a priority as the LM2596 module is set to output 6V for heat reduction.

### Switching Mechanism

To switch between the LM2596 boards for battery and AC power, I employed two Schottky diodes. The output connects to four SX1308 (MT3608) DC-DC converters, each capable of handling up to 2A. Since I had several of these on hand, I allocated one for each device to simplify the setup.

### Housing and Cooling

To improve thermal management, the batteries are separated from the DC converters and Schottky diodes, housed in two plastic candy containers. I'm also considering a 3D-printed enclosure to enhance ventilation and heat dissipation.

### Performance

This UPS setup has been operational for over two months without any issues. It successfully provides 5-6 hours of power supply and can fully recharge within 7-9 hours after being completely drained.

## Conclusion

This project embodies an efficient way to maintain network connectivity during power outages by repurposing spare components and batteries. I invite you to explore the code, schematic, and any potential improvements this DIY UPS can offer!

Feel free to contribute, suggest improvements, or ask questions!
