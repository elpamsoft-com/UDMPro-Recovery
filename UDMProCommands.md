# What has been tried already?
#### WARNING: Updating or alterting firmware is dangerous

## The corrupt uBoot theory
Both rolling back uBoot firmware and updating to the latest versions have proven fruitless.

The uBoot is stored on the 8MB MX25U6435F chip. This chip is devided into 6 partitions.

```
6 fixed-partitions partitions found on MTD device spi0.0
Creating 6 MTD partitions on "spi0.0":
0x000000-0x1c0000 : "u-boot"				mtd0		UBOOT
0x1c0000-0x1d0000 : "u-boot env"			mtd1		ENV
0x1d0000-0x1e0000 : "u-boot env redundant"	mtd2		ENV
0x1e0000-0x1f0000 : "Factory"				mtd3		empty
0x1f0000-0x200000 : "EEPROM"				mtd4		MAC address, board model
0x200000-0x800000 : "config"				mtd5		version information
```

The first u-boot partition is divided into preboot, device trees for all UDM models, and the uboot itself as yo can see below.

```
ALPINE_UBNT_UDM_ALL> flash_contents_toc_print
SF: Detected MX25U6435F with page size 256 Bytes, erase size 4 KiB, total 8 MiB
#  | OBJ ID                    | Instance | Name     | Device  | Offset   | Max Size
------------------------------------------------------------------------------------
 0 | 00000d (     PRE_BOOT_V2) |        0 |  preboot | Current | 00000000 | 00080000
 1 | 000002 (              DT) |        0 |   dt_pro | Current | 00081000 | 00007000
 2 | 000002 (              DT) |        1 |       dt | Current | 00088000 | 00007000
 3 | 000002 (              DT) |        2 | dt_pro_1 | Current | 0008f000 | 00007000
 4 | 000002 (              DT) |        3 | dt_pro_1 | Current | 00096000 | 00007000
 5 | 000002 (              DT) |        4 | dt_pro_s | Current | 0009d000 | 00007000
 6 | 000002 (              DT) |        5 | dt_pro_m | Current | 000a4000 | 00007000
 7 | 000005 (           UBOOT) |        0 |    uboot | Current | 000ab000 | 00115000
 8 | 000007 (       UBOOT_ENV) |        0 | uboot-en | Current | 001c0000 | 00010000
 9 | 000008 (   UBOOT_ENV_RED) |        0 | uboot-re | Current | 001d0000 | 00230000
 ```

##### WARNING: During testing I managed to "Extra brick" my test UDMPro a few time that required removing the MX25U6435F chip and using a TL866II to reflash a new uBoot.

## A corrupt EEPROM theory
This is the 64KB AT24C64D EEPROM found at I2C Address 0x57 and read at boot. If this chip is corrupt the SBL (secondary boot loader) fails to load at all.

A dump of a good EEPROM can be taken from a working UDM-Pro ([See this page](UDMProExtractFirmware.md))

## Booting from a Recovery image
Booting to recovery does not seem to be very helpful and does not restore the missing hardware. 

1. Download a recovery image ([see here](Firmware/))
2. Connect via [serial cable](UDMProConsoleCable.md)
3. Using something that supports YMODEM (eg. [ExtraPutty](https://sourceforge.net/projects/extraputty/)) connect to the COM port
4. Boot the UDMPro and at the prompt type "loady"
5. In ExtraPutty top menu, select "File Transfer", "YMODEM", then "Send File"
6. Select the Recovery BIN file and send it, this could take 45min.
7. Type the command "bootm"

You can also upload a new uBoot BIN using simular commands, but you are likely to make the device worse if you try with an old uboot-1 build.