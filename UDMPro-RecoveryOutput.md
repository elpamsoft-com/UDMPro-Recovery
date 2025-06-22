```
ALPINE_UBNT_UDM_ALL> bootm
## Loading kernel from FIT Image at 08000000 ...
   Using 'udmpro@1' configuration
   Verifying Hash Integrity ... OK
   Trying 'kernel@1' kernel subimage
     Description:  AL324 UDMPRO
     Type:         Kernel Image
     Compression:  gzip compressed
     Data Start:   0x080000d8
     Data Size:    5662610 Bytes = 5.4 MiB
     Architecture: AArch64
     OS:           Linux
     Load Address: 0x04080000
     Entry Point:  0x04080000
     Hash algo:    sha1
     Hash value:   30a108dda2eb6d071afc4db5eb3ab2ceea4764c6
     Sign algo:    sha1,rsa2048:udm_al324
     Sign value:   c0877e78be46ac55b62ec68931f6a162b2e9a1a969390c2a192c3150c405736eca2040046e7b8699cf61aa9832a4b2134c04a7095307855b                                                                                                                                                                                          c1c39480fe4609c9d4fc0e34ac9bccdab994b5e10d7e7ea93734b04becc6f6cefc0fe17111b5d8c7483c159d60a1ba6e7f5570b6b9cf20565d8586ca91d1d8201f5                                                                                                                                                                                          0102bb9ddbbfc82fe9c8b5a0bf0fcf17f8447580d5d8643fb377361fa0217f90e58731b1a9edb7e0b25cc14b02f8b119cd1fde97f61dbc77f94341dc01339f81d6b                                                                                                                                                                                          1e8c879b9cc53bd8933056eb0e42dd01d1269dce63a14c78a6d6d51d221a44c0f176a225566b55834300c423a3493853589eb31f2116a8713c9f624cb0d5af1e2b3                                                                                                                                                                                          00f373b
   Verifying Hash Integrity ... sha1,rsa2048:udm_al324+ sha1,rsa2048:udm_al324+ sha1+ OK
## Loading ramdisk from FIT Image at 08000000 ...
   Using 'udmpro@1' configuration
   Trying 'ramdisk@1' ramdisk subimage
     Description:  ramdisk
     Type:         RAMDisk Image
     Compression:  gzip compressed
     Data Start:   0x08573298
     Data Size:    7057329 Bytes = 6.7 MiB
     Architecture: AArch64
     OS:           Linux
     Load Address: unavailable
     Entry Point:  unavailable
     Hash algo:    sha1
     Hash value:   490e1df910f2f1cfdfc7dcfc60a1fc8af14b5ef0
     Sign algo:    sha1,rsa2048:udm_al324
     Sign value:   82dbb9beff36e95b09d37a9d4252603e39123a0d1f59b642a8f82ce787ac2b94a0d5bb97c0d98010918985f46621eefe039937292ec77d77                                                                                                                                                                                          e0182794bfc53e68f1564cb66c6e4236bd5fd4f4b16f07943e917376f050343e4c5a9b55cb86705b628b04f740a5f1fb75d77975032e469150212013918b4e4d4a0                                                                                                                                                                                          fabdd8727fc3ae6bfee0afc71fb561b540193c9261ec915e116654387c9b9c44b79b7ea4c4d2afbc2071277cefcd15e68c2cbbd51fd203f7ddc92387236da1964aa                                                                                                                                                                                          26f3d9c312208c511f828556c76f8fd833636d027a0534dca85c4258a7e8b16fb8dd3fed8383e31843f2e7046df3475d495be27824716bf8f70a754ec1364d07733                                                                                                                                                                                          1051be0
   Verifying Hash Integrity ... sha1,rsa2048:udm_al324+ sha1,rsa2048:udm_al324+ sha1+ OK
## Loading fdt from FIT Image at 08000000 ...
   Using 'udmpro@1' configuration
   Trying 'fdt@1' fdt subimage
     Description:  al324-ubnt-udmpro-10g
     Type:         Flat Device Tree
     Compression:  uncompressed
     Data Start:   0x08566aec
     Data Size:    24698 Bytes = 24.1 KiB
     Architecture: AArch64
     Hash algo:    sha1
     Hash value:   a230ce4b18048c0f2f1b58d1df8765cb17dd1b04
     Sign algo:    sha1,rsa2048:udm_al324
     Sign value:   7390a96a6c8e81abe710401a7b3a1a6f211bc7bdac007d8fd12e3da06a0e46aacbb3ed08b1a949f790eeadc1959517da6c17842ec8777653                                                                                                                                                                                          b63032e8af4833b6e80ecef4a992edddfa080fb7c188fefdfd5dde3c800d4db92f42c8c3a752a468c15fe1dd97c91a77aa5f3119e1403ad76fbaffd3283a63d4978                                                                                                                                                                                          f1cdc551e11f36570426514a70c2c04126eb3cd607040388f0702e2b7c04974e8319d80a872c9a877858fe0fd9291d546035a1b7741d115461c43153253a8d56a6b                                                                                                                                                                                          cb8c6f9d1995ba94457bee8c5dbc64a8afbb1e647d31dd0a6c180577e72795f89761c80b9fe90fd313e78b8378995401bc1c8ed3cbbaa13050b32ea352fc580545e                                                                                                                                                                                          55dc463
   Verifying Hash Integrity ... sha1,rsa2048:udm_al324+ sha1,rsa2048:udm_al324+ sha1+ OK
   Loading fdt from 0x08566aec to 0x04078000
   Booting using the fdt blob at 0x4078000
   Uncompressing Kernel Image ... OK
   reserving fdt memory region: addr=0 size=100000
   Loading Ramdisk to 03458000, end 03b12fb1 ... OK
   Using Device Tree in place at 0000000004078000, end 0000000004081079

Starting kernel ...

[    0.722489] al_dma 0000:00:05.0: writing to VF config space
[    0.722518] al_dma 0000:00:05.0: al_dma_pci_probe: pci_enable_sriov failed, status -38
[    0.741209] al_eth 0000:00:01.0: writing to VF config space
Loading, please wait...
Starting version 241
Begin: Loading essential drivers ... modprobe: module linear not found in modules.dep
modprobe: module multipath not found in modules.dep
modprobe: module raid0 not found in modules.dep
modprobe: module raid456 not found in modules.dep
modprobe: module raid5 not found in modules.dep
modprobe: module raid6 not found in modules.dep
modprobe: module raid10 not found in modules.dep
done.
Begin: Running /scripts/init-premount ... done.
Begin: Mounting root file system ... sysid (ea15) detect, load ui-boot-udm

Ubiquiti Debian OS initialization...
Begin: UDM migration check ... Begin: Waiting device /dev/boot6 ... 5 ...
4 ...
3 ...
2 ...
1 ...
done.
Mount /mnt/data in UDM layout
mount: mounting /dev/boot6 on /udm-data failed: No such file or directory
Failure: Failed to mount udm /mnt/data, GG
Begin: Waiting device /dev/mtdblock5 ... done.
Begin: Waiting device /dev/disk/by-partlabel/overlay ... 5 ...
4 ...
3 ...
2 ...
1 ...
done.
Begin: Mounting /dev/disk/by-partlabel/overlay to /mnt/.rwfs ... Recovering userdev
/dev/disk/by-partlabel/overlay is corrupted, format and restore configs ...
Touch restore flag ...
mount: mounting /dev/disk/by-partlabel/overlay on /mnt/.rwfs failed: No such file or directory
ERROR: mount fail (-o rw,noatime -t ext4 /dev/disk/by-partlabel/overlay /mnt/.rwfs)


BusyBox v1.22.1 (Debian 1:1.22.0-19+deb9u2) built-in shell (ash)
Enter 'help' for a list of built-in commands.

(initramfs)
```


