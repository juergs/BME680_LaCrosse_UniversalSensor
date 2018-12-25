# BME680_UniversalSensor

Special FW-Version for ESP8266 with BME680 sensor.
Using BOSCH\Sensortec static lib BSEC_1.4.5.1_Generic_Release_20171116.
Check needed special manual arduino linker configuration, specified in pdf: BST-BME680-AN008-45.pdf in the \doc-directory.
Implementing LaCrosse-Universal-Sensor-protokol, thankful derived from github/hdgucken's work.

Using Peter's (pemue) pcb at fhem community: https://forum.fhem.de/index.php/topic,51329.msg876501.html#msg876501 and 
pcb: https://forum.fhem.de/index.php/topic,51329.0.html 

This project is based on my cc_sensor, HCS has made some changes to upgrade it to the UniversalSensor, many thanks to HCS !
The main component is an ESP8266 nodemcu, but i dont use the wifi section, wireless transmission is done by an RFM69CW module.
Since V3.0 you can use ESP8266 based NodeMCU/Wemos D1 mini OR STM32F103Cx based BluPill/Maple mini boards !
Hardware setup you can find in the sketch.
The RFM69 transmit at 868.30 MHz with LaCrosse Weatherstation Protocoll. The signal is decoded by a LaCrosseGateway module (by HCS),
wich transmitt the data to a FHEM server. There is created a LaCrosse like weather sensor with all the sensor data as readings.
This sensor gives you the following data:
temerature (degree Celsius), humidity (% rH), air pressure (hPa/mBar), air quality, light intensity (Lux) and battery voltage (V).
You can use an optional 128x64 OLED Display with SH1106/SSD1306 Controller, to display the data. It is autodetected, simply connect it or not.
The Lightsensor (BH1750) is optional too, it not need to be connected.
The RFM69CW not need to be connected too, in this case, no wireless transmission is possible. The data where transmitted
by the serial port only (115200 Baud).
