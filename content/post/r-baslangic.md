---
title: R'a Başlangıç
date: 2020-07-12
hero: "/images/r-brew.jpg"
excerpt: R'la bir şeyler yapmak 
authors:
  - Hugo Authors
Draft: False 

---

R günümüzde bilimsel hesaplama ve grafik çizdirme gibi işlerde en sık kullanılan dillerden biri. Uzun süredir ha başladım ha başlayacağım modundaydım ve bugün başladım. Aslında çok çok uzun süre önce R'ı kullanmıştım. Geometrik morfometri çalışmaları yapıyordum. Elimdeki örnekler ve veriler oldukça problemliydi. Örneklerim kemik olduğu için iki boyutlu değildi ve fotoğraflarda torsiyon sıkıntı yaratıyordu. Bunları çözmeye çalıştığım dönemde R'ın geometrik morfometri paketlerinden faydalanmıştım. O zamanlar R pek bilinmiyordu. Hocama da pek anlatamamıştım R'ı. O yüzden de R'dan ne kadar hoşlansam da çalışmada onu kullanamamıştık.

R'la yeniden bir şeyler yapmak ve tekrar başlamak için kendime çeşitli kaynaklar baktım. R'ı genel olarak öğrenmek için Coursera'da [R Programming](https://www.coursera.org/learn/r-programming/home/welcome) dersine kaydoldum ve kurulum sürecini bu dersi takip ederek yaptım. 

<h4>Kısaca Kurulum Süreci:

Daha önceden bir şeyler kurarken Homebrew paket derleyicisini kullanmaya alışmıştım. R'ı da Homebrew'le kurmayı düşünüyordum. Ama dersteki yönergeyi takip etmeyi tercih ettim. Yani kısaca [https://cran.r-project.org](https://cran.r-project.org) adresinden indirdim ve kurdum. Sonra da RStudio'yu kurdum. 

Kurduktan sonra ufak bir hata aldım. 

```
<During startup - Warning messages:
1: Setting LC_CTYPE failed, using "C" 
2: Setting LC_COLLATE failed, using "C" 
3: Setting LC_TIME failed, using "C" 
4: Setting LC_MESSAGES failed, using "C" 
5: Setting LC_MONETARY failed, using "C" 
[R.app GUI 1.72 (7847) x86_64-apple-darwin17.0]

WARNING: You're using a non-UTF8 locale, therefore only ASCII characters will work.
Please read R for Mac OS X FAQ (see Help) section 9 and adjust your system preferences accordingly.
> 
```

Hatanın karakter setiyle ilgili olduğunu anladım. İki yol vardı önümde: görmezden gelmek ya da sorunu çözmek. 

Sorunu daha iyi anlamak ve çözebilmek için önce Emre'yle konuştum beni Stack Overflow'a yönlendirdi. Yaşadığım sorunun benzerlerini tabi ki [başkaları](https://stackoverflow.com/questions/9689104/installing-r-on-mac-warning-messages-setting-lc-ctype-failed-using-c) da yaşamıştı. Ayrıca aynı sorunu ve çözümünü R'ın kendi sitesinde FAQ kısmında da bulabilirsiniz ( [Internationalization of the R.app](https://cran.r-project.org/bin/macosx/RMacOSX-FAQ.html#Internationalization-of-the-R_002eapp) ). 

Buradaki çözümlerden şunu terminale yazarak denedim: 

```
defaults write org.R-project.R force.LANG en_US.UTF-8
```

Karakter setini ayarladıktan sonra RStudio'dan Coursera'daki talimatları takip etmeye devam ettim. 

### R'ı ikinci kez HomeBrew'le kurdum 

Diğer bilgisayarıma kurarken homebrew'le kurmayı tercih ettim. Bunun içinde terminale r ve RStudio için sırayla şunları yazdım:

```
brew install r 
```

```
brew cask install rstudio
```

brew gibi bir paket yönetim sistemi kullanırken sanki bir arkadaşımdan bir şeyler yapmasını rica eder gibi hissediyorum kendimi. Brew pls install R my dear diyesim de geliyor. 

### R'ın geçmişi


Temel olarak "R nedir?" sorusunun cevabı için, R'ın S dilinin dialekti olduğunu söyleyebiliriz. Peki S nedir? 

S John Chambers ve arkadaşlarının Bell Laboratuvarlarında geliştirdiği, 1976'da kullanılmaya başlanmış bir dildir. 1988'de dil C ile yenilenmiştir. "Statistical Models in S" kitabında Chambers ve (Trevor) Hastie S dilinin istatistik analiz fonksiyonlarını anlatmışlardır. Dilin 4. ve günümüzdeki versiyonu 1998 yılında "Programming with Data" (Yeşil Kitap) ismiyle Chambers tarafından yayınlanmıştır. Günümüzde hala kullanılmaktadır ve 1998 den beri S dilinde çok bir değişiklik olmamıştır. 

S dilinin yaratıcısı Chambers, "Stages in the Evolution of S"'de S dilini kullananların interaktif bir ortama girmeleridir. Dilin tüm detaylarını bilmeden ya da programlamaya hakim olmadan da kullanıcıların S dilini kullanabilmesini istemiştir. R dili için de aynı arka plan geçerlidir. 

R'ın S'in dialekti olduğundan bahsetmiştik. Peki R nasıl gelişti? Yeni Zelanda'da Ross Ihaka ve Robert Gentleman 1991'de R dilini geliştirdi. 1993 yılında ilk kez R'ı herkese açık olarak duyurdular. 1996'da R-help ve R-devel isimli açık epsota listelerini oluşturdular. 1997'de The R Core Group'u yani R'ın kaynak kodlarını kontrol eden çekirdek grubu oluşturdular. 2000 yılında 1.0.0 versiyonu yayınlandı. 2013 yılında ise 3.0.2 versiyonu yayınlandı. 

R'ın temel özellikleri syntaxı S'e çok benziyor, S-PLUS kullanıcılarının çok kolay geçebileceği bir dil. Semantik olarak S'e benzese de aslında biraz daha farklı bir dil. R hemen hemen her platformda ve işletim sisteminde çalışıyor. PlayStation 3'te bile çalışıyor. 

### Örnek Bir Çalışma Konusu

Pandemiyle ilgili haritalar ya da görselleştirmeler yapmak oldukça faydalı alıştırma konuları. Eğer bunlarla ilgileniyorsanız aşağıdaki kaynaklardan faydalanabilirsiniz. 

Pandemi Grafiklerini R'da çizmek için kaynaklar:

1-) https://projects.datacamp.com/projects/870 

2-) https://rcatlord.github.io/GSinR/setup.html

3-) https://www.statsandr.com/blog/how-to-create-a-simple-coronavirus-dashboard-specific-to-your-country-in-r/#how-to-create-your-own-coronavirus-dashboard 

4-) https://www.statsandr.com/blog/top-r-resources-on-covid-19-coronavirus/ 

5-) Veri kaynağı: https://www.ecdc.europa.eu/en/publications-data/download-todays-data-geographic-distribution-covid-19-cases-worldwide 

