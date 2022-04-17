# Swift Bitwise va Bit Shift operatorlari

Ushbu o'quv qo'llanmada biz misollar yordamida Swift'dagi bitli operator va turli xil siljish operatorlari haqida bilib olamiz.

Bitli operatorlar individual bit darajasida butun sonli ma'lumotlar bilan operatsiyalarni bajaradilar. Ushbu operatsiyalar haqiqiy bitlarni sinab ko'rish, sozlash yoki o'zgartirishni o'z ichiga oladi. Misol uchun,

```
a & b
a | b
```

Misolda `&`va `|`bitli operatorlardir.

Bu erda Swift-ga kiritilgan turli xil bitli operatorlar ro'yxati

| Operatorlar | Ism                                                                                                 | Misol    |
| ----------- | --------------------------------------------------------------------------------------------------- | -------- |
| `&`         | [Bit boʻyicha VA](https://www.programiz.com/swift-programming/bitwise-operators#and)                | `a & b`  |
| `\|`        | [Bit bo'yicha OR](https://www.programiz.com/swift-programming/bitwise-operators#or)                 | `a \| b` |
| `^`         | [Bitli XOR](https://www.programiz.com/swift-programming/bitwise-operators#xor)                      | `a ^ b`  |
| `~`         | [Bitwise EMAS](https://www.programiz.com/swift-programming/bitwise-operators#not)                   | `~ a`    |
| `<<`        | [Bit bo'yicha chapga siljitish](https://www.programiz.com/swift-programming/bitwise-operators#left) | `a << b` |
| `>>`        | [Bitwise o'ngga siljitish](https://www.programiz.com/swift-programming/bitwise-operators#right)     | `a >> b` |

***

### Bitwise AND Operator <a href="#and" id="and"></a>

Bit bo'yicha **AND operatori 1**`&` ni qaytaradi , agar ikkala operand ham **1** bo'lsa . **Aks holda, u 0** ni qaytaradi .

Bit bo'yicha **AND** operatsiyasi `a`va `b`quyidagi jadvalda ko'rsatilishi mumkin:

| a | b | a & b |
| - | - | ----- |
| 0 | 0 | 0     |
| 0 | 1 | 0     |
| 1 | 0 | 0     |
| 1 | 1 | 1     |

**Eslatma:** Yuqoridagi jadval bitli AND operatori uchun "Haqiqat jadvali" sifatida tanilgan.

Keling , ikkita tamsayı **12** va **25** ning bit bo'yicha **AND** ishini ko'rib chiqaylik :

```
12 = 00001100 (In Binary)

25 = 00011001 (In Binary)

// Bitwise AND Operation of 12 and 25

     00001100
&    00011001
_____________
     00001000  = 8 (In Decimal)
```

***

#### 1-misol: Bitli VA operatori

```
var a = 12
var  b = 25

var result = a & b 
print (result)    // 8
```

Yuqoridagi misolda biz ikkita o'zgaruvchini e'lon qildik `a`va `b`. Mana, chiziqqa e'tibor bering,

```
var result = a & b 
```

Bu erda biz va o'rtasida bit bo'yicha **VA** amalini bajaramiz .`ab`

***

### Bitwise OR Operator <a href="#or" id="or"></a>

Bit bo'yicha **OR** operatori operandlardan kamida bittasi **1 bo'lsa, 1**`|` ni qaytaradi . **Aks holda, u 0** ni qaytaradi .

Bit bo'yicha **OR** operatsiyasi `a`va `b`quyidagi jadvalda ko'rsatilishi mumkin:

| a | a | a \| b |
| - | - | ------ |
| 0 | 0 | 0      |
| 0 | 1 | 1      |
| 1 | 1 | 1      |
| 1 | 0 | 1      |

**Keling, ikkita butun 12** va **25 sonlarning bit bo'yicha OR** ishlashini ko'rib chiqaylik  :

```
12 = 00001100 (In Binary)
25 = 00011001 (In Binary)

Bitwise OR Operation of 12 and 25
    00001100
|   00011001
____________
    00011101  = 29 (In decimal)
```

***

#### 2-misol: Bitli OR operatori

```
var a = 12
var  b = 25

var result = a | b
print(result)    // 29
```

**Bu erda biz 12** va **25** oralig'ida bit bo'yicha **OR** ni bajaramiz .

***

### Bitwise XOR operatori <a href="#xor" id="xor"></a>

Bitli **XOR** operatori , agar operandlardan biri **1 bo'lsa, 1**`^` ni qaytaradi . Biroq, agar ikkala operand ham **0** bo'lsa yoki ikkalasi ham **1** bo'lsa, natija **0** bo'ladi.

Bitwise **XOR** operatsiyasi `a`va `b`quyidagi jadvalda ko'rsatilishi mumkin:

| a | b | a ^ b |
| - | - | ----- |
| 0 | 0 | 0     |
| 0 | 1 | 1     |
| 1 | 0 | 1     |
| 1 | 1 | 0     |

Ikkita tamsayı **12** va **25 ning bit boʻyicha  XOR** ishini koʻrib chiqamiz :

```
12 = 00001100 (In Binary)
25 = 00011001 (In Binary)

Bitwise XOR Operation of 12 and 25
    00001100
^   00011001
____________
    00010101  = 21 (In decimal)
```

#### 3-misol: Bitli XOR operatori

```
var a = 12
var  b = 25

var result = a ^ b
print(result)    // 21
```

Bu erda biz **12** va **25** oralig'ida bit bo'yicha **XORni** bajaramiz .

***

### Bitwise EMAS operatori <a href="#not" id="not"></a>

Bit bo'yicha **NOT** `~` operatori bitni o'zgartiradi ( **0 1** ga , **1 0** ga aylanadi ) .

![Swift bit yoʻnalishi boʻyicha EMAS 0 ni 1 va 1 ni 1 ga aylantirmaydi](https://cdn.programiz.com/cdn/farfuture/QBEo8yqV\_J-Wm4wekvDF9zEWD3zk-ws0LWdEDYE8tKA/mtime:1618825577/sites/tutorial2program/files/swift-bitwise-not.png)Swift Bitwise EMAS

Bit bo'yicha **EMAS** operatsiyasini `a`quyidagi jadvalda ko'rsatish mumkin:

Shuni ta'kidlash kerakki, har qanday N butun sonning bit yo'nalishi EMAS **- (N + 1)** ga teng . Misol uchun,

**35** butun sonni ko'rib chiqing . Qoidaga ko'ra, 35 ning bit yo'nalishi bo'yicha EMAS **- (35 + 1)** = **-36** bo'lishi kerak . Keling, to'g'ri javobni olamizmi yoki yo'qmi, bilib olaylik.

```
35 = 00100011 (In Binary)

// Using bitwise NOT operator
~  00100011 
   ________
   11011100 
```

Yuqoridagi misolda **00100011 ning bit yo'nalishi bo'yicha NO 11011100** dir . **Bu yerda natijani kasrga aylantirsak 220** ni olamiz .

Ammo shuni ta'kidlash kerakki, biz natijani to'g'ridan-to'g'ri kasrga aylantira olmaymiz va kerakli natijani olamiz. Buning sababi, ikkilik natija **11011100** ham **-36** ga teng .

Buni tushunish uchun birinchi navbatda **-36** ning ikkilik chiqishini hisoblashimiz kerak . Manfiy butun sonlarning ikkilik sonini hisoblash uchun **2 ning to‘ldiruvchisidan** foydalanamiz .

***

#### 2 ning to‘ldiruvchisi

**N** sonning 2 ning **to‘ldiruvchisi -N** ni beradi . U bitlarni ( **0** dan **1** gacha va **1** dan **0 ga) teskari aylantirish va keyin 1** ni qo'shish orqali hisoblanadi. Masalan,

```
36 = 00100100 (In Binary)

1's Complement = 11011011 

2's Complement :   
11011011
 +     1
________
11011100   
```

Bu erda 2 ning **36 ning to'ldiruvchisi** (ya'ni **-36** ) **11011100 ni ko'rishimiz mumkin** . Bu qiymat biz oldingi bo'limda hisoblagan **35** ning bit bo'yicha to'ldiruvchisiga teng .

**Demak, 35** = **-36** ning bit bo'yicha to'ldiruvchisi, deb aytishimiz mumkin .

***

#### 4-misol: Bitwise NOT Operator

```
var  b = 12

var result = ~b

print(result)     // -13
```

Yuqoridagi misolda biz **12 da bitli EMAS** operatsiyasini bajardik .

```
The bitwise complement of 12 = - (12 + 1) = -13
i.e. ~12 = -13 
```

Bu biz chiqishda aniq bo'lgan narsadir.

***

### Chapga siljish operatori <a href="#left" id="left"></a>

Chapga siljish operatori barcha bitlarni belgilangan miqdordagi bitlar bilan chapga siljitadi. Bu bilan belgilanadi `<<`.

![Barcha bitlarni 1 bitga siljitish uchun chapga siljishdan foydalanish.](https://www.programiz.com/sites/tutorial2program/files/swift-left-shift.png)Swift Left Shift operatori

Yuqoridagi rasmdan ko'rib turganimizdek,

* Bizda 4 xonali raqam bor. **Unda 1** bit chapga siljish amalini bajarganimizda , har bir bit **1** bitga chapga siljiydi .
* Natijada, eng chapdagi bit tashlanadi, o'ngdagi bit esa bo'sh qoladi. Bu vakansiya **0** bilan almashtiriladi .

***

#### 5-misol: Chapga siljish operatori

```
var a = 3

var result = a << 2

print(result)    // 12
```

Yuqoridagi misolda biz `a`qiymati bilan o'zgaruvchi yaratdik `3`. Bayonotga e'tibor bering

```
var result = a << 2
```

Bu erda biz **2** bitni chapga siljitish operatsiyasini bajaramiz `a`.

***

### O'ngga siljish operatori <a href="#right" id="right"></a>

To'g'ri siljish operatori barcha bitlarni ma'lum miqdordagi belgilangan bitlar bilan o'ngga siljitadi. Bu bilan belgilanadi `>>`.

![Bitwise Right Shift barcha bitlarni ma'lum bitlar bilan o'ngga siljitadi](https://cdn.programiz.com/cdn/farfuture/elquVxNqctCtxNJRjzAxNwexFK8k\_XQIUMYjbXD54JI/mtime:1618825602/sites/tutorial2program/files/swift-Right-shift.png)Swift Right Shift operatori

Yuqoridagi rasmdan ko'rib turganimizdek,

* Bizda 4 xonali raqam bor. **Unda 1 bitli** o'ngga siljish amalini bajarganimizda , har bir bit **o'ngga 1 bitga siljiydi** .
* Natijada, eng o'ngdagi bit o'chiriladi, chapdagi bit esa bo'sh qoladi. **Bu vakansiya imzosiz raqamlar** uchun **0** bilan almashtiriladi .
* **Imzolangan raqamlar** uchun ishora biti ( **musbat** son uchun **0 , manfiy** son uchun **1** ) bo'shatilgan bit o'rinlarini to'ldirish uchun ishlatiladi.

**Eslatma:** Belgilangan butun son ham musbat, ham manfiy butun sonlarni ifodalaydi, belgisiz butun son esa faqat musbat sonlarni ifodalaydi.

***

#### 5-misol: O'ngga siljish operatori

```
var a = 4

var result = a >> 2
print(result)    // 1

a = -4

result = a >> 2
print(result)    // -1
```

Yuqoridagi misolda biz **4** va **-4 qiymatlari bo'yicha 2** bitli o'ngga siljish amallarini bajarmoqdamiz .

Ko'rib turganingizdek, natija **4** va **-4** uchun farq qiladi . Buning sababi shundaki, **4** ishorasiz butun son bo'lib, bo'sh o'rin **0** bilan to'ldiriladi va **-4 manfiy** belgili raqam bo'lib, bo'sh joy 1 bilan to'ldiriladi **.**
