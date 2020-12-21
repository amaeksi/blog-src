---
title: "R ve Github"
date: 2020-12-21T08:32:49+03:00
hero: "/images/rvegithub.png"
excerpt: "R'da yeniyiz, yetmez, github'ı da katalım "
authors:
  - Hugo Authors

---

Bu dönem Zeynep Hoca'dan arkeometride veri analizi dersi alıyorum. Derste veri analizi için R ve RStudio kullanıyoruz. Normalde içinde kod geçen çalışmalarımı olabildiğince GitHub'da tutmaya çalışıyorum. Bu ders ve konuyla ilgili alıştırmaları da GitHub'da tutmak istedim. Bunun için de RStudio'yu GitHub'a bağladım.

Adım adım nasıl yaptığımı paylaşacağım:

1-) GitHub'ınız var mı?

[github.com](http://github.com) adresine gidip kendinize bir hesap açmalısınız. Bu kısımın çok  da detayına ihtiyacınız yok. Yapmanız gereken [github.com](http://github.com)'u ziyaret etmek, kaydol tuşuna tıklamak ve önünüze çıkan yönergeleri takip etmek.

2-) R ve RStudio'nuz güncel mi ?

Bilgisayarınızda R ve RStudio yüklü olması gerekiyor. Ya da yüklüyse güncellemeyi unutmayın.

Bilgisayarınızda hangi R sürümü var kontrol etmek için terminali açıp
```
R -  -version
```
yazmanız yeterli. Gelen cevapta hangi sürüm olduğunu göreceksiniz.

R'ın hangi versiyonunun yüklü olduğunu RStudio'dan da kontrol edebilirsiniz. Bunun içinde RStudio'da 
```
R.version.string
```
yazmanız yeterli.

Eğer R ve R Studio bilgisayarınızda yüklü değilse şurada anlattığım gibi kolayca kurabilirsiniz: https://elcineksi.com/post/r-baslangic/

3-) Git'i kurdunuz mu?

Bilgisayarınızda gitin yüklü olması gerekiyor. Bunun için öncelikle olup olmadığına hangi versiyonunun olduğuna bakmanız faydalı:

Terminale bunları yazarak kontrol edebilirsiniz:

```bash
which git
git --version
```

Eğer bilgisayarınızda git yoksa aşağıdakileri yazarak kurabilrisiniz:

```
brew install git
```

Windows için ise şuradaki yöntemleri inceleyebilirsiniz: https://gitforwindows.org

Ubuntu'da ise şu şekilde kurabilirsiniz:

```
sudo apt-get install git
```

4-) Şimdi bir github hesabınız ve bilgisayarınızda da Git var. github hesabınızı kendi bilgisayarınızdan kullanmak için aşağıdakileri yapabilirsiniz:

Önce git'e kendinizi aşağıdaki şekilde tanıtın. Bu işlem için github'daki e-posta adresinizi kullanın.

```
git config --global [user.name](<http://user.name/>) 'Jane Doe'
git config --global user.email 'jane@example.com'
git config --global --list
```

Sonra github hesabınızı bağlayın:

Öncelikle github hesabınıza girin ve menüden yada profil sayfanızdan yeni bir repository (repo) oluşturun. Yeşil "New" tuşu bu işi görüyor. Ben bir myrepo ismini verdiğim repo açtım ve içine de bir README.txt açıp açıklamasını yazdım: "test repository for R"

Eğer iki bilgisayarınız ve tek bir github hesabınız varsa ve her iki bilgisayarınızdan da bu hesaba push edecekseniz, dikkat etmek gereken diğer bir nokta da her iki cihazında güncel olması. Bu ne demek, push ederek github'a gönderdiğimiz gibi pull ederek github'dan güncellemeleri çekebiliyoruz ve her iki cihazından güncel olması önemli demek.

Şimdi bu bilgisayarımda https yöntemini kullanarak, R ile ilgili dosyalarımın olduğu klasöre, github repositorymi çekeceğim. Ancak, bu bilgisayarda github ile hiç işlem yapmadığım için github hesabım yetkilendirilmemiş (authorize olmamış), eğer repom public olmasaydı repoyu ilk çektiğimde bana kullanıcı adı şifre soracak ve bunları az önce kurduğumuz git kendi ayarlarına kaydedecekti.Ancak "myrepo" public olduğu için ilk kez klonlarken bana bunları sormayacak. Ancak push ederken yine soracak.

