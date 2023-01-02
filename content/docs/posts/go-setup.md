---
title: "1. GO Kurulumu"
weight: 1
# bookFlatSection: false
# bookToc: true
# bookHidden: false
# bookCollapseSection: false
# bookComments: false
# bookSearchExclude: false
---

# GO Kurulumu 

Öncelikle resmi siteye giderek kurulum dosyalarını bulup indiriyoruz. 


![official-go](/img/official-go.png)

**WEBSITE**
[https://go.dev/dl/](https://go.dev/dl/)


----------

## Linux 

### Elle Kurulum


1. [https://go.dev/dl/](https://go.dev/dl/) web sitesine gidilir ve ilgili Linux sürümü bulunur.

{{<hint warning>}}
**UYARI:** Eğer sisteminizde daha önceden yüklü bir sürüm varsa bu sürümü silin.
{{</hint>}}

Aşağıdaki kod sistemde `/usr/local/go` adresi içerisinde yer alan sürümü kaldırır ve aynı klasörün içine `go1.19.4.linux-amd64.tar.gz` isimli indirdiğimizi tar dosyasını aynı klasöre açar.

```bash
sudo rm -rf /usr/local/go && tar -C /usr/local -xzf go1.19.4.linux-amd64.tar.gz
```

{{<hint danger>}}
**DİKKAT:**
Asla mevcut sürümü  `/usr/local/go` klasörünü tamamen silip kaldırmadan aynı klasöre **tar** dosyasını açmayın.
{{</hint>}}

2.  PATH ortam değişkenine `/usr/local/go/bin` ekleyin.

Bunu `$HOME/.profile` veya `/etc/profile` dosyanıza aşağıdaki satırı ekleyerek yapabilirsiniz (sistem çapında bir kurulum için):

```bash 
export PATH=$PATH:/usr/local/go/bin
```

{{<hint warning>}}

Not: Bir profil dosyasında yapılan değişiklikler, bilgisayarınızda bir sonraki oturum açışınıza kadar geçerli olmayabilir. Değişiklikleri hemen uygulamak için doğrudan kabuk komutlarını çalıştırın veya bunları  `$HOME/.profile` gibi bir komut kullanarak profilden yürütün.

{{</hint>}}

3. Bir komut istemi açıp aşağıdaki komutu yazarak Go'yu yüklediğinizi doğrulayın.

```bash 
go version
```

4. Komutun yüklü Go sürümünü yazdırdığını onaylayın.`go version` Ekran çıktısı aşağıdakine benzer olmalıdır. 

```bash
go version go1.19.4 linux/amd64
```

### snap Kurulumu


1. İlk olarak snap içerisinde ilgili go sürümünü arayın. 

```bash 
snap search go
```

Çıktı aşağıdakine benzer şekilde olmalıdır.

```bash 
Name                                  Version                      Publisher           Notes    Summary
go                                    1.19.4                       mwhudson            classic  Go programming language compiler, linker, stdlib
```

2. snap üzerinden GO  indir.

```bash
snap install go
```

----------


## Windows 

1. İlgili windows MSI dosyasını indirin.

2. İndirdiğiniz MSI dosyasını açın ve Go'yu yüklemek için talimatları izleyin.
3. Varsayılan olarak yükleyici, Program Dosyalarına Git veya Program Dosyalarına (x86) kuracaktır. Konumu gerektiği gibi değiştirebilirsiniz. 
4. Kurduktan sonra, yükleyici tarafından ortamda yapılan değişikliklerin komut istemine yansıtılması için tüm açık komut istemlerini kapatıp yeniden açmanız gerekir.
5. Go'yu yüklediğinizi doğrulayın.
6. Windows'ta, Başlat menüsüne tıklayın.
7. Menünün arama kutusuna cmd yazın ve ardından Enter tuşuna basın.
8. Görünen Komut İstemi penceresinde aşağıdaki komutu yazın:
```bash
go version
```
9. Komutun yüklü Go sürümünü yazdırdığını onaylayın.

----------

## Mac 

1. İndirdiğiniz paket dosyasını açın ve Go'yu yüklemek için talimatları izleyin.
2. Paket, Go dağıtımını `/usr/local/go` konumuna kurar. Paket `/usr/local/go/bin `dizinini PATH ortam değişkeninize konulmalıdır. 
3. Değişikliğin etkili olması için tüm açık Terminal oturumlarını yeniden başlatmanız gerekebilir.
4. Bir komut istemi açıp aşağıdaki komutu yazarak Go'yu yüklediğinizi doğrulayın:
```bash
go version
```
1. Komutun yüklü Go sürümünü yazdırdığını onaylayın.
