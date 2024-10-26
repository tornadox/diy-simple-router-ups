Hi!

I've made this DIY UPS for my home network equipment for the long hours without electricity (16-18 hours per day). I already had a commercial UPS from Aliexpress, but it used a high current of 18650 cells which I plan to use in a power bank for a laptop project. So, the idea of a UPS from generic cheap components was born. The goal was to reuse a bunch of Li-pol batteries of different sizes and other parts that I bought from Aliexpress because they were cheaper to buy in bulk and I had never used them. 

![UPS](https://github.com/user-attachments/assets/aae098c7-c57a-4024-a9c8-327fb953a988)

The circuit can be simplified, but I have 2 ethernet switches—one uses 5V and the other 9V—while the router and ONU use 12V. Each Li-pol cell has its own BMS, and they are all connected in parallel. The capacity is unknown, but I estimated it to be about 10Ah.

These LM2596 DC-DC converters should handle up to 3A, but they seem to be fake as they produce a lot of heat (https://www.youtube.com/watch?v=hBOJDlftKTU). Since I had a pack, I used 2: one for charging and the other for powering the equipment when AC is present. The heat is reduced during charging in such cases.

I used TP4056 modules because I had a pack of them. One can charge at 1A, which is very slow and couldn't charge enough during the 2-hour electricity presence periods. So, they're connected in parallel and charge at 2A. I can probably add another one, but I don't want to overheat the LM2596 module, which is configured to 6V to reduce heat. TP4056 allows up to 8V input, but again, heat management is a concern.

Two Schottky diodes are used for switching between the LM2596 boards from battery to AC. The output is connected to 4 SX1308 (MT3608) DC-DC converters, each handling up to 2A. Since I had a pack of them, I just used a separate board for each device.

The batteries are separated from the DC converters and Schottky diodes for heat management, basically, they are in two plastic candy cases. But I'm planning to 3D print one so there is good ventilation. This setup has been running for 2 months without issues, providing 5-6 hours of power and fully charging in 7-9 hours if fully discharged. 
