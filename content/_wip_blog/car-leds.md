---
title: Car LEDs
date: "2020-10-12T22:26:05Z"
description: "Arduinos, and chips, and Pis, oh my!"
---



ESP8622:
- EEPROM used for small configuration values
- No EEPROM, have to use flash memory that emulates EEPROM.
- Requires flashing entire sector when values change which is bad wear on flash mem.
- Two libs to help mitigate this by rotating locations:
    - https://github.com/jwrw/ESP_EEPROM
    - https://github.com/xoseperez/eeprom_rotate
- As a web server, need to be able to serve larger files. Can hard code in Arduino sketch, but not pretty.
  - Instead use LittleFS (SPIFFS is deprecated) to store and access files on flash memory
- Plan to add web interface for controlling lights, will log to web server with circular buffer for n last logs. Web socket real time??