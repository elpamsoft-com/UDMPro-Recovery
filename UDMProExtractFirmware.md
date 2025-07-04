# Extract Firmware

## Download pre-extracted firmware
Download file [here](Firmware/)

## Extracting Recovery firmware from a working UDM-Pro
If you have the luxuary of a working UDMPro you can connect over SSH and configure a TFTP server to receive the firmware dump.

```
dd if=/dev/disk/by-partlabel/recovery of=/volume1/recovery.bin
tftp -l /volume1/recovery.bin -r recovery.bin -p 192.168.214.120
rm /volume1/recovery.bin
```

###### replace "192.168.214.120" with your local PC IP address with a [TFTP Server](http://tftpd32.jounin.net) running as Administrator.

## Extracting uBoot from a downloaded UDM-Pro firmware
Download a [UDMPro firmware](https://ui.com/download/software/udm-pro) 

Use a hex editor to find the uBoot offset and length.
1. Find the text "PARTuboot" is older or "FILEuboot" (See Image)in newer firmware.
2. Record the length in hex (6 digits - See Image)
3. Find the uboot offset start
![alt text](Diagrams/UDMPro-uBootExtract.png "UDM-Pro uBoot Hex")
4. Convertboth Hex numbers to Dec
5. uBoot Length hex=16 6c e4 [converted](https://www.rapidtables.com/convert/number/hex-to-decimal.html?x=166CE4) to decimal is 1469668
6. uBoot offset hex=144 [converted](https://www.rapidtables.com/convert/number/hex-to-decimal.html?x=144) to decimal is 324

Linux
```
dd if=9a40-UDMPRO-4.2.12.bin of=uboot-4.2.12.bin bs=1 skip=324 count=1469668 conv=notrunc
```

Windows Powershell
```
$filePath = "C:\Path\To\9a40-UDMPRO-4.2.12.bin"
$offset = 324
$bytesToExtract = 1469668
$outputPath = "C:\Path\To\uboot-4.1.12.bin"

try {
    Write-Host "Extracting $bytesToExtract bytes from offset $offset to $outputPath"
    $fileBytes = [System.IO.File]::ReadAllBytes($filePath)
    $extractedBytes = $fileBytes | Select-Object -Skip $offset -First $bytesToExtract
    [System.IO.File]::WriteAllBytes($outputPath, $extractedBytes)
    Write-Host "Successfully extracted $bytesToExtract bytes from offset $offset to $outputPath"
} catch {
    Write-Error "Error extracting file: $($_.Exception.Message)"
}
```

## Extracting Recovery from a downloaded UDM-Pro firmware
Download a [UDMPro firmware](https://ui.com/download/software/udm-pro) 

Use a hex editor to find the uBoot offset and length.
1. Find the text "PARTkernel" in older or "FILEkernel" (See Image) in newer firmware. Older fimrware have a dedicated "PARTrecovery".
2. Record the length in hex (6 digits - See Image)
3. Find the Recovery offset starting at "D0 0D FE ED" (See Image)
![alt text](Diagrams/UDMPro-RecoveryExtract.png "UDM-Pro Recovery Hex")
4. Convertboth Hex numbers to Dec
5. Recovery Length hex=c2 ec c6 [converted](https://www.rapidtables.com/convert/number/hex-to-decimal.html?x=C2ECC6) to decimal is 12774598
6. Recovery offset hex=16 fb e0 [converted](https://www.rapidtables.com/convert/number/hex-to-decimal.html?x=16FBE0) to decimal is 1506272

Linux
```
dd if=e2cf-udmpro-2.4.27.bin of=recovery-2.4.27.bin bs=1 skip=1506272 count=12774598 conv=notrunc
```

Windows Powershell
```
$filePath = "C:\Path\To\e2cf-udmpro-2.4.27.bin"
$offset = 1506272
$bytesToExtract = 12774598
$outputPath = "C:\Path\To\recovery-2.4.27.bin"

try {
    Write-Host "Extracting $bytesToExtract bytes from offset $offset to $outputPath"
    $fileBytes = [System.IO.File]::ReadAllBytes($filePath)
    $extractedBytes = $fileBytes | Select-Object -Skip $offset -First $bytesToExtract
    [System.IO.File]::WriteAllBytes($outputPath, $extractedBytes)
    Write-Host "Successfully extracted $bytesToExtract bytes from offset $offset to $outputPath"
} catch {
    Write-Error "Error extracting file: $($_.Exception.Message)"
}
```

## Extract EEPROM from a working UDM-Pro
A copy of the 64KB EEPROM AT24C64D found at I2C Address 0x57 can be downloaded from a working UDM-Pro you can connect over SSH and configure a TFTP server to receive the firmware dump.

This EEPROM is different from the EEPROM partition found on the 8MB SPI chip. (See [Board Info](UDMProBoardInfo.md))

To do this you must mount the AT24C64D chip at I2C address 0x57. dump its contents to a file, then unmount the chip again.

```
echo 24c64 0x57 > /sys/bus/i2c/devices/i2c-2/new_device
dd if=/sys/bus/i2c/devices/2-0057/eeprom of=/volume1/eeprom.bin
tftp -l /volume1/eeprom.bin -r eeprom.bin -p 192.168.214.120
rm /volume1/eeprom.bin
echo 0x57 > /sys/bus/i2c/devices/i2c-2/delete_device
```
###### replace "192.168.214.120" with your local PC IP address with a [TFTP Server](http://tftpd32.jounin.net) running as Administrator.