
# Sensor temp and hum CWT-TH03S via RS485

Temperature and humidity sensor using CWT-TH03S sensor via RS485. I need wired sensor in sauna for temperatures above 100 celsius. This is due to technical issues with the SHT30 sensor which was often disconnecting due to lenght of wires in my sauna. 

FTP cable used. Each twisted pair shall be connected to own pin. It means 8 wires = 4 pairs of wires <=> 4 pins.


Components:

- ESP32 or ESP8266 or similar
- CWT-TH03S
- MAX485 (TTL na RS-485)
- battery or charger

POZOR! Pro oboji je potreba 5V napajeni

## Wiring

| CWT-TH03S                   | connected to     |
| ---------------------------| ---------- |
| [Black]    GND              | ESP32 GND  |
| [Red]      Power +(DC5-30V) | ESP32 VCC  |
| [Yellow]   RS485 A+         | MAX485 A+  |
| [Blue]     RS485 B-         | MAX485 B-  |


| MAX485      | connected to      |
| ----------- | -----------------| 
| GND         | ESP32 GND              | 
| RXD         | ESP32 VIN/5V | 
| TXD         | RS485 A+         | 
| VCC         | RS485 B-         | 
| ----------- | -----------------|
| A+          | CWT-TH03S yellow/RS485 A+              | 
| B-          | CWT-TH03S blue/RS485 B- | 
| ?           | not used         | 


| ESP32      | connected to      |
| ----------- | -----------------| 
| GND         | CWT-TH03S GND    | 
| VCC         | CWT-TH03S VIN/5V | 
| TXD0 GPIO1  | MAX485 TXD       | 
| RXD0 GPIO3  | MAX485 RFX       | 


## Screenshots

![App Screenshot](https://github.com/jindrich296/sensor-temp-hum-CWT-TH03S-via-RS485/blob/main/IMG_2034.jpg)

![App Screenshot](https://github.com/jindrich296/sensor-temp-hum-CWT-TH03S-via-RS485/blob/main/IMG_2033.jpg)
