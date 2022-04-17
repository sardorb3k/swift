# Swift lug'ati

Ushbu qo'llanmada biz Swift lug'atlari haqida hamma narsani bilib olamiz; ular qanday yaratilganligi, ularga kirish, qo'shish, elementlarni olib tashlash va turli o'rnatilgan usullar.

Swift lug'ati - bu tartibsiz elementlar to'plami. U elementlarni **kalit/qiymat** juftliklarida saqlaydi. Bu erda **kalitlar har bir qiymat** bilan bog'langan noyob identifikatorlardir .

Keling, bir misolni ko'rib chiqaylik.

Agar biz mamlakatlar va ularning poytaxtlari haqidagi ma'lumotlarni saqlamoqchi bo'lsak, biz **kalit sifatida davlat nomlari va qiymat** sifatida bosh harflar bilan lug'at yaratishimiz mumkin .

| **Kalitlar** | **Qiymatlar** |
| ------------ | ------------- |
| Nepal        | Katmandu      |
| Italiya      | Rim           |
| Angliya      | London        |

***

### Swift-da lug'at yarating <a href="#create" id="create"></a>

Swift-da qanday qilib lug'at yaratishimiz mumkin.

```
var capitalCity = ["Nepal": "Kathmandu", "Italy": "Rome", "England": "London"]
print(capitalCity)
```

**Chiqish**

```
["Nepal": "Katmandu", "Angliya": "London", "Italiya": "Rim"]
```

Yuqoridagi misolda biz nomli lug'at yaratdik `capitalCity`. Bu yerda,

* **Kalitlar** , `"Nepal"`, `"Italy"`\_`"England"`
* **Qadriyatlar** , `"Kathmandu"`, `"Rome"`\_`"London"`

Ushbu kodni ishga tushirganimizda, biz boshqa tartibda chiqishimiz mumkin. Buning sababi shundaki, lug'atda alohida tartib yo'q.

**Eslatma:** Bu erda kalitlar va qiymatlar ikkala `String`turdagi. Shuningdek, bizda turli xil ma'lumotlar turlarining kalitlari va qiymatlari bo'lishi mumkin.

***

### Misol: Swift lug'ati

```
// dictionary with keys and values of different data types
var numbers = [1: "One", 2: "Two", 3: "Three"]
print(numbers)
```

**Chiqish**

```
[3: “Uch”, 1: “Bir”, 2: “Ikki”]
```

Yuqoridagi misolda biz nomli lug'at yaratdik `numbers`. Bu erda **kalitlar** turdagi `Int`va **qiymatlar** turdagi `String`.

***

### Lug'atga elementlar qo'shish <a href="#add" id="add"></a>

Biz bilan lug'at nomidan foydalanib, lug'atga elementlar qo'shishimiz mumkin `[]`. Misol uchun,

```
var capitalCity = ["Nepal": "Kathmandu", "England": "London"]
print("Initial Dictionary: ",capitalCity)

capitalCity["Japan"] = "Tokyo"

print("Updated Dictionary: ",capitalCity)
print(capitalCity["Japan"])
```

**Chiqish**

```
Dastlabki lug'at: ["Nepal": "Katmandu", "Angliya": "London"]
Yangilangan lug'at: ["Nepal": "Katmandu", "Angliya": "London", "Yaponiya": "Tokio"]
```

Yuqoridagi misolda biz nomli lug'at yaratdik `capitalCity`. Chiziqqa e'tibor bering,

```
capitalCity["Japan"] = "Tokyo"
```

**Bu yerda biz key** : va **value** : `capitalCity`bilan yangi element qo‘shdik .`JapanTokyo`

***

### Lug'at qiymatini o'zgartirish <a href="#change" id="change"></a>

`[]`Muayyan kalit bilan bog'langan qiymatni o'zgartirish uchun ham foydalanishimiz mumkin . Misol uchun,

```
var studentID = [111: "Eric", 112: "Kyle", 113: "Butters"]
print("Initial Dictionary: ", studentID)

studentID[112] = "Stan"

print("Updated Dictionary: ", studentID)
```

**Chiqish**

```
Dastlabki lug'at: [111: "Erik", 113: "Sariqlar", 112: "Kyle"]
Yangilangan lug'at: [111: "Erik", 113: "Butters", 112: "Stan"]
```

Yuqoridagi misolda biz nomli lug'at yaratdik `studentID`. `112`Dastlab, kalit bilan bog'langan qiymat `"Kyle"`. Endi chiziqqa e'tibor bering,

```
studentID[112] = "Stan"
```

Bu erda biz kalit bilan bog'langan qiymatni `112`o'zgartirdik `"Stan"`.

***

### Lug'atdan elementlarga kirish <a href="#access" id="access"></a>

Swift-da biz lug'atning kalitlari va qiymatlariga mustaqil ravishda kirishimiz mumkin.

