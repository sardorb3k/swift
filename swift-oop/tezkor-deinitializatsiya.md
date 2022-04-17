# Tezkor deinitializatsiya

Ushbu qo'llanmada biz misollar yordamida Swift deinitializatsiyasi haqida bilib olamiz.

Deinitializatsiya - bu kerak bo'lmaganda sinf misollarini ajratish jarayoni. Bu tizim egallagan xotira maydonini bo'shatadi.

`deinit`Kalit so'zdan deinitializer yaratish uchun foydalanamiz . Misol uchun,

```
class Race {
  ...

  // create deinitializer
  deinit {
    // perform deinitialization
    ... 
  }
} 
```

Bu yerda `deinit`ning deinitializatoriPoygasinf.

Deintializerlar haqida bilishdan oldin, [Swift Initializer](https://www.programiz.com/swift-programming/initializer) haqida bilishingizga ishonch hosil qiling .

***

### Misol: Swift Deinitializer <a href="#example" id="example"></a>

```
// declare a class
class  Race {
  var laps: Int

  // define initializer
  init() {
    laps = 5
    print("Race Completed")
    print("Total laps:", laps)
  }

  // define deinitializer
  deinit {
    print("Memory Deallocated")
  }
}

// create an instance
var result: Race? = Race()

// deallocate object
result = nil
```

**Chiqish**

```
Poyga tugallandi
Jami aylanishlar: 5
Xotira ajratilgan
```

Yuqoridagi misolda,

1\. Biz ichida deinitializer yaratdikPoygasinf.

```
deinit {
  print("Memory Deallocated")
}
```

2\. Keyin, biz bir misol yaratdikPoygasinf va uni a ga tayinladiPoyganomli turdagi o‘zgaruvchinatija.

```
// create an instance
var result: Race? = Race()
```

Bu yerda,Poygami?ekanligini bildiradinatijaixtiyoriy , shuning uchun u ikki turdagi qiymatlarni saqlashi mumkin [:](https://www.programiz.com/swift-programming/optionals)

* qiymatlariPoygaturi.
* qiymat `nil`.

`nil`3. Nihoyat , biz tayinlaymiznatija:

```
// deallocate instance
result = nil
```

Bu misolni ajratadi. Deinitializer sinf namunasi ajratilishidan oldin avtomatik ravishda chaqiriladi. Va uning ichidagi bayonot bajariladi.

**Eslatma** :

* Swift-da biz initsializatorlardan faqat misollarni qo'lda ajratishni xohlaganimizda foydalanamiz. Aks holda, Swift avtomatik ravishda ajratishni amalga oshiradi.
* Deinitializers faqat sinflar bilan ishlatilishi mumkin, strukturalar bilan emas.
* Har bir sinfda faqat bitta deinitializer bo'lishi mumkin.
