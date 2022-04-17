# Swift for-in Loop

Ushbu qo'llanmada biz misollar yordamida Swift-da for-in tsiklidan qanday foydalanishni o'rganamiz.

Kompyuter dasturlashda kod blokini takrorlash uchun sikllardan foydalaniladi.

Misol uchun, agar biz xabarni 100 marta ko'rsatmoqchi bo'lsak, unda biz tsikldan foydalanishimiz mumkin. Bu oddiy misol; looplar yordamida ko'proq narsaga erishishingiz mumkin.

Swift-da 3 turdagi halqalar mavjud:

1. [for in loop](https://www.programiz.com/swift-programming/for-in-loop#for-in)
2. [while tsikli](https://www.programiz.com/swift-programming/repeat-while-loop#while)
3. [takrorlang... while loop](https://www.programiz.com/swift-programming/repeat-while-loop#repeat-while)

***

### Swift for-in Loop <a href="#for-in" id="for-in"></a>

Swift-da `for-in`tsikl kod blokini ma'lum bir necha marta ishlatish uchun ishlatiladi. U massiv, diapazon, satr va boshqalar kabi har qanday ketma-ketlikni takrorlash uchun ishlatiladi.

Loopning sintaksisi `for-in`:

```
for val in sequence{
  // statements
}
```

Bu yerda, har bir iteratsiyaning `val`har bir elementiga kiradi . `sequence`Loop ning oxirgi elementiga yetguncha davom etadi `sequence`.

***

### For-in Loop sxemasi <a href="#flowchart" id="flowchart"></a>

![Swift-da for-in tsikli qanday ishlaydi](https://cdn.programiz.com/cdn/farfuture/VnHaNoAxPKR16dbzBzkIhnkn4qfFiw13hMjiqdLblWU/mtime:1619682225/sites/tutorial2program/files/swift-for-loop.png)For-in siklining ishlashi

***

### Misol: Massiv ustida aylanish <a href="#array" id="array"></a>

```
// access items of an array 
let languages = ["Swift", "Java", "Go", "JavaScript"]

for language in languages {
      print(language)
}
```

**Chiqish**

```
Tezkor
Java
Bor
JavaScript
```

Yuqoridagi misolda biz nomli massiv yaratdik `languages`.

Dastlab ning qiymati `language`massivning birinchi elementiga o'rnatiladi, ya'ni `Swift`, shuning uchun sikl ichidagi chop etish operatori bajariladi.

`language`massivning keyingi elementi bilan yangilanadi va chop etish operatori yana bajariladi. Shunday qilib, sikl massivning oxirgi elementiga kirgunga qadar ishlaydi.

***

### for where bandi bilan Loop <a href="#where" id="where"></a>

`where`Swift-da biz loopli bandni ham qo'shishimiz mumkin `for-in`. Loopda filtrlarni amalga oshirish uchun ishlatiladi. Ya'ni, agar `where`banddagi shart qaytarsa `true`, sikl bajariladi.

```
// remove Java from an array

let languages = ["Swift", "Java", "Go", "JavaScript"]

for language in languages where language != "Java"{
  print(language) 
}
```

**Chiqish**

```
Tezkor
Bor
JavaScript
```

Yuqoridagi misolda biz `for-in`har bir elementga kirish uchun tsikldan foydalanganmiz `languages`. `where`Davrda gapning ishlatilishiga e'tibor bering `for-in`.

`for language in languages where language != "Java"`

Bu yerda, agar `where`banddagi shart qaytarsa `true`, sikl ichidagi kod bajariladi. Aks holda, u bajarilmaydi.

| Takrorlash | til        | shart: != "Java" | Chiqish                  |
| ---------- | ---------- | ---------------- | ------------------------ |
| 1          | Tezkor     | rost             | `Swift`chop etiladi.     |
| 2          | Java       | yolg'on          | `Java`chop etilmaydi     |
| 3          | Bor        | rost             | `Go`chop etiladi         |
| 4          | JavaScript | rost             | `JavaScript`chop etiladi |

***

### For Loop With Range <a href="#range" id="range"></a>

[Diapazon](https://www.programiz.com/swift-programming/ranges) ikki raqamli intervallar orasidagi qiymatlar qatoridir . Misol uchun,

```
var values = 1...3
```

Bu erda **1** , **2** , **3**`1...3` qiymatlarini o'z ichiga olgan diapazonni belgilaydi .

Swift-da biz `for`intervalni takrorlash uchun loopdan foydalanishimiz mumkin. Misol uchun,

```
// iterate from i = 1 to 1 = 3
for i in 1...3 {
    print(i)
}
```

**Chiqish**

```
1
2
3
```

Yuqoridagi misolda biz **1** dan **3**`for-in` gacha bo'lgan oraliqda takrorlash uchun tsikldan foydalanganmiz .

ning qiymati `i`o'rnatiladi `1`va u har bir iteratsiyada diapazonning keyingi raqamiga yangilanadi. Bu jarayon `3`erishilgunga qadar davom etadi.

| Takrorlash | Vaziyat | Harakat                                   |
| ---------- | ------- | ----------------------------------------- |
| 1          | `true`  | `1`chop etiladi. `i`2 ga oshiriladi **.** |
| 2          | `true`  | `2`chop etiladi. **3**`i` ga oshiriladi . |
| 3          | `true`  | `3`chop etiladi. **4**`i` ga oshiriladi . |
| 4          | `false` | Loop tugadi                               |

***

### For Stride funktsiyasi bilan Loop <a href="#stride" id="stride"></a>

Agar biz tsiklning har bir iteratsiyada ma'lum bir belgilangan qiymatga oshishini istasak, diapazon o'rniga biz **stride(from:to:by)** funktsiyasidan foydalanishimiz kerak. Misol uchun,

```
for i in stride(from: 1, to: 10, by: 2) {
    print(i)
}
```

**Chiqish**

```
1
3
5
7
9
```

Yuqoridagi misolda halqa **1** dan **10 gacha** oraliqda **2** interval bilan takrorlanadi . Biroq, **10** qatorga kiritilmagan.

Bu erda ning qiymati `i`o'rnatiladi va u har bir iteratsiyada **2**`1` oraliq bilan yangilanadi .
