# Cartracker_Hardware
KiCad

# General
- Component type SMD
- Components need to be clearly suitable for soldering by hand
- Manufactured at pcbway
- Design environment KiCad, Circuit Diagram

STM32 supports CAN protocol. Is it possible to access OBD2 CAN HIGH and CAN LOW.
https://components101.com/connectors/obd2

## Components overview
- STM32F103C8T
- NEOWAY M590: GSM/GPRS, UART 3.3V
- Bluetooth: HM-10, UART 3.3V
- U-Blox NEO-6M: GPS, SPI. STM32 as Master, GPS as Slave.
- MPU-9250/6500: IMU, I2C. 
- W-Bus(Webasto) interface: L9637D, UART 5V
### Extra
- Raspberry Pi 4, Bluetooth. Raspberry uses BLE to connect the microcontroller. (Does raspberry have any need to connect microcontroller?) 2 Possible option BLE or SPI.

### Datasheets:
- https://www.u-blox.com/sites/default/files/products/documents/NEO-6_DataSheet_%28GPS.G6-HW-09005%29.pdf
- http://cyntech.co.uk/downloads/neoway-m590-hardware-design-manual-v1.pdf
- https://www.st.com/resource/en/datasheet/stm32f103c8.pdf
- https://www.academia.edu/15633281/GSM_GPRS_Modem_-_Neoway_M590_M590E

## Processor:

For microcontroller using STM32F103C8T6 (Recommend buying from Aliexpress). Has 3 Uarts and 2 of them are 5V tolerant. 
- Ref: https://opencircuit.shop/resources/content/ad8542259ac19/crop/900-600/STM32-ARM-development-board-STM32F103C8T6.jpg

## Power

For power we use Switching circuit and W-Bust connectors +VB(Battery voltage). Red wiring bring 12V to circuit. Which then is connected to switching circuit and converted to 3.3V and 5V. As for converter chips using Step-Down(Buck) chips TPS62160
### 3.3V Output
- TPS62160 1A
### 5V Output
- TPS62160 1A
- ACT4060A 2A. Due the power reuquirements of NEOWAY GSM module.
### Car battery monitorin

When car is running and battery is charged voltage jumps to 13.7V or 14.7V. Need to find out.

- Ref: http://www.ti.com/product/TPS62160
- Ref: https://media.digikey.com/pdf/Data%20Sheets/Active-Semi%20PDF's/ACT4060A.pdf

## Webasto W-Bus.
On Webasto T91 transmitter/receiver, found 4pin cable ment for Webasto timer. On Volkswagen Caddy this was located to driver side.
To access this cable you need to open the drivers desk from left side, next to wheel.

### Wiring:

Wiring colors can change depending on car.

- Yellow cable: W-Bus
- Red cable: 12V. Not sure if this comes straight from Car Battery. If yes can be used to monitor battery voltage.
- Black: Ground
- Brown: Ground

### Interface:
As for interface using L9637D to shift 12V to 5V. Can be attached to UART 2 line which is 5V tolerant.
- Ref: https://www.mikrocontroller.net/attachment/251313/W-Bus.png
