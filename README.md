# anovo-sousvides
This repo is a playground to reverse engineer the Anovo sousvide.
Model: ASVPIPE1.2

# Hadware overview
## CPU.
ARM: STM32f103RBT6
http://www.st.com/resource/en/datasheet/cd00161566.pdf

## Flash
Windbond: 25q64fvsig
https://www.winbond.com/resource-files/w25q64fv%20revs%2007182017.pdf

## Touch screen controller
TI: TSC2046
http://www.ti.com/product/TSC2046

## Display / touchscreen
2.8Inch
QR4 5265S01 G1/2 TP28017
ILI 9341 or ILI 9325compatible? This is a guess...
Flatcable connector seems to be compatible with:
https://www.sparkfun.com/datasheets/LCD/ELT240320ATP.pdf
https://cdn-shop.adafruit.com/datasheets/ILI9341.pdf
https://github.com/joseluu/STM32F103-LCD-test

1: db1
2: db2
3: db3
4: db4


22:
23:
24:
25:
26:
27:
28:
33: vcc (3v3)
34: grnd

## Other hardware
SRU-09VDC-S-L-C Relay to Heating element
lm358 Dual opamp.Connected to heating element temp sensor. Is this some hardware level security to prevent overheating?


## MCU board to power board connector:
1. Electronics cooling fan +
2. Ground
3. VCC
4. Heating through moc3041 opto coupler and (a triac?)
5. Engine through moc3041 opto coupler and BTA16 triac
6. Flued level detector +
7. Water Temperature +
8. Water Temperature -

J2: Debug header

1.
2. 3v3
3.
4. MCU 7 (NRST)
5. MCU 50 (PA15/JTDI)
6. MCU 55 (PB3/JTDO)
7. MCU 46 (PA13/JTMS/SWDIO)
8.
9. MCU 49 (PA14/JTCK/SWCLK)
10.GND

J6:

3v3: 3v3
t: PA10
r: PA9
g: Ground

J7:

1 & 2: Connected to pin 1 & 2 of J4 (MCU to powerboard)


MCU Pinout:

|Pin | Description|
|---|---|
|1.||
|2. | Speaker (R38 -> Q2) |
|3.||
|4.||
|5.||
|6.||
|7.||
|8.||
|9.||
|10.||
|11.||
|12.||
|13.||
|14.||
|15.||
|16.||
|17.||
|18.||
|19.||
|20.| RA4 -> Flash C/S|
|21.| RA5 -> Flash Clk|
|22.| RA6 -> Flash DO|
|23.| RA7 -> Flash DI|
|24.||
|25.||
|26.| PB0 -> J4-4|
|27.| PB1 -> J4-5|
|28.| PB2 ->|
|29.||
|30.||
|31.||
|32.||
|33.||
|34.||
|35.||
|36.||
|37.||
|38.||
|39.||
|40.||
|41.||
|42. |PA9 -> J6 -> TX|
|43. |PA10 -> J6 -> RX|
|44. |PA11 -> R20 -> usb connector data not connected|
|45. |PA12 -> R21 -> Usb connector data not connected|
|46.||
|47.||
|48.||
|49.||
|50.||
|51.||
|52.||
|53.||
|54.||
|55.||
|56.||
|57.||
|58.||
|59.||
|60.||
|61.||
|62.||
|63.||
|64.||

# Reverse enineering resources
http://jcjc-dev.com/2016/06/08/reversing-huawei-4-dumping-flash/

## FTDI 2232h
|FT2232H Pin# | Pin Name | MPSEE Function | Type | Description |
|----|----|----|----|----|
| 16 | ADBUS0 | SCLK | Output |Serial Clock |
| 17 | ADBUS1 | DO (MOSI) |Output | Master Out |
| 18 | ADBUS2 | DI (MISO) |Input | Master In |
| 19 | ADBUS3 | CS |Output | Chip Select |

## w25q64fw Flash pinout
|Pin # | Pin Name| |
|----|------|----|
| 1 | CS | Chip select input|
| 2 | DO (IO1) | Data Output|
| 3 | | |
| 4 | Gnd | Ground|
| 5 | DI | Data input|
| 6 | CLK | Serial clock input|
| 7 | HOLD / RESET | |
| 8 | VCC | Power supply |

## Read protection
https://medium.com/@LargeCardinal/how-to-bypass-debug-disabling-and-crp-on-stm32f103-7116e7abb546
https://gist.github.com/egirault/7b3fe7041e1bf5e2258ed5df7083f14d
