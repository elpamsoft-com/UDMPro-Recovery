# UDMPro-Recovery

My Dream Machine Pro is not booting what is wrong?

### 1. Not booting after an update
Power cycle the UDM and see if it boots. If still broken, remote the power cable for 20min and try boot agin.

### 2. Little bit bricked
Try the official "Reset" button recovery procedure.
[Official Link]

### 3. Quite bricked
If no network link (the little light on the network port) during the "Reset" button recovery procedure.

### 4. Really bricked
The only way to confirm "Really Bricked" is to connect a serial console cable to the board and watch the console during boot.

[Link to Console Cable]

A "Really Bricked" device will show the following on boot:
```
agent_wakeup v2.10
I2C Preload Disabled!
EEPROM Revision ID = 00
Device ID = 0000
Device Info:
```
If it is not "Really Bricked" the device will show the following during boot:
```
agent_wakeup v2.10
EEPROM Revision ID = 39
Device ID = a324
Device Info: v2sil-39-rc1
```