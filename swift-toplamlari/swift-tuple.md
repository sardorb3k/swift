# Swift Tuple

Ushbu qo'llanmada biz misollar yordamida Swift kortejlari haqida hamma narsani bilib olamiz

Swiftda kortej turli qiymatlar guruhidir. Va kortej ichidagi har bir qiymat turli xil ma'lumotlar turlari bo'lishi mumkin.

Aytaylik, mahsulotning nomi va narxi haqidagi ma'lumotlarni saqlashimiz kerak, biz nomini (string) saqlash uchun qiymat va narxni (float) saqlash uchun boshqa qiymatga ega kortej yaratishimiz mumkin.

***

### Tuple yaratish <a href="#create" id="create"></a>

Swift-da biz `()`kortej elementlarini saqlash uchun qavsdan foydalanamiz. Misol uchun,

```
var product = ("MacBook", 1099.99)
```

Bu erda `product`satr qiymati `Macbook`va butun qiymati **1099,99 bo'lgan kortej mavjud** .

***

### Tuple elementlariga kirish <a href="#access" id="access"></a>

Massiv singari, [kortejning](https://www.programiz.com/swift-programming/arrays) har bir elementi indeks raqamlari ( **0** , **1 , ... ) bilan ifodalanadi, bunda birinchi element 0** indeksida joylashgan .

Tuple elementlariga kirish uchun indeks raqamidan foydalanamiz. Misol uchun,

```
// access the first element
product.0

// access second element
product.1
```

***

#### Misol: Swift Tuple

```
// create tuple with two elements
var product = ("MacBook", 1099.99)

// access tuple elements
print("Name:", product.0)
print("Price:", product.1)
```

**Chiqish**

```
Nomi: MacBook
Narxi: 1099.99
```

`product`Yuqoridagi misolda biz ikkita qiymat bilan nomlangan kortej yaratdik .

Biz indeks raqamidan foydalandik: `product.0`va `product.1`kortej elementlariga kirish uchun.

**Eslatma** : Kortejning birinchi qiymati satr, ikkinchisi esa butun son bo'lgani uchun. Shunday qilib, kortejning turi `(String, Int)`.

***

### Tuple elementini o'zgartirish <a href="#modify" id="modify"></a>

Muayyan indeksga yangi qiymat belgilash orqali kortej elementini o'zgartirishimiz mumkin. Misol uchun,

```
// create tuple with two elements
var product = ("MacBook", 1099.99)

print("Original Tuple: ")

// access tuple elements 
print("Name:", product.0)
print("Price:", product.1)

// modify second value
product.1 = 1299.99

print("\nTuple After Modification: ")

// access tuple elements
print("Name:", product.0)
print("Price:", product.1)
```

**Chiqish**

```
Asl to'plam:
Nomi: MacBook
Narxi: 1099.99

O'zgartirishdan keyin to'plam:
Nomi: MacBook
Narxi: 1299.99
```

Yuqoridagi misolda biz quyidagi `product`qiymatlar bilan nomlangan kortej yaratdik: `MacBook`va **1099.99.** Chiziqqa e'tibor bering,

```
product.1 = 1299.99 
```

Bu erda biz **1 indeksidagi kortej qiymatini 1299,99** ga o'zgartirdik .

**Eslatma** : Tuple indeksi har doim **0** bilan boshlanadi . **Demak, kortejning birinchi elementi 1** emas, balki **0** indeksida mavjud .

***

### Nomlangan Tuplelar <a href="#named" id="named"></a>

Swift-da biz kortejning har bir elementi uchun nom berishimiz mumkin. Misol uchun,

```
var company = (product: "Programiz App", version: 2.1)
```

Nomlangan kortejning elementlariga kirish uchun indeks raqamlari o'rniga ushbu nomlardan ham foydalanishimiz mumkin.

```
// access "Programiz App"
company.product 
```

***

#### Misol: Nomlangan Tuple

```
// create named tuple
var company = (product: "Programiz App", version: 2.1)

// access tuple element using name
print("Product:", company.product)
print("Version:", company.version)
```

**Chiqish**

```
Mahsulot: Programiz ilovasi
Versiya: 2.1
```

Yuqoridagi misolda biz nomlar berdik: `product`va `version`kortejning birinchi va ikkinchi elementiga.

Biz `.`kortejning mos qiymatlariga kirish uchun belgi va berilgan nomlardan foydalandik.

**Eslatma** : Bu nomli kortejlardan foydalanish eng yaxshi amaliyotdir, chunki bu bizning kodimizni yanada o'qilishi mumkin.

***

### Swift Nested Tuple <a href="#nested" id="nested"></a>

Swift-da biz kortejni boshqa kortejning elementi sifatida yaratishimiz mumkin. Misol uchun,

```
var alphabets = ("A", "B", "C", ("a", "b", "c"))
```

Bu erda biz kortejning `("a", "b", "c")`uchinchi elementi sifatida kortejga egamiz `alphabets`. Bu ichki o'rnatilgan kortej deb ataladi.

***

#### Misol: ichki o'rnatilgan to'plam

```
var alphabets = ("A", "B", "C", ("a", "b", "c"))

// access first element
print(alphabets.0)   // prints "A"

// access the third element
print(alphabets.3)

// access nested tuple
print(alphabets.3.0)  // prints "a"
```

Yuqoridagi misolda chiziqqa e'tibor bering,

```
print(alphabets.3)
```

Bu erda biz birinchi navbatda kortejning uchinchi elementiga `alphabets`kirdik.

ning uchinchi elementi ham kortej bo'lgani uchun biz foydalandik

```
alphabets.3.0
```

ichki o'rnatilgan kortejning birinchi elementiga kirish uchun.

***

### Tupledan elementlarni qo'shish/o'chirish <a href="#add-remove" id="add-remove"></a>

Biz Swift-da kortejga elementlar qo'sha olmaymiz yoki olib tashlay olmaymiz. Misol uchun,

```
var company = ("Programiz","Apple")

company.2 = "Google"

company.remove("Apple")

print(company)
```

**Chiqish**

```
xato: "(String, String)" turidagi qiymatni o'zgartirib bo'lmadi
xato: "(String, String)" kortej turi qiymatida "olib tashlash" a'zosi yo'q
```

Bu erda biz qiymatlar bilan kortej yaratdik: `"Programiz"`va `"Apple"`. Endi kortej turi ga o'rnatiladi `(String, String)`.

Shunday qilib, biz kortejga elementlarni qo'shish va olib tashlashga harakat qilsak, biz xatolarga duch kelamiz.

#### Tuple ichidagi lug'at

Swift-da biz kortejga element qo'shish uchun lug'atdan foydalanishimiz mumkin. Misol uchun,

```
var laptopLaunch = ("MacBook", 1299, ["Nepal": "10 PM", "England": "10 AM"])
print(laptopLaunch.2)

laptopLaunch.2["USA"] = "11 AM"

print(laptopLaunch.2)
```

**Chiqish**

```
["Nepal": "10 PM", "Angliya": "10 AM"]
["Nepal": "22.00", "Angliya": "10.00", "AQSh": "11.00"]
```

Yuqoridagi misolda kortejning uchinchi elementi lug'atdir

```
["Nepal": "10 PM", "England": "10 AM"]
```

Ma'lumki, biz lug'atga elementlar qo'shishimiz mumkin. Shunday qilib, biz kodni ishlatamiz.

```
laptopLaunch.2["USA"] = "11 AM"
```

lug'at ichiga element qo'shish uchun.

Shunday qilib, biz kortejga element qo'shishimiz mumkin. Va, kortej turi hali ham bir xil `(String, String, Dictionary)`. Shunday qilib, biz hech qanday xatoga yo'l qo'ymaymiz.

Lug'at haqida ko'proq ma'lumot olish uchun [Swift lug'atiga tashrif buyuring](https://www.programiz.com/swift-programming/dictionary)
