---
title: "5. Değişkenler (Variables)"
weight: 5
# bookFlatSection: false
# bookToc: true
# bookHidden: false
# bookCollapseSection: false
# bookComments: false
# bookSearchExclude: false
---



# Değişkenler (Variables)

Değişken ( **Variable** ) , bir değeri tutmak için bir depolama konumudur. İzin verilen değerler kümesi, değişkenin türüne göre belirlenir.

```go 
// string degisken turu
var isim string = "Gokay"
```

Yani elimizde `isim` diye bir değişken olduğunu var sayalım. İzin verilen deger olarak degisken türü dikkate alındığında `string`  type bir ifade olduğunu düşünürsek bu ifade yalnızca string veri tipinde tutulabilir. Yani yazı olarak saklanabilir. 

{{<hint danger>}}
>`string` olarak saklanan bir değişkene, bir tam sayı `integer`  veya ondalıklı sayı `float` değer verirsek, veyahut mantıksal `bool` bir ifade verirsek sistemden hata alırız.  `isim` değişkenimiz yalnızca string olarak sistemde saklanabilir.
{{</hint>}}

Değişken ifadeleri adı üzerinde değişebilen ifadelerdir. Sabitler `const` ifadelerinden farkları **tanımlandıktan sonra sistemdeki değerlerinin değişebilmesinden ileri gelmektedir.**

## Değişkenlerin özellikleri 

- İşleme tabi tutulabilirler 
- Üzerlerine defalarca değer ataması yapılabilir. 
- Sistemden çağrıldıkları zaman son atanan değeri döndürürler.

## Değişken Tanımlama 

Peki nasıl değişken tanımlarız. Tanımlama şekilleri nelerdir? 

İlk tanımlama şeklimiz detaylı tanımlama şeklidir.

```go
var country string = "Turkey"
```

Bu tanımlama ifadesini biraz daha kısaltabiliriz. 

>GO programlama dili otomatik olarak değişken türü tanıma ve atama özelliğine sahiptir.

```go
var country = "Turkey"
```

Eğer ifademizi bir fonksiyon içinde tanımlıyorsak alternatif bir kısa yazım daha mevcuttur. Bu ifadede `:=`  karakterleri ile eşitlik yazımı mevcuttur. 

> Bu tanımlama yanlızca  fonksiyon scope'u içinde tanımlamalarda mümkündür.

```go

func main(){
	country := "Turkey"
}
```

## Birden Çok Değişkeni Tek Satırda Tanımlama 

Eğer elimizde birden çok değişken varsa ve bunları tek satır içerisinde tanımlamak istiyorsak  aşağıdaki yazım türünde tanımlarız.

```go 
var b, c int = 1, 2
```

Burada b ve c olmak üzere, iki adet `int` ifadesini tek bir satır içerisinde virgül ile ayırarak tanımladık. 

Aynı şekilde değişken tipini yazmadan da değişkene değer  atama işlemi yapabiliyoruz. GO otomatik olarak değişken türünü tanımlayıp atamasını yapmaktadır.

```go
var en, boy = 100, 50
```


Peki ifadelerden biri string diğeri bool olsaydı nasıl tanımlayacaktık? 

```go 
var para bool, miktar float64 = true, 5500.25  
```

aynı ifadeyi bir de kısaltılmış olarak yazabiliriz.

```go
var para, miktar = true, 5500.25
```

Biraz daha karmaşık bir şekilde tanımlama işlemi yapalım. 

```go 
var isim ,soyisim , matematik , edebiyat , gecmeDurum  = "Ahmet","YILMAZ", 75, 83, true
```


## Uygulama Örneği 

Aşağıda bir uygulamamız bulunuyor. Bu uygulamada birden çok değişken tanımlıyoruz ve `fmt` yardımı ile sonuçları ekrana yazdırıyoruz. 

```go
package main

import "fmt"

func main(){

	sehir := "Edirne"
	var kilo float64 = 75.3
	var boy float64 = 182.3
	yas := 35

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
