# Swift Singleton

Ushbu qo'llanmada biz misollar yordamida Swift Singleton haqida bilib olamiz.

Swift-da Singleton - bu sinf faqat bitta ob'ektga ega bo'lishini ta'minlaydigan dizayn naqshidir. Bunday sinf singleton sinf deb ataladi.

Singleton sinfini yaratish uchun biz ba'zi qoidalarga amal qilishimiz kerak

**1. Shaxsiy ishga tushirgich yarating**

Initsializator bizga sinf ob'ektini yaratishga imkon beradi. Va sinfning initsializatorini yaratish sinfdan tashqaridan sinf ob'ektini yaratishni cheklaydi.

```
class FileManager {
 
  ... 
  // create a private initializer
  private init() {
  }
}

// Error Code
let obj = FileManager()
```

`FileManager`Bu erda sinfning initsializatori `private`. `FileManager`Shunday qilib, biz sinfdan tashqari ob'ektni yaratmoqchi bo'lganimizda , biz xatoga duch kelamiz.

**2. Statik turdagi Singleton Ob'ektini yarating**

Singleton sinfida biz sinfning yagona statik turdagi obyektini yaratamiz. Ob'ektni statik qilish bizga sinf nomidan foydalanib ob'ektga kirish imkonini beradi.

```
class FileManager {
  
  // static property to create singleton
  static let fileObj = FileManager()
  ... 
}

// access the singleton 
let data = FileManger.fileObj
```

Bu erda biz `fileObj`ob'ektga sinf nomidan foydalanib kiramiz `FileManager`.

***

### Misol: Swift Singleton

```
class FileManager{

 // create a singleton
 static let fileObj = FileManager()

 // create a private initializer
private init() {
  
}

 // method to request file
func checkFileAccess(user: String) {

  // condition to check username
  if user == ("@programiz.com") {  

    print("Access Granted")
  }

  else {
    print(" Access Denied")
  }
}
}

let userName = "@programiz.com"

// access method
let file = FileManager.fileObj

file.checkFileAccess(user: userName)
```

**Chiqish**

```
Kirish berilgan
```

Yuqoridagi misolda biz singleton sinfini yaratdik `FileManager`. Bu singleton sinfi bo'lgani uchun biz initsializatorni `private`yaratdik va nomli `static`ob'ektni yaratdik `fileObj`.

Chiziqqa e'tibor bering,

```
var file = FileManager.fileObj
file.checkFileAccess(user: userName)
```

Bu erda biz ob'ektga `fileObj`sinf nomidan foydalanib kirdik `FileManager`. Keyin usulga kirdik `checkFileAccess()`.

**Eslatma:** Dizayn namunasi butun dunyo bo'ylab dasturchilar tomonidan baham ko'rilgan turli xil kodlash usullarini o'z ichiga olgan kod kutubxonamizga o'xshaydi.

***

Shuni ta'kidlash kerakki, bir nechta stsenariylar (masalan, fayllarni boshqarish, API so'rovlari) mavjud, bu erda singletonlar mantiqiy. Agar siz ulardan foydalanish kerakmi yoki yo'qmi, aniq bo'lmasa, singllardan butunlay foydalanishdan qochishingizni tavsiya qilamiz. Ko'proq bilib oling: [Singletonning nimasi yomon?](https://stackoverflow.com/questions/137975/what-is-so-bad-about-singletons)
