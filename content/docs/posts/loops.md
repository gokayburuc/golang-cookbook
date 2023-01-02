---
title: "14. Döngüler (Loops)"
weight: 14
# bookFlatSection: false
# bookToc: true
# bookHidden: false
# bookCollapseSection: false
# bookComments: false
# bookSearchExclude: false
---

# Döngüler (Loops)

GO programlama dilinde tek bir döngü mevcuttur; bu da `for` döngüsüdür.  Bu döngü C, C++, Java, C# dillerindeki ile benzerlik göstermektedir. #java #cplusplus #csharp #c 

### Yazım Biçimi (Syntax)

Yazım şekli de aşağıdaki gibidir. 

```go
for initialization; condition; post{
       // statements....
}
```


1. Başlatma ifadesi (intialization) : Başlatma ifadesi isteğe bağlıdır ve for döngüsü başlamadan önce yürütülür. Başlatma ifadesi her zaman değişken bildirimleri, artış veya atama ifadeleri veya işlev çağrıları gibi basit bir ifadededir.
2. Şart (condition) : Koşul ifadesi, döngünün her yinelemesinin başlangıcında değerlendirilen bir boole ifadesi içerir. Koşullu ifadenin değeri doğruysa, döngü yürütülür.
3. Post : Post ifadesi, for döngüsünün gövdesinden sonra yürütülür. Post deyiminden sonra, koşul deyiminin değeri yanlış ise koşul deyimi tekrar değerlendirilir, ardından döngü sona erer.
4. Statement (Durum) : Eğer koşul sağlanırsa gövdede gerçekleşecek işlemleri belirtir.


```go
package main

import "fmt"

// Main function
func main() {
	
	// for döngüsü
	// Bu döngü i = 0 değeri gerçekleştiğinde başlar
	//  i<4 şartı gerçekleşip true anahtarı ortaya çıkana kadar devam eder 
	// post ifadesi i++ 'dir. Bu da döngü boyunca i değerini 1 arttır anlamına gelir.
	for i := 0; i < 4; i++{
	fmt.Printf("GOKAYBURUC.DEV\n")
	}
	
}

```

> Yukarıda yazdığımız kod scriptini çalıştırdığımızda işlem gerçekleşinceye kadar 4 defa ekrana "GOKAYBURUC.DEV" yazısını yazıdıracaktır.

### Sonsuz For Döngüsü (Endless For Loop)

for değerini sonsuza dek tekrar edecek şekilde kullanmak için aşağıdaki ifade şeklinde yazılması gerekir. 

```go

for {
	// statement

}
```

Bu ifadede herhangi bir şart sağlanmayacağı için döngüyü çalıştıran anahtar sonsuza dek `true` olarak kalacaktır. Bir önceki örneğimizde i<4 şartı sağlandığında değer `false` döneceği için döngü durmuştu. 

```go
package main 

import "fmt"

func main(){
	
    for{
        fmt.Println("Sonsuza dek yaz!")
    }
}
```

### İken Formatında For Döngüsü ( For Loop as While Loop)

`for` döngüsü sırasında belirtilen şart sağlandığında döngü kesilecek şekilde yazılır. Aşağıda örnekte i değeri 3 değerini geçtiğinde döngü sonlanacaktır.


```go
package main

import "fmt"

func main() {
	i:= 0
	// i degeri 0 olarak tanımlanır
	for i < 3 {
	// i degeri ilk olarak 2 sonra 4 degeri alır 
	// şart sağlandığı için döngü kesilir
	i += 2
	}
fmt.Println(i)
}
```

### For Döngüsünde Basit Aralık (Simple range in for loop)


```go
for i, j:= range rvariable{
   // statement..
}
```

- i ve j, yinelemenin değerlerinin atandığı değişkenlerdir. Yineleme değişkenleri olarak da bilinirler.  
- İkinci değişken, yani j isteğe bağlıdır.  
- Aralık ifadesi, döngü başlamadan önce bir kez değerlendirilir.


```go
package main

import "fmt"

func main() {
	// array
	sehirler := []string{"Bursa", "Edirne", "İstanbul"}
	for i, j := range sehirler {
	fmt.Printf("Sehir : %v , index : %v \n", j, i)
	}
}
```


`string`  ifadeler için de for range ifadeleri kullanılabilir. 

```go
package main

import "fmt"

func main() {
	
	// 
	for i, j:= range "EDİRNE" {
	fmt.Printf("Karakter: %U , index : %d \n", j, i)
	}	
}
```

Çıktı:
```go
Karakter: U+0045 , index : 0 
Karakter: U+0044 , index : 1 
Karakter: U+0130 , index : 2 
Karakter: U+0052 , index : 4 
Karakter: U+004E , index : 5 
Karakter: U+0045 , index : 6 
```


Aynı ifade içerisinde 

### Maps (Haritalar) için For Döngüsü 

Map ifadeleri bir ader anahtar ve bu anahtara bağlı bir adet değerden oluşur.  Bu ifadeler için bir for-range döngüsü yapıldığında yazım aşağıdaki şekilde olacaktır.

FOR-RANGE MAP SYNTAX  :
```go
for key, value := range map { 
     // Statement.. 
}
```


Aşağıda bir map ifadesi içinde plaka şehir eşleştirmesi yapılmıştır. Bu değerleri sıralamaya başlıyoruz.

```go
package main

import "fmt"

func main() {

//map tanımlanıyor
plaka := map[int]string{22: "Edirne", 39: "Kırklareli", 59: "Tekirdağ", 17: "Çanakkale"}

//
for i, j := range plaka {
	fmt.Printf("Plaka:%v İl:%v \n", i, j)
	}
}
```

Bu ifadenin çıktısı şu şekilde olacaktır.

```go
Plaka:22 İl:Edirne 
Plaka:39 İl:Kırklareli 
Plaka:59 İl:Tekirdağ 
Plaka:17 İl:Çanakkale 
```

### Kanal (Channel) için For-Range Döngüsü 

Kanal ifadelerinde de `for` döngüsü kullanılabilir. Burada kanal belirli şart sağlanıp kapanana kadar döngü yinelenecektir. 

```go
for item := range Chnl { 
     // statements..
}
```

Şimdi bir kanal örneği üzerinden konuya bakalım. 

```go 
package main

import "fmt"

// Main function
func main() {

    // using channel
    chnl := make(chan int)

    //goroutines ve channel ifadeleri ile birlikte bir isimsiz fonksiyon
    go func(){
        chnl <- 100
        chnl <- 1000
        chnl <- 10000
        chnl <- 100000
        close(chnl)
    }()

    //ifadeyi itere edilebilir bir hale getirdik
    for i:= range chnl {
     fmt.Println(i) 
 }

}
```

KAYNAKÇA : 

1. [https://www.geeksforgeeks.org/loops-in-go-language/?ref=gcse](https://www.geeksforgeeks.org/loops-in-go-language/?ref=gcse)
