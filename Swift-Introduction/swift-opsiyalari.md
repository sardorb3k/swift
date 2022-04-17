# Swift opsiyalari

Ushbu maqolada siz Swift-da ixtiyoriy, undan foydalanish holatlari va ixtiyoriy ishlov berish haqida bilib olasiz.

Oldingi maqolada biz Swift-da mavjud bo'lgan turli xil ma'lumotlar turlari haqida bilib oldik va shuningdek, ushbu turdagi e'lon qilingan o'zgaruvchi yoki doimiy qiymat birlamchi qiymatga ega ekanligini ko'rdik.

**Misol:**

```
let someValue = Int()
chop etish (ba'zi qiymat)
```

Dasturni ishga tushirganingizda, natija quyidagicha bo'ladi:

```
0
```

Biroq, Swift-da ixtiyoriy deb nomlangan yana bir ma'lumot turi mavjud, uning standart qiymati null qiymat ( `nil`). O'zgaruvchi yoki konstanta unda hech qanday qiymat bo'lmasligini istasangiz, ixtiyoriy foydalanishingiz mumkin. Ixtiyoriy tur qiymatni o'z ichiga olishi yoki qiymat bo'lmasligi mumkin (null qiymat).

Texnik nuqtai nazardan, siz poyabzal qutisi sifatida ixtiyoriy deb o'ylashingiz mumkin. Poyafzal qutisi ichida poyabzal bo'lishi mumkin yoki bo'lmasligi mumkin. Shunday qilib, qutidagi poyafzalga kirishda siz oldindan bilishingiz kerak.

***

### Ixtiyoriyni qanday e'lon qilish kerak? <a href="#declare" id="declare"></a>

Siz shunchaki ma'lumotlar turini ixtiyoriy sifatida `!`yoki `?`ga qo'shishingiz mumkin `Type`. Agar ixtiyoriy unda qiymat bo'lsa, u qiymatni qaytaradi `Optional<Value>`, bo'lmasa qaytaradi `nil`.

#### 1-misol: Swift-da ixtiyoriyni qanday e'lon qilish mumkin?

```
var someValue:Int?
var someAnotherValue:Int!
print(someValue)
print(someAnotherValue)
```

Dasturni ishga tushirganingizda, natija quyidagicha bo'ladi:

```
nol
nol
```

Yuqoridagi dasturda biz `?`va yordamida ixtiyoriy turni ishga tushirdik `!`. Ikkala usul ham ixtiyoriy yaratish uchun amal qiladi, ammo biz quyida ko'rib chiqamiz.

Ixtiyoriy Int ni e'lon qilish o'zgaruvchining butun qiymatga ega bo'lishini yoki hech qanday qiymatga ega bo'lmasligini anglatadi. O'zgaruvchiga hech qanday qiymat berilmaganligi sababli , ekranda ikkala `print`bayonot chiqishini ham ko'rishingiz mumkin.`nil`

***

#### 2-misol: ixtiyoriy qiymatdan qiymat belgilash va unga kirish <a href="#assign" id="assign"></a>

```
let someValue:Int? = 5
print(someValue)
print(someValue!)
```

Dasturni ishga tushirganingizda, natija quyidagicha bo'ladi:

```
Ixtiyoriy(5)
5
```

Yuqoridagi dasturda biz ixtiyoriy `Int`turni e'lon qildik va unda 5 qiymatini belgiladik.

Ko'rib turganingizdek, ixtiyoriyni chop etish `print(someValue)`sizga bermaydi, `5`lekin `Optional(5)`. U yuqorida tavsiflangan shaklda: `Optional<Value>`. Undan kirish uchun `<Value>`bizga ochish deb nomlangan mexanizm **kerak** .

`!`Keyingi qatordagi kabi oʻzgaruvchi/doimiy oxiriga belgi qoʻshish orqali ixtiyoriyni ochishingiz mumkin `print(someValue!)`. `print(someValue!)`ixtiyoriyni ochadi va `5`ekranda chiqadi.

Biroq, esda tutingki, bunday ochish mexanizmi faqat siz unga kirganingizda ixtiyoriy qiymatga ega bo'lishiga ishonchingiz komil bo'lgandagina foydalanish kerak.

***

#### 3-misol: Ochilmagan ixtiyoriyni aniq e'lon qilish <a href="#declare-unwrapped" id="declare-unwrapped"></a>

Bundan tashqari, oʻramni ochilmagan ixtiyoriy yaratishingiz mumkin:

```
let someValue:Int! = 5
print(someValue)
```

Dasturni ishga tushirganingizda, natija quyidagicha bo'ladi:

```
5
```

