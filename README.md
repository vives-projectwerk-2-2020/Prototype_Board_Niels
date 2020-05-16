# Prototype_Board_Niels

## Description

In this readme you can find all information about the prototype board with sensors. I made first a test board this board cannot be placed inside the box. This board works perfect with all sensors. The second board i made is made to put inside the box, i also implemented extra pins for the other boards. I also added a extra part to get the SDS011 sensor in sleep mode i will explain this in the info below.

## Shematic of the old board

![old shematic](/images/oldShematic.png)

## The print when nothing was soldered

![print not soldered](/images/board_not_soldered.png)

## The print when everything is soldered

![print soldered](/images/board_soldered.png)

## Testing the SDS011 sensor (succesfull)

1. Setup of the sensor.

![setup SDS011](/images/setup_sensor_SDS011.png)

2. Reading the values in putty.

![putty SDS011](/images/putty_SDS011.png)

3. Extra information.
    * The pins are connected on D0 and D1.

## Testing the EEPROM driver (succesfull)

1. Setup of the sensor.

![setup EEPROM](/images/EEPROM.png)

2.Reading out an array in putty.

![putty EEPROM](/images/putty_EEPROM.png)

3.Extra information.
    * While testing i connected the pins to D4 and D5.