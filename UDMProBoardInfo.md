# UDM-Pro Dream Machine Pro

## Circuit Layout

The SOC is connected to the main eMMC storage via a USB3 controller.

AL324_SOC --PCIe--> ASM1042A --USB3--> GL3224E --> eMMC

## Board Layout
| ID  | Description  | ID  | Description  |
|:---:|-------------:|:---:| ------------:|
| A   | GL3224E</br>USB3.0 eMMC Controller         | G   | Annapurna Labs AL324</br>Cortex A57         |
| B   | THGBMFG7C1LBAIL</br>16GB eMMC Flash         | H   | 4GB DDR (4x 512MB DDR RAM)         |
| C   | ASM1042A</br>PCIe USB3.0 Controller         | J   | LMK00338</br>PCIe Level Translator |
| D   | W25X05CL</br>ASM1042A USB3.0 Firmware         | K   | Network Switch         |
| E   | MX25U6435F</br>8MB SPI FLASH | L   | ADT7470</br>Temperature, Sensor and Fans |
| F   | AT24C64D</br>64KB EEPROM</br>I2C Address 0x57         | N   | TCA9546A</br>I2C Expander |
| M   | AR8033-AL1A</br>WAN 1G Ethernet | O   | TXB0104</br>Voltage-Level Translator |


![alt text](Diagrams/UDMPro-Board.png "UDM-Pro Board")
