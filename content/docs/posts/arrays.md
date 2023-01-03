---
title: "8. Diziler - Arrays"
weight: 8
# bookFlatSection: false
# bookToc: true
# bookHidden: false
# bookCollapseSection: false
# bookComments: false
# bookSearchExclude: false
---

# Diziler (Arrays)

Diziler, aynı veri türüne ait olan elemanlar kümesidir.  Yani `string` veri türündeki ifadelerin bir araya gelmesinden oluşan bir küme dizi `string` türünde bir dizidir. Aynı şekilde `int` , `float` , `bool` ifadeleri de birer dizi oluşturabilir.

{{<hint warning>}}
**DİKKAT:** GO programlama dili farklı veri tiplerinin bir arada olduğu dizilere izin vermez.
{{</hint>}}

## Dizilerin Tanımlanması

Bir dizi aşağıdaki format ile tanımlanır.

```go
var dizi = [3]string{}
```

Burada 3 elemanı olan ve `string` türünde veriler barındıracak bir dizi tanımladınız. Ama dizimizin henüz hiç elemanı yok.

Peki dizi elemanları nasıl yazılır?

```go
    dizi[0] = "Edirne" // dizinin ilk degeri
    dizi[1] = "Bursa" // dizinin ikinci değeri
    dizi[2] = "Manisa" // dizinin üçüncü değeri
```

{{<hint info>}}
**HATIRLATMA:**
Programlama dillerinde, dizi elemanları sıfırdan başlayarak index değeri alırlar. Yani `a` dizisinin ilk değeri `a[0]` değeridir.
{{</hint>}}


Şimdi yazdığımız kodu derleyerek çalıştıralım. 

```go
package main 
import (
    "fmt"
)

func main(){
    var dizi = [3]string{}

    dizi[0] = "Edirne"
    dizi[1] = "Bursa"
    dizi[2] = "Manisa"

    //dizinin goruntulenmesi
    fmt.Println(dizi)

    // dizinin birinci degeri 
    fmt.Println(dizi[1])
}
```

`go run dosyaAdi` ile daha önce kaydettiğiniz kodu çalıştırdığınızda ekrandaki çıktıyı alacaksınız. 

```bash
[Edirne Bursa Manisa]
Bursa
```

Görüldüğü üzere dizinin kendisi ilk satırda ve dizinin 1 indeksli elemanı da ikinci satırda görüntülendi.

## Out of Bounds (Sınırlama Dışında Değer) Hatası 

Peki 3 elemanla sınırlanmış bir diziye bir tane dördüncü eleman atarsak ne olurdu? Kodumuzda dizi değerlerini yazdığımız kısma aşağıdaki kodu ilave edip tekrar çalıştıralım.

```go
dizi[3] = "Amasya"
```

Kodumuzun son hali:

```go
package main 
import (
    "fmt"
)

func main(){
    var dizi = [3]string{}

    dizi[0] = "Edirne"
    dizi[1] = "Bursa"
    dizi[2] = "Manisa"
    dizi[3] = "Amasya" // yeni eklediğimiz değer 

    //dizinin goruntulenmesi
    fmt.Println(dizi)

    // dizinin birinci degeri 
    fmt.Println(dizi[1])
}
```

Kodu çalıştırdığımızda aşağıdaki hatayı alacaksınız. 

```bash
invalid argument: index 3 out of bounds [0:3]
```

Bu şu demektir:

{{<hint danger>}}
Siz dize tanımlarken 3 değerden oluşan bir dize tanımlayacağınızı belirttiniz fakat şimdi dördüncü elemanı tanımlıyorsunuz. Ya bu kuralı belirtmeyin açık uçlu bir dize tanımlayın ya da sayıyı arttırın.
{{</hint>}}


## Kısa Biçimde Dizi Tanımlama


Peki biz her seferinde `dizi[1], dizi[2] ...` şeklinde tek tek değerleri mi atayacağız? Bunun kısa yolu yok mu? Bu soruyu sorduğunuzu bildiğim için doğrudan diyorum ki "evet var". 
Buyrun:

```go

package main 

import (  
    "fmt"
)

func main() {  
   dizi := [3]int{12, 78, 50} // short hand declaration - kısa şekilde tanımlama
    fmt.Println(dizi)
}


```

Kodumuzu çalıştırdığımızda aynı şekilde kod ekranında 3 değerden oluşan bir dizi görüntüleyeceksiniz.

## Sınırlama Olmaksızın Dizi Tanımlama 

Şuana kadar kaç adet değer gireceğimizi sisteme sürekli belirttik ama "Bu değer girme faslı olmadan ben ne kadar yazarsam yazayım GO 'da bunu kabul etsin kardeşim. 1 milyonluk diziyi de ona belirtmek zorunda mıyım?" dediğinizi duyar gibiyim. Bunu da çözmüşler.

`[...]int{}` şeklinde yapılan tanımlamalar, derleyici(compiler) tarafından kendiliğinden sayılır ve işleme bu şekilde devam edilir.

```go
package main

import (  
    "fmt"
)

func main() {  
    dizi := [...]int{12, 78, 50} // ben değil de derleyici sayıp tanımlasın beni yormasın
    fmt.Println(dizi)
}

```


## Dizi Uzunluğunun Ekranda Görüntülenmesi 

Yazdığımız dizinin uzunluğunu ekranda görüntülemek istediğimiz zaman kullanacağımız fonksiyon `len()` fonksiyonudur.

```go
package main

import "fmt"

func main() {  
    dizi := [...]float64{67.7, 89.8, 21, 78}
    fmt.Println("Dizi Uzunluğu : ",len(dizi))

}
```

Yukarıdaki örnek çalıştırıldığında, dizi uzunluğu 4 olarak ekrana yazdırılacaktır.


## Çok Boyutlu Diziler - MultiDimensional Arrays 

Peki bizim diziler hep tek şekilde mi olacak hiç dizi değerleri içerisinde birden çok dizi olan matrisleri kullanamayacak mıyız? Bu soruya da yanıt verelim.



```go
diziAdı := [dimension1][dimension2][dimension3][dimension...]string
```

Bir çok boyutlu dizi tanımlarken boyut miktarı kadar `[]` ifadesi ve sonrasında `string`, `int`,`float`, `bool` gibi veri tipleri bildirilerek tanımlama yapılır.

```go
	hayvanlar := [3][2]string{
		{"aslan", "kaplan"},
		{"kedi", "köpek"},
		{"güvercin", "kartal"}, // sondaki virgül gereklidir 
	}
```

3 satır ve 2 sütundan oluşan bir dize tanımladık. Dizimiz 2 boyutludur. Eğer başka bir köşeli parantez ve değer daha eklersek dizimiz  3 boyutlu bir dizi olacaktır.

{{<hint danger>}}
**DİKKAT:**
`{"güvercin", "kartal"},` ifadesinde yer alan sondaki virgül `,`  gereklidir.Alt alta satır yazarken en son satır virgül ile bitirilir. GO yazım kuralları gereğince dizi tanımlaması sırasında birden çok satır kullanılırsa virgül ile bitirilmelidir.
{{</hint>}}


Şimdi dizimizi ekrana yazdıralım:

```go
package main 
import "fmt" 

func main(){ 
    
    hayvanlar := [3][2]string{
		{"aslan", "kaplan"},
		{"kedi", "köpek"},
		{"güvercin", "kartal"}, // sondaki virgül gereklidir 
	}
    // dizi 
    fmt.Println(hayvanlar)

    // dizinin ikinci elemanının birinci degeri
    fmt.Println(hayvanlar[2][1])
}
```

Ekran çıktımız: 

```go
[[aslan kaplan] [kedi köpek] [güvercin kartal]]
kartal
```

şeklinde olacaktır.