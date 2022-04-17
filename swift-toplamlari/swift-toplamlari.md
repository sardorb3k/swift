# Swift to'plamlari

Ushbu qo'llanmada biz misollar yordamida Set va uning Swift-dagi turli operatsiyalarini o'rganamiz.

To'plam - bu noyob ma'lumotlar to'plami. Ya'ni, to'plam elementlarini takrorlash mumkin emas. Misol uchun,

**Aytaylik, biz talaba identifikatorlari** haqidagi ma'lumotlarni saqlamoqchimiz . **Talaba identifikatorlari** ikki nusxada bo'lmasligi sababli, biz to'plamdan foydalanishimiz mumkin .

![Talaba ID to'plami](https://cdn.programiz.com/cdn/farfuture/KuLlX7XzUe0Uy9kpqpcbk3xoAqaPA9TVXb0mjujNlXc/mtime:1620988175/sites/tutorial2program/files/swift-set-intro.png)To'plam elementlari

***

### Swift-da to'plam yarating <a href="#create" id="create"></a>

Swift-da qanday qilib to'plam yaratishimiz mumkin.

```
// create a set of integer type
var studentID : Set = [112, 114, 116, 118, 115]

print("Student ID: \(studentID)")
```

**Chiqish**

```
Talaba identifikatori: [112, 114, 115, 118, 116]
```

Yuqoridagi misolda, bayonotga e'tibor bering,

```
var studentID : Set = [112, 114, 115, 118, 116]
```

Bu erda `Set`kalit so'z buni bildiraditalaba IDto'plamdir. To'plamning barcha elementlari butun sonlar bo'lgani uchun,talaba IDturlari to‘plamidir `Int`.

Biroq, biz to'plamning turini ham belgilashimiz mumkin

```
var studentID : Set<Int> = [112, 114, 115, 116, 118]
```

**Eslatma** : Ushbu kodni ishga tushirganingizda, siz boshqa tartibda chiqishingiz mumkin. Buning sababi shundaki, to'plamda alohida tartib yo'q.

***

### To'plamga elementlar qo'shing <a href="#add" id="add"></a>

`insert()`Belgilangan elementni to'plamga qo'shish usulidan foydalanamiz . Misol uchun,

```
var employeeID: Set = [21, 34, 54, 12]

print("Initial Set: \(employeeID)")

// using insert method
numbers.insert(32)

print("Updated Set: \(numbers)") 
```

**Chiqish**

```
Dastlabki toʻplam: [54, 21, 34, 12]
Yangilangan toʻplam: [54, 21, 34, 12, 32]
```

Yuqoridagi misolda biz nomli to'plam yaratdikxodim ID. Chiziqqa e'tibor bering,

```
numbers.insert(32)
```

Bu erda bizning to'plamimizga **32**`insert()` qo'shiladi .

***

### To'plamdan elementni olib tashlang <a href="#remove" id="remove"></a>

`remove()`Belgilangan elementni to'plamdan olib tashlash uchun usuldan foydalanamiz . Misol uchun,

```
var languages: Set = ["Swift", "Java", "Python"]

print("Initial Set: \(languages)")

// remove Java from a set
let removedValue = languages.remove("Java")

print("Set after remove(): \(languages)")
```

**Chiqish**

```
Dastlabki to'plam: ["Python", "Java", "Swift"]
O'chirishdan keyin o'rnating(): ["Python", "Swift"]
```

Xuddi shunday, biz ham foydalanishimiz mumkin

* `removeFirst()`- to'plamning birinchi elementini olib tashlash uchun
* `removeAll()`- to'plamning barcha elementlarini olib tashlash uchun

***

### Boshqa sozlash usullari <a href="#other" id="other"></a>

| Usul              | Tavsif                                           |
| ----------------- | ------------------------------------------------ |
| `sorted()`        | to'plam elementlarini tartiblaydi                |
| `forEach()`       | har bir elementda belgilangan amallarni bajaradi |
| `contains()`      | to'plamda ko'rsatilgan elementni qidiradi        |
| `randomElement()` | to'plamdan tasodifiy elementni qaytaradi         |
| `firstIndex()`    | berilgan elementning indeksini qaytaradi         |

***

### To'plam ustida takrorlash <a href="#iterate" id="iterate"></a>

To'plam elementlarini takrorlash [uchun for tsiklidan](https://www.programiz.com/swift-programming/for-in-loop) foydalanishimiz mumkin . Misol uchun,

```
let fruits: Set = ["Apple", "Peach", "Mango"]

print("Fruits:")

// for loop to access each fruits
for fruit in fruits {
  print(fruit)
}
```

**Chiqish**

```
Mevalar:
Shaftoli
Mango
olma
```

***

### To'plam elementlari sonini toping <a href="#count" id="count"></a>

`count`To'plamda mavjud elementlar sonini topish uchun xususiyatdan foydalanishimiz mumkin . Misol uchun,

```
let evenNumbers = [2,4,6,8]
print("Set: \(evenNumbers)")

// find number of elements
print("Total Elements: \(evenNumbers.count)")
```

**Chiqish**

```
Toʻplam: [2, 6, 8, 4]
Jami elementlar: 4
```

***

### Swift Set operatsiyalari

Swift Set birlashma, kesishish, ayirish va simmetrik farq kabi matematik to'plam operatsiyalarini bajarish uchun turli xil o'rnatilgan usullarni taqdim etadi.

#### 1. Ikki to'plamning birligi <a href="#union" id="union"></a>

Ikki A va B to'plamlarning birlashishi **A** va **B to'plamning** barcha **elementlarini** o'z ichiga oladi .

![Ikki to'plamning birligi A va B](https://cdn.programiz.com/cdn/farfuture/WK59Fax48S2EPdM6lCbNX8gAawtTr9ZqROGE\_v-ZKpY/mtime:1620992181/sites/tutorial2program/files/set-union-swift.png)Ikki to'plam ittifoqi

`union()`O'rnatilgan birlashma operatsiyasini bajarish uchun usuldan foydalanamiz . Misol uchun,

```
// first set
let setA: Set = [1, 3, 5]
print("Set A: ", setA)

// second set
let setB: Set = [0, 2, 4]
print("Set B: ", setB)

// perform union operation
print("Union: ", setA.union(setB))
```

**Chiqish**

```
A toʻplami: [1, 5, 3]
B toʻplami: [0, 2, 4]
Birlashma: [0, 5, 2, 4, 1, 3]
```

**Eslatma** : o'rnatilgan operatsiyaga `setA.union(setB)`teng .`A ⋃ B`

***

#### 2. Ikki to'plam orasidagi kesishish <a href="#intersection" id="intersection"></a>

Ikki A va B to'plamlarning kesishishi **A** va **B to'plamlari** orasidagi **umumiy** elementlarni o'z ichiga oladi .

![Ikki A va B to'plamlar orasidagi kesishish operatsiyasi](https://cdn.programiz.com/cdn/farfuture/Xmgz4R1wQjVfdlp4RXhdICOT6XxdlUJi\_ZYa4b\_c-Ao/mtime:1620992194/sites/tutorial2program/files/set-intersection-swift.png)Ikki to'plamning kesishishi

`intersection()`Ikki to'plam orasidagi kesishishni amalga oshirish uchun usuldan foydalanamiz . Misol uchun,

```
// first set
let setA: Set = [1, 3, 5]
print("Set A: ",  setA)

// second set
let setB: Set = [1, 2, 3]
print("Set B: ",  setB)

// perform intersection operation
print("Intersection: ", setA.intersection(setB))
```

**Chiqish**

```
A toʻplami: [5, 3, 1]
B toʻplami: [1, 2, 3]
Chorraha: [3, 1]
```

**Eslatma** : o'rnatilgan operatsiyaga `setA.intersection(setB)`teng .`A ⋂ B`

***

#### 3. Ikki to'plam orasidagi farq <a href="#subtracting" id="subtracting"></a>

Ikki **A** va **B to'plamlar orasidagi farq A to'plamning B** to'plamida mavjud bo'lmagan elementlarini o'z ichiga oladi .

![Ikki A va B to'plamlari orasidagi farq](https://cdn.programiz.com/cdn/farfuture/1XogAQOZpNuoLaRPjvj6ETGxyqQGcOepjzJjSyEmdcI/mtime:1620992209/sites/tutorial2program/files/swift-set-difference.png)Ikki to'plam o'rtasidagi farq

`subtracting()`Ikki to'plam orasidagi farqni bajarish uchun usuldan foydalanamiz . Misol uchun,

```
// first set
let setA: Set = [2, 3, 5]
print("Set A: ",  setA)

// second set
let setB: Set = [1, 2, 6]
print("Set B: ",  setB)

// perform subtraction operation
print("Subtraction: ", setA.subtracting(setB))
```

**Chiqish**

```
A toʻplami: [3, 5, 2]
B toʻplami: [1, 6, 2]
Ayirish: [3, 5]
```

**Eslatma** : o'rnatilgan operatsiyaga `setA.substracting(setB)`teng .`A - B`

***

#### 4. Ikki to‘plam orasidagi simmetrik farq <a href="#symmetric-difference" id="symmetric-difference"></a>

Ikki A va B to'plamlari orasidagi nosimmetrik farq **umumiy** elementlarsiz **A va** B **ning** barcha elementlarini o'z ichiga oladi .

![Ikki A va B to'plamlari orasidagi simmetrik farq](https://cdn.programiz.com/cdn/farfuture/tK42nJ7dJJDL9NKsylPid4IWTsFPq0gIHevWyUNiUKU/mtime:1620992187/sites/tutorial2program/files/set-symmetric-difference-swift.png)Ikki to'plam o'rtasidagi simmetrik farq

`symmetricDifference()`Ikki to'plam orasidagi nosimmetrik farqni bajarish uchun usuldan foydalanamiz . Misol uchun,

```
// first set
let setA: Set = [2, 3, 5]
print("Set A: ",  setA)

// second set
let setB: Set = [1, 2, 6]
print("Set B: ",  setB)

// perform symmetric difference operation
print("Symmetric Difference: ", setA.symmetricDifference(setB))
```

**Chiqish**

```
A toʻplami: [5, 2, 3]
B toʻplami: [2, 6, 1]
Simmetrik farq: [1, 6, 3, 5]
```

***

#### 5. To'plamning pastki to'plamini tekshiring <a href="#subset" id="subset"></a>

Agar **B** ning barcha elementlari A da ham mavjud bo'lsa, **B** to'plam **A to'plamning** kichik to'plami deyiladi .

![A to'plam B to'plamining kichik to'plamidir](https://cdn.programiz.com/cdn/farfuture/jUy9FF9pKUX0F3BebQlDe3chRRXdtkJACuU9S1kw1J4/mtime:1620992202/sites/tutorial2program/files/swift-set-subset.png)To'plamning pastki to'plami

`Subset()`Bir to'plam boshqasining to'plami yoki yo'qligini tekshirish uchun usuldan foydalanamiz . Misol uchun,

```
// first set
let setA: Set = [1, 2, 3, 5, 4]
print("Set A: ",  setA)

// second set
let setB: Set = [1, 2]
print("Set B: ",  setB)

// check if setB is subset of setA or not
print("Subset: ", setB.isSubset(of: setA))
```

**Chiqish**

```
A toʻplami: [3, 1, 2, 5]
B toʻplami: [1, 2]
Kichik to'plam: rost
```

***

### Ikki to'plam teng yoki yo'qligini tekshiring <a href="#equality" id="equality"></a>

`==`Ikki to'plam teng yoki teng emasligini tekshirish uchun operatordan foydalanishimiz mumkin . Misol uchun,

```
let setA: Set = [1, 3, 5]
let setB: Set = [3, 5, 1]

if setA == setB {
  print("Set A and Set B are equal")
}
else {
  print("Set A and Set B are different")
}
```

**Chiqish**

```
A to'plami va B to'plami tengdir
```

Yuqoridagi misolda `setA`va `setB`bir xil elementlarga ega, shuning uchun shart

```
if setA == setB
```

ga baho beradi `true`. Demak, `print("Set A and Set B are same")`ichidagi bayonot `if`bajariladi.

***

### Bo'sh to'plam yarating <a href="#empty-set" id="empty-set"></a>

Swift-da biz bo'sh to'plamni ham yaratishimiz mumkin. Misol uchun,

```
var emptySet = Set<Int>()
print("Set:", emptySet)
```

**Chiqish**

```
Sozlash: [ ]
```

Shuni ta'kidlash kerakki, bo'sh to'plamni yaratishda biz ma'lumotlar turini, `<>`so'ngra initsializator sintaksisini ko'rsatishimiz kerak `()`.

Bu erda `<Int>()`bo'sh to'plam faqat butun son ma'lumotlar elementlarini saqlashi mumkinligini bildiradi.
