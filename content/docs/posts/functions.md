---
title: "11. Fonksiyonlar (Functions)"
weight: 11
# bookFlatSection: false
# bookToc: true
# bookHidden: false
# bookCollapseSection: false
# bookComments: false
# bookSearchExclude: false
---


# Fonksiyonlar (Functions)

Bir fonksiyon (işlev), sıfır veya daha fazla giriş parametresinin sıfır veya daha fazla çıkış parametresine eşlenmesidir.


{{<hint warning>}}
**HATIRLATMA:** 
Giriş parametreleri fonksiyonlarda **argüman** olarak adlandırılırlar. Konu içerisinde geçen argüman ifadeleri fonksiyonlara giriş yapılan değerler anlamına gelir.
{{</hint>}}


## Fonksiyon Kullanmanın Avantajları

Fonksiyonların (İşlevlerin) kullanmanın avantajları şunlardır:

- Kod tekrarını azaltma
- Karmaşık problemleri daha basit parçalara ayırma
- Kodun netliğini artırma
- Kodun yeniden kullanımı
- Bilgi gizleme

## Fonksiyonların Uygulama Alanları 

Fonksiyonlar GO programlama dilini daha esnek hale getirirler. 

* Fonksiyonlar değişkenlere atanabilirler
* Fonksiyonlara argüman olarak iletilebilir
* Fonksiyonlardan döndürülebilir 

## Fonksiyonların Yapısı 

Fonksiyonlar, belirli kısımlardan oluşur. 

```go
func FonksiyonAdi(parametreler) döndürülecekVeri Tipi {
    //gövde - body 
}
``` 

Yukarıda bir fonksiyonun temel yapısını görüyorsunuz. 

1. GO dilinde bir fonksiyon yazarken önce `func` ifadesi yazılır.
2. `func` ifadesi sonrasında fonksiyonun adı yazılır. Bu yazım sırasında sayı ve boşluk ifadeleri kullanılmaz.
3. Eğer kullanılacaksa fonksiyona giriş yapılacak argüman (`argument`) ifadeleri `()` içine yazılır.
4. Döndürülecek veri tipi `return` ifadesi sonrasında fonksiyondan çıkış yapacak değeri ifade eder. Bu değerin veri tipi `()` sonrasında yazılır.
5. `{}` süslü parantez ile fonksiyon gövdesi `body` ifadesi oluşturulur. Fonksiyonun yapacağı işlemler bu parantez içinde kalan bölgeye yazılır.




### func 
Go'daki işlevler `func` anahtar sözcüğüyle oluşturulur. 

```go
// Fonksiyon Gövdesi - function body
func SayHi(name string) string {
	// islemler - transactions 
}
```

### return 
İşlevlerden değer döndürmek için `return` anahtar sözcüğünü kullanırız. Return ifadesinde döndürülecek verinin türü `()` ifadesi sonrasında belirtilir. `string` , `int`, `float` gibi ifadelerle belirtilir.

```go 

func Merhaba(isim string) string {
	fmt.Println("Merhaba ", isim)

    // cumle isimli degisken
	cumle := "Merhaba " + isim + " hoşgeldin!"
	
    // degiskenin döndürülmesi
    return cumle
}

```

### Fonksiyon Gövdesi - Function Body
Fonksiyonun gövdesi, fonksiyon çağrıldığında yürütülen ifadelerden oluşur. Gövde, bir **çift kıvrık parantez** `{}` ile sınırlandırılmıştır. 

```go
func Merhaba(isim string) string {
    // 
}

```
 
### Fonksiyonların Çağırılması - Function Calling 

{{<hint info>}}
Bir fonksiyonu çağırmak için adını yazar ve ardından yuvarlak parantezler () koyarız. 
{{</hint>}}

Bir fonksiyon **parametre** alabilir veya almayabilir.

## main Fonksiyonu 

`main` isimli fonksiyon go programlama dilinin modül - paket mimarisinin temel taşıdır ve başlatıcı fonksiyon olma özelliği taşır. Her go projesinde varsayılan olarak yer alan bir fonksiyondur.

{{<hint warning>}}
GO programlama dilinde biz yazmasak dahil her başlatılan projede bir `main` paketi ve `main` fonksiyonu mevcuttur.
{{</hint>}}


```go 
package main 

func main(){
    // tüm islemler main isimli pakette ve main isimli 
    //fonksiyonun baslattigi olaylar zinciri ile gerçekleşir. 
}

``` 

{{<hint info>}}
GO programlama dilinde bir paket içinde gerçekleşen tüm işlemler main isimli paket altında ve main fonksiyonun başlattığı ve yürüttüğü işlemler ile gerçekleşir.
{{</hint>}}



## Fonksiyon Örneği

```go
package main

import "fmt"

func main() {
    // fonksiyon cagirma -  function call
	x := SayHi("Gokay")
	fmt.Println("Return : ", x)
}

// Fonksiyon 
func SayHi(name string) string {
	fmt.Println("Hello ", name)
	sentence := "Hello " + name + " welcome!"
	return sentence
}


```


## Basit Fonksiyon Yazımı Örneği 

Aşağıda toplama işlemi yapan bir fonksiyon yazdık. Bu fonksiyon xotomatik olarak toplama işlemi gerçekleştirir.

```go
package main

import "fmt"

func main() {

    x := 4
    y := 5

    z := topla(x, y)

    fmt.Printf("Çıktı: %d\n", z)
}

func topla(a int, b int) int {

    return a + b
}
```

`topla` isimli fonksiyon tanımlanırken `a` ve `b` isimli argümanlar `int` veri tipinde verilmiştir. Bu sisteme girilecek verilerin `int` formatında olması gerektiğini belirtir. 

`()` dışında kalan `int` ifadesi ise, işlem sonrasında `return` ifadesinin yanında döndürülecek verinin tipinin `int` olacağını belirtmektedir.

Yazdığımız fonksiyon a ve b isimli değişkenkenleri toplayarak onucu ekrana yazdırır. 



