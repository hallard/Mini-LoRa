Mini Lora Node, Arduino Mini LoraWAN sensor
===========================================

<img src="https://github.com/hallard/Mini-LoRa/raw/master/pictures/Mini-LoRa-18650-Clip.jpg">

At the begining this PCB has been created to help wiring between Arduino Mini and RFM95 Lora module and to be able to put the whole thing powered by various Batteries type (AA, 18650, A, ...).

Then I decided to add some funky stuff like:

**new in V1.2**

- Footprint for Ultra Low Power controller TPL5110
- R9 1206 or PTH Footprint to easily change resistor and thus delay between wake
- renamed silk pin to function instead of arduino name
- Optional Tactile Switch to wake from TPL5110

**all version**

- Easy to build and solder, 0805 or PTH components
- I2C connector (or grove) to be able to add internal/external sensors such as BME280, SI7021 or HTU21D
- Footprint for Lora RFM95
- Footprint for a Microchip 24AA02E64T EUID 
- RBG Led
- Optional Tactile Switch
- Various Battery Connector and type AA/A/18650/CR123
- Two A4/A5 pins position so you can use different Mini Clone (see BOM)

**On version 1.1, I2C A4/A5 (the ones bottom right) are not connected**, thanks to tkerby who detected this point on [issue #1](https://github.com/hallard/Mini-LoRa/issues/1).
This is now fixed on version 1.1a. Pcbs.io PCB have been updated.

Detailed Description
====================

No specific documentation for now, it's just a kind of wiring helper as follow

```
 Arduino Mini   RFM9x Module
 A0          <----> RST
 MISO  (D12) <----> MISO
 MOSI  (D11) <----> MOSI
 SCK   (D13) <----> CLK
 SS    (D10) <----> SEL (Chip Select)
 D2          <----> DIO0
 D7          <----> DIO1
 D8          <----> DIO2

 Arduino Mini    Shield PCB
 D3          <----> Push Button (Has Pull Down)
 D9          <----> Led Red
 D6          <----> Led Green
 D5          <----> Led Blue
 A1          <----> DONE of TPL5110 (to indicate we done)
 A2          <----> DRVN of TPL5110 (pulse out to wake CPU)
 SDA (A4)    <----> I2C SCL Connector
 SCL (A5)    <----> I2C SDA Connector
```

R9 determine Wake Time interval from TPL5110 as follow 
  - 170K 2 hours
  - 120K ~1 hour
  - 100K ~35 min
  - 47K ~6 min

please read TPL5110 [datasheet](http://www.ti.com/lit/ds/symlink/tpl5110.pdf) for more information or Adafruit TPL5110 Learning [page](https://learn.adafruit.com/adafruit-tpl5110-power-timer-breakout/)

Installation
============

If you're using Battery clip connector, please isolate the A4/A5 and FTDI (V1.0 only) pads from clip because it will do shorts and prevent I2C to work.

I'm Using the [LMIC stack](https://github.com/matthijskooijman/arduino-lmic) as his with custom sketch, this one is under NDA for Ultra Low Power, So I can't provide it but you can use the one in example of LMIC.

You may need to disable debug of LMIC stack if missing.

I'm also changing the Bootloader to use optiboot and win 1.5K of flash code and setup the Brown Out Detect to 1.8V to be able to works under 2.7V. Please see this [Pro-Mini-ICSP-FTDI](https://github.com/hallard/Pro-Mini-ICSP-FTDI) repo if you need to flash your Arduino Pro Mini with this bootloader. You'll see in [bootloader](https://github.com/hallard/Pro-Mini-ICSP-FTDI/tree/master/bootloaders) folder, I've compiled some for various Speed and for 8MHz and 16MHz Crystal (I use the 250KBPS one, it's fast and reliable).

Schematic
=========

<img src="https://github.com/hallard/Mini-LoRa/raw/master/pictures/Mini-Lora-sch.png">

Boards 
======

**Top & bottom side V1.2**

<img src="https://github.com/hallard/Mini-LoRa/raw/master/pictures/Mini-LoRa-V12-top.jpg">
<img src="https://github.com/hallard/Mini-LoRa/raw/master/pictures/Mini-LoRa-V12-bot.jpg">


**Top & bottom side Grove V1.1**

<img src="https://github.com/hallard/Mini-LoRa/raw/master/pictures/Mini-LoRa-Grove-top.jpg">
<img src="https://github.com/hallard/Mini-LoRa/raw/master/pictures/Mini-LoRa-Grove-bot.jpg">

You can order PCBs of this board at [PCBs.io][3]

- [V1.2](https://www.PCBs.io/share/r1a3J) Classic I2C connector
- [V1.1a](https://www.PCBs.io/share/8AGb2) Classic I2C connector
- [V1.1a](https://www.PCBs.io/share/zjKdY) Grove I2C connector
- [V1.0](https://www.PCBs.io/share/r3LdE)

 PCBs.io give me some reward when you order my designed boards from their site. This is pretty good, because I can use these rewards to create and design new boards and order boards for a discounted price, so if you don't care about PCB manufacturer please use PCBs.io.

Assembled boards with sensors
=============================

<img src="https://github.com/hallard/Mini-LoRa/raw/master/pictures/Mini-LoRa-FrontBig.jpg" alt="Fully assembled with sensors">

Sensors values en Cayenne
<img src="https://github.com/hallard/Mini-LoRa/raw/master/pictures/Mini-LoRa-Cayenne.jpg" alt="Monitoring with external sensors">


Bill Of Material
================

Nothing fancy, all components are 0805 and/or PTH and can be ordered almost anywhere (digikey, mouser, radiospare, ...). 
use only what you need dependings on what you want to do. 


Octopart [BOM file](https://octopart.com/bom-tool/MsqCYjTr)

Example of option parts, and other source
- Arduino Pro Mini (just take care your board has A4/A5 at the correct place, some clone are not)
    - [Geekcreit](https://www.banggood.com/Pro-Mini-ATMEGA328P-5V16M-Improved-Version-Module-For-Arduino-p-985618.html) 5V 16MHz (power it with 3.3V and/or remove regulator)
    - [ebay](http://www.ebay.com/itm/201562503063) 3V3 8MHz
- [RFM95](https://www.digikey.com/product-detail/en/rf-solutions/RFM95W-868S2/RFM95W-868S2-ND/5051755) (check Frequency)
- Common Anode RGB Led, search `diffused 5MM RGB LED common anode` on ebay
- Battery Connector format
    - Holder [AA](https://www.digikey.com/product-detail/en/mpd-memory-protection-devices/BCAAPC/BCAAPC-ND/232723)
    - Clip [AA](https://www.digikey.com/product-detail/en/mpd-memory-protection-devices/BK-92/BK-92-ND/2079904)
    - Clip [A/18650](https://www.digikey.com/product-detail/en/keystone-electronics/54/36-54-ND/2254090) 
    - PTH [CR123](https://www.digikey.com/product-detail/en/mpd-memory-protection-devices/BH123A/BH123A-ND/2817712)
- Batteries
    - 3.0V Lithium [CR123](https://www.digikey.com/product-detail/en/panasonic-bsg/CR-123PE-BN/P703-ND/7064720)
    - 3.6V Lithium Thionyle Chloride [2600mAh](http://fr.rs-online.com/web/p/piles-aa/2019438/)
    - 3.6V Lithium Thionyle Chloride [3600mAh](http://fr.rs-online.com/web/p/piles-aa/778-1087/)

License
=======

<img alt="Creative Commons Attribution-NonCommercial 4.0" src="https://i.creativecommons.org/l/by-nc/4.0/88x31.png">   

This work is licensed under a [Creative Commons Attribution-NonCommercial 4.0 International License](http://creativecommons.org/licenses/by-nc/4.0/)    
If you want to do commercial stuff with this project, please contact [CH2i company](https://www.ch2i.eu/en#support) so we can organize an simple agreement.

Misc
====

See TTN dedicated [post](https://www.thethingsnetwork.org/forum/t/8059) and news and other projects on my [blog][1] 
 
[1]: https://hallard.me
[3]: https://www.PCBs.io

[20]: http://www.seeedstudio.com/depot/index.php?main_page=opl_info&opl_id=4
[21]: http://www.ebay.com/itm/170578495165
[22]: http://www.ebay.com/itm/351690376555
[23]: http://www.ebay.com/itm/351738196013
[24]: http://www.ebay.com/itm/371534934746
[25]: https://www.adafruit.com/products/1979
[26]: https://www.sparkfun.com/products/11114

[27]: http://www.ebay.com/itm/121929386506?var=420920026758
[28]: http://www.ebay.com/itm/371348168950
[29]: http://www.ebay.com/itm/351588181858


[40]: http://www.ebay.com/itm/262500056078
[41]: http://www.aliexpress.com/item/Free-Shipping-Good-Quality-ABS-Material-Transparent-Cover-IP66-Waterproof-Electrical-Switch-Box-125-125-75mm/32522255056.html
[42]: http://www.aliexpress.com/item/Temperature-and-humidity-Protective-sleeve-Accessories-PCB-for-SHT20-SHT21-SHT25/32695663191.html?spm=2114.13010208.99999999.264.dgLxek
[43]: http://www.ebay.com/itm/401000227934
[44]: http://www.ebay.com/itm/182181715511?var=483966356069
[46]: http://www.ebay.com/itm/391462862706
[47]: http://www.ebay.com/itm/232153789354?var=531358445664
[48]: http://www.ebay.com/itm/301856945402

[50]: https://octopart.com/bom-tool/MsqCYjTr