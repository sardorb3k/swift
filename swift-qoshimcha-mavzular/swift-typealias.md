# Swift Typealias

Ushbu maqolada siz Swift-da tipalias va undan foydalanish holatlari haqida bilib olasiz.

Taxallus turi dasturga mavjud [ma'lumotlar turi](https://www.programiz.com/swift-programming/data-types) uchun yangi nom berish imkonini beradi . Turga taxallus e'lon qilingandan so'ng, butun dastur davomida mavjud tur o'rniga taxallus nomidan foydalanish mumkin.

Taxallus turi yangi turlarni yaratmaydi. Ular shunchaki mavjud turga yangi nom beradi.

ning asosiy maqsadi `typealias`bizning kodimizni inson tushunishi uchun yanada o'qilishi va aniqroq qilishdir.

***

### Tipalias qanday yaratiladi? <a href="#create" id="create"></a>

U quyidagi kalit so'z yordamida e'lon `typealias`qilinadi:

```
typealias nomi = mavjud tur
```

Swift-da siz `typealias`ko'pgina turlar uchun foydalanishingiz mumkin. Ular quyidagilardan biri bo'lishi mumkin:

* **Oʻrnatilgan turlar** (masalan: String, Int)
* **Foydalanuvchi tomonidan belgilangan turlar** (masalan: sinf, struktura, enum)
* **Murakkab turlar** (masalan: yopilishlar)

***

### O'rnatilgan turlar uchun tipaliklar <a href="#built-in" id="built-in"></a>

String, Int, Float va boshqalar kabi barcha o'rnatilgan ma'lumotlar turlari uchun tipaliasdan foydalanishingiz mumkin.

**Misol uchun:**

```
typealias StudentName = String
```

Yuqoridagi deklaratsiya ruxsat beradiTalaba ismio'rniga hamma joyda qo'llanilishi kerak `String`. Shunday qilib, agar siz satr tipidagi doimiyni yaratmoqchi bo'lsangiz, lekin talaba nomiga o'xshash bo'lsa. Siz shunday qilishingiz mumkin:

```
let name:StudentName = "Jek"
```

Typealias-dan foydalanmasdan, qator tipidagi doimiyni quyidagicha e'lon qilishingiz kerak:

```
let name:String = "Jek"
```

Yuqoridagi ikkala misolda turning doimiysi hosil bo'ladi `String`. Lekin bilan e'lon qilsak `typealias`, bizning kodimiz o'qilishi mumkin bo'ladi.

***

### Foydalanuvchi tomonidan belgilangan turlar uchun tipalias <a href="#user-defined" id="user-defined"></a>

O'zingizning ma'lumotlar turini yaratishingiz kerak bo'lgan ko'p holatlar mavjud. Faraz qilaylik, siz Studentni ifodalovchi Turni yaratmoqchi boʻlsangiz, uni quyidagi sinf yordamida yaratishingiz mumkin:

```
class Student {

}
```

Endi talabalar guruhini massiv sifatida quyidagicha ko'rsatish mumkin:

```
var student:Array<Student> = []
```

Yuqoridagi deklaratsiyani quyidagi tarzda ishlatish uchun o'z turingizni yaratish orqali yanada o'qilishi `Array<Student>`mumkin `typealias`:

```
typealias Students = Massiv<Talaba>
```

Endi biz kodimizni quyidagicha o'qilishi mumkin:

```
var talabalar: Talabalar = []
```

***

### Murakkab turlar uchun tipaliklar <a href="#complex" id="complex"></a>

Yana bir misolni tahlil qilaylik. Aytaylik, bizda kirish parametri sifatida yopishni oladigan usul mavjud.

Agar siz yopilishlar haqida bilmasangiz, tashvishlanmang. Buni faqat funktsiyaning maxsus turi sifatida tasavvur qiling. Biz buni maqolada batafsil bayon qildik: _Tez yopilishlar_ .

```
func someMethod(oncomp:(Int)->(String)){

}
```

Yuqoridagi misol ga kirish sifatida yopishni oladi `someMethod`. Yopish `Int`qiymat oladi va qaytaradi `String`.

`(Int)->(String)`Foydalanish o'quvchi uchun kamroq ma'noga ega ekanligini ko'rishingiz mumkin . Siz `typealias`unga yangi nom berish uchun foydalanishingiz mumkin:

```
typealias CompletionHandler = (Int)-> (String)
```

Endi siz usulni quyidagicha qayta yozishingiz mumkin:

```
func someMethod(oncomp:CompletionHandler){

}
```

Biz bir xil kodni ishlatish bilan yanada aniqroq va dasturchilarga qulay ko'rinishini ko'rishimiz mumkin `typealias`.
