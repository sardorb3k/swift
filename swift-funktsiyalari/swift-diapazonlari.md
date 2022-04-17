# Swift diapazonlari

Ushbu maqolada biz misollar yordamida Swift diapazonlari va uning turlari haqida bilib olamiz.

Swift-da diapazon ikki raqamli intervallar orasidagi qiymatlar qatoridir. Misol uchun,

```
var numbers = 1...4
```

Bu yerda,

* `...`diapazon operatori hisoblanadi
* `1...4`**1** , **2** , **3** , **4** qiymatlarini o'z ichiga oladi
* **1** pastki **chegara** (birinchi element)
* **4** - **yuqori chegara** (oxirgi element)

***

### Swift-da diapazon turlari <a href="#types" id="types"></a>

Swift-da diapazonning uch turi mavjud:

* [Yopiq diapazon](https://www.programiz.com/swift-programming/ranges#closed)
* [Yarim ochiq diapazon](https://www.programiz.com/swift-programming/ranges#half-open)
* [Bir tomonlama diapazon](https://www.programiz.com/swift-programming/ranges#one-sided)

***

### 1. Yopiq diapazon <a href="#closed" id="closed"></a>

Yopiq diapazon pastki chegaradan yuqori chegaragacha bo'lgan oraliqdagi barcha qiymatlarni o'z ichiga oladi.

`...`U (3 nuqta) operatori yordamida e'lon qilinadi . Misol uchun,

```
// 1...4 is close range
for numbers in 1...4 {
  print(numbers)
}
```

**Chiqish**

```
1
2
3
4
```

Yuqoridagi misolda biz yopiq diapazon yaratdik `1...4`.

Bu yopiq diapazon bo'lgani uchun u **1** dan **4** gacha bo'lgan barcha raqamlarni o'z ichiga oladi, shu jumladan pastki chegara ( **1** ) va yuqori chegara ( **4** ).

Bu yerda biz diapazondagi barcha qiymatlarga kirish [uchun Swift for loopidan foydalandik.](https://www.programiz.com/swift-programming/for-in-loop)

***

### 2. Yarim ochiq diapazon <a href="#half-open" id="half-open"></a>

Yarim ochiq diapazon pastki chegaradan yuqori chegaragacha bo'lgan barcha qiymatlarni o'z ichiga oladi. Biroq, u yuqori chegarani (oxirgi raqam) istisno qiladi.

`..<`Bu operator yordamida e'lon qilinadi . Misol uchun,

```
for numbers in 1..<4 {
  print(numbers)
}
```

**Chiqish**

```
1
2
3
```

Yuqoridagi misolda biz yarim ochiq diapazonni yaratdik `1..<4`. Yarim ochiq diapazon bo'lgani uchun u yuqori chegara elementini **4** istisno qiladi .

***

### 3. Bir tomonlama diapazon <a href="#one-sided" id="one-sided"></a>

`...`Biz yoki `..<`operatordan foydalanib bir tomonlama diapazon yaratishimiz mumkin .

Bir tomonlama diapazonda bir yo'nalishda cheksizgacha bo'lgan elementlar mavjud. Misol uchun,

```
let range1 = ..<2
```

Bu erda `...<2`bir tomonlama diapazon mavjud. **U 2** dan **-∞** gacha bo'lgan barcha elementlarni o'z ichiga oladi . Xuddi shunday, diapazon

```
let range2 = 2...
```

**2** dan **+∞** gacha bo'lgan barcha elementlarni o'z ichiga oladi .

Buni diapazonda ma'lum raqam mavjudligini tekshirish orqali tekshirishimiz mumkin. Misol uchun,

```
// one-sided range using 
// ..< operator
let range1 = ..<2

// check if -9 is in the range
print(range1.contains(-1))

// one-sided range using
// ... operator
let range2 = 2...

// check if 33 is in the range
print(range2.contains(33))
```

**Chiqish**

```
rost
rost
```

Bu erda biz `contains()`diapazonda ma'lum bir raqam mavjudligini tekshirish usulidan foydalandik.

**Eslatma:** Bir tomonlama diapazon bilan biz faqat yuqori yoki pastki chegarani o'rnatamiz.

***

### Swift Range yordamida massiv elementlariga kirish <a href="#access-array" id="access-array"></a>

[Massiv elementlariga](https://www.programiz.com/swift-programming/arrays) kirish uchun biz Swift diapazonidan ham foydalanishimiz mumkin . Misol uchun,

```
let languages = ["Swift", "Java", "C"]

// access array elements
print(languages[0...2]) 
```

**Chiqish**

```
["Swift", "Java", "C"]
```

Bu yerda diapazon `0...2`massiv indekslari vazifasini bajaradi va massivning barcha elementlariga kirishimizga yordam beradi.

***

### Swift Range haqida eslash kerak bo'lgan narsalar <a href="#remember" id="remember"></a>

1\. Pastki chegara qiymati yuqori chegara qiymatidan kichikroq bo'lishi kerak. Misol uchun,

```
// Invalid Range
3...1

// Valid Range
1...3
```

2\. Pastki chegara va yuqori chegara qiymati manfiy bo'lishi mumkin. Misol uchun,

```
// negative lower bound
-3...1

// negative upper and lower bound
-9...-2
```
