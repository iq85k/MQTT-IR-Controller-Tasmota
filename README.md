# MQTT-IR-Controller-Tasmota

Simple and Easy smart IR controller based on Tasmota via IRHVAC via SmartIR plugin

It's been about a 2 years since i made my first MQTT IR Controller and it been working flawlessly with Home Assistant and i feel it's about time to share this.

This conntroller is runing with Tasmota IR 8.3.1 if you want to know More about Tasmota <a href="https://github.com/arendst/Tasmota">Click Here</a> the reason why I'm using old version of Tasmota IR that this is the one worked best for me and never had any issues with so i keeped using it.

also using the SmartIR plugin that creates the Home Assistant climate componant and publish the commands via MQTT you can find more about it in details and more about installation <a href="https://github.com/smartHomeHub/SmartIR">Click Here</a>

# Required Components

<table>
  <tr>
    <th>Name</th>
    <th>Photo</th>
  </tr>
  <tr>
    <td>ESP-01</td>
    <td><img src="https://github.com/iq85k/MQTT-IR-Controller-Tasmota/blob/main/Required%20Components/ESP-01.jpg" height="100" title="hover text"></td>
  </tr>
  <tr>
    <td>Hi-Link 3.3v</td>
    <td><img src="https://github.com/iq85k/MQTT-IR-Controller-Tasmota/blob/main/Required%20Components/Hi-Link%203.3v.jpg" height="100" title="hover text"></td>
  </tr>
  <tr>
    <td>2N2222 Transistor</td>
    <td><img src="https://github.com/iq85k/MQTT-IR-Controller-Tasmota/blob/main/Required%20Components/2N2222%20Transistor.jpg" height="100" title="hover text"></td>
  </tr>
  <tr>
    <td>IR TX LED</td>
    <td><img src="https://github.com/iq85k/MQTT-IR-Controller-Tasmota/blob/main/Required%20Components/IR%20TX%20LED.jpg" height="100" title="hover text"></td>
  </tr>
  <tr>
    <td>10k Resistor</td>
    <td><img src="https://github.com/iq85k/MQTT-IR-Controller-Tasmota/blob/main/Required%20Components/10k%20Risistor.jpg" height="100" title="hover text"></td>
  </tr>
    <tr>
    <td>DHT11 temperature and humidity sensor</td>
    <td><img src="https://github.com/iq85k/MQTT-IR-Controller-Tasmota/blob/main/Required%20Components/DHT11%20temperature%20and%20humidity%20sensor.jpg" height="100" title="hover text"></td>
  </tr>
  <tr>
    <td>PCB screw terminal 2P connector</td>
    <td><img src="https://github.com/iq85k/MQTT-IR-Controller-Tasmota/blob/main/Required%20Components/PCB%20screw%20terminal%202P%20connector.jpg" height="100" title="hover text"></td>
  </tr>
  <tr>
    <td>Double-Side Prototype Board PCB</td>
    <td><img src="https://github.com/iq85k/MQTT-IR-Controller-Tasmota/blob/main/Required%20Components/Double-Side%20Prototype%20Board%20PCB.jpg" height="100" title="hover text"></td>
  </tr>
</table>

# Circuit diagram
![alt text](https://github.com/iq85k/MQTT-IR-Controller-Tasmota/blob/main/Circuit%20diagram.jpg)

# Instructions
- first you will need to flash Tasmota on ESP-01 using USB to Serial UART adapter of your choice with the BIN file provided in files above.
- after flashing you will need to connect to WIFI signal Called tasmota-xxxxxxxxx and insert your home WIFI credentials.
- you need to find your device IP address by checking you router DHTP clients page.
- after the device is connected successfully you will be able to access your device to put in your MQTT info and choose a topic.
