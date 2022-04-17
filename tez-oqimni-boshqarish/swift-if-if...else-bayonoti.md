# Swift if, if...else bayonoti

Ushbu o'quv qo'llanmada siz qaror qabul qilish dasturlarini yaratish uchun misollar yordamida Swift if...else bayonoti haqida bilib olasiz.

Kompyuter dasturlashda biz `if`faqat ma'lum bir shart bajarilganda blok kodini ishlatish uchun bayonotdan foydalanamiz.

Masalan, talaba olgan baholar asosida ( **A** , **B** , **C ) baholar qo'yish.**

1. agar foiz **90 dan yuqori bo'lsa, A** bahosini bering
2. agar foiz **75 dan yuqori bo'lsa, B** bahosini bering
3. agar foiz **65 dan yuqori bo'lsa, S** darajasini belgilang

***

`if...else`Swift-da bayonotning uchta shakli mavjud .

1. `if`bayonot
2. `if...else`bayonot
3. `if...else if...else`bayonot

***

### 1. Swift if bayonoti <a href="#if" id="if"></a>

`if`Swift-dagi bayonot sintaksisi :

```
if (condition) {
  // body of if statement
}
```

Bayonot qavs ichida `if`baholanadi .`condition()`

* Agar `condition`ga baholansa `true`, ning tanasi ichidagi kod `if`bajariladi.
* Agar `condition`ga baholansa `false`, asosiy qismidagi kod `if`o'tkazib yuboriladi.

**Eslatma:** Ichkaridagi kod bayonotning `{ }`asosiy qismidir .`if`

