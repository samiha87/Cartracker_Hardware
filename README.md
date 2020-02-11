# Cartracker_Hardware
KiCad

## Power

For power we use Switching circuit and W-Bust connectors +VB(Battert voltage). Red wiring bring 12V to circuit. Which then is connected to switching circuit and converted to 3.3V and 5V.

## Webasto W-Bus.
On Webasto T91 transmitter/receiver, found 4pin cable ment for Webasto timer. On Volkswagen Caddy this was located to driver side.
To access this cable you need to open the drivers desk from left side, next to wheel.

### Wiring:
- Yellow cable: W-Bust
- Red cable: 12V
- Black: Ground
- Brown: Ground

### Interface:
As for interface using L9637D to shift 12V to 5V. 
- Ref: https://www.mikrocontroller.net/attachment/251313/W-Bus.png
