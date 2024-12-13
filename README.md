# Weather Dashboard

> LCD weather dash powered by an ESP32-C3 and a 1.8" TFT

## BOM

- 1x Wemos C3 Mini
  LDO Datasheet: https://stm32-base.org/assets/pdf/regulators/ME6211.pdf
  Schematic: https://www.wemos.cc/en/latest/_static/files/sch_c3_mini_v2.1.0.pdf
- 1x 1.8" ST7355 TFT
- 1x 300-800 mAh Li-Po battery with BMS - probably not the best idea to get from Aliexpress
  https://www.aliexpress.us/item/3256806874686429.html ($2.96 gift / $3.79) 850 mAh "2pin 2.0mm"
  https://www.aliexpress.us/item/3256807284093967.html ($4.26 / $9.26) 800 mAh
  https://www.aliexpress.us/item/3256807984479268.html ($5.13 gift / $10.90) 1000 mAh
  https://www.aliexpress.us/item/3256802542021832.html ($3.55 welcome / $9.55) 1000 mAh
  https://www.aliexpress.us/item/3256806084256547.html ($6.11 / $10.54) 1000 mAh
  https://www.aliexpress.us/item/3256806667777057.html ($4.33 / $8.50) 500 mAh
  https://www.aliexpress.us/item/3256806281367340.html ($5.45 / $9.40) 600 mAh
- 2x JST PH-2.0 connector + wires/plug
  https://www.aliexpress.us/item/3256806041370367.html ($0.99 welcome / $1.08) 5 sets 2P
- 1x 3 pin SPDT switch - 0.5A
  https://www.aliexpress.us/item/2255800513009332.html ($0.82 / $0.84) 10 pcs
  https://www.aliexpress.us/item/3256803752541650.html ($0.99 gift / $2.36)
  SS-12F15
- 1x 1N5817 diode
  https://www.diodes.com/assets/Datasheets/1N5817-1N5819.pdf
  https://www.aliexpress.us/item/3256801365779334.html ($0.91 50pcs welcome)
  https://www.aliexpress.us/item/2255801086330895.html ($1.03 50pcs)
- 1x TP4056 board - choose "18650 Type C" - make sure it has 6 holes total (w/ protection)
  https://dlnmh9ip6v2uc.cloudfront.net/datasheets/Prototyping/TP4056.pdf
  https://www.aliexpress.us/item/3256807605386962.html ($0.61 gift / $1.35)
  https://www.aliexpress.us/item/3256806824094515.html ($0.99 gift 5 pcs / $2.56 gift 5 pcs)
  https://www.aliexpress.us/item/3256804241424963.html ($1.29 5 pcs)
  https://www.aliexpress.us/item/3256807979673795.html ($0.80 gift / $2.28)
  https://www.aliexpress.us/item/3256807931985778.html ($0.99 welcome / $1.08)
  https://www.aliexpress.us/item/3256807944765163.html ($1.45 5 pcs)
  https://www.aliexpress.us/item/3256808009574936.html ($0.99 welcome 5 pcs / $3.77 5 pcs)
- 2x Tactile button cap - gray
  https://www.aliexpress.us/item/2251832842559353.html ($0.99 gift / $2.93 20pcs)
  https://www.aliexpress.us/item/2251832629712765.html ($0.99 gift / $1.53 100pcs)
  https://www.aliexpress.us/item/2251832660080884.html ($0.99 gift / $2.50 100pcs)
- 3x M3 Heatset Inserts 
  https://www.aliexpress.us/item/3256803396040989.html ($0.99 gift / $1.84) M3(OD4.5mm) 3.5mm 50pcs
- M3 heatset insert soldering iron tip
  https://www.aliexpress.us/item/3256806515637370.html ($0.99 gift / $2.37)
  
- 1x DHT11 board
- 2x basic push button
- 1x 10 ohm resistor THT
- 2x 10K resistor THT
- 1x 1x3 female header
- 3x 1x8 male header
- 1x 1x4 male header

Voltage Calculations:

1. ESP32-C3 requires 3.0-3.6V input voltage
2. The LDO technically requires 4.3V for a stable 3.3V, _but_ starts providing 3.0V at an input of ~3.1V
3. The battery is 3.8V
4. The 1N5817 Schottky has a voltage drop of 0.25V at 200 mA
5. Therefore, the LDO will be provided with 3.45V and will output 3.2-3.3V
