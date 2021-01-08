# Panel Control Hardware

## Power

### Requirements 
* Power button which either boots or sends a signal to the RPI to shutdown.
* Battery status indication (can be crude, maybe just color or flashing to indicate low battery vs charging vs charged)
* Should not draw too much current when off but fully charged
* OE needs to be disabled on panels when PI is off
* MCU with analog voltage from battery
* MCU needs to tell RPI to shut down when battery is <10%

### Ideas
* Use MOSFET rated for 15W (5V/3A) to power on the RPI
* RPI GPIO to act as a power status pin. Shutdown sequence waits for a level change on this pin before cutting the power.
    * High means PI is shutting down; when it goes low, its finished powering off.
# LED Interface

(old README, needs update)

This is a hat designed for a Raspberry Pi Zero. It consists of two headers for I2S microphones (the sort of which are availble for under 2$ on aliexpress) and two level shifted outputs.

The primary purpose is to control 4-wire LED strips using the four pin header. This should also be able to provide the Pi Zero with power.

There's also a HUB-75 connector for driving LED panels. This might be less useful, and probably wasn't neccessary. (These are much better suited to be driven off a PI 3 or 4 if the
frame rate or color depth matters, and some research into [hzeller's](https://github.com/hzeller/rpi-rgb-led-matrix) excellent library points out that the I2S CLK pin is also the same
as the PWM pin which drives the OE signal to the panels for better performance. I'm using a different pin mapping anyway (TODO: write it down..) so it wont work out of the box in any case.)