```
(initramfs) dmesg
[    0.000000] Booting Linux on physical CPU 0x0000000000 [0x411fd073]
[    0.000000] Linux version 4.19.152-ui-alpine (bdd@builder) (gcc version 6.3.0 20170516 (Debian 6.3.0-18)) #4.19.152 SMP Thu Jan 19 14:13:14 CST 2023
[    0.000000] Machine model: Annapurna Labs Alpine V2 UBNT
[    0.000000] efi: Getting EFI parameters from FDT:
[    0.000000] efi: UEFI not found.
[    0.000000] On node 0 totalpages: 524288
[    0.000000]   DMA32 zone: 8192 pages used for memmap
[    0.000000]   DMA32 zone: 0 pages reserved
[    0.000000]   DMA32 zone: 524288 pages, LIFO batch:63
[    0.000000] psci: probing for conduit method from DT.
[    0.000000] psci: PSCIv0.2 detected in firmware.
[    0.000000] psci: Using standard PSCI v0.2 function IDs
[    0.000000] psci: MIGRATE_INFO_TYPE not supported.
[    0.000000] random: get_random_bytes called from start_kernel+0x90/0x3c0 with crng_init=0
[    0.000000] percpu: Embedded 20 pages/cpu s44696 r8192 d29032 u81920
[    0.000000] pcpu-alloc: s44696 r8192 d29032 u81920 alloc=20*4096
[    0.000000] pcpu-alloc: [0] 0 [0] 1 [0] 2 [0] 3
[    0.000000] Detected PIPT I-cache on CPU0
[    0.000000] ARM_SMCCC_ARCH_WORKAROUND_1 missing from firmware
[    0.000000] CPU features: enabling workaround for EL2 vector hardening
[    0.000000] Built 1 zonelists, mobility grouping on.  Total pages: 516096
[    0.000000] Kernel command line: pci=pcie_bus_perf console=ttyS0,115200 net.ifnames=0 sysid=ea15 boot_carrier=4 root=rootfs.bkp
[    0.000000] Dentry cache hash table entries: 262144 (order: 9, 2097152 bytes)
[    0.000000] Inode-cache hash table entries: 131072 (order: 8, 1048576 bytes)
[    0.000000] Memory: 2038420K/2097152K available (8252K kernel code, 700K rwdata, 2404K rodata, 448K init, 316K bss, 58732K reserved, 0K cma-reserved)
[    0.000000] SLUB: HWalign=64, Order=0-3, MinObjects=0, CPUs=4, Nodes=1
[    0.000000] rcu: Hierarchical RCU implementation.
[    0.000000] NR_IRQS: 64, nr_irqs: 64, preallocated irqs: 0
[    0.000000] GICv3: GIC: Using split EOI/Deactivate mode
[    0.000000] GICv3: Distributor has no Range Selector support
[    0.000000] GICv3: no VLPI support, no direct LPI support
[    0.000000] GICv3: CPU0: found redistributor 0 region 0:0x00000000f0280000
[    0.000000] arch_timer: cp15 timer(s) running at 50.00MHz (phys).
[    0.000000] clocksource: arch_sys_counter: mask: 0xffffffffffffff max_cycles: 0xb8812736b, max_idle_ns: 440795202655 ns
[    0.000002] sched_clock: 56 bits at 50MHz, resolution 20ns, wraps every 4398046511100ns
[    0.000130] Console: colour dummy device 80x25
[    0.000141] Calibrating delay loop (skipped), value calculated using timer frequency.. 100.00 BogoMIPS (lpj=500000)
[    0.000146] pid_max: default: 32768 minimum: 301
[    0.000199] Mount-cache hash table entries: 4096 (order: 3, 32768 bytes)
[    0.000210] Mountpoint-cache hash table entries: 4096 (order: 3, 32768 bytes)
[    0.000713] ASID allocator initialised with 32768 entries
[    0.000742] rcu: Hierarchical SRCU implementation.
[    0.000967] EFI services will not be available.
[    0.001055] smp: Bringing up secondary CPUs ...
[    0.001217] Detected PIPT I-cache on CPU1
[    0.001230] GICv3: CPU1: found redistributor 1 region 0:0x00000000f02a0000
[    0.001242] CPU1: Booted secondary processor 0x0000000001 [0x411fd073]
[    0.001426] Detected PIPT I-cache on CPU2
[    0.001434] GICv3: CPU2: found redistributor 2 region 0:0x00000000f02c0000
[    0.001443] CPU2: Booted secondary processor 0x0000000002 [0x411fd073]
[    0.001618] Detected PIPT I-cache on CPU3
[    0.001627] GICv3: CPU3: found redistributor 3 region 0:0x00000000f02e0000
[    0.001635] CPU3: Booted secondary processor 0x0000000003 [0x411fd073]
[    0.001661] smp: Brought up 1 node, 4 CPUs
[    0.001663] SMP: Total of 4 processors activated.
[    0.001666] CPU features: detected: GIC system register CPU interface
[    0.001668] CPU features: detected: 32-bit EL0 Support
[    0.001684] CPU: All CPU(s) started at EL2
[    0.001692] alternatives: patching kernel code
[    0.002130] devtmpfs: initialized
[    0.003897] clocksource: jiffies: mask: 0xffffffff max_cycles: 0xffffffff, max_idle_ns: 19112604462750000 ns
[    0.003903] futex hash table entries: 1024 (order: 4, 65536 bytes)
[    0.004095] DMI not present or invalid.
[    0.004224] NET: Registered protocol family 16
[    0.004549] cpuidle: using governor ladder
[    0.004556] cpuidle: using governor menu
[    0.004675] DMA: preallocated 256 KiB pool for atomic allocations
[    0.004711] Initializing Peripheral Bus System - PBS
[    0.008084] HugeTLB registered 2.00 MiB page size, pre-allocated 0 pages
[    0.008332] vgaarb: loaded
[    0.008398] SCSI subsystem initialized
[    0.008448] libata version 3.00 loaded.
[    0.008502] usbcore: registered new interface driver usbfs
[    0.008514] usbcore: registered new interface driver hub
[    0.008532] usbcore: registered new device driver usb
[    0.011439] pps_core: LinuxPPS API ver. 1 registered
[    0.011442] pps_core: Software ver. 5.3.6 - Copyright 2005-2007 Rodolfo Giometti <giometti@linux.it>
[    0.011447] PTP clock support registered
[    0.011508] EDAC MC: Ver: 3.0.0
[    0.011605] Advanced Linux Sound Architecture Driver Initialized.
[    0.011758] Bluetooth: Core ver 2.22
[    0.011767] NET: Registered protocol family 31
[    0.011768] Bluetooth: HCI device and connection manager initialized
[    0.011772] Bluetooth: HCI socket layer initialized
[    0.011775] Bluetooth: L2CAP socket layer initialized
[    0.011785] Bluetooth: SCO socket layer initialized
[    0.011889] clocksource: Switched to clocksource arch_sys_counter
[    0.013939] NET: Registered protocol family 2
[    0.014139] tcp_listen_portaddr_hash hash table entries: 1024 (order: 2, 16384 bytes)
[    0.014147] TCP established hash table entries: 16384 (order: 5, 131072 bytes)
[    0.014191] TCP bind hash table entries: 16384 (order: 6, 262144 bytes)
[    0.014289] TCP: Hash tables configured (established 16384 bind 16384)
[    0.014350] UDP hash table entries: 1024 (order: 3, 32768 bytes)
[    0.014361] UDP-Lite hash table entries: 1024 (order: 3, 32768 bytes)
[    0.014421] NET: Registered protocol family 1
[    0.014568] PCI: CLS 0 bytes, default 64
[    0.014617] Unpacking initramfs...
[    0.178285] Freeing initrd memory: 6888K
[    0.178741] Initialise system trusted keyrings
[    0.178822] workingset: timestamp_bits=46 max_order=19 bucket_order=0
[    0.719677] Key type asymmetric registered
[    0.719681] Asymmetric key parser 'x509' registered
[    0.719703] Block layer SCSI generic (bsg) driver version 0.4 loaded (major 249)
[    0.719706] io scheduler noop registered
[    0.719708] io scheduler deadline registered
[    0.719764] io scheduler cfq registered (default)
[    0.719998] pl061_gpio fd887000.gpio0: PL061 GPIO chip @0x00000000fd887000 registered
[    0.720081] pl061_gpio fd888000.gpio1: PL061 GPIO chip @0x00000000fd888000 registered
[    0.720157] pl061_gpio fd889000.gpio2: PL061 GPIO chip @0x00000000fd889000 registered
[    0.720230] pl061_gpio fd88a000.gpio3: PL061 GPIO chip @0x00000000fd88a000 registered
[    0.720303] pl061_gpio fd88b000.gpio4: PL061 GPIO chip @0x00000000fd88b000 registered
[    0.720377] pl061_gpio fd897000.gpio5: PL061 GPIO chip @0x00000000fd897000 registered
[    0.720469] al-sgpo fd8b4000.sgpo: Alpine SGPO driver probed.
[    0.720530] al-internal-pcie fbc00000.pcie-internal: host bridge /soc/pcie-internal ranges:
[    0.720539] al-internal-pcie fbc00000.pcie-internal:   MEM 0xfe000000..0xfeffffff -> 0xfe000000
[    0.720580] al-internal-pcie fbc00000.pcie-internal: PCI host bridge to bus 0000:00
[    0.720583] pci_bus 0000:00: root bus resource [bus 00]
[    0.720586] pci_bus 0000:00: root bus resource [mem 0xfe000000-0xfeffffff]
[    0.720686] pci 0000:00:01.0: [1c36:0001] type 00 class 0x020000
[    0.720695] pci 0000:00:01.0: reg 0x10: [mem 0xfe000000-0xfe01ffff 64bit]
[    0.720700] pci 0000:00:01.0: reg 0x18: [mem 0xfe020000-0xfe020fff 64bit]
[    0.720705] pci 0000:00:01.0: reg 0x20: [mem 0xfe024000-0xfe027fff 64bit]
[    0.720722] pci 0000:00:01.0: PME# supported from D3hot D3cold
[    0.720970] pci 0000:00:05.0: [1c36:0022] type 00 class 0x010400
[    0.720978] pci 0000:00:05.0: reg 0x10: [mem 0xfe040000-0xfe05ffff 64bit]
[    0.720985] pci 0000:00:05.0: reg 0x20: [mem 0xfe060000-0xfe06ffff 64bit]
[    0.721001] pci 0000:00:05.0: PME# supported from D3hot D3cold
[    0.722342] pci 0000:00:01.0: BAR 0: assigned [mem 0xfe000000-0xfe01ffff 64bit]
[    0.722348] pci 0000:00:05.0: BAR 0: assigned [mem 0xfe020000-0xfe03ffff 64bit]
[    0.722352] pci 0000:00:05.0: BAR 4: assigned [mem 0xfe040000-0xfe04ffff 64bit]
[    0.722357] pci 0000:00:01.0: BAR 4: assigned [mem 0xfe050000-0xfe053fff 64bit]
[    0.722361] pci 0000:00:01.0: BAR 2: assigned [mem 0xfe054000-0xfe054fff 64bit]
[    0.722480] al_dma: Annapurna Labs DMA Driver 0.01
[    0.722489] al_dma 0000:00:05.0: writing to VF config space
[    0.722501] al_dma 0000:00:05.0: enabling device (0000 -> 0002)
[    0.722518] al_dma 0000:00:05.0: al_dma_pci_probe: pci_enable_sriov failed, status -38
[    0.722523] al_ssm_dma_init_aux: non optimal adapter configuration
[    0.723358] Serial: 8250/16550 driver, 4 ports, IRQ sharing enabled
[    0.723769] console [ttyS0] disabled
[    0.723786] fd883000.uart0: ttyS0 at MMIO 0xfd883000 (irq = 23, base_baud = 31250000) is a 16550A
[    0.737303] console [ttyS0] enabled
[    0.737454] fd884000.uart1: ttyS1 at MMIO 0xfd884000 (irq = 24, base_baud = 31250000) is a 16550A
[    0.737590] fd885000.uart2: ttyS2 at MMIO 0xfd885000 (irq = 25, base_baud = 31250000) is a 16550A
[    0.738053] [DEBUG] boot_carrier = 4
[    0.738419] m25p80 spi0.0: found mx25u6435f, expected spi_flash_jedec_detection
[    0.738423] m25p80 spi0.0: mx25u6435f (8192 Kbytes)
[    0.739370] 6 fixed-partitions partitions found on MTD device spi0.0
[    0.739372] Creating 6 MTD partitions on "spi0.0":
[    0.739376] 0x000000000000-0x0000001c0000 : "u-boot"
[    0.739633] 0x0000001c0000-0x0000001d0000 : "u-boot env"
[    0.739822] 0x0000001d0000-0x0000001e0000 : "u-boot env redundant"
[    0.740016] 0x0000001e0000-0x0000001f0000 : "Factory"
[    0.740198] 0x0000001f0000-0x000000200000 : "EEPROM"
[    0.740391] 0x000000200000-0x000000800000 : "config"
[    0.740996] libphy: Fixed MDIO Bus: probed
[    0.741049] tun: Universal TUN/TAP device driver, 1.6
[    0.741178] al_eth_drv: Initializing Peripheral Bus System (PBS) resources
[    0.741209] al_eth 0000:00:01.0: writing to VF config space
[    0.746794] al_eth 0000:00:01.0: AnnapurnaLabs unified 1GbE/10GbE/25GbE Ethernet Driver with SR-IOV al_eth v3.5.3 (Mar 14, 2019)
[    0.746800] al_eth 0000:00:01.0: driver_data is 0x0
[    0.746828] al_eth 0000:00:01.0: eth rev_id 2 (orig_rev_id 2) dev_id 1
[    0.746925] al_eth 0000:00:01.0: Board info: phy exist Yes. phy addr 4. mdio freq 2500 Khz. SFP connected No. media 1
[    0.746928] al_eth 0000:00:01.0: al_mod_eth_function_reset: performing FLR
[    0.752751] al_eth 0000:00:01.0 eth0: AnnapurnaLabs unified 1Gbe/10Gbe/25Gbe integrated found at mem fe000000, mac addr 92:b7:34:70:b5:1d
[    0.752779] libphy: alpine_mdio_shared: probed
[    0.753900] al_eth 0000:00:01.0 eth0: phy[4]: device alpine_mdio_shared_8:04, driver Generic PHY
[    0.753904] al_eth 0000:00:01.0 eth0: phy[4]:supported 6280 adv 6280
[    0.754095] ehci_hcd: USB 2.0 'Enhanced' Host Controller (EHCI) Driver
[    0.754097] ehci-pci: EHCI PCI platform driver
[    0.754113] ehci-platform: EHCI generic platform driver
[    0.754148] ohci_hcd: USB 1.1 'Open' Host Controller (OHCI) Driver
[    0.754156] ohci-pci: OHCI PCI platform driver
[    0.754168] uhci_hcd: USB Universal Host Controller Interface driver
[    0.754217] usbcore: registered new interface driver cdc_acm
[    0.754219] cdc_acm: USB Abstract Control Model driver for USB modems and ISDN adapters
[    0.754232] usbcore: registered new interface driver usb-storage
[    0.754259] usbcore: registered new interface driver cp210x
[    0.754266] usbserial: USB Serial support registered for cp210x
[    0.754350] mousedev: PS/2 mouse device common for all mice
[    0.754393] i2c /dev entries driver
[    0.758435] rtc-s35390a 1-0030: rtc core: registered rtc-s35390a as rtc0
[    0.758454] i2c i2c-0: Added multiplexed i2c bus 1
[    0.758511] i2c i2c-0: Added multiplexed i2c bus 2
[    0.758570] i2c i2c-0: Added multiplexed i2c bus 3
[    0.758667] i2c i2c-0: Added multiplexed i2c bus 4
[    0.758670] pca954x 0-0071: registered 4 multiplexed busses for I2C switch pca9546
[    0.762366] adt7475 4-002e: hwmon_device_register() is deprecated. Please convert the driver to use hwmon_device_register_with_info().
[    0.762392] adt7475 4-002e: ADT7475 device, revision 1
[    0.762395] adt7475 4-002e: Optional features: fan4 pwm2
[    0.785706] al_thermal_probe: Thermal Sensor Loaded
[    0.785848] sp805-wdt fd88c000.wdt0: registration successful
[    0.785865] Bluetooth: HCI UART driver ver 2.3
[    0.785867] Bluetooth: HCI UART protocol H4 registered
[    0.785869] Bluetooth: HCI UART protocol BCSP registered
[    0.786169] usbcore: registered new interface driver usbhid
[    0.786170] usbhid: USB HID core driver
[    0.786234] usbcore: registered new interface driver snd-usb-audio
[    0.786518] IPVS: Registered protocols ()
[    0.786545] IPVS: Connection hash table configured (size=4096, memory=64Kbytes)
[    0.786595] IPVS: ipvs loaded.
[    0.786649] gre: GRE over IPv4 demultiplexor driver
[    0.786651] ip_gre: GRE over IPv4 tunneling driver
[    0.787029] IPv4 over IPsec tunneling driver
[    0.787212] Initializing XFRM netlink socket
[    0.787387] NET: Registered protocol family 10
[    0.787826] Segment Routing with IPv6
[    0.787916] sit: IPv6, IPv4 and MPLS over IPv4 tunneling driver
[    0.788087] NET: Registered protocol family 17
[    0.788094] NET: Registered protocol family 15
[    0.788108] bridge: filtering via arp/ip/ip6tables is no longer available by default. Update your scripts to load br_netfilter if you need this.
[    0.788145] Bluetooth: RFCOMM socket layer initialized
[    0.788156] Bluetooth: RFCOMM ver 1.11
[    0.788160] Bluetooth: BNEP (Ethernet Emulation) ver 1.3
[    0.788166] Bluetooth: BNEP socket layer initialized
[    0.788167] Bluetooth: HIDP (Human Interface Emulation) ver 1.2
[    0.788170] Bluetooth: HIDP socket layer initialized
[    0.788171] 8021q: 802.1Q VLAN Support v1.8
[    0.788355] registered taskstats version 1
[    0.788357] Loading compiled-in X.509 certificates
[    0.790432] Key type encrypted registered
[    0.790732] input: soc:gpio_keys as /devices/platform/soc/soc:gpio_keys/input/input0
[    0.791937] rtc-s35390a 1-0030: setting system clock to 2025-06-22 14:10:40 UTC (1750601440)
[    0.791993] cfg80211: Loading compiled-in X.509 certificates for regulatory database
[    0.857186] cfg80211: Loaded X.509 cert 'sforshee: 00b28ddf47aef9cea7'
[    0.857195] ALSA device list:
[    0.857197]   No soundcards found.
[    0.857422] Freeing unused kernel memory: 448K
[    0.857485] platform regulatory.0: Direct firmware load for regulatory.db failed with error -2
[    0.857488] cfg80211: failed to load regulatory.db
[    0.901975] Run /init as init process
[    0.975169] al_eth 0000:00:01.0 eth8: renamed from eth0
[    1.029457] loop: module loaded
[    1.033403] squashfs: version 4.0 (2009/01/31) Phillip Lougher
[    1.038854] random: fast init done
[   11.116387] random: crng init done
[   11.249529] EXT4-fs (mtdblock5): recovery complete
[   11.300570] EXT4-fs (mtdblock5): mounted filesystem with ordered data mode. Opts: (null)
(initramfs)
```