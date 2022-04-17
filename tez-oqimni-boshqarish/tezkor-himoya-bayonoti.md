# Tezkor himoya bayonoti

Ushbu o'quv qo'llanmada biz dasturingizning bajarilishini nazorat qilish uchun guard iborasidan foydalanishni o'rganamiz.

Swift-da biz `guard`ma'lum shartlar bajarilmasa, dastur boshqaruvini doiradan tashqariga o'tkazish uchun bayonotdan foydalanamiz.

Bayonot bitta asosiy farq bilan bayonotga `guard`o'xshaydi . `if`Bayonot `if`ma'lum bir shart bajarilganda ishlaydi. Biroq, `guard`bayonot ma'lum bir shart bajarilmasa ishlaydi.

***

### Qo'riqchi bayonoti sintaksisi

Bayonotning sintaksisi `guard`:

```
guard expression else {
  // statements
  // control statement: return, break, continue or throw.
}
```

Bu erda yoki yoki `expression`qaytaradi . Agar ifoda ga baholansa`truefalse`

* `true`- kod bloki ichidagi `guard`operatorlar bajarilmaydi
* `false`- kod bloki ichidagi `guard`operatorlar bajariladi

**Eslatma:** Qo'riqlash doirasidan chiqish uchun , `return`yoki dan foydalanishimiz kerak .`breakcontinuethrow`

***

### Swift guard bayonotining ishlashi <a href="#working" id="working"></a>

