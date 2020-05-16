# Prototype board with sensors

## Description

In this readme you can find all information about the prototype board with sensors. I made first a test board this board cannot be placed inside the box. This board works perfect with all sensors. The second board i made is made to put inside the box, i also implemented extra pins for the other boards. I also added a extra part to get the SDS011 sensor in sleep mode i will explain this in the info below.

## Shematic of the old board

In this shematic you see in the center of the shematic 2 big blocks the top one is the left side of the nucleo-L432KC. The block below is the right side of the nucleo-L432KC. On the right side from the second nucleo-L432KC block you can see 2 pins they are called JP2 and JP3. These pins were provided for the solar panel board, JP2 is connected with the Vin from the nucleo and JP3 is just the ground. There is also a reset button connected to NRST on the nucleo.

Right below the pins JP2 and JP3 you can see one big connector, this is the connector for connecting the LoRaWAN-antenna board. Pins 1, 8, 9 are connected to the ground, pin 12 is connected with the 3V3 and a capacitor with a value of 100 nF.
Pins 7, 10, 11, 15 are not connected, pin 2 is connected to pin D12 on the nucleo. Pin 3 is connected with D11 on the nucleo, pin 4 is connected with D13 on the nucleo, pin 5 is connected with D0 on the nucleo. Pin 6 is connected with a resistor with a value of 4k7 ohm, this pin is also connected with D1 on the nucleo. Pin 13 is connected with D2 on the nucleo, pin 14 is connected with D3 on the nucleo.

Left from the top block from the nulceo you can see a connector that is called SDS011. This connector has pins so that you connect the SDS011 sensor on it. You can see that pin 1 is not connected this is because the connector from the SDS011 has 5 pins and one is not connected. Pin 2 is connected to 3v3 but this has been changed in the newer shematic because the sensor has to work on 5V, pin 3 is connected to the ground. Pin 4 is connected to D1 on the nucleo and Pin 5 is connected to D0 on the nucleo.

Right from the top block from the nulceo you can see a connector that is called BME280. This connector has female pins so you can put the BME280 sensor on it. Pin 2 is not connected, Pin 1 and 7 are connected to 3V3 and pin 3 and 5 are connected to the ground. Pin 4 is connected to D5 on the nucleo and pin 6 is connected to D4 on the nucleo.

On top of the shematic you can see a big block this is the EEPROM. Pin 2 is connected to the ground and pin 4 is connected to the VCC. Pin 5 is not connected, pin 1 is connected to a resistor with a value of 2k2 ohm to protect the SCL line and is connected tot the D5 on the nucleo. Pin 3 is connected to a resistor with a value of 2k2 ohm to protect the SDA line and is connected with D4 on the nucleo.

![old shematic](/images/oldShematic.png)

## Board shematic of the old board

On the top of the board you can see 4 holes this is the VCC of the SDS011 sensor. These holes are were provided so you could erase the line and add more voltage to it from the solar pannel board. These holes were removed on the newest board.

![old board](/images/oldBoard.png)

![old board polygoon](/images/oldBoardPolygoon.png)

## The print when nothing was soldered

![print not soldered](/images/board_not_soldered.png)

## The print when everything is soldered

![print soldered](/images/board_soldered.png)

## Tests

## Testing the SDS011 sensor

1. Setup of the sensor.

   ![setup SDS011](/images/setup_sensor_SDS011.png)

2. Reading the values in putty.

   ![putty SDS011](/images/putty_SDS011.png)

3. Extra information.
    * The pins are connected on D0 and D1.

## Testing the EEPROM driver

1. Setup of the sensor.

   ![setup EEPROM](/images/setup_EEPROM.png)

2. Reading out an array in putty.

   ![putty EEPROM](/images/putty_EEPROM.png)

3. Extra information.
    * While testing i connected the pins to D4 and D5.

## Testing the BME280 sensor

I could not test this sensor because i don't have that sensor at home. I tested it with the fake values from Ladzlo and something was wrong with compiling. But other people tried this sensor and connected it just like how i connected it in my shematic so normally it would work perfectly.

1. Setup of the sensor.

   Connect the sensor in the pins in the red circle shown in the picture below.

   ![setup BME](/images/setup_BME.png)

2. Extra information.
    * I connected the BME to pins D4 and D5 on the nucleo.

## Testing antenna PCB board

This test has been executed by Laura this pcb works perfectly together with my board all the info about the tests can you find in the github repository from the antenna board.

1. Setup of the boards.

   ![setup LoRaWan](/images/LoRaWAN_pcb.png)

2. Extra information.
    * You can find extra information in the link below.
    * [Link testing LoRaWAN-antenna](https://github.com/vives-projectwerk-2-2020/LoRaWAN-antenna/tree/master/testing)
