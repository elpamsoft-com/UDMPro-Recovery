# What has been tried already?
#### WARNING: Updating or alterting firmware is dangerous

## The corrupt uBoot theory
Both rolling back uBoot firmware and updating to the latest versions have proven fruitless.

##### WARNING: During testing I managed to "Extra brick" my test UDMPro a few time that required removing the MX25U6435F chip and using a TL866II to reflash a new uBoot.

## Booting from a Recovery image
Booting to recovery does not seem to be very helpful and does not restore the missing hardware. 

1. Download a recovery image ([see here](Firmware/))
2. Connect via [serial cable](UDMProConsoleCable.md)
3. Using something that supports YMODEM (eg. [ExtraPutty](https://sourceforge.net/projects/extraputty/)) connect to the COM port
4. Boot the UDMPro and at the prompt type "loady"
5. In ExtraPutty top menu, select "File Transfer", "YMODEM", then "Send File"
6. Select the Recovery BIN file and send it, this could take 45min.
7. Type "bootm"

You can also upload a new uBoot BIN using simular commands, but you are likely to make the device worse if you try with an old uboot-1 build.