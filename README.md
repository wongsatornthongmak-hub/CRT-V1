# CRT-V1
โครงสร้าง EA

```

```


```
M15 = Trend Filter

↓
หา CRT Candle

↓
รอ Liquidity Sweep

↓
รอ BOS/MSS

↓
รอ Retest

↓
วาง Pending Order

↓
จัดการ TP/SL อัตโนมัติ
```

ส่วนที่ 1 : Trend Filter (M15)
Buy Only
เงื่อนไข

```

```


```
EMA20 > EMA50

และ

ราคาปิดอยู่เหนือ EMA20
```

Sell Only

```

```


```
EMA20 < EMA50

และ

ราคาปิดต่ำกว่า EMA20
```

ส่วนที่ 2 : หา CRT Candle
ใช้แท่ง M15 ก่อนหน้า
เก็บค่า

```

```


```
CRT_High
CRT_Low
CRT_Mid
```

คำนวณ

```

```


```
CRT_Mid =
(CRT_High + CRT_Low)/2
```

ตัวอย่าง

```

```


```
High = 3400

Low = 3380

Mid = 3390
```

ส่วนที่ 3 : Liquidity Sweep
Buy Setup
ราคาแทงต่ำกว่า

```

```


```
CRT_Low
```

อย่างน้อย

```

```


```
2-5 จุด
```

แล้วปิดกลับเข้ากรอบ
ตัวอย่าง

```

```


```
CRT Low = 3380

Sweep = 3378

Close = 3382
```

ถือว่ากวาดแล้ว
Sell Setup
ราคาแทงเหนือ

```

```


```
CRT_High
```

แล้วกลับมาปิดในกรอบ
ส่วนที่ 4 : BOS / MSS
หลัง Sweep
รอ M1
Buy
ต้องเบรก Swing High ล่าสุด

```

```


```
Higher High
```

เกิดขึ้น
Sell
ต้องเบรก Swing Low ล่าสุด

```

```


```
Lower Low
```

เกิดขึ้น
ส่วนที่ 5 : Retest
ห้ามเข้า Market ทันที
รอ

```

```


```
Retest
```

บริเวณ

*  BOS Zone 
*  FVG 
*  OB 
ส่วนที่ 6 : Pending Order
Buy Stop
วางเหนือแท่ง BOS

```

```


```
+20 points
```

Sell Stop
วางใต้แท่ง BOS

```

```


```
-20 points
```

ส่วนที่ 7 : Stop Loss
วางหลัง Liquidity Sweep
ตัวอย่าง

```

```


```
Sweep Low = 3380

SL = 3377
```

Buffer

```

```


```
20-30 points
```

ส่วนที่ 8 : Take Profit
TP1
1R
ปิด 50%
TP2
2R
ปิด 30%
TP3
Liquidity ถัดไป
ปิด 20%
ส่วนที่ 9 : Breakeven
เมื่อกำไรถึง

```

```


```
1R
```

ย้าย

```

```


```
SL → Entry
```

ทันที
ส่วนที่ 10 : Trailing Stop
เริ่มทำงานเมื่อ

```

```


```
1.5R
```

Trailing

```

```


```
0.5R
```

ตัวกรองข่าว
หยุดเทรดก่อนข่าวแดง

```

```


```
30 นาที
```

และ
หลังข่าว

```

```


```
30 นาที
```

ตัวกรอง Spread
ไม่เทรดเมื่อ

```

```


```
Spread > 300 points
```

สำหรับ XAUUSD
ตัวกรองเวลา
ช่วงดีที่สุด

```

```


```
London Open

+

New York Open
```

เช่น

```

```


```
13:00-18:00

และ

19:00-24:00
```

การคำนวณล็อต
สูตร

```

```


```
Risk = Balance × 1%

Lot = Risk / SL Distance
```

เงื่อนไขห้ามเข้า
หากเกิดข้อใดข้อหนึ่ง

```

```


```
ไม่มี Sweep

ไม่มี BOS

ไม่มี Retest

Spread สูง

ใกล้ข่าวแดง

```

เวอร์ชันที่ผมแนะนำจริงสำหรับ XAUUSD M1

```

```


```
M15 EMA Trend

+
CRT Candle

+
Liquidity Sweep

+
M1 BOS

+
FVG Retest

+
Pending Order

+
SL หลัง Sweep

+
TP 2R

+
Breakeven 1R

+
Trailing 1.5R

+
News Filter

+
Spread Filter
```
