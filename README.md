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

## Shematic of the new board

The difference between the old and the new board is that i added extra pins for the battery pcb and also pins for an extra board so that the voltage can go from 3V3 to 5V so that the SDS011 sensor can work well. I also added sleep mode for the SDS011.

Left from the lowest nucleo shematic i added added 3 extra connectors. SV3 is provided so that the solar board can be connected to my board. SV2 are connectors to add the extra print that converts te voltage 3V3 to 5V, we have to do that so that the SDS011 can function well.

Below the SV2 connector there are 2 pins these pins are provided to connect the wires from the batteries to my pcb. In the board you can also see a lot of holes. These holes are provided to connect the pcb with the box, the 2 holes in the center are provided for the batteries you can connect these under the PCB or above.

In the top left of the shematic you can see i added there also extra components. These components are provided so that the SDS011 can go in sleep mode. I connected this to pin D2 on the nucleo, the info about the shematic can you find in the topic "Adding components to the old board so that the SDS011 sensor can go in sleep mode" this will be discussed below.

![shematic of new board](/images/newShematic.png)

## Adding components to the old board so that the SDS011 sensor can go in sleep mode

I upgraded the old shematic a bit so that the SDS011 sensor can go in sleep mode. In the picture below you can see the shematic about how to make it.

![shematic of sleepmode](/images/sleep.png)

When the digital output goes high, Q1 is turned on. That pulls down the gate of Q2 low, turning it on.
When the digital output is low, Q1 is held off. R1 then pulls the gate high, turning off Q2.
R1 was chosen to be so high to minimize the current when the device is powered on.

## Board shematic of the new board

![new board](/images/newBoard.png)

![new polygoon](/images/newPolygoon.png)

## Partlist

* [Female header](https://be.farnell.com/samtec/ssw-107-01-t-s/connector-rcpt-7pos-1row-2-54mm/dp/2667434)
* [Pinheader SDS011](https://be.farnell.com/molex/22-28-4050/connector-header-5pos-1row-2-54mm/dp/2381173)
* [Push button](https://be.farnell.com/c-k-components/pts645sl43-2-lfs/tactile-switch-spst-0-05a-12vdc/dp/2435161)
* [EEPROM](https://be.farnell.com/microchip/24aa64t-i-ot/serial-eeprom-64kbit-400khz-sot/dp/2101260)
* [100 nF capacitor](https://be.farnell.com/avx/02016d104kat2a/cap-0-1-f-6-3v-10-x5r-0201/dp/1657913?st=smd%20capacitor)
* [2k2 ohm resistor](https://be.farnell.com/vishay/crcw06032k20fkeahp/res-2k2-1-0-33w-0603-thick-film/dp/1738909?st=2k2%20smd%20resistor)
* [100k ohm resistor](https://be.farnell.com/vishay/crcw0402100kfked/res-100k-1-0-063w-0402-thick-film/dp/1469671?st=100k%20smd%20resistor)
* [1M ohm resistor](https://be.farnell.com/vishay/crcw04021m00fked/res-1m-1-0-063w-0402-thick-film/dp/1469667?st=1M%20smd%20resistor)
* [4k7 ohm resistor](https://be.farnell.com/vishay/crcw06034k70fkea/res-4k7-1-0-1w-0603-thick-film/dp/1469807?st=4k7%20smd%20resistor)
* [15 pins Female header](https://be.farnell.com/harwin/m20-7821546/connector-rcpt-15pos-2-54mm-1row/dp/3225931)
* [4 pins Female header](https://be.farnell.com/multicomp/2212s-04sg-85/socket-pcb-1-row-4way/dp/1593460)
* [5 pins Female header](https://be.farnell.com/multicomp/2212s-05sg-85/socket-pcb-1-row-5way/dp/1593461)
* [2 pins Male header](https://be.farnell.com/amp-te-connectivity/5-146281-2/board-board-connector-header-2/dp/1792060)
* [Nucleo](https://be.farnell.com/stmicroelectronics/nucleo-l432kc/dev-board-nucleo-32/dp/2580786?scope=partnumberlookahead&ost=NUCLEO-L432KC&searchref=searchlookahead&exaMfpn=true&ddkey=https%3Anl-BE%2FElement14_Belgium%2Fw%2Fsearch)
* [Transistor](https://be.farnell.com/on-semiconductor/mmbt4401lt1g/transistor-npn-sot-23/dp/1459105?st=MMBT4401)
* [Mosfet](https://be.farnell.com/on-semiconductor/ntr4101pt1g/mosfet-p-20v-sot-23/dp/1431303?st=NTR4101PT1G%20P-Channel%20MOSFET)
