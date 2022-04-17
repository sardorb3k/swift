# Tez kirishni boshqarish

Ushbu qo'llanmada biz Swift kirishni boshqarish, uning turlari va ulardan qanday foydalanishni misollar yordamida bilib olamiz.

Swift-da kirishni boshqarish vositalari sinflar, tuzilmalar, raqamlashlar, xususiyatlar, usullar, initsializatorlar va pastki yozuvlarning mavjudligini (ko'rinishini) o'rnatish uchun ishlatiladi. Misol uchun,

```
class Vehicle {

  public func method1() {...}
  private func method2() {...}
}
```

Bu yerda,

1. `method1()`ya'ni `public`unga boshqa sinflar kirishi mumkin.
2. `method2()`ya'ni `private`unga boshqa sinflar kira olmaydi.

Kalit so'zga e'tibor bering `public`va `private`. Bular Swift-dagi kirish boshqaruvlari.

***

### Tez kirishni boshqarish turlari <a href="#types" id="types"></a>

Swift-da to'rtta kirish boshqaruvi mavjud:

| Boshqaruv     | Tavsif                                                                       |
| ------------- | ---------------------------------------------------------------------------- |
| `public`      | deklaratsiyalarga hamma joydan kirish mumkin                                 |
| `private`     | deklaratsiyalarga faqat belgilangan sinf yoki struktura ichida kirish mumkin |
| `fileprivate` | deklaratsiyalarga faqat joriy Swift faylida kirish mumkin                    |
| `internal`    | deklaratsiyalarga faqat belgilangan modul doirasida kirish mumkin (standart) |

***

### ommaviy kirish nazorati <a href="#public" id="public"></a>

Swift-da usullar, xususiyatlar, sinflar va boshqalar e'lon qilinganda `public`, biz ularga istalgan joydan kirishimiz mumkin.

Kirish `public`modifikatorida qamrov cheklovi yo'q. Misol uchun,

```
class Animal {

  // public property
  public var legCount: Int = 0

  // public method
  public func display() {
    print("I am an animal.");
    print("Total Legs:", legCount)
  }
}

// create an object
var obj = Animal()

// access and assign value to public property
obj.legCount = 4

// access the public method
obj.display()
```

**Chiqish**

```
Men hayvonman.
Umumiy oyoqlar: 4
```

`Animal`Yuqoridagi misolda biz ikkita `public`ma'lumot a'zosi bilan nomlangan sinf yaratdik :legCountva `display()`.

`Animal`Keyin biz nomli sinf ob'ektini yaratdikobj. Keyin kodlar va `public`kodlardan foydalangan holda to'g'ridan-to'g'ri ma'lumotlar a'zolariga kiramiz .`obj1.legCountobj1.display()`

***

### shaxsiy kirish nazorati <a href="#private" id="private"></a>

Biz turdagi a'zoni deb e'lon qilsak `private`, unga faqat bitta sinf yoki struktura ichida kirish mumkin. Misol uchun,

```
class Student {

  // private property
  private var name = "Tim Cook"

  // private method    
  private func display() {
    print("Hello from Student class")
  }
}

// create object of Student class
var student1 = Student()
    
// access name property
print("Name:", student1.name)

// access display() method 
student1.display()
```

Yuqoridagi misolda biz `Student`xususiyat bilan nomlangan sinf yaratdiknomiva usul `display()`. Bayonotlarga e'tibor bering,

```
// access name property
print("Name:", student1.name)

// access display() method
student1.print();
```

berinomiva `display()`sifatida belgilangan `private`, biz tashqarida ularga kirish imkoniga ega emasmiz `Student`. Bu erda kod quyidagi xatoni keltirib chiqaradi.

```
error: 'name' is inaccessible due to 'private' protection level
error: 'display' is inaccessible due to 'private' protection level
```

***

### faylga kirishni boshqarish <a href="#file-private" id="file-private"></a>

Biz turdagi a'zoni deb e'lon qilsak `fileprivate`, unga faqat belgilangan manba fayl ichida kirish mumkin. Misol uchun,

```
class Student {

  // fileprivate property
  fileprivate var name = "Tim Cook"

  // fileprivate method    
  fileprivate func display() {
    print("Hello from Student class")
  }
}

// create object of Student class
var student1 = Student()
    
// access name property
print("Name:", student1.name)

// access display method 
student1.display()
```

**Chiqish**

```
Nomi: Tim Kuk
Talabalar sinfidan salom
```

Yuqoridagi misolda biz `fileprivate`ma'lumotlar a'zolarini yaratdiknomiva sinf `display()`ichida .`Student`

dan berinomiva `display()`sifatida belgilangan `fileprivate`bo'lsa, bu ma'lumotlar a'zolariga u belgilangan manba faylning istalgan joyidan kirish mumkin.

**Eslatma** : Agar biz boshqa Swift faylini yaratsak va `fileprivate`ma'lumotlar a'zolariga kirishga harakat qilsak, xatoga duch kelamiz.

***

### ichki kirish nazorati <a href="#internal" id="internal"></a>

Tur yoki turdagi a'zoni deb e'lon qilganimizda `internal`, unga faqat bitta modul ichida kirish mumkin.

Modul - bu turlar (sinflar, protokollar va boshqalar) va resurslar (ma'lumotlar) to'plami. Ular birgalikda ishlash va funksionallikning mantiqiy birligini tashkil qilish uchun qurilgan.

***

#### Misol: ichki bir xil modul ichida

```
class Student {

  // define internal property
  internal var name = "Tim Cook"
}

// create object of Student class
var student1 = Student()
  
// access name property
print("Name:", student1.name)
```

**Chiqish**

```
Nomi: Tim Kuk
```

Yuqoridagi misolda biz `Student`xususiyat bilan nomlangan sinf yaratdiknomi. berinomiya'ni `internal`, biz unga sinfdan tashqarida kirishimiz mumkin, chunki ular bir modulda.

Agar biz `internal`bitta modul ichida foydalansak, u xuddi `public`kirish modifikatori kabi ishlaydi.

**Eslatma** :

* Agar biz boshqa modul yaratsak va `internal`ma'lumotlar a'zolariga kirishga harakat qilsak, xatoga duch kelamiz.
* Modul yaratishni o'rganish uchun [Swift](https://www.raywenderlich.com/17753301-creating-a-framework-for-ios) moduliga tashrif buyuring .