Çekmek için öncelikle github'da yeni açtığım reponun (myrepo) anasayfasındaki yeşil "Code" düğmesine tıklayıp, oradaki https bağlantısını kopyalıyorum. Kopyaladığım https linkini şöyle çalıştırıyorum:

```
git clone https://...
```

Daha sonra ilgili klasöre gidip baktığınızda github'da myrepo altında bulunan dosyalarınız gelmiş olduğunu göreceksiniz. Bu klasöre bakmak için doğrudan gidip klasörlerini kontrol edebilirsiniz. Ancak bunun yanı sıra terminale şunları yazarak da bu reponun içindekileri kontrol edebilirsiniz:

```
cd myrepo
ls
```
------

**Şimdi son durumu bir gözden geçirelim.**

1-) Github hesabı açtık.

2-) R ve R Studio'yu güncelledik

3-) Bilgisayarımıza Git'i kurduk (Not: Git ve Github farklı şeyler, unutmayalım.)

4-) Git ve github'ı bağladık, github'da ilk repomuzu açtık ve githubdaki repoları bilgisayarımıza çektik

------

Şimdi ise şunu yapacağız. Gelen dosyalardaki değişiklikleri github'daki dosyalara da göndereceğiz. Yani githubdaki master branch'ı localde (yani bilgisayarımızda) yaptığımız değişikliklerle güncel tutma işini nasıl yapacağımızı deneyerek öğrenelim. Normalde terminalden 
```
git push origin master
```
yazmanız bu işe yarıyor. Ancak bu çalışmada daha çok R ve RStudio odaklı olacağız. 

Öncelikle dosyada değişiklik yapalım. Bu ne olabilir. myrepo klasöründe yeni bir klasör açsam ve içine bir dosya koysam bu değişiklik gidecek mi bunu kontrol edebilirim. Ancak boş klasörler push yaptığımda gitmeyecektir. Bundan başka pull diyerek çektiğimiz dosyaların içindeki README.txt dosyasında değişiklik yapıp, bu değişikliği master brancha yollamayı deneyeceğim.

README.txt içinde değişiklik yapmamın bir yolu dosyayı açıp bir metin editöründe içine bir şeyler yazabilirim. Ancak bunu yapmayacağım. Bunun yerine, terminalde yazdıklarımı echo ile dosyanın içine yazdıracağım. Bununla ilgili detaylı bilgiyi Emre'nin şu (https://emre.xyz/unix-girdi-cikti-yonlendirme) yazısından okuyabilirsiniz. Ancak ben sadece nasıl yapıldığını göstereceğim.

```
echo "The first update from mac mini." >> README.md
```

echo ile >>README.md dosyası içine bu cümleyi yazdım. Şimdi bu değişiklikleri kontrol edeceğim. Git değişiklik var mı yok mu bana söyleyecek. Bunun için şunu yazıyorum:
```
git status
```
git bana dosyanın modified olduğunu belirtti. Bundan sonraki adım bu dosyayı github'a göndermek ve master branch altında birleştirmek.

github'a (Yayın evindeki kitap olsun mesela) yaptığımız değişiklikleri kuryeyle gönderdiğimizi düşünelim. Kuryeye sadece değişiklik yaptığımız sayfayı verebiliriz, kuryeye değişiklikle birlikte tüm kitabı verebiliriz vb.. github'a çeşitli detaylarla dosyayı göndermemiz mümkün bunları aşağıdaki kodlarla yapabiliriz: 

```
add -A
```
kurye kardeş bul değişiklikleri al götür, ( okuyucunun görmeyeceği duvara yapıştırılmış kitap yazarken kullanılan post-itler de buna dahil)

```
git add dosya_adi
```
kurye kardeş değişiklikler bunlar, bu sayfaları götür.

```
git add *
```
kuryeci değişikliklerin hepsini götür ama duvardaki post-itler kalsın

Tabi kuryeye taşıdığı yük hakkında bir de irsaliye vereceğiz; aşağıdaki kodla:

```
git commit -m "A commit from my local-mac mini"
```
Kurye artık yola çıkabilir!

```
git push
```
Aa! o da nesi! Şimdi github hesabımda kullandığım kullanıcı adımı ve şifremi gireceğim ve sonra lokal güncellemelerim githuba gidecek.

Peki bu işlemi yaparken her seferinde şifre girmem gerekecek mi? Buradaki yöntemle yaptıysanız teorik olarak gerekmemesi lazım.

Hadi hızlıca bir tekrar yapalım.

1-) Terminali açalım. Dosyaya gidelim.

2-) echo "The second update from mac mini." >> README.md

3-) git add  *

4-) git commit -m "my first update."

5-) git push

------

Sayın yolcularımız, 40 dakika konaklayacağımız Bolu Dağı Varan Tesislerine varmış bulunmaktayız. (Şaka bir yana yeniden açılmış diye duydum. Pandemi sebepli yolculuk yapmıyor olsak da, umarım ki pandemi bittiğinde gidip karla kaplı çamları izlerken domates çorbasını içeceğim.)

------

Buraya kadar bilgisayarımıza git kurduk, bu git'le github'ımızı bağladık. Ancak myrepo dışında da github'a şifresiz dosya push/pull edebilmek istiyorum. Hem de githubla mac minim arasında düzeyli bir ilişki olmasını tercih ediyorum. Bunun için github'a bir anahtar vereceğim. Zili çalmadan eve gelip kargoları alıp götürsün istiyorum.

Sonra da R ve RStudio'ya sıra gelecek.

Bu kapıyı çalmadan gelip gitme olayı için şurada yazan yönergeleri (https://docs.github.com/en/free-pro-team@latest/github/authenticating-to-github/connecting-to-github-with-ssh) takip edeceğiz.

1-) Elimizde hiç githuba verecek anahtar var mı hemen bir kontrol edelim:
```
cat ~/.ssh/id_rsa.pub
```
Sonuçta "No such file or directory" diyorsa anahtarımız yok demek. Hemen çilingire gitmiyoruz. Kendimiz üretebiliyoruz. Nasıl yapıyoruz:
```
ssh-keygen -t rsa
```
yazıyoruz ve evet evet diye diye anahtarı ürettiriyoruz.

sonra anahtar geldi mi hemen kontrol edelim tekrar:
```
cat ~/.ssh/id_rsa.pub
```
bunun sonucunda bize ;
```
ssh-rsa XYZXYZXYZABCABC...........KLMKLM...... PRTPRT....MNOMNO.....ZXYZXYZABCABC...........KLMKLM...... PRTPRT....MNOMNO.....ZXYZXYZABCABC...........KLMKLM...... PRTPRT....MNOMNO.....ZXYZXYZABCABC...........KLMKLM...... PRTPRT....MNOMNO.....
```
gibi bir şey verecek. Bu anahtar işte. Bu ürettiğimiz anahtarı sadece github'la seviyeli bir ilişki için kullanacağız. Hemen https://github.com/settings/keys adresine gideceğiz. SSH key lere bakacağız. Yeşil New SSH Key düğmesine tıklayacağız. Bu anahtarımızı yapıştıracağız. Ve ta taa... Bilgisayarımız ve github hesabımız bağlandı. Artık bize hiçbir işlemde şifre sormayacak.

Peki önceki myrepo'da kullandığımız HTTPS ayarı ne olacak? myrepo (ya da hangi isimle açtıysanız) klasörünüzün içinde terminalden
```
cat .git/config
```
komutunu çalıştırdığınız zaman HTTPS ayarlarını da göreceksiniz. Bunlara manuel müdahale de edebilirsiniz. Ancak biz temiz çalışmayı prensip edineceğimiz için böyle işler yapmayacağız. Ne yapacağız peki?

