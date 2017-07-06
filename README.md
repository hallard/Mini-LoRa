Mini Lora Node, Arduino Mini LoraWAN sensor
===========================================

<img src="https://raw.githubusercontent.com/hallard/Mini-LoRa/master/pictures/Mini-LoRa-18650-Clip.jpg">     
<img src="https://github.com/hallard/Mini-LoRa/raw/master/pictures/Mini-LoRa-18650-Clip.jpg">
test
![Image](../blob/master/pictures/Mini-LoRa-18650-Clip.jpg?raw=true)

At the begining this PCB has been created to help wiring between Arduino Mini and RFM95 Lora module and to be able to put the whole thing powered by various Batteries type (AA, 18650, A, ...).

Then I decided to add some funky stuff like:

- Easy to build and solder, 0805 or PTH components
- I2C connector (or grove) to be able to add internal/external sensors such as BME280, SI7021 or HTU21D
- Footprint for Lora RFM95
- Footprint for a Microchip 24AA02E64T EUID 
- RBG Led
- Optionnal Tactile Switch
- Various Battery Connector and type AA/A/18650/CR123


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
 SDA (A4)    <----> I2C SCL Connector
 SCL (A5)    <----> I2C SDA Connector
```

Installation
============

I'm Using the LMIC stack as his with custom sketch, this one is under NDA for Ultra Low Power, So I can't provide it.


Schematic
=========

![schematic](https://raw.githubusercontent.com/hallard/Mini-LoRa/master/pictures/Mini-LoRa-sch.png)  

Boards 
======

**Top side**
<img src="https://raw.githubusercontent.com/hallard/Mini-LoRa/master/pictures/Mini-LoRa-top.jpg" alt="PCB Top">    

**Top side Grove**
<img src="https://raw.githubusercontent.com/hallard/Mini-LoRa/master/pictures/Mini-LoRa-Grove-top.jpg" alt="PCB Top">    

**Bottom side**
<img src="https://raw.githubusercontent.com/hallard/Mini-LoRa/master/pictures/Mini-LoRa-bot.jpg" alt="PCB Bottom">    

**Bottom side Grove**
<img src="https://raw.githubusercontent.com/hallard/Mini-LoRa/master/pictures/Mini-LoRa-Grove-bot.jpg" alt="PCB Bottom">    

You can order the PCB of this board at [PCBs.io][3]. PCBs.io give me some reward when you order my designed boards from their site. This is pretty good, because I can use these rewards to create and design new boards and order boards for a discounted price, so if you don't care about PCB manufacturer please use PCBs.io.

Assembled boards with sensors
=============================

<img src="https://raw.githubusercontent.com/hallard/Mini-LoRa/master/pictures/Mini-LoRa-FrontBig.jpg" alt="Fully assembled with sensors">     

Sensors values en Cayenne
<img src="https://raw.githubusercontent.com/hallard/Mini-LoRa/master/pictures/Mini-LoRa-Cayenne.jpg" alt="Monitoring with external sensors">     


Bill Of Material
================

Nothing fancy, all components are 0805 and/or PTH and can be ordered almost anywhere (digikey, mouser, radiospare, ...). 
use only what you need dependings on what you want to do. 

- [RFM95](https://www.digikey.com/product-detail/en/rf-solutions/RFM95W-868S2/RFM95W-868S2-ND/5051755) (check Frequency)
- Microchip [24AA02E64T](https://www.digikey.com/product-detail/en/microchip-technology/24AA02E64T-I-OT/24AA02E64T-I-OTCT-ND/4292622) EUID 
- Common Anode [RBG Led](https://www.digikey.com/product-detail/en/kingbright/WP154A4SUREQBFZGW/754-1492-ND/2261457), search `diffused 5MM RGB LED common anode` on ebay
- C&K [Tactile Switch](https://www.digikey.com/product-detail/en/c-k/PTS810-SJK-250-SMTR-LFS/CKN10503CT-ND/4176675)
- Battery Connector format
    - Holder [AA](https://www.digikey.com/product-detail/en/mpd-memory-protection-devices/BCAAPC/BCAAPC-ND/232723)
    - Clip [AA](https://www.digikey.com/product-detail/en/mpd-memory-protection-devices/BK-92/BK-92-ND/2079904)
    - Clip [A/18650](https://www.digikey.com/product-detail/en/keystone-electronics/54/36-54-ND/2254090) 
    - PTH [CR123](https://www.digikey.com/product-detail/en/mpd-memory-protection-devices/BH123A/BH123A-ND/2817712)
- Batteries
    - 3.0V Lithium [CR123](https://www.digikey.com/product-detail/en/panasonic-bsg/CR-123PE-BN/P703-ND/7064720)
    - 3.6V Lithium Thionyle Chloride [2600mAh](http://fr.rs-online.com/web/p/piles-aa/2019438/))
    - 3.6V Lithium Thionyle Chloride [3600mAh](http://fr.rs-online.com/web/p/piles-aa/778-1087/)


License
=======

<img alt="Creative Commons Attribution-NonCommercial 4.0" src="https://i.creativecommons.org/l/by-nc/4.0/88x31.png">   

This work is licensed under a [Creative Commons Attribution-NonCommercial 4.0 International License](http://creativecommons.org/licenses/by-nc/4.0/)    
If you want to do commercial stuff with this project, please contact [CH2i company](https://www.ch2i.eu/en#support) so we can organize an simple agreement.

Misc
====

See news and other projects on my [blog][1] 
 
[1]: https://hallard.me
[3]: https://PCBs.io/share/rmVdD

[20]: http://www.seeedstudio.com/depot/index.php?main_page=opl_info&opl_id=4
[21]: http://www.ebay.com/itm/170578495165
[22]: http://www.ebay.com/itm/351690376555
[23]: http://www.ebay.com/itm/351738196013
[24]: http://www.ebay.com/itm/371534934746

[25]: https://www.adafruit.com/products/1979
[26]: https://github.com/ch2i/ic880a-gateway/tree/ch2i-rpi-shield

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