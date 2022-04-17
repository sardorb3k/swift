# Swift ma'lumotlar turlari

Ushbu qo'llanmada siz misollar yordamida Swift dasturlashda ma'lumotlar turlari haqida bilib olasiz.

Kompyuter dasturlashda ma'lumotlar turlari o'zgaruvchining ichida saqlanishi mumkin bo'lgan ma'lumotlar turini belgilaydi. Misol uchun,

```
var num: Int
```

Bu o'zgaruvchining faqat butun sonli ma'lumotlarni saqlashi mumkinligini `Int`ko'rsatadigan ma'lumotlar turi .`num`

Swift dasturlashda ma'lumotlar turlarining oltita asosiy turi mavjud.

***

### Swift ma'lumotlar turlari <a href="#data-types" id="data-types"></a>

| Ma'lumotlar turlari | Misol                  | Tavsif                                       |
| ------------------- | ---------------------- | -------------------------------------------- |
| `Character`         | `"s"`,`"a"`            | 16-bitli Unicode belgisi                     |
| `String`            | `"hello world!"`       | matnli ma’lumotlarni ifodalaydi              |
| `Int`               | `3`,`-23`              | butun son                                    |
| `Float`             | `2.4`, `3.14`,`-23.21` | 32-bitli suzuvchi nuqtali raqamni ifodalaydi |
| `Double`            | `2.422342412414`       | 64-bitli suzuvchi nuqtali raqamni ifodalaydi |
| `Bool`              | `true`va`false`        | Ikki qiymatdan har biri: rost yoki noto'g'ri |

***

### Tezkor xarakter <a href="#character" id="character"></a>

Belgilar ma'lumotlari turi bitta belgili qatorni ifodalash uchun ishlatiladi. `Character`Belgilar tipidagi o'zgaruvchilar yaratish uchun kalit so'zdan foydalanamiz . Misol uchun,

```
// create character type variable
var letter: Character = "s"

print(letter)

// Output: s
```

Yuqoridagi misolda biz `Character`nomli turdagi o'zgaruvchi yaratdik `letter`. `"s"`Mana , biz `letter`.

**Eslatma** : Agar siz bir nechta belgilarni belgilashga harakat qilsangiz, like"abc"turidagi o'zgaruvchilar uchun `Character`siz xato xabarini olasiz.

***

### Swift String <a href="#string" id="string"></a>

Matnli ma'lumotlarni ko'rsatish uchun string ma'lumotlar turi ishlatiladi.

Biz `String`kalit so'zdan string tipidagi o'zgaruvchilar yaratish uchun foydalanamiz. Misol uchun,

```
// create string type variable
var language: String = "swift"

print(name)

// Output: swift
```

Yuqoridagi misolda biz `String`nomli turdagi o'zgaruvchi yaratdik `language`. `"swift"`Mana , biz `language`.

