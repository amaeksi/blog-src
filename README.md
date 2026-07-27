# elcineksi.com

Elçin Ekşi’nin kişisel sitesi ve Güneşimden Kaç yaratıcı doğa atölyelerinin ana kaynağıdır. Site, bağımlılığı olmayan özel Hugo şablonlarıyla üretilir ve GitHub Pages üzerinde yayınlanır.

## Yerelde çalışmak

Güncel Hugo Extended sürümünü kurun (workflow şu anda Hugo `0.152.2` kullanır):

```sh
hugo server
```

Üretim çıktısını yerelde almak için:

```sh
hugo --gc --minify
```

Çıktı `public/` dizinine yazılır; bu dizin Git’e eklenmez.

## İçerik yapısı

- `content/hakkimda/`: kısa biyografi; eski `/about/` adresi buraya yönlenir.
- `content/gunesimden-kac/`: proje ve atölye sayfaları.
- `content/post/`: eski yazı arşivi. Yazıların kalıcı adresleri `/post/.../` olarak korunur; arşiv listesi `/yazilar/`dadır.
- `content/isigin-rengi-rehber-h7n4/`: QR katılımcı rehberi. Navigasyonda yer almaz, `noindex,nofollow` taşır ve özel sitemap şablonu sayesinde sitemap’e girmez. Bu URL erişim kontrolü değildir; bağlantıyı bilen kişi sayfayı açabilir.
- `static/images/`: eski arşivden korunan yazı ve kişisel fotoğrafları.

## Kayıt formu ve bağlantılar

Google Form URL’si yalnızca [`data/links.yaml`](data/links.yaml) içindeki `registration_form` alanına yazılır. Alan boşken tüm kayıt CTA’ları bağlantı üretmez ve “Kayıt bağlantısı yakında” durumunda kalır.

Form için önerilen içerik:

- Başlık: **Yeni atölyelerden haberdar ol**
- Açıklama: “Güneşimden Kaç’ın yeni atölye tarihlerini ve zaman zaman paylaşacağımız kısa doğa notlarını almak için e-posta adresini bırakabilirsin. Sık e-posta göndermeyeceğiz.”
- Zorunlu alan: e-posta adresi; isteğe bağlı alan: ad.
- Onay: “Güneşimden Kaç’ın yeni atölyeleri ve ilgili içerikleri hakkında e-posta yoluyla bilgilendirilmek istiyorum.”
- Veri notu: “E-posta adresin yalnızca Güneşimden Kaç duyuruları için kullanılacak; üçüncü kişilerle paylaşılmayacaktır.”

Bu metin hukuki uyumluluk beyanı değildir. Form yayına alınmadan önce KVKK ve elektronik ileti kuralları ayrıca değerlendirilmelidir.

Yeni bir atölye eklemek için `content/gunesimden-kac/` altında yeni bir içerik dizini açın, front matter’da `layout: workshop` kullanın ve ilgili sayfayı proje içeriğinden bağlayın. Kayıt CTA’sı için içerikte `{{< registration-cta label="Yeni tarihleri ilk sen öğren" >}}` shortcode’unu kullanın.

## Yayınlama

`.github/workflows/deploy.yml`, `main` dalına gelen push’larda Hugo’yu derler ve resmi GitHub Pages artifact/deploy action’larıyla yayınlar. GitHub deposunda **Settings → Pages → Build and deployment → Source** seçeneğini **GitHub Actions** yapın.

### Özel alan adı

`static/CNAME` dosyası canonical alan adını `elcineksi.com` olarak taşır. GitHub Pages ayarlarında **Custom domain** alanına `elcineksi.com` yazın, doğrulama tamamlandıktan sonra **Enforce HTTPS** seçeneğini etkinleştirin.

DNS sağlayıcısında aşağıdaki kayıtları eklemek kullanıcı tarafında yapılacak işlemdir:

| Tür | Ad | Değer |
| --- | --- | --- |
| A | `@` | `185.199.108.153` |
| A | `@` | `185.199.109.153` |
| A | `@` | `185.199.110.153` |
| A | `@` | `185.199.111.153` |
| AAAA | `@` | `2606:50c0:8000::153` |
| AAAA | `@` | `2606:50c0:8001::153` |
| AAAA | `@` | `2606:50c0:8002::153` |
| AAAA | `@` | `2606:50c0:8003::153` |
| CNAME | `www` | `amaeksi.github.io` |

DNS yayılımı sonrasında GitHub Pages’de alan adının doğrulandığını kontrol edin. `www.elcineksi.com` için CNAME kaydı eklendikten sonra GitHub Pages’in özel alan adı yönlendirmesi ziyaretçileri canonical `https://elcineksi.com` adresine taşır.

GitHub’ın güncel DNS ve domain doğrulama yönergeleri için [özel alan adını yapılandırma dokümantasyonunu](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site) referans alın.
