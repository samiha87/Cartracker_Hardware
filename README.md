# Cartracker_Hardware
KiCad

# General
- Component type SMD
- Components need to be clearly suitable for soldering by hand
- Manufactured at pcbway
- Design environment KiCad

## Components overview
- NEOWAY M590: GSM/GPRS, UART 3.3V
- Bluetooth: HM-10, UART 3.3V
- U-Blox NEO-6M-0-0: GPS, SPI. STM32 as Master, GPS as Slave.
- MPU-9250/6500: IMU, I2C. 
- W-Bust interface: L9637D, UART 5V
### Extra
- Raspberry Pi 4, SPI. STM32 as Slave, Raspberry as Master.

### Datasheets:
- https://www.u-blox.com/sites/default/files/products/documents/NEO-6_DataSheet_%28GPS.G6-HW-09005%29.pdf

## Processor:

For microcontroller using STM32F103C8T6 (Recommend buying from Aliexpress). Has 3 Uarts and 2 of them are 5V tolerant. 
- Ref: https://opencircuit.shop/resources/content/ad8542259ac19/crop/900-600/STM32-ARM-development-board-STM32F103C8T6.jpg

## Power

For power we use Switching circuit and W-Bust connectors +VB(Battery voltage). Red wiring bring 12V to circuit. Which then is connected to switching circuit and converted to 3.3V and 5V. As for converter chips using Step-Down(Buck) chips TPS62160
- Ref: http://www.ti.com/product/TPS62160

## Webasto W-Bus.
On Webasto T91 transmitter/receiver, found 4pin cable ment for Webasto timer. On Volkswagen Caddy this was located to driver side.
To access this cable you need to open the drivers desk from left side, next to wheel.

### Wiring:

Wiring colors can change depending on car.

- Yellow cable: W-Bust
- Red cable: 12V
- Black: Ground
- Brown: Ground

### Interface:
As for interface using L9637D to shift 12V to 5V. Can be attached to UART 2 line which is 5V tolerant.
- Ref: https://www.mikrocontroller.net/attachment/251313/W-Bus.png