**1. Faqat kirish kalitlari**

Biz `keys`lug'atdagi barcha kalitlarga kirish uchun mulkdan foydalanamiz. Misol uchun,

```
var cities = ["Nepal":"Kathmandu", "China":"Beijing", "Japan":"Tokyo"]

print("Dictionary: ", cities)

// cities.keys return all keys of cities
var countryName  = Array(cities.keys)

print("Keys: ", countryName)
```

**Chiqish**

```
Lug'at: ["Nepal": "Katmandu", "Yaponiya": "Tokio", "Xitoy": "Pekin"]
Kalitlar: ["Nepal", "Yaponiya", "Xitoy"]
```

**2. Faqat qiymatlarga kirish**

Xuddi shunday, biz `values`lug'atdagi barcha qiymatlarga kirish uchun xususiyatdan foydalanamiz. Misol uchun,

```
var cities = ["Nepal":"Kathmandu", "China":"Beijing", "Japan":"Tokyo"]

print("Dictionary: ", cities)

// cities.values return all values of cities
var countryName  = Array(cities.values)

print("Values: ", countryName)
```

**Chiqish**

```
Lug'at: ["Nepal": "Katmandu", "Xitoy": "Pekin", "Yaponiya": "Tokio"]
Qadriyatlar: ["Katmandu", "Pekin", "Tokio"]
```

***

### Lug'atdan elementni olib tashlang <a href="#remove" id="remove"></a>

Biz `removeValue()`lug'atdan elementni olib tashlash usulidan foydalanamiz. Misol uchun,

```
var studentID = [111: "Eric", 112: "Kyle", 113: "Butters"]

print("Initial Dictionary: ", studentID)

var removedValue  = studentID.removeValue(forKey: 112)

print("Dictionary After removeValue(): ", studentID)
```

**Chiqish**

```
Dastlabki lug'at: [113: "Sariqlar", 111: "Erik", 112: "Kayl"]
Lug'at keyin removeValue(): [111: "Erik", 113: "Sariqlar"]
```

Bu erda biz lug'at yaratdik `studentID`. E'tibor bering

```
var removedValue  = studentID.removeValue(forKey: 112)
```

Usul `removeValue()`kalit bilan bog'langan elementni olib tashlaydi `112`.

**Eslatma**`removeAll()` : Biz lug'atning barcha elementlarini o'chirish uchun funksiyadan ham foydalanishimiz mumkin .

***

### Boshqa lug'at usullari <a href="#other" id="other"></a>

| Usul              | Tavsif                                        |
| ----------------- | --------------------------------------------- |
| `sorted()`        | lug'at elementlarini tartiblaydi              |
| `shuffled()`      | lug'at elementlarining tartibini o'zgartiradi |
| `contains()`      | belgilangan element mavjudligini tekshiradi   |
| `randomElement()` | lug'atdan tasodifiy elementni qaytaradi       |
| `firstIndex()`    | belgilangan elementning indeksini qaytaradi   |

***

### Lug'at ustida takrorlash <a href="#iterate" id="iterate"></a>

Lug'at elementlarini takrorlash uchun biz [for tsiklidan foydalanamiz. ](https://www.programiz.com/swift-programming/for-in-loop)Misol uchun,

```
var classification = ["Fruit": "Apple", "Vegetable": "Broccoli", "Beverage": "Milk"]

print("Keys: Values")

for (key,value) in classification {
  print("\(key): \(value)")
}
```

**Chiqish**

```
Kalitlar: qiymatlar
Sabzavotlar: brokkoli
Ichimlik: sut
Meva: olma
```

***

### Lug'at elementlari sonini toping <a href="#count" id="count"></a>

`count`Lug'atda mavjud bo'lgan elementlar sonini topish uchun xususiyatdan foydalanishimiz mumkin. Misol uchun,

```
var studentID = [111: "Eric", 112: "Kyle", 113: "Butters"]
print(studentID.count)
```

**Chiqish**

```
3
```

***

### Bo'sh lug'at yarating <a href="#empty" id="empty"></a>

Swift-da biz bo'sh lug'at yaratishimiz mumkin. Misol uchun,

```
var emptyDictionary =  [Int: String]()
print("Empty Dictionary: ",emptyDictionary)
```

**Chiqish**

```
Bo'sh lug'at: [:]
```

Yuqoridagi misolda biz bo'sh lug'at yaratdik. Ifodaga e'tibor bering

```
[Int: String]()
```

Bu yerda,

* `Int`lug'at kalitlari butun son tipida bo'lishini bildiradi
* `String`lug'at qiymatlari String tipida bo'lishini bildiradi.

**Eslatma** : Bo'sh lug'at yaratishda lug'atning ma'lumotlar turini ko'rsatish majburiydir.
