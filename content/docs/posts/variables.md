---
title: "6. Değişkenler - Variables"
weight: 6
# bookFlatSection: false
# bookToc: true
# bookHidden: false
# bookCollapseSection: false
# bookComments: false
# bookSearchExclude: false
---



# Değişkenler (Variables)

Değişken ( **Variable** ) , bir değeri tutmak için bir depolama konumudur. Değişken adı üzerinde atama yapıldıktan sonra işleme dahil edilebilen ve işlemlerle değeri değişebilen hafıza konumlarıdır.

Değişken ifadeleri adı üzerinde değişebilen ifadelerdir. Sabitler `const` ifadelerinden farkları **bir kez tanımlandıktan sonra sistemdeki değerlerinin değişebilmesinden kaynaklanmaktadır.**

```go
// string (metin) degisken turu
var isim string = "Gokay"
```

{{<hint info>}}
Bir değişkende izin verilen değerler kümesi, değişkenin türüne göre belirlenir.
{{</hint>}}

Yani elimizde `isim` diye bir değişken olduğunu var sayalım. İzin verilen deger olarak degisken türü dikkate alındığında `string`  type bir ifade olduğunu düşünürsek isim değişken ifadesi yalnızca string veri tipinde değer tutabilir.

{{<hint danger>}}
>`string` olarak saklanan bir değişkene, bir tam sayı `integer`  veya ondalıklı sayı `float` değer verirsek, veyahut mantıksal `bool` bir ifade verirsek sistemden hata alırız.
{{</hint>}}

## Değişkenlerin Özellikleri

Değişkenlerin özellikleri şunlardır:

- İşleme tabi tutulabilirler
- Üzerlerine defalarca değer ataması yapılabilir.
- Sistemden çağrıldıkları zaman son atanan değeri döndürürler.

## Değişken Tanımlama

Peki nasıl değişken tanımlarız. Tanımlama şekilleri nelerdir?

### Tip Belirterek Tanımlama

İlk tanımlama şeklimiz detaylı tanımlama şeklidir.

```go
var country string = "Turkey"
```

### Tip Belirtmeden Tanımlama

Bu tanımlama ifadesini biraz daha kısaltabiliriz.

>GO programlama dili otomatik olarak değişken türü tanıma ve atama özelliğine sahiptir.

```go
var country = "Turkey"
```

### Fonksiyon Scope'u İçinde Değişken Tanımlama

Eğer ifademizi bir fonksiyon içinde tanımlıyorsak alternatif bir kısa yazım daha mevcuttur. Bu ifadede `:=`  karakterleri ile eşitlik yazımı mevcuttur.

> Bu tanımlama yanlızca  fonksiyon scope'u içinde tanımlamalarda mümkündür.

```go

func main(){
 country := "Turkey"
}
```

## Birden Çok Değişkeni Tek Satırda Tanımlama

Eğer elimizde birden çok değişken varsa ve bunları tek satır içerisinde tanımlamak istiyorsak aşağıdaki yazım türünde faydalanırız.

```go
var b, c int = 1, 2
```

Burada b ve c olmak üzere, iki adet `int` türünde değişken ifadesini tek bir satır içerisinde virgül ile ayırarak tanımladık.

Aynı şekilde değişken tipini yazmadan da değişkene değer atama işlemi yapabiliyoruz. GO otomatik olarak değişken türünü tanımlayıp atamasını yapmaktadır.

```go
var en, boy = 100, 50
```

Peki ifadelerden biri string diğeri bool olsaydı nasıl tanımlayacaktık?

```go
var paraVar bool, miktar float64 = true, 55000.25  
```

aynı ifadeyi bir de kısaltılmış olarak yazabiliriz.

```go
var paraVar, miktar = true, 55000.25
```

Biraz daha uzun bir şekilde tanımlama işlemi yapalım. Burada

```go
var isim ,soyisim , matematik , edebiyat , gecmeDurum , ortalama = "Ahmet","YILMAZ", 74, 83, true, 75.8
```

## Örnek Uygulama

Aşağıda bir uygulamamız bulunuyor. Bu uygulamada birden çok değişken tanımlıyoruz ve `fmt` yardımı ile sonuçları ekrana yazdırıyoruz.

```go
package main

import "fmt"

func main(){

 sehir := "Edirne"
 var kilo float64 = 75.3
 var boy float64 = 182.3
 yas := 30

 var mezuniyet,askerlik bool = true, true 

 fmt.Println(boy,kilo,yas,sehir)

 fmt.Println(mezuniyet, askerlik)
 
 var isim ,soyisim , matematik , edebiyat , gecmeDurum  = "Ahmet","YILMAZ", 75, 83, true
 
 // alternatif kısa gösterim 
 //isim ,soyisim , matematik , edebiyat , gecmeDurum  := "Ahmet","YILMAZ", 75, 83, true

 fmt.Println(isim,soyisim,matematik,edebiyat,gecmeDurum)
}

```

## Kaynakça

1. [https://gobyexample.com/variables](https://gobyexample.com/variables)
2. [https://golangbot.com/variables/](https://golangbot.com/variables/)
3. [https://zetcode.com/golang/variable/](https://zetcode.com/golang/variable/)
4. [https://www.w3schools.com/go/go_variable_multi.php](https://www.w3schools.com/go/go_variable_multi.php)
