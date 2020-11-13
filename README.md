# LED Interface for Raspberry Pi Zero

This is a hat designed for a Raspberry Pi Zero. It consists of two headers for I2S microphones (the sort of which are availble for under 2$ on aliexpress) and two level shifted outputs.

The primary purpose is to control 4-wire LED strips using the four pin header. This should also be able to provide the Pi Zero with power.

There's also a HUB-75 connector for driving LED panels. This might be less useful, and probably wasn't neccessary. (These are much better suited to be driven off a PI 3 or 4 if the
frame rate or color depth matters, and some research into [hzeller's](https://github.com/hzeller/rpi-rgb-led-matrix) excellent library points out that the I2S CLK pin is also the same
as the PWM pin which drives the OE signal to the panels for better performance. I'm using a different pin mapping anyway (TODO: write it down..) so it wont work out of the box in any case.)

