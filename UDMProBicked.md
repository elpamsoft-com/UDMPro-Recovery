# What is causing the UDM Pro to not boot?

Lets examine the console output bit by bit.

```
stage2_loader v2.22.3
SPD I2C Address: 57
Executing next!
```

The AL324 finds the 64KB EEPROM at I2C 0x57

```
-----------------------------------------------------
Stage 3 version: 2.22.0
Commit ID: 6088bc3
CVOS commit ID: bac1d521
HAL commit ID: 61afa9c3b
Build date: Nov  3 2023 00:42:11
-----------------------------------------------------
```

This looks good so far, the AL324 is starts booting uBOOT from the 8MB SPI chip using configuration stored on a tiny bit of flash on the AL324

```
agent_wakeup v2.10
I2C Preload Disabled!
EEPROM Revision ID = 00
Device ID = 0000
Device Info:
```

Oh no, "I2C Preload Disabled!". This I2C chip is available, but the Stage 3 loader has been configured to not load the board information. Without the board information it doesnt know what the device tree it should load.

Lets continue booting using fail safe [Device Tree Control](https://docs.u-boot.org/en/latest/develop/devicetree/control.html).

```
DRAM frequency violation!
CPU frequency violation!
subsystem id: 0xea15
hardware revision id: 0x0002d308
instance_num =  3
Loading DT to 01100000 (25844 bytes)...
obj_hdr_dt_offset: 0x96000
Board config ID: alpine_v2_ubnt udm pro v6.0
group A off violation!
group B off violation!
group C off violation!
group D off violation!
SATA 0 violation!
ETH violation!
PCIe 0 speed violation (1 > 0)!
PCIe 1 speed violation (1 > 0)!
```

Violations due to the wrong DRAM and CPU frequencies are trying to be set since the board information is not known.
The hardware revision id is correct, it is reading this from the I2C 0x57 EEPROM, so thats nice.

Okay, lets load the next stage of uBoot from the 8MB SPI chip.

```
Loading application to 01100000 (769144 bytes)...
Executing application...


U-Boot 2015.07-alpine_db-2.21-HAL (Jan 19 2024 - 15:34:25 +0800), Build: ubnt_udm_all0-5-2024-01-19-15-34-00-b0ce2f0f

I2C:   ready
DRAM:  2 GiB
Trace early: 0000000000ff0000, 10000
```

Wait, this device has 4 GiB DRAM, not 2 GiB. Looks like the fail safe board config only configures 2 GiB.


```
   _
  /_\  _ __  _ __   __ _ _ __  _   _ _ __ _ __   __ _
 //_\\| '_ \| '_ \ / _` | '_ \| | | | '__| '_ \ / _` |
/  _  \ | | | | | | (_| | |_) | |_| | |  | | | | (_| |
\_/ \_/_| |_|_| |_|\__,_| .__/ \__,_|_|  |_| |_|\__,_|
   __       _           |_|
  / /  __ _| |__  ___
 / /  / _` | '_ \/ __|
/ /__| (_| | |_) \__ \
\____/\__,_|_.__/|___/
               ___             _
 /\ /\        / __\ ___   ___ | |_
/ / \ \_____ /__\/// _ \ / _ \| __|
\ \_/ /_____/ \/  \ (_) | (_) | |_
 \___/      \_____/\___/ \___/ \__|

temprature: 46 degrees
eeprom_per_device_init: no valid information found!
power_init_board: EEPROM per device information is not valid - using defaults!
SF: Detected MX25U6435F with page size 256 Bytes, erase size 4 KiB, total 8 MiB
U-Boot script not found in TOC!
Board config ID: alpine_v2_ubnt udm pro v6.0, 113-723-8
Trace disabled
NAND:  0 MiB
SF: Detected MX25U6435F with page size 256 Bytes, erase size 4 KiB, total 8 MiB
*** Warning - bad CRC, using default environment
```

Looks like eeprom_per_device_init and power_init_board are failing so defaults are going to be used.

```
model = udmpro, board_info->bom_rev = 8, fit_index = 2
mac: [74acb95ac732] + [3]
setenv eth3addr: 74:ac:b9:5a:c7:32
setenv ethaddr: 74:ac:b9:5a:c7:33
setenv eth2addr: 74:ac:b9:5a:c7:34
PCI:
  00:01.0     - 1c36:0001 - Network controller
  00:05.0     - 1c36:0022 - Mass storage controller
handle_link: PCIE_0 no link found
handle_link: PCIE_1 no link found
handle_link: PCIE_2 no link found
```

PCIe devices are only found on 01.0 and 05.0, on a proper boot eight devices should be found, not just these two.

This is just the AL324 inbuilt network controller, and the Mass Storage controller is the SATA controller


```
In:    serial
Out:   serial
Err:   serial
Reset gpio number: 23
Entering recovery mode: 1/1
!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!
!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!
!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!

             I2C Preload Disabled!

!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!
!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!
!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!
!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!
!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!
!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!

   Bootstraps / DT / Capabilities Mismatch!

!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!
!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!
!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!
```
Once again we get the "I2C Preload Disabled!" as well as "Capabilities Mismatch!" due to fail safe defaults being not compatible.

```
Net:   , al_eth1
Warning: al_eth1 using MAC address from net device

Setting bus to 4
al_eth_init: No link!
rtk_switch_probe: Unsupported chip
rtk_switch_init: -1
rtl83xx_switch_initialize: rtk_switch_init -> [-1]
rtl83xx_switch_initialize: rtk_port_macForceLinkExt_set for EXT_PORT1 -> [-1]
setup_led: config_led!!
enable_sled_oe:: gpio(42) gpio_get_value(1) 1
enable_sled_oe:: gpio(42) gpio_get_value(2) 0
Autobooting in 2 seconds, press "<Esc><Esc>" to stop
bootargs=pci=pcie_bus_perf console=ttyS0,115200 net.ifnames=0 sysid=ea15 boot_carrier=4 root= boot=recovery
starting USB...
USB0:   XHCI host controller not found
Port not available.
starting USB...
USB0:   XHCI host controller not found
Port not available.
USB is stopped. Please issue 'usb start' first.
USB is stopped. Please issue 'usb start' first.
Wrong Image Format for bootm command
ERROR: can't get kernel image!
ALPINE_UBNT_UDM_ALL>
```

So, we have no network, no USB controller normally found on the PCIe bus, this no eMMC can be found.