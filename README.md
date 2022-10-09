# MQTT-IR-Controller-Tasmota

Simple and Easy smart IR controller based on Tasmota via IRHVAC via SmartIR plugin

It's been about a 2 years since i made my first MQTT IR Controller and it been working flawlessly with Home Assistant and i feel it's about time to share this.

This conntroller is runing with Tasmota IR 8.3.1 if you want to know More about Tasmota Click Here the reason why I'm using old version of Tasmota IR that this is the one worked best for me and never had any issues with so i keeped using it.

also using the SmartIR plugin that creates the Home Assistant climate componant and publish the commands via MQTT you can find more about it in details and more about installation Click Here

# Required Componants

- ESP-01
- Hi-Link 3.3v
- 2N2222 Transistor
- IR TX LED
- 10k Risistor
- DHT11 temperature and humidity sensor
- PCB screw terminal 2P connector

# Circuit diagram
![alt text](https://github.com/iq85k/MQTT-IR-Controller-Tasmota/blob/main/Circuit%20diagram.jpg)
