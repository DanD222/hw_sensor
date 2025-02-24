# PCB Concept
- Format to fit aluminium enclosure: 1455K1202 (120x78x43 space for DGNSS)  or 1455J1201 (120x78x27 for single GNSS)
- ESP32-WROOM-32U for an improve connectivity. Could also be used to flash the STM32F4 via WIFI. Example for WIFI / TCP: https://github.com/AlphaLima/ESP32-Serial-Bridge connection. Simultaneously two smartphone connections in a double seater are possible via wifi. 
- Footprint for a milled 5mm pressure hose connector on the edge.
- U.FL connectors for GNSS and Wifi/BT antennas via external SMA-Pigtails.
- USB-C connectors for GNSS, ESP32 and STM32
- 2 RJ45 connectors for CAN and RS232

# Changes Version 2.0
- Changed the PCB format to fit the aluminum enclosure 1455K1202 or 1455J1201.
- Redesigned the analog 3.3VA voltage supply with a capacity multiplier and a separate LDO after the 5V Buck converter.
- Introduced a separated analog section on the board and placed the regulator, filter and sensors there.
- Replaced the Bluetooth module with an esp32 for improved Bluetooth and WiFi connectivity.
- Removed the low cost Gyro, Acc and Mag components and added 3 mounting holes in 0.8inch distance for sparkfun headers.
- Removed the second MS5611 and improved the layout.
- Replaced the existing USART-3 connector with a Pixhawk standard JST-GH 6 pin Connector to connect and supply DGNSS simpleRTK2B+heading modules. 1: 5V_IN, 2: RX (3.3V level), 3: TX (3.3V level), 4,5: Not connected, 6: GND.
- Changed to two single RJ45 connectors for CAN and RS232.
- Added a footprint for a milled pressure hood including mounting screws to connect static and pitot on the PCBs edge.
- Redesigned the digital voltage supply regulators and added sufficient capacity.
- Added a separate boost converter to boost the USB Voltage.
- Added a Larus Symbol on the board.
- Changed the SMA to a u.fl connector for the GNSS Antenna.
- Added active current limiting of GNSS antenna feed with circuit taken from the U-Blox F9P hardware integration manual.
- Added ESD-protection diodes for voltage supply, GNSS antenna and USB connectors.
- Added thermal reliefs on copper fills to improve hand solder-ability.
- Added more status and error LEDs and labeling.
- Connected USB, RJ45 shields and aluminum enclosure to a separate shield ground net. Routed the shield ground around the PCB and connected it on one point with a ferrit to ground. 
- Changed the RJ45 CAN pin out so that a twisted pair of a standard patch cable is used.
- Improved anti-alias filtering for supply voltage measurement.
- Added a switch for boot0 at the pcb edge.
- Added the missing GNSS reset pull-up resistor.
- Enabled detecting the hardware version with an ADC input and a 1:1 voltage divider for this version.
- Decreased test point size to 1mm

# Changes Version 2.2
- increased the size of the usb-c smd throughholes 
- added uart GNSS solder jumpers to optionally disconnect the onboard M9N GNSS module. (For later upgrading to a D-GNSS module)
- switched DGNSS pixhawk RX, TX connector pins so that a 1:1 connection cable works
- moved RJ45 connectors towards each other to increase space on the pcb edge
- added CAN Termination switch on the pcb backside below the pressure hood. 
- added ESD protecton diodes for the SD card sdio interface. 

# Ideas for next hardware iteration
- Change to F9P GNSS Module on PCB or add sockets for 2 DGNSS modules: https://www.gnss.store/gnss-gps-modules/145-elt128.html,  https://www.ardusimple.com/product/simplertk2blite/


# Links to some parts
Gauge pressure: HSCMRRV001PG2A3
https://de.farnell.com/honeywell/hscmrrv001pg2a3/drucksensor-1psi-i2c-digital/dp/3439040
https://de.rs-online.com/web/p/drucksensor-ics/2269696

Static pressure:
https://www.mouser.de/ProductDetail/Measurement-Specialties/MS561101BA03-50?qs=%252BgKeJhng5iV%252BnCz6Qd5iDw%3D%3D

IMU:  MTi-1
https://de.farnell.com/xsens/mti-1-0i-t/mems-modul-2-16-3-6v-lcc-28/dp/3793980?st=mti-1-0i-t

GNSS:
https://www.mouser.de/ProductDetail/u-blox/NEO-M9N-00B?qs=DPoM0jnrROVeJ6BHpcwcjw%3D%3D

RJ45:
https://www.mouser.de/ProductDetail/Amphenol-Commercial-Products/RJHSE-5380?qs=rM3ofmSYd5RUaPrWD7oMhw%3D%3D

Enclosure:
43mm height: 1455K1202 https://www.reichelt.de/profilgehaeuse-1455-k-120-x-78-x-43-mm-silber-1455k1202-p221356.html?CCOUNTRY=445&LANGUAGE=de
https://www.mouser.de/ProductDetail/Hammond-Manufacturing/1455K1202?qs=bDnubaabCY889pgt9Jk8KQ%3D%3D
27mm height: 1455J1202 https://www.reichelt.de/profilgehaeuse-1455-j-120-x-78-x-27-mm-silber-1455j1202-p221348.html?&trstct=pos_0&nbc=1
https://www.mouser.de/ProductDetail/Hammond-Manufacturing/1455J1202?qs=y9%2FpVxnqej%2FD6uE6GgHhOQ%3D%3D

Barbs brass: 5mm-M5 external 5mm hose, 2.5mm-M5 internal hose

Internal tubing: 1 x 3mm silicon tube

Milled pressure hood. 2x8mm M2 brass screws. PU glue (e.g. UHU Max Repair Power, Sikaflex) to seal the pressure hood.

U.FL - Pigtails  for GNSS (SMA)  and Bluetooth/Wifi (SMA-RP) Antenna

SMA GNSS Antenna

SMA-RP 2.4GHz Antenna

For STM32 Debugging 6 x 1.25mm pitch JST connector socket and cable. 4, 6 and 8 x 1.25mm for auxilary debug connectors. 

To be designed: front and back cover pcb with openings for status leds, 2 x rj45, 2 x usb, 3 x SMA Wifi/Bluetooth, GNSS-1, GNSS-2(DGNSS option), 5mm hose connectors and a nice logo and some descriptive silkscreen.