Yuqoridagi dasturda `Int!`ixtiyoriy oʻramni yaratadi, u siz kirish vaqtida qiymatni avtomatik ravishda ochadi, shunda siz har safar `!`belgi qoʻshishingiz shart emas.

Ushbu turdagi ixtiyoriylardan foydalanganda ishonch hosil qiling, o'zgaruvchiga kirganingizda har doim qiymatga ega bo'lishi kerak bo'ladi. Agar shunday qilmasangiz, halokatli xato halokatiga duch kelasiz.

***

#### 4-misol: ixtiyoriy ravishda oʻralmagan nullga kirishda jiddiy xatolik <a href="#unwrapped-fatal" id="unwrapped-fatal"></a>

```
var someValue:Int!
var unwrappedValue:Int = someValue //crashes due to this line
```

Dasturni ishga tushirganingizda, **halokatli xatolik paydo bo'ladi: ixtiyoriy qiymatni ochishda kutilmaganda nol topildi,** chunki kod ixtiyoriydan qiymat `unwrappedValue:Int = someValue`belgilashga harakat qiladi.someValueo'zgaruvchigaunwrappedValue.

Biroq,qandaydir qiymatqiymatni `Optional`o'z ichiga olgan tur . `nil`O'zgaruvchiga nol qiymatini belgilashga urinishunwrappedValueixtiyoriy bo'lmagani halokatga olib keladi.

Ushbu ishni hal qilish uchun turli xil texnikalar mavjud, ular quyida tavsiflanadi.

***

### Ixtiyoriy ishlov berish <a href="#optional-handling" id="optional-handling"></a>

Ixtiyoriy qiymatdan foydalanish uchun uni ochish kerak. `!`Ixtiyoriy qiymatdan foydalanishning eng yaxshi usuli operator yordamida oʻramni majburan ochishdan koʻra shartli ochishdir .

Buning sababi, shartli ravishda o'ramni ochish **ushbu o'zgaruvchining qiymati borligini tekshiringmi?** . Ha bo'lsa, qiymatni bering, aks holda u nol holatini ko'rib chiqadi.

Aksincha, oʻramni majburan ochishda **siz foydalanayotganingizda bu oʻzgaruvchining qiymati borligini** aytadi . Shuning uchun, siz nolga teng bo'lgan o'zgaruvchini ochishga majbur qilganingizda, dasturingiz **ixtiyoriy istisnoni ochishda kutilmaganda topilgan nolni chiqaradi va ishdan chiqadi** . Shartli ravishda o'rashning ba'zi usullari quyida tushuntirilgan:

#### 1. If- deyimi <a href="#if" id="if"></a>

Ixtiyoriy soʻzda qiymat bor yoki yoʻqligini bilish uchun if iborasidan foydalanishingiz va ixtiyoriyni nol bilan solishtirishingiz mumkin. If iborasida taqqoslash operatoridan "teng" operatoridan ( `==`) yoki "teng emas" operatoridan ( `!=`) foydalanishingiz mumkin.

**5-misol: if else ifodasi bilan ixtiyoriy ishlov berish**

```
var someValue:Int?
var someAnotherValue:Int! = 0
        
if someValue != nil {
	print("It has some value \(someValue!)")
} else {
	print("doesn't contain value")
}
        
if someAnotherValue != nil {
	print("It has some value \(someAnotherValue!)")
} else {
	print("doesn't contain value")
}
```

Dasturni ishga tushirganingizda, natija quyidagicha bo'ladi:

```
qiymatni o'z ichiga olmaydi
U 0 qiymatiga ega
```

Yuqoridagi dasturda if operatori ichidagi kod, agar ixtiyoriy qo'shimchada qiymat bo'lsa, bajariladi, aks holda else blokidagi operator bajariladi. Ushbu texnikadan foydalangan holda ixtiyoriy ishlov berishning asosiy kamchiligi shundaki, siz hali ham ixtiyoriy `!`operator yordamida qiymatni ochishingiz kerak.

***

#### 2. Ixtiyoriy bog‘lash (if-let) <a href="#if-let" id="if-let"></a>

Ixtiyoriy bog'lash ixtiyoriyda qiymat bor yoki yo'qligini aniqlashga yordam beradi. Agar ixtiyoriy qiymatda qiymat bo'lsa, bu qiymat vaqtinchalik doimiy yoki o'zgaruvchi sifatida mavjud bo'ladi. Shuning uchun, ixtiyoriy bog'lanish ixtiyoriy ichidagi qiymatni tekshirish va bu qiymatni bitta amalda doimiy yoki o'zgaruvchiga chiqarish uchun if bayonoti bilan ishlatilishi mumkin.

