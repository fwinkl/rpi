# rpi
Some utilities for the Raspberry Pi.

## bin/cec-listen

My RPI is constantly on and connected to the TV. However, I did not want to continously run Kodi because even when
idle this tends to increase the CPU (and presumably power) usage of the RPI. This script listens on the HDMI port
and starts Kodi when the TV switches to this channel. Follow these steps:

1. `sudo apt install cec-utils`
2. Find the TV name by running `cec-client --log-level 4` on the PI, switch the TV to the appropriate channel and look for the `source activated...` line in the output. Replace that string in the script with your own name.
3. Configure Kodi to shutdown when idle : Settings - System - Power saving - Shutdown function timer
4. Test that all is working by running `cec-listen`

You probably want to install `cec-listen` as a systemd user service or launch it on system startup by other means.
