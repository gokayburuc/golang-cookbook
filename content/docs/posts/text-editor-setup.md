---
title: "2. Metin Editörü Kurulumu"
weight: 2
# bookFlatSection: false
# bookToc: true
# bookHidden: false
# bookCollapseSection: false
# bookComments: false
# bookSearchExclude: false
---


# Metin Editörü Kurulumu

Birden çok ortamda geliştirme yapma imkanınız mevcuttur. Hatta hiçbir özel program indirmeden dahi sisteminizde kurulu olan metin editörlerinden geliştirme yapabilirsiniz. Fakat VSCode ve Sublime Text gibi metin editörleri otomatik biçimlendirme, kod hatalarını görüntüleme gibi GO özelliklerini desteklediği için kodlama sürenizi muazzam ölçüde düşürecektir.

## VSCODE

![vscode](/img/vscode.png)

**WEBSITE:**
[https://code.visualstudio.com/](https://code.visualstudio.com/)

GO programlama diliyle ilgili en fazla desteğe sahip editördür. Hatta desteklediği özellikler sayesinde en kapsamlı editördür de denilebilir.

{{<hint info>}}
`gopls` : Format, hata ve diğer özelliklerin denetlendiği kütüphanedir.
{{</hint>}}

1. Programı indirip kurulum tamamlıyoruz.
2. `CTRL+SHIFT+P` ile `Extensions: install extension` yazarak eklenecek paketlerin olduğu ekranı açın.
3. Ekrandaki arama çubuğuna `GO` yazın ve  enter tuşuna basın. 
4. Açılan ekranda install butonunu bulun ve yükleyin.

## SUBLIME TEXT

![sublime-text](/img/sublime-text.png)

**Website:**
[https://www.sublimetext.com/](https://www.sublimetext.com/)

1. Sublime Text i resmi sitesinden indiriyoruz ve kurulumu sağlıyoruz.
2. Sublime Text'i açıp `CTRL + SHIFT + P` tuş kombinasyonu ile hızlı erişim paletini açıyoruz.
3. açılan kısma `install package control`  yazıp `enter` tuşuna basarak Package Control kurulumu yapıyoruz.
4. [https://packagecontrol.io/search/go%20](https://packagecontrol.io/search/go%20) adresinden gerekli go paketlerini buluyoruz.
5. Buradan `LSP` isimli paketi buluyoruz ve ayarlarını GO için düzenliyoruz.
6. Sublime Text ekranını açıp `CTRL + SHIFT + P` 'e basın ve `install package` yazın. Açılan ekranda bulduğunuz GO paketlerinin isimlerini yazıp kurulumu tamamlayın.

## NOTEPAD++

Windows kullanıcıları için geliştirme yapabilecekleri bir başka editör de Notepad++ editörüdür.

