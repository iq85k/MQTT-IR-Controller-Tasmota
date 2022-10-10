# MQTT-IR-Controller-Tasmota

Simple and Easy smart IR controller based on Tasmota via IRHVAC via SmartIR plugin

It's been about a 2 years since i made my first MQTT IR Controller and it been working flawlessly with Home Assistant and i feel it's about time to share this.

This conntroller is runing with Tasmota IR 8.3.1 if you want to know More about Tasmota <a href="https://github.com/arendst/Tasmota">Click Here</a> the reason why I'm using old version of Tasmota IR that this is the one worked best for me and never had any issues with so i keeped using it.

also using the SmartIR plugin that creates the Home Assistant climate componant and publish the commands via MQTT you can find more about it in details and more about installation <a href="https://github.com/smartHomeHub/SmartIR">Click Here</a>

# First things first
  - make sure that you install SmartIR
  - make sure that you have MQTT installed in Home Assistant and enable discovery
  - Make sure that you have the Tasmota plug in installed and configured in Home Assistant

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

# Sending IRHVAC Commands
Source <a href="https://tasmota.github.io/docs/Tasmota-IR/#sending-irhvac-commands">Click Here</a>
<table>
<thead>
  <tr>
    <th>Command</th>
    <th>Parameters</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>IRHVAC</td>
    <td>Send HVAC IR remote control code as JSON payload<br><br>IRHVAC {"Vendor":"Mitsubishi_Heavy_152", "Power":"On","Mode":"Hot","FanSpeed":3,"Temp":22.5}<br><br>"Protocol" or "Vendor" (select one of the following):<br>COOLIX, DAIKIN, KELVINATOR, MITSUBISHI_AC, GREE, ARGO, TROTEC, TOSHIBA_AC, FUJITSU_AC, MIDEA, HAIER_AC, HITACHI_AC, HAIER_AC_YRW02, WHIRLPOOL_AC, SAMSUNG_AC, ELECTRA_AC, PANASONIC_AC, DAIKIN2, VESTEL_AC, TECO, TCL112AC, MITSUBISHI_HEAVY_88, MITSUBISHI_HEAVY_152, DAIKIN216, SHARP_AC, GOODWEATHER, DAIKIN160, NEOCLIMA, DAIKIN176, DAIKIN128<br><br>"Model":<br> <br>Some HVAC have variants in protocols, this field allows to specify the variant, see <a href="https://github.com/crankyoldgit/IRremoteESP8266/blob/master/SupportedProtocols.md" target="_blank" rel="noopener noreferrer">detailed list</a><br><br>- Fujitsu_AC: ARRAH2E|ARDB1<br>- Panasonic_AC: LKE|NKE|DKE|JKE|CKP|RKR<br>- Whirlpool_AC: DG11J13A|DG11J104|DG11J1-04|DG11J191<br><br>"Power":<br>&nbsp;&nbsp;&nbsp;On, Yes, True, 1,<br>&nbsp;&nbsp;&nbsp;Off, No, False, 0<br><br>"Mode":<br>&nbsp;&nbsp;&nbsp;Off, Stop<br>&nbsp;&nbsp;&nbsp;Auto, Automatic<br>&nbsp;&nbsp;&nbsp;Cool, Cooling<br>&nbsp;&nbsp;&nbsp;Heat, Heating<br>&nbsp;&nbsp;&nbsp;Dry, Drying, Dehumidify<br>&nbsp;&nbsp;&nbsp;Fan, Fanonly, Fan_Only<br><br>"FanSpeed":<br>&nbsp;&nbsp;&nbsp;Auto, Automatic<br>&nbsp;&nbsp;&nbsp;Min, Minimum, Lowest, 1<br>&nbsp;&nbsp;&nbsp;Low, 2<br>&nbsp;&nbsp;&nbsp;Med, Medium, Mid, 3<br>&nbsp;&nbsp;&nbsp;High, Hi, 4<br>&nbsp;&nbsp;&nbsp;Max, Maximum, Highest, 5<br><br>"SwingV":<br>&nbsp;&nbsp;&nbsp;vertical swing of Fan<br>&nbsp;&nbsp;&nbsp;Auto, Automatic, On, Swing<br>&nbsp;&nbsp;&nbsp;Off, Stop<br>&nbsp;&nbsp;&nbsp;Min, Minimum, Lowest, Bottom, Down<br>&nbsp;&nbsp;&nbsp;Low<br>&nbsp;&nbsp;&nbsp;Mid, Middle, Med, Medium, Centre, Center<br>&nbsp;&nbsp;&nbsp;High, Hi<br>&nbsp;&nbsp;&nbsp;Highest, Max, Maximum, Top, Up<br><br>"SwingH":<br>&nbsp;&nbsp;&nbsp;horizontal swing of Fan<br>&nbsp;&nbsp;&nbsp;Auto, Automatic, On, Swing<br>&nbsp;&nbsp;&nbsp;Off, Stop<br>&nbsp;&nbsp;&nbsp;LeftMax, Left Max, MaxLeft, Max Left, FarLeft, Far Left<br>&nbsp;&nbsp;&nbsp;Left<br>&nbsp;&nbsp;&nbsp;Mid, Middle, Med, Medium, Centre, Center<br>&nbsp;&nbsp;&nbsp;Right<br>&nbsp;&nbsp;&nbsp;RightMax, Right Max, MaxRight, Max Right, FarRight, Far Right<br>&nbsp;&nbsp;&nbsp;Wide<br><br>"Celsius": temperature is in Celsius ("On") or Farenheit ("Off")<br><br>"Temp": Temperature, can be float if supported by protocol<br><br>"Quiet": Quiet mode ("On"/"Off")<br><br>"Turbo": Turbo mode ("On"/"Off")<br><br>"Econo": Econo mode ("On"/"Off")<br><br>"Light": Light ("On"/"Off")<br><br>"Filter": Filter active ("On"/"Off")<br><br>"Clean": Clean mode ("On"/"Off")<br><br>"Beep": Beep active ("On"/"Off")<br><br>"Sleep": Timer in seconds<br><br>"StateMode":<br>&nbsp;&nbsp;&nbsp;SendOnly (default)<br>&nbsp;&nbsp;&nbsp;StoreOnly<br>&nbsp;&nbsp;&nbsp;SendStore</td>
  </tr>
</tbody>
</table>
# SmartIR Component Config
First you will have to copy your json config to SmartIR directory and sve it with a number XXXX.json

```
<config directory>/
|-- custom_components/
|   |-- smartir/
|       |-- codes
|           |-- climate
```

you can nowadd your device config in climate.yaml

Example:
```yaml
- platform: smartir
  name: Office A/C 
  unique_id: office_ac
  device_code: 1600 # your JSON file number
  controller_data: cmnd/studio/IRhvac # Change to match your device topic
  temperature_sensor: sensor.studio_temperature # Change to match your sensor id in Home Assistant
  humidity_sensor: sensor.studio_humidity # Change to match your sensor id in Home Assistant 
  power_sensor: binary_sensor.ac_power
```