**5-misol: if let iborasi yordamida ixtiyoriy ishlov berish**

```
var someValue:Int?
var someAnotherValue:Int! = 0
       
if let temp = someValue {
	print("It has some value \(temp)") 
} else {
	print("doesn't contain value")
}
        
if let temp = someAnotherValue {
	print("It has some value \(temp)")
} else {
	print("doesn't contain value")      
}
```

Dasturni ishga tushirganingizda, natija quyidagicha bo'ladi:

```
qiymatni o'z ichiga olmaydi
U 0 qiymatiga ega
```

Yuqoridagi dasturda, agar ixtiyoriy qiymat bo'lsa, if operatori ichidagi kod bajariladi. Aks holda else bloki bajariladi. Bayonot `if-let`shuningdek, qiymatni avtomatik ravishda ochadi va ochilgan qiymatni ichiga joylashtiraditempdoimiy. Ushbu texnikaning katta afzalligi bor, chunki siz ixtiyoriy qiymatni o'z ichiga olganligiga ishonchingiz komil bo'lsa-da, qiymatni majburan ochishingiz shart emas.

***

#### 3. Qo'riqchi bayonoti <a href="#guard" id="guard"></a>

Swift-da ixtiyoriylarni boshqarish uchun qo'riqchidan foydalanishingiz mumkin. Agar qo'riqchi nima ekanligini bilmasangiz, tashvishlanmang. Hozircha qorovulni `if-else`if ​​bloki bo'lmagan shart deb hisoblang. Agar shart bajarilmasa, else bayoni bajariladi. Agar yo'q bo'lsa, keyingi bayonot bajariladi. Batafsil ma'lumot uchun [Swift guard](https://www.programiz.com/swift-programming/guard-statement) -ga qarang.

**6-misol: guard-let yordamida ixtiyoriy ishlov berish**

```
func testFunction() {
	let someValue:Int? = 5
	guard let temp = someValue else {
		return
	}
	print("It has some value \(temp)")
}

testFunction()
```

Dasturni ishga tushirganingizda, natija quyidagicha bo'ladi:

```
U 5 qiymatiga ega
```

Yuqoridagi dasturda qo'riqchi ixtiyoriy emasligi shartini o'z ichiga oladisomeValueqiymatni o'z ichiga oladi yoki yo'q. Agar u qiymatni o'z ichiga olsa, `guard-let`bayonot avtomatik ravishda qiymatni ochadi va ochilmagan qiymatni joylashtiraditempdoimiy. Aks holda, aks holda blok bajariladi va u chaqiruv funksiyasiga qaytadi. Ixtiyoriy qiymatni o'z ichiga olganligi sababli, `print`funktsiya chaqiriladi.

***

#### 4. Nil-birlashuvchi operator <a href="#nil-coalescing" id="nil-coalescing"></a>

Swift-da ixtiyoriy qiymat bor yoki yo'qligini tekshirish uchun nil-coalescing operatoridan ham foydalanishingiz mumkin. Bu kabi aniqlanadi `(a ?? b)`. U ixtiyoriyni ochadiava agar u qiymatni o'z ichiga olgan bo'lsa yoki standart qiymatni qaytarsa, uni qaytaradibagaranol.

**7-misol: nil-coalescing operatori yordamida ixtiyoriy ishlov berish**

```
var someValue:Int!
let defaultValue = 5
let unwrappedValue:Int = someValue ?? defaultValue
print(unwrappedValue)
```

Dasturni ishga tushirganingizda, natija quyidagicha bo'ladi:

```
5
```

Yuqoridagi dasturda o'zgaruvchansomeValueixtiyoriy belgilangan va o'z ichiga oladinolqiymat. nil birlashma operatori ixtiyoriyni ocholmaydi, shuning uchun qaytib keladidefaultValue. Shuning uchun bayonot `print(unwrappedValue)`konsolda 5 ni chiqaradi.

```
var someValue:Int? = 10
let defaultValue = 5
let unwrappedValue:Int = someValue ?? defaultValue
print(unwrappedValue)
```

Dasturni ishga tushirganingizda, natija quyidagicha bo'ladi:

```
10
```

Biroq, yuqoridagi dasturda ixtiyoriy o'zgaruvchisomeValue10 qiymati bilan ishga tushiriladi. Shunday qilib, nil birlashtiruvchi operator qiymatni muvaffaqiyatli ochadi.someValue. Shuning uchun, bayonot `someValue ?? defaultValue`10 ni qaytaradi va bayonot `print(unwrappedValue)`konsolda 10 ni chiqaradi.