1-) Aşağıdaki komutu yazıp reponun remote origin adresini sileceğiz:
```
git remote remove origin
```
Bir de şu aşağıdakini yazıp iyice emin olalım:
```
git remote -v
```
2-) myrepo'nun originini sildik. Şimdi yeni originini ekleyeceğiz. Bunun için github'a gidiyoruz, ilgili repoya giriyoruz, yeşil "Code" düğmesine tıklıyoruz, SSH'yi seçiyoruz, oradaki linki kopyalıyoruz.

3-) Geliyoruz terminale, aşağıdaki komutu çalıştırıp yeni origini ekliyoruz:
```
git remote add origin git@github.com:kullanıcıadi/myrepo.git
```
Evet bu dosyanın erişim ayarlarını da düzelttik. Şimdi konumuz olan R ve RStudio'ya dönebiliriz.

RStudio'yu açıyoruz. Şu yolu takip edip git ve github repomuzu klonluyoruz. File > New Project > Version Control > Git.

Açılan pencereye;

reponuzun SSH adresini girin, adını girin ve "devam et"'e tıklayın sonra size bir sorusu olacak, okuyun ve yes diyerek devam edin.

RStudio'da README dosyanızda bir değişiklik yapın. Ben üçüncü satıra "local changes" yazdım. Şimdi bu README dosyasındaki değişikliği github'daki mastera göndermem lazım. Bunu RStudio'dan nasıl yapacağım?

Sağ üstteki kutunun üstünde Environment, History, Connections, Git ve Tutorial diye sekmeler göreceksiniz. Evet buradaki Git sekmesine tıklıyoruz. Sonra orada karşımıza README dosyası çıkacak. README dosyasının staged sütununa check atıyoruz. Sonra Environment, History, Connections, Git ve Tutorial yazan sekmelerin altında "Commit" tuşu gözünüze ilişecek. Buraya yorumumuzu yazıyoruz. Sonra da yukarı yeşil ok, PUSH, ile github'a bu dosyayı gönderiyoruz. Eğer github'dan dosya çekecek olsaydık aşığı mavi oka tıklayıp PULL ile çekecektik.

Lokal repomuzla github repomuzu birbirine denkleştireceğiz. github'a gidip bir repo açıyoruz. Bu reponun SSH adresini (Code yazan yeşil buton-SSH) kopyalıyoruz. Bundan sonra takip edilebilecek iki yol var. Biri terminalde diğeri ise RStudio'da. Ben şimdi RStudio'daki yöntemi takip edeceğim.

Sağ üstteki Git kutusunun orda iki mor, bir beyaz dikdörtgenden oluşan bir buton var. Remote oluşturmaya yarıyor. Tıklıyoruz bu kutuya. Add remote düğmesine tıklıyoruz. İsim veriyoruz, SSH linkini yapıştırıyoruz ve ok diyoruz. Bize şöyle bir yanıt verecek :
```
> > > /usr/bin/git checkout -B branch Switched to a new branch 'branch'
>
> > > /usr/bin/git push -u testhub branch remote: remote: Create a pull request for 'branch' on GitHub by visiting: remote: https://github.com/kullaniciadi/testrepo/pull/new/branch remote: To [github.com](http://github.com/):kullaniciadi/testrepo.git

- [new branch] branch -> branch Branch 'branch' set up to track remote branch 'branch' from 'testhub'.
```



Kısaca RStudio'da yaptığımız işleri github repomuzda tutmak için bu işlemleri yapmamız yeterli. Şimdilik bitti diyebiliriz. Ancak tabii ki çok daha detaylı çalışmanız mümkün. Ben bu çalışmayı yaparken aşağıdaki happygitwithr.com'dan temel olarak faydalandım. İki farklı bilgisayardan tek GitHub hesabıma commit etmeyi Emre ile birlikte çözdüm ve çoğu işlemi daha hızlı yapmam konusunda bana yardımcı oldu. 



Faydalanılan kaynaklar: 


https://happygitwithr.com/rstudio-git-github.html

https://uvastatlab.github.io/phdplus/installR.html

https://docs.github.com/en/free-pro-team@latest/github/authenticating-to-github/connecting-to-github-with-ssh

https://emre.xyz/unix-girdi-cikti-yonlendirme

