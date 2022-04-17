# Tez sharhlar

Ushbu maqolada siz Swift sharhlari, ularni nima uchun va qanday ishlatish haqida bilib olasiz.

Kompyuter dasturlashda sharhlar bizning kodimizni yanada tushunarli qilish uchun foydalanadigan maslahatlardir.

Sharhlar kompilyator tomonidan butunlay e'tiborga olinmaydi. Ular boshqa dasturchilar uchun mo'ljallangan.

Swift-da sharh qo'shishning ikki yo'li mavjud:

* `//`- Yagona qatorli sharhlar
* `/*...*/`- Ko'p qatorli sharhlar

***

### Bir qatorli sharh <a href="#single-line" id="single-line"></a>

Swift-da bilan boshlangan har qanday satr `//`bitta satr izohidir. Misol uchun,

```
// create a variable 
var name = "Cartman"

// print the value
print(name)
```

Bu erda biz ikkita bitta qatorli sharh yaratdik:

* `// create a variable`
* `// print the value`

Kod bilan birga bitta qatorli izohdan ham foydalanishimiz mumkin.

```
var name = "swift" // name is a string
```

***

### Ko'p qatorli sharh <a href="#multi-line" id="multi-line"></a>

`/*`Swift-da va orasidagi har qanday matn `*/`ko'p qatorli sharhdir. Misol uchun,

```
/* create a variable
to store salary of employees
*/

var salary = 10000
print(salary)
```

Yuqoridagi misolda biz `/*...*/`bir nechta satrlarga cho'zilgan izohni yozish uchun foydalanganmiz.

***

### Swift sharhidan foydalanish <a href="#why" id="why"></a>

**1. Kodni tushunishni osonlashtiring**

Kodimizda sharhlar yozsak, kelajakda murojaat qilish osonroq bo'ladi.

Bundan tashqari, boshqa ishlab chiquvchilar uchun kodni tushunish osonroq bo'ladi.

**2. Nosozliklarni tuzatish uchun izohlardan foydalanish**

Agar dasturni ishga tushirishda xatolik yuzaga kelsa, uni olib tashlash o'rniga xatoga sabab bo'lgan kod qatoriga izoh berishimiz mumkin. Misol uchun,

```
print("Swift")

// print("Error Line )

print("UIKit")
```

Bu erda `print("Error Line)`xatolik yuzaga keldi, shuning uchun biz uni sharh sifatida o'zgartirdik. Endi dastur hech qanday xatosiz ishlaydi.

Shunday qilib, sharhlar nosozliklarni tuzatish uchun qimmatli vosita bo'lishi mumkin.

**Eslatma:** Qanday qilib qilganimizni emas, balki nima uchun nima qilganimizni tushuntirish uchun har doim sharhlardan foydalaning. Sharhlar noto'g'ri yozilgan kodni tushuntirish usuli o'rnini bosa olmaydi.