![Swift-da himoya bayonoti qanday ishlaydi](https://cdn.programiz.com/cdn/farfuture/grxAHo-K0JpCJsssz2p6hqar4smYhQSfGYsQvRhkNOQ/mtime:1620126821/sites/tutorial2program/files/swift-guard-statement.png)Swift-da qo'riqchi bayonotining ishlashi

***

#### Misol: Swift Guard bayonoti

```
var i = 2

while (i <= 10) {
    
  // guard condition to check the even number 
  guard i % 2 == 0 else {
   
     i = i + 1
    continue
  }

  print(i)
  i = i + 1
} 
```

**Chiqish**

```
2
4
6
8
10
```

Yuqoridagi misolda biz `guard`raqamning juft yoki toq ekanligini tekshirish uchun bayonotdan foydalanganmiz. Chiziqqa e'tibor bering,

```
guard i % 2 == 0 else {...}
```

Mana, agar `i`bo'lsa

* **toq** - , `i % 2== 0`ga baholaydi `false`. Va ichidagi kod `guard`bajariladi.
* **juft** - , `i % 2 == 0`ga baholaydi `true`. Va ichidagi kod `guard`o'tkazib yuboriladi.

Shunday qilib, biz faqat juft raqamlarni mahsulot sifatida olamiz.

Boshqaruvni siklning keyingi iteratsiyasiga o'tkazish uchun ichidagi [davom](https://www.programiz.com/swift-programming/continue-statement) iborasidan foydalandik .`guard`

**Eslatma**`continue` : , va hokazo kabi boshqaruv iboralaridan foydalanish `break`majburiydir. Aks holda, biz xatoga duch kelamiz: `'guard' body must not fall through, consider using a 'continue' or 'return' to exit the scope`.

***

### guard Funktsiya ichidagi bayonot <a href="#function" id="function"></a>

Bayonot `guard`odatda funktsiyalar bilan ishlatiladi. Funksiya ma'lum bir vazifani bajaradigan kod blokidir. Qo'shimcha ma'lumot olish uchun [Swift Function](https://www.programiz.com/swift-programming/functions) ga tashrif buyuring .

Keling `guard`, funksiyalar bilan ifodani qanday ishlatishimiz mumkinligini ko'rib chiqaylik.

```
// create a function
func checkOddEven() {
  var number = 23

  // use of guard statement
  guard number % 2 == 0 else {
    
    print("Odd Number")
    return
  }

  print("Even Number")
}

// function call
checkOddEven()
```

**Chiqish**

```
Toq raqam
```

Yuqoridagi misolda biz nomli funksiya yaratdik `checkOddEven()`. `guard`Funktsiya ichidagi bayonotdan foydalanishga e'tibor bering .

```
guard number % 2 == 0 else {
    
  print("Odd Number")
  return
}
```

Bu erda `guard`bayonot raqamning juft yoki toq ekanligini tekshiradi. G'alati bo'lgani `number`uchun shart `number % 2 == 0`qaytariladi `false`.

Demak, bayonot ichidagi kod `guard`bajariladi.

Keling, ning qiymatini `number`juft songa o'zgartiramiz, deylik `24`.

```
// create a function
func checkOddEven() {
  var number = 24

  // use of guard statement
  guard number % 2 == 0 else {
    
    print("Odd Number")
    return
  }

  print("Even Number")
}

// function call
checkOddEven()
```

**Chiqish**

```
Juft son
```

Bu yerda `number`juft bo'lgani uchun shart `number % 2 == 0`ga baholanadi `true`.

Shunday qilib, `guard`bayonot ichidagi kod o'tkazib yuboriladi va funktsiya ichidagi boshqa kod bajariladi. Shunday qilib, biz chiqish `Even Number`sifatida olamiz

***

### bir nechta shartlar bilan qo'riqlash <a href="#multiple-conditions" id="multiple-conditions"></a>

`guard`Shuningdek, bayonotlar **vergul (,)** bilan ajratilgan bir nechta shartlarni zanjirlashi mumkin:

```
func checkJobEligibility() {
    
  var age = 33

  guard age >= 18, age <= 40 else {
    print("Not Eligible for Job")
    return
  }

  print("You are eligible for this job")

}

checkJobEligibility()
```

**Chiqish**

```
Siz bu ishga munosibsiz
```

Yuqoridagi misolda `guard`gapda vergul bilan ajratilgan ikkita shart mavjud.

Bu erda ikkita shart o'rtasida [Mantiqiy VA](https://www.programiz.com/swift-programming/operators#logical) munosabati bo'ladi. Ya'ni, `guard`shart `true`faqat ikkala shart ham bo'lsa `true`.

***

### guard-let bayonoti <a href="#guard-let" id="guard-let"></a>

[Swift Optionals](https://www.programiz.com/swift-programming/optionals) bilan ishlashda `guard`bayonot bayonot sifatida ishlatiladi `guard-let`. Misol uchun,

```
func checkAge() {
	
  var age: Int? = 22

  guard let myAge = age else {
    print("Age is undefined")
    return
  }

  print("My age is \(myAge)")
}

checkAge()
```

**Chiqish**

```
Mening yoshim 22 da
```

Yuqoridagi misolda biz nomli ixtiyoriy o'zgaruvchini yaratdik `age`. Bu erda biz qiymat bor yoki `guard-let`yo'qligini tekshirish uchun bayonotdan foydalanamiz.`age`

Ba'zi qiymatlarni o'z ichiga olganligi sababli `age`, blok ichidagi kod `guard-let`bajarilmaydi. `guard`Bu bo'lish shartiga o'xshash ishlaydi `true`.

***

### guard Vs if bayonoti <a href="#guard-vs-if" id="guard-vs-if"></a>

Bayonot `guard`bayonotga muqobil sifatida kiritiladi `if`. Misol uchun,

Biror kishining ovoz berish huquqiga ega yoki yo'qligini tekshirmoqchi bo'lsak, `if`bayonotni quyidagicha ishlatishimiz mumkin:

```
func voteEligibility() {
    
  var age = 42

  if age >= 18 {
  print("Eligible to vote")
  }
  else {
  print("Not eligible to vote")
  }

}

voteEligibility()
```

**Chiqish**

```
Ovoz berish huquqiga ega
```

`guard`Xuddi shu dastur quyidagi bayonot yordamida yozilishi mumkin :

```
func voteEligibility() {
    
  var age = 42

  guard age >= 18 else {
  print("Not Eligible to vote")
  return
  }

  print("Eligible to vote")
}

voteEligibility()
```

**Chiqish**

```
Ovoz berish huquqiga ega
```

Ko'rib turganingizdek, `guard`bayonot yordamida shart ga baholanishi bilanoq funktsiyadan chiqishimiz mumkin `false`.
