# Swift operatorlari

Ushbu maqolada siz Swift dasturlash tilidagi har xil turdagi operatorlar, ularning sintaksisi va ulardan misollar bilan qanday foydalanish haqida hamma narsani bilib olasiz.

Operatorlar - o'zgaruvchilar va qiymatlar ustida amallarni bajaradigan maxsus belgilar. Misol uchun,

```
print(5 + 6)   // 11
```

Mana, `+`ikkita raqamni qo'shadigan operator: **5** va **6** .

***

### Operatorlar turlari

Quyida ushbu qoʻllanmada oʻrganadigan Swift operatorlarining har xil turlari roʻyxati keltirilgan.

1. [Arifmetik operatorlar](https://www.programiz.com/swift-programming/operators#arithmetic)
2. [Belgilash operatorlari](https://www.programiz.com/swift-programming/operators#assignment)
3. [Taqqoslash operatorlari](https://www.programiz.com/swift-programming/operators#comparison)
4. [Mantiqiy operatorlar](https://www.programiz.com/swift-programming/operators#logical)
5. [Bitli operatorlar](https://www.programiz.com/swift-programming/operators#bitwise)
6. [Boshqa operatorlar](https://www.programiz.com/swift-programming/operators#other)

***

### 1. Tezkor arifmetik operatorlar <a href="#arithmetic" id="arithmetic"></a>

Arifmetik operatorlar qoʻshish, ayirish, koʻpaytirish kabi matematik amallarni bajarish uchun ishlatiladi. Masalan,

```
var sub = 10 - 5 // 5
```

Bu erda `-`ikkita qiymat yoki o'zgaruvchini ayiruvchi arifmetik operator.

| Operator | Operatsiya   | Misol       |
| -------- | ------------ | ----------- |
| `+`      | Qo'shish     | `5 + 2 = 7` |
| `-`      | Ayirish      | `4 - 2 = 2` |
| `*`      | Ko'paytirish | `2 * 3 = 6` |
| `/`      | Bo'lim       | `4 / 2 = 2` |
| `%`      | Modul        | `5 % 2 = 1` |

***

#### 1-misol: Swift-dagi arifmetik operatorlar

```
var a = 7
var b = 2

// addition
print (a + b)  

// subtraction
print (a - b) 

// multiplication
print (a * b)  
```

**Chiqish**

```
9
5
14
```

Yuqoridagi misolda biz foydalandik

* `+`qo'shish `a`va`b`
* `-b`dan ayirmoq`a`
* `*`ko'paytirish `a`va`b`

**/ Bo'lim operatori**

Operator `/`ikkita raqam o'rtasida bo'linishni amalga oshiradi. Biroq, agar ikkita raqam butun son bo'lsa, biz faqat qismni olamiz. Misol uchun,

```
// returns quotient only
7 / 2 = 3
```

Agar `/`operatorni suzuvchi nuqtali raqamlar bilan ishlatsak, biz haqiqiy natijaga erishamiz. Misol uchun,

```
// perform division
7.0 / 3.0 = 3.5
```

**% modul operatori**

Modul operatori `%`qolgan qismini hisoblab chiqadi. Misol uchun,

```
print(9 % 4)     // 1
```

**Eslatma:** Operatordan `%`faqat butun sonlar bilan foydalanish mumkin.

***

### 2. Tezkor tayinlash operatorlari <a href="#assignment" id="assignment"></a>

O'zgaruvchilarga qiymat berish uchun tayinlash operatorlari qo'llaniladi. Misol uchun,

```
// assign 5 to x 
var x = 5
```

Bu yerda, ga `=`tayinlaydigan tayinlash operatori . Bu erda Swift-da mavjud bo'lgan turli tayinlash operatorlari ro'yxati.`5x`

| Operator | Ism                      | Misol                  |
| -------- | ------------------------ | ---------------------- |
| `=`      | Belgilash operatori      | `a = 7`                |
| `+=`     | Qo'shimcha topshiriq     | `a += 1 // a = a + 1`  |
| `-=`     | Ayirish topshirig'i      | `a -= 3 // a = a - 3`  |
| `*=`     | Ko'paytirish topshirig'i | `a *= 4 // a = a * 4`  |
| `/=`     | Bo'lim topshirig'i       | `a /= 3 // a = a / 3`  |
| `%=`     | Qolgan topshiriq         | `a %= 10 // a = a % 5` |

***

#### 2-misol: tayinlash operatorlari

```
// assign 10 to a
var a = 10

// assign 5 to b
var b = 5 

// assign the sum of a and b to a
a += b      // a = a + b

print(a)
```

**Chiqish**

```
15
```

***

### 3. Tez taqqoslash operatorlari <a href="#comparison" id="comparison"></a>

Taqqoslash operatorlari ikkita qiymatni/o'zgaruvchini solishtiradi va mantiqiy natijani qaytaradi: `true`yoki `false`. Misol uchun,

```
var a = 5, b =2
print (a > b)      // true
```

Bu yerda `>`solishtirish operatori dan katta yoki `a`katta emasligini solishtirish uchun ishlatiladi `b`.

| Operator | Ma'nosi            | Misol                              |
| -------- | ------------------ | ---------------------------------- |
| `==`     | ga teng            | `3 == 5`bizga **yolg'on beradi**   |
| `!=`     | Teng emas          | `3 != 5`bizga **haqiqatni beradi** |
| `>`      | Kattaroq           | `3 > 5`bizga **yolg'on beradi**    |
| `<`      | Dan kam            | `3 < 5`bizga **haqiqatni beradi**  |
| `>=`     | Kattaroq yoki teng | `3 >= 5`bizga **yolg'on bering**   |
| `<=`     | Kichik yoki teng   | `3 <= 5`bizga **haqiqatni beradi** |

#### 3-misol: Taqqoslash operatorlari

```
var a = 5, b = 2

// equal to operator
print(a == b)

// not equal to operator
print(a != b)

// greater than operator
print(a > b)

// less than operator
print(a < b)

// greater than or equal to operator
print(a >= b)

// less than or equal to operator
print(a <= b)
```

**Chiqish**

```
yolg'on
rost
rost
yolg'on
rost
yolg'on
```

**Eslatma:** Taqqoslash operatorlari qaror qabul qilishda va tsikllarda qo'llaniladi. Taqqoslash operatori haqida keyingi darslarda ko'proq gaplashamiz.

***

### 4. Swift mantiqiy operatorlari <a href="#logical" id="logical"></a>

`true`Mantiqiy operatorlar ifoda yoki ekanligini tekshirish uchun ishlatiladi `false`. Ular qaror qabul qilishda qo'llaniladi. Misol uchun,

```
var a = 5, b = 6
print((a > 2) && (b >= 6))    // true
```

Mana, **AND**`&&` mantiqiy operatori . Ikkala va ham bo'lgani uchun, natija bo'ladi .`a > 2b >= 6truetrue`

| Operator | Misol        | Ma'nosi                                                                                                             |
| -------- | ------------ | ------------------------------------------------------------------------------------------------------------------- |
| `&&`     | a **&&** b   | <p><strong>Mantiqiy AND</strong> :<br><code>true</code>faqat ikkala operand ham bo'lsa<code>true</code></p>         |
| `\|\|`   | a **\|\|** b | <p><strong>Mantiqiy OR</strong> :<br><code>true</code>agar operandlardan kamida bittasi bo'lsa<code>true</code></p> |
| `!`      | **!** a      | <p><strong>Mantiqiy EMAS</strong> :<br><code>true</code>agar operand bo'lsa <code>false</code>va aksincha.</p>      |

#### 4-misol: Mantiqiy operatorlar

```
// logical AND
print(true && true)      // true
print(true && false)     // false

// logical OR
print(true || false)      // true

// logical NOT
print(!true)                  // false
```

**Chiqish**

```
rost
yolg'on
rost
yolg'on
```

***

### 5. Swift Bitwise operatorlari <a href="#bitwise" id="bitwise"></a>

Swift-da bitli operatorlar alohida bitlar ustida operatsiyalarni bajarish uchun ishlatiladi.

| Operator | Tavsif                 |
| -------- | ---------------------- |
| `&`      | Ikkilik VA             |
| `\|`     | Ikkilik OR             |
| `^`      | Ikkilik XOR            |
| `~`      | Ikkilik to‘ldiruvchi   |
| `<<`     | Chapga ikkilik siljish |
| `>>`     | Ikkilik siljish o'ngga |

Bitwise operatorlari kundalik dasturlashda kam qo'llaniladi. [Batafsil maʼlumot olish uchun Swift bitli operatorlariga](https://www.programiz.com/swift-programming/bitwise-operators) tashrif buyuring .

***

### 6. Boshqa Swift operatorlari <a href="#other" id="other"></a>

Bu erda Swift-da mavjud bo'lgan boshqa operatorlar ro'yxati. Ushbu operatorlar haqida keyingi darslarda ko'proq bilib olamiz

| Operator | Tavsif                                                                                                                                               | Misol                                      |
| -------- | ---------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------ |
| `? :`    | [Uchlik operator](https://www.programiz.com/swift-programming/ternary-conditional-operator) - shartga asoslangan qiymatni qaytaradi                  | `(5 > 2) ? "Success" : "Error" // Success` |
| `??`     | [Nil-Coalescing operatori](https://www.programiz.com/swift-programming/optionals#nil-coalescing) - ixtiyoriyda qiymat bor yoki yo'qligini tekshiradi | `number ?? 5`                              |
| `...`    | [Diapazon operatori](https://www.programiz.com/swift-programming/ranges) - qiymatlarni o'z ichiga olgan diapazonni belgilaydi                        | `1...3 // range containing values 1,2,3`   |