Satrlar va belgilar haqida ko'proq ma'lumot olish uchun [Swift Characters and Strings](https://www.programiz.com/swift-programming/characters-strings) -ga tashrif buyuring .

***

### Swift butun son <a href="#integer" id="integer"></a>

Butun sonli ma'lumotlar turi kasr komponenti bo'lmagan butun sonni ifodalash uchun ishlatiladi. Butun `Int`son tipidagi o‘zgaruvchilar yaratish uchun kalit so‘zdan foydalanamiz. Misol uchun,

```
// create integer type variable
var number: Int = 3

print(number)

// Output: 3
```

Yuqoridagi misolda biz `Int`nomli turdagi o'zgaruvchi yaratdik `number`. `3`Mana , biz `number`.

Swift dasturlashda butun sonlarning asosiy xususiyatlaridan ba'zilari.

* **Hajmi** : platforma turiga bog'liq
* **Diapazon** : **-2 31** dan **2 31 -1** (32 bitli platforma)\
  **-2 63** dan **2 63 -1** (64 bitli platforma)

#### Int tipidagi variantlar

Swift dasturlash turli `Int`xil o'lchamlarga ega bo'lgan turdagi turli xil variantlarni taqdim etadi.

| Variant | Hajmi               | Diapazon                                                                                    |
| ------- | ------------------- | ------------------------------------------------------------------------------------------- |
| Int8    | 8 bit               | **-128** dan **127 gacha**                                                                  |
| Int16   | 16 bit              | **-2 15** dan **2 15 -1 gacha**                                                             |
| Int32   | 32 bit              | **-2 31** dan **2 31 -1 gacha**                                                             |
| Int64   | 64 bit              | **-2 63** dan **2 63 -1 gacha**                                                             |
| UInt    | Platformaga bog'liq | **0** dan **2 gacha 32** (32 bitli platforma) **0** dan **2 64 gacha** (64 bitli platforma) |

***

### Tez mantiqiy <a href="#boolean" id="boolean"></a>

Mantiqiy ob'ektlarni ifodalash uchun mantiqiy ma'lumotlar turi ishlatiladi. U ikkita qiymatdan biriga ega bo'lishi mumkin: `true`yoki `false`. Biz `Bool`mantiqiy tipdagi o'zgaruvchilarni yaratish uchun kalit so'zdan foydalanamiz. Misol uchun,

```
// create boolean type variable

let passCheck: Bool = true
print(passCheck)

let failCheck: Bool = false
print(failCheck)
```

**Chiqish**

```
rost
yolg'on
```

Yuqoridagi misolda biz `Bool`o'zgaruvchilar turini yaratdik:passCheckvamuvaffaqiyatsiz tekshiruv. Mana, biz `true`tayinladikpassChecko'zgaruvchiga `false`vamuvaffaqiyatsiz tekshiruvo'zgaruvchan.

Agar biz mantiqiy o'zgaruvchiga hech qanday qiymat bermasak, u `false`standart qiymat sifatida qabul qilinadi.

**Eslatma** : Mantiqiy so'zlar tez-tez `if-else`iboralar bilan ishlatiladi. [Batafsil ma’lumot olish uchun Swift if...else bayonotiga](https://www.programiz.com/swift-programming/if-else-statement) tashrif buyuring .

***

### Swift Float <a href="#float" id="float"></a>

Float ma'lumotlar turi kasr komponentli sonni ifodalash uchun ishlatiladi. `Float`Float tipidagi o'zgaruvchilarni yaratish uchun kalit so'zdan foydalanamiz . Misol uchun,

```
// create float type variable

let piValue: Float = 3.14
print(piValue)

// Output: 3.14
```

Yuqoridagi misolda biz `Float`nomli turdagi o'zgaruvchi yaratdik `piValue`. Mana, biz `3.14`tayinladik `piValue`.

Swift dasturlashda floatning asosiy xususiyatlaridan ba'zilari.

* **Hajmi** : 32-bitli suzuvchi nuqtali raqam
* **Diapazon** : **1,2 x 10 -38** dan **3,4 x 10 38** gacha (6 kasrgacha)

***

### Swift Double <a href="#double" id="double"></a>

Kabi `Float`, qo'sh ma'lumotlar turi kasr komponentlari bo'lgan sonni ifodalash uchun ham ishlatiladi.

Biroq, Double 15 kasrgacha bo'lgan ma'lumotlarni qo'llab-quvvatlaydi. `Double`Ikki o'zgaruvchini yaratish uchun kalit so'zdan foydalanamiz . Misol uchun,

```
// create double type variable
let latitude: Double = 27.7007697012432

print(latitude)

// Output: 27.7007697012432
```

Yuqoridagi misolda biz `Double`nomli turdagi o'zgaruvchi yaratdik `latitude`. Mana, biz `27.7007697012432`tayinladik `latitude`.

Swift dasturlashda double ning asosiy xususiyatlaridan ba'zilari:

* **Hajmi** : 64-bitli suzuvchi nuqtali raqam
* **Diapazon** : **2,3 x 10 -308** dan **1,7 x 10 308** gacha (15 kasrgacha)

**Eslatma** : Agar bizda kabi raqam bo'lsa `27.7007697012432`, biz foydalanamiz:

* `Double`raqamni aniqroq saqlash uchun (15 kasrgacha)
* `Float`raqamni kamroq aniqlikda saqlash uchun (6 kasrgacha)[\
  ](https://www.programiz.com/swift-programming/variables-constants-literals)
