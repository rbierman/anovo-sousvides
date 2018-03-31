# anovo-sousvides
This repo is a playground to reverse engineer the Anovo sousvide.
Model: ASVPIPE1.2

# Hadware overview
## CPU.
ARM: STM32f103RBT6
http://www.st.com/resource/en/datasheet/cd00161566.pdf

## Flash
Windbond: 25q64fvsig
https://www.winbond.com/resource-files/w25q64fw_revd_032513.pdf

## Touch screen controller
TI: TSC2046
http://www.ti.com/product/TSC2046

## Display / touchscreen
QR4 5265S01 G1/2 TP28017
ILI 9341 compatible? This is a guess...
https://cdn-shop.adafruit.com/datasheets/ILI9341.pdf

## Other hardware
SRU-09VDC-S-L-C Relay to Heating element
lm358 Dual opamp.Connected to heating element temp sensor (pin 2)


## MCU board to power board connector:
1. Electronics cooling fan +
2. Heating element temp sensor 
3. +5 v?
4. Heating element?
5. Engine through moc3041 opto coupler and BTA16 triac
6. Flued level detector +
7. Water Temperature +
8. Water Temperature -