![Agar shart rost bo'lsa if ning tanasi ichidagi kod bajariladi.](https://cdn.programiz.com/cdn/farfuture/ERV8oL5-f8HavxwOxEGpFVvMx1wjHqb78Pn-zUxkp\_s/mtime:1618994409/sites/tutorial2program/files/swift-if-statement.png)If bayonotining ishlashi

***

#### 1-misol: if bayonoti <a href="#example-if" id="example-if"></a>

```
let number = 10

// check if number is greater than 0
if (number > 0) {
  print("Number is positive.")
}

print("The if statement is easy")
```

**Chiqish**

```
Raqam ijobiy.
If iborasi oson
```

Yuqoridagi misolda biz nomli o'zgaruvchi yaratdik `number`. Sinov holatiga e'tibor bering,

```
number > 0
```

Mana, beriraqam**0** dan katta bo'lsa , shart baholanadi `true`.

Agar o'zgaruvchini manfiy butun songa o'zgartirsak. Aytaylik **-5** .

```
let number = -5
```

Endi, dasturni ishga tushirganimizda, natija quyidagicha bo'ladi:

```
If iborasi oson
```

Buning sababi ning qiymati **0**`number` dan kichik . Demak, shart ga baholanadi . Va blokning tanasi o'tkazib yuboriladi.`falseif`

***

### 2. Swift if...else bayonoti <a href="#if-else" id="if-else"></a>

`if`Bayonotda ixtiyoriy `else`band bo‘lishi mumkin .

Bayonotning sintaksisi `if-else`:

```
if (condition) {
  // block of code if condition is true
}
else {
  // block of code if condition is false
}
```

Bayonot qavsning ichki qismini `if...else`baholaydi .`condition`

**Agar shart rost deb baholansa,**

1. ichidagi kod `if`bajariladi
2. ichidagi kod `else`o'tkazib yuborilgan

**Agar shart noto'g'ri deb baholansa,**

1. ichidagi kod `else`bajariladi
2. ichidagi kod `if`o'tkazib yuborilgan

![Qanday qilib if... else iborasi ishlaydi](https://cdn.programiz.com/cdn/farfuture/Jc1vJ7wGgZm6Hp7\_wzbfH5s9MrlNBj0sowRzn3pMyE0/mtime:1618994418/sites/tutorial2program/files/swift-if-else-statement.png)if...else iborasining ishlashi

***

#### 2-misol: Swift if...else bayonoti <a href="#example-if-else" id="example-if-else"></a>

```
let number = 10

if (number > 0) {
    print("Number is positive.")
}

else {
    print("Number is negative.")
}

print("This statement is always executed.")
```

**Chiqish**

```
Raqam ijobiy.
Ushbu bayonot har doim bajariladi.
```

Yuqoridagi misolda biz nomli o'zgaruvchi yaratdik `number`. Mana, test ifodasi

```
number > 0
```

ning qiymati bo'lgani `number`uchun `10`test ifodasi ga baholanadi `true`. Shunday qilib, tanasi ichidagi kod `if`bajariladi.

Agar o'zgaruvchini manfiy butun songa o'zgartirsak. Aytaylik **-5** .

```
let number = -5
```

Endi biz dasturni ishga tushirsak, natija quyidagicha bo'ladi:

```
Raqam salbiy.
Ushbu bayonot har doim bajariladi.
```

Bu erda test ifodasi ga baholanadi `false`. Shunday qilib, tanasi ichidagi kod `else`bajariladi.

***

### 3. Swift if...else if...else Bayonoti <a href="#if-else-if" id="if-else-if"></a>

Bayonot `if...else`ikkita muqobil variant orasida kod blokini bajarish uchun ishlatiladi.

Biroq, agar siz ikkitadan ortiq muqobil o'rtasida tanlov qilishingiz kerak bo'lsa, biz ushbu `if...else if...else`bayonotdan foydalanamiz.

Bayonotning sintaksisi `if...else if...else`:

```
if (condition1) {
    // code block 1
}

else if (condition2){
    // code block 2
}

else {
    // code block 3
}
```

Bu yerda,

1. Agar **shart** 1 ga baholansa `true`, **kod bloki 1** bajariladi.
2. Agar 1- **shart** ga baholansa `false`, u holda 2- **shart** baholanadi.
   1. Agar **shart** 2 bo'lsa `true`, **kod bloki 2** bajariladi.
   2. Agar **shart** 2 bo'lsa `false`, **kod bloki 3** bajariladi.

![Qanday bo'lsa, agar ... boshqacha bo'lsa ... boshqacha ifoda ishlaydi](https://cdn.programiz.com/cdn/farfuture/s\_yF9OSmjjPaHSizGytGlSqFc4gZ5UXh\_JxTotarDgQ/mtime:1618994424/sites/tutorial2program/files/swift-if-else-if-statement.png)if...else if iborasining ishlashi

***

#### 3-misol: Swift if..else if Bayonoti <a href="#example-else-if" id="example-else-if"></a>

```
// check whether a number is positive, negative, or 0.

let number = 0

if (number > 0) {
    print("Number is positive.")
}

else if (number < 0) {
    print("Number is negative")
}

else {
    print("Number is 0.")
}

print("This statement is always executed")
```

**Chiqish**

```
Raqam 0.
```

Yuqoridagi misolda biz nomli o'zgaruvchi yaratdikraqam**0** qiymati bilan . Bu erda ikkita shart ifodasi mavjud:

1. `if (number > 0)number`- dan katta ekanligini tekshiradi`0`
2. `else if (number < 0)number`-dan kamligini tekshiradi`0`

Bu erda ikkala shart ham ga baholanadi `false`. Demak ning tanasi ichidagi gap `else`bajariladi.

***

### Swift ichki o'rnatilgan if bayonoti <a href="#nested-if-else" id="nested-if-else"></a>

Bundan tashqari, `if`bayonot ichidagi bayonotdan foydalanishingiz mumkin `if`. **Bu ichki o'rnatilgan if** iborasi sifatida tanilgan .

**Ichki if** iborasining sintaksisi :

```
// outer if statement
if (condition1) {
    // statements

    // inner if statement
    if (condition2) {
    // statements
    }
}
```

**Eslatmalar:**

1. Agar kerak bo'lsa, biz ichki bayonotga `else`va bayonotlarni qo'shishimiz mumkin .`else ifif`
2. Shuningdek, biz tashqi yoki bayonotlar ichiga ichki `if`bayonotni kiritishimiz mumkin (agar ular mavjud bo'lsa)`elseelse if`
3. `if`Biz bayonotlarning bir nechta qatlamlarini joylashtirishimiz mumkin .

***

#### 4-misol: Ichki if...else bayonoti <a href="#example-nested" id="example-nested"></a>

```
var number = 5

// outer if statement
if (number >= 0) {

  // inner if statement
  if (number == 0) {
      print("Number is 0")
  }

  // inner else statement
  else {
      print("Number is positive");
  }
}

// outer else statement
else {
    print("Number is negative");
}
```

**Chiqish**

```
Raqam ijobiy
```

Yuqoridagi misolda biz berilgan sonning musbat, manfiy yoki 0 ekanligini tekshirish uchun **ichki o'rnatilgan if iborasidan foydalanganmiz.**
