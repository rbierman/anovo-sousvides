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
lm358 Dual opamp.Connected to heating element temp sensor. Is this some hardware level security to prevent overheating?


## MCU board to power board connector:
1. Electronics cooling fan +
2. Ground
3. VCC
4. Heating element?
5. Engine through moc3041 opto coupler and BTA16 triac
6. Flued level detector +
7. Water Temperature +
8. Water Temperature -

J7:
1 & 2: Connected to pin 1 & 2 of J4 (MCU to powerboard)

J6:
3v3: 3v3
t: PA10
r: PA9
g: Ground

MCU Pinout:
1.
2. Speaker (R38 -> Q2)
3.
4.
5.
6.
7.
8.
9.
10.
11.
12.
13.
14.
15.
16.
17.
18.
19.
20. RA4 -> Flash C/S
21. RA5 -> Flash Clk
22. RA6 -> Flash DO
23. RA7 -> Flash DI
24.
25.
26. PB0 -> J4-4
27. PB1 -> J4-5
28. PB2 ->
29.
30.
31.
32.
33.
34.
35.
36.
37.
38.
39.
40.
41.
42.PA9 -> J6 -> TX
43.PA10 -> J6 -> RX
44.PA11 -> R20 -> usb connector data not connected
45.PA12 -> R21 -> Usb connector data not connected
46.
47.
48.
49.
50.
51.
52.
53.
54.
55.
56.
57.
58.
59.
60.
61.
62
63.
64.







