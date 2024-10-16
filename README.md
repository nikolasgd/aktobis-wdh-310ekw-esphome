# Aktobis WDH-310EKW for ESPHome

A hardware and software manual to transform the Aktobis WDH-310EKW dehumidifier from Tuya into an ESPHome device.

This will remove the Tuya chip and replace it with an ESP 07 (same pin layout) making it a full blown ESPHome device to use in Home Assistant and removing the need for Tuya cloud.

![image](/aktobis.jpeg)

Requirements:
- An ESP 07 
- Hot air rework station to remove the Tuya microcontroller
- A pullup resistor between TX and VCC of the ESP (i.e. 4.7K)
- An ESP programmer (i.e. CP2102)

Steps:
1. First open up the back of the dehumidifier by unscrewing all Phillips screws.
2. Locate the PCB holding the Tuya chip on the left side of the opened dehumidifier and remove it by opening the plastic cover and unplugging the 4 line connector.
3. Flash your ESP 07 with a programmer and ESPHome with the code the configuration file: esphome.yaml
4. Desolder the Tuya chip with hot air and replace it with the ESP. Don't even try to use a regular solder iron. Buy a cheap hot air rework station from Amazon (i.e. 858D will do fine).
5. Solder a pullup resistor between VCC and TX pin, otherwise the ESP will fail to boot.

That's it! Reassemble and your new device will show up in Home Assistant, if you have the ESPHome integration installed.
