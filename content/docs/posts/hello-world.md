---
title: "4. Hello World Uygulaması "
weight: 4
# bookFlatSection: false
# bookToc: true
# bookHidden: false
# bookCollapseSection: false
# bookComments: false
# bookSearchExclude: false
---


# HELLO WORLD (MERHABA DÜNYA) UYGULAMASI

GO programlama dili ve birçok programlama dilinde kodlamaya başlayanların ilk yaptıkları şey, ekranda "hello world!" yazısının yazdırılmasıdır.

Bu örnekte GO programlama dilinin çalışma mantığını öğreneceksiniz.

```go
package main  
import "fmt"  
func main() {  
   fmt.Println("Hello, World")  
}  
```

Şimdi örneğimizi parçalarına ayırarak incelemeye başlayalım.

## Programın İncelenmesi

### package main

```go
package main
```

Bu ifade paket deklerasyonu (package declaration) ifadesidir.

{{<hint info>}}
GO programlama dilinde paket modül mimarisi mevcuttur.
{{</hint>}}

### import

```go
import "fmt"
```

Bu satırda yer alan `fmt` isimli paketi kullanmak üzere import (ithal etmek, içeri sokmak) ediyoruz. Yani bu paket içerisinde yer alan tüm fonksiyon ve modülleri kullanıma açıyoruz ve bu bilgiyi GO diline bildiriyoruz.

{{<hint info>}}
`fmt` isimli modül, built-in format paketidir.Yani programda kurulum gerektirmeden varolan ve ekrana veri yazdırma işlemleri sırasında metin biçimlendirme işlemlerinin yapılabildiği pakettir.

{{</hint>}}

Derleyici (`compiler`) bizim adımıza  varsayılan (`built-in`) paketlere giderek  `fmt` isimli paketi ve bu pakete bağlı `module` ve `function` ifadelerini kullanılmak üzere hazırda bekletiliyor.

{{<hint info>}}
**COMPILER:**
Derleyici, bir programlama dilinde (kaynak dil `source language`) yazılmış bilgisayar kodunu başka bir dile (hedef dil `target language`) çeviren bir bilgisayar programıdır.
{{</hint>}}

Bizim örneğimizde derleyici GO kaynak dilinde yazılmış kodları binary makine diline çevirip işlemleri gerçekleştirir.

- **Kaynak Dil (source language):** GO
- **Hedef Dil (target language):** 1 ve 0 'lardan oluşan Makine Dili  (Binary)

### func main()

`main` isimli fonksiyon sistem içinde derlenen tüm kodların çalıştırıldığı dahili başlatıcı fonksiyondur.

```go
func main() {
   fmt.Println("Hello, World!")
}
```

{{<hint warning>}}
**UYARI:**
GO projelerinizi derlerken tüm yazdığınız kodlar, `package main` paketi altında ve `func main(){}` de çağrılma sırasına göre derlenir.
{{</hint>}}

## Programın Çalıştırılması

İlk olarak bir klasör linux terminalizden yeni bir klasör oluşturuyoruz.

```bash
mkdir hello-world
```

Şimdi klasörümüzün içine giriyoruz.

```bash
cd hello-world
```

Projemizin bir GO klasörü olduğunu ve modüllerin derleneceğini belirtmek için aşağıdaki komutu yazıyoruz. burada `hello.world` bizim klasörümüzün modül ismidir. `go mod init` ise GO dilinde bu isimde bir modül başlatacılacağını belirtir. GO programı bu klasördeki dosyaları GO kurallarına göre derler.

```bash
go mod init hello.world
```

{{<hint warning>}}
Klasörünüze baktığınızda `go mod` isimli bir dosya oluştuğunu göreceksiniz. Bu dosya modüle ait bilgileri ve dışarıdan çağrılan paketlerin bilgilerinin yer aldığı dosyadır.
{{</hint>}}

`go.mod` isimli dosyayı incelediğimizde aşağıdaki bilgileri göreceksiniz.

```go
module hello.world
go 1.19
```

- `module hello.world` işlemlerin yapıldığı ve saklanacağı modülün ismini belirtir.
- `go 1.19` ise derleyici olan GO 'nun versiyon bilgisidir.

{{<hint warning>}}
**HATIRLATMA:**
Eğer modülümüze dışarıdan bir paket veya modül çağırılırsa, `go mod` içerisinde çağrılan modüle ait modül bilgileri yer alacaktır.
{{</hint>}}

Bir sonraki basamakta `Hello.go` isimli bir dosya oluşturup içine aşağıdaki kodları yazın ve kaydedin.

```go
package main  
import "fmt"  
func main() {  
   fmt.Println("Hello, World")  
}  
```

İşlem bitişinde yazdığımız kodları terminalden çalıştıralım.

```bash
go run Hello.go
```

Terminal ekranında aşağıdaki çıktıyı göreceksiniz.

```bash
Hello, World!
```

----------------------------



