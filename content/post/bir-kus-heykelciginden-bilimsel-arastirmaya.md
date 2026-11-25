---
title: "Bir kuş heykelciği, 251 yırtıcı kuş ve bilimden iş dünyasına uzanan bir hikâye"
date: 2026-11-25T00:00:00+03:00
draft: false
description: "Lindos'un yırtıcı kuşlarından RStudio'daki ekolojik ve filogenetik araştırmaya; Doğa Kuvvetleri, NaturaLogic ve ERES Akademi arasında bilimsel merakın izini sürmek."
slug: "bir-kus-heykelciginden-bilimsel-arastirmaya"
---

Bazen bir müzede karşılaştığınız küçük bir heykelcik, sizi hiç planlamadığınız bir bilimsel araştırmanın içine sürükleyebiliyor.

8 Nisan 2023'te İstanbul Arkeoloji Müzeleri'ni gezerken fotoğrafladığım Lindos kökenli bir yırtıcı kuş heykelciği vardı. Müze etiketinde atmaca olarak tanımlanmıştı. Ancak benim dikkatimi çeken başka bir ayrıntı vardı. Kuşun gagasından gövdesine doğru uzanan kabartmayı bir yılan olarak yorumlamıştım.

Peki bu kuş bir yılan kartalı (*Circaetus gallicus*) olabilir miydi?

Ekoloji ve arkeometri çalışan bir biyolog olarak müzelerde karşılaştığım hayvan figürlerine biraz farklı bakıyorum. Bir hayvanın hangi tür olduğunu anlamaya çalışırken ister istemez onun yaşadığı çevreyi, davranışlarını, diğer canlılarla ilişkilerini ve geçmişte yaşamış insanların bu hayvanı nasıl gözlemlemiş olabileceklerini de düşünüyorum.

Elbette stilize edilmiş bir heykelcikten kesin bir tür teşhisi yapmak kolay değil. Ancak bazen bir sorunun kesin yanıtından çok, bizi götürdüğü yerler ilginç oluyor.

Bu kez de öyle oldu.

## Her şey iki yılan avcısıyla başladı

Geçtiğimiz günlerde Doğa Kuvvetleri için Lindos'un yırtıcı kuşlarını konu alan bir yazı hazırladım. Heykelciklerin arkeolojik geçmişini, Lindos'tan İstanbul'a uzanan hikâyelerini ve temsil ediyor olabilecekleri hayvanların ekolojik özelliklerini araştırdım.

Yazıyı hazırlarken yılan kartalıyla birlikte Afrika'nın oldukça ilginç bir yırtıcı kuşu olan kâtip kuşunu (*Sagittarius serpentarius*) da ele aldım.

Bu iki kuşun ikisi de yılan avlayabiliyor. Ancak bunu birbirlerinden oldukça farklı biçimlerde yapıyorlar. Biri avını çoğunlukla havadan tespit ederken diğeri güçlü ve uzun bacaklarıyla yerde avlanıyor. Evrimsel geçmişleri de birbirlerinden oldukça farklı.

Bir biyolog olarak burada benim için daha ilginç bir soru ortaya çıkıyor:

**Canlıların evrimsel akrabalıkları ile doğadaki kaynakları kullanma biçimleri arasında nasıl bir ilişki var?**

Yakın akraba türler benzer ekolojik özelliklere mi sahip? Birbirinden uzak evrimsel soylar benzer kaynakları kullanabiliyor mu? Bir canlı grubundaki tür sayısının fazla olması, o grubun ekolojik çeşitliliğinin de fazla olduğu anlamına mı geliyor?

Doğa Kuvvetleri'ndeki yazım tamamlanmıştı ama zihnimdeki sorular henüz bitmemişti.

[Doğa Kuvvetleri: Lindos’un Yırtıcı Kuşlarını Kim Yaptı, Kim Buldu, Kim Gördü?](https://dogakuvvetleri.com/lindosun-yirtici-kuslarini-kim-yapti-kim-buldu-kim-gordu/)

## Müzeden RStudio'ya

Bu soruları yalnızca literatürdeki birkaç örnek üzerinden tartışmak yerine, gerçek verilerle incelemek istedim.

Böylece kendimi RStudio'da, dünya genelindeki yırtıcı kuşların ekolojik özelliklerini ve filogenetik ilişkilerini araştırırken buldum.

AVONET ve AVONICHE veri kaynaklarından yararlanarak Accipitriformes takımındaki 251 türün beslenme ve avlanma özelliklerini bir araya getirdim. Dokuz geniş besin kategorisini ve bunların avlanma stratejileriyle birlikte tanımlandığı 32 ayrıntılı ekolojik niş kategorisini inceledim.

Ardından yayımlanmış bir kuş filogenisini kullanarak evrimsel ilişkileri analizime dahil ettim.

Bilimsel araştırmanın her zaman dışarıdan göründüğü kadar doğrusal ilerlemediğini burada da gördüm. Veri tabanları arasındaki taksonomik farklılıklar, tür isimlerinin eşleştirilmesi, filogenetik ağacın hazırlanması ve hangi istatistiksel yöntemin hangi soruya karşılık geldiğinin belirlenmesi gibi pek çok ayrıntıyla uğraştım.

Sonuçta 218 türü filogenetik ağaçla eşleştirerek 23.653 farklı tür çiftinin ekolojik ve evrimsel uzaklıklarını karşılaştırdım. Bunlar birbirinden bağımsız gözlemler değildi; bu nedenle istatistiksel değerlendirmede tür etiketlerinin permütasyonuna dayanan bir yöntem kullandım.

Bir müzede gördüğüm küçük bir kuş figüründen, binlerce biyolojik karşılaştırma içeren bir araştırmaya gelmiştim.

## Peki doğayı anlamak için türleri saymak yeterli mi?

Araştırmada evrimsel olarak birbirinden daha uzak türlerin, beslenme ve avlanma özellikleri bakımından da daha farklı olma eğiliminde olduğunu gördüm. Ancak bu ilişki kusursuz değildi.

Daha da ilginç olanı, incelediğim 28 cinste tür sayısı ile türler arasındaki ortalama ekolojik farklılaşmanın belirgin bir monoton ilişki göstermemesiydi.

Bu sonuç, tür sayısının önemsiz olduğu anlamına gelmiyor. Ancak doğanın çeşitliliğini anlamak için kullandığımız farklı göstergelerin birbirlerinin yerine geçemeyeceğini hatırlatan güzel bir örnek sunuyor.

Bir ekosistemde kaç tür bulunduğu kadar, bu türlerin ne yaptığı, hangi kaynakları kullandığı, birbirleriyle nasıl ilişki kurduğu ve çevresel değişimlerden nasıl etkilenebileceği de önemli.

Özellikle besin ağlarının üst seviyelerinde yer alan yırtıcı kuşları düşündüğümüzde bu ilişkiler daha da ilginç hale geliyor. Bu kuşların yaşamları, kendilerinin çok ötesinde pek çok ekolojik sürece bağlı.

İşte burada araştırmanın benim için başka bir boyutu başladı.

## NaturaLogic: Bilimsel bilgiyi iş dünyası için anlamlı hale getirmek

Bir süredir NaturaLogic'te üzerinde çalıştığım Nature Intelligence yaklaşımının temelinde oldukça benzer bir soru bulunuyor.

Şirketlerin sürdürülebilirlik raporlarında doğaya ilişkin çeşitli sayılar, göstergeler ve ölçümler var.

Peki bu sayılar gerçekten neyi anlatıyor?

Bir şirketin sahip olduğu yeşil alanın büyüklüğünü bilmek, o alanın ekolojik niteliğini anlamaya yeter mi? Bir alanda gözlemlenen türlerin sayısı, oradaki ekolojik ilişkilerin durumunu ne ölçüde temsil ediyor? Bir kurum doğayla olan ilişkisini değerlendirirken hangi bilgileri gözden kaçırıyor olabilir?

Biyolojik çeşitlilik, yalnızca sayılardan oluşan bir envanter değil. Canlıların, kaynakların, süreçlerin ve zaman içerisinde şekillenen ilişkilerin meydana getirdiği dinamik bir sistem.

Yırtıcı kuşlar üzerine gerçekleştirdiğim araştırmayı bu nedenle NaturaLogic'e taşıdım.

Amacım şirketlere yırtıcı kuşlar hakkında bilgi vermekten çok, gerçek bir bilimsel araştırma üzerinden doğaya ilişkin verilerin nasıl okunabileceğini göstermekti.

Bu araştırma herhangi bir şirketin ekolojik etkisini ölçmüyor. Ancak kurumların biyoçeşitlilik göstergelerini değerlendirirken neden daha geniş bir ekolojik bakış açısına ihtiyaç duyabileceklerini ortaya koyan bir örnek sunuyor.

NaturaLogic'te geliştirmeye çalıştığım şey de tam olarak bu: Ekolojinin, evrimsel biyolojinin ve doğa bilimlerinin bize kazandırdığı düşünme biçimini, iş dünyasının kendi kararlarında kullanabileceği bir yetkinliğe dönüştürmek.

[NaturaLogic: Doğa Verilerinden İş Zekâsına](https://naturalogiclabs.com/research/beyond-species-richness/)

## ERES Akademi: Sonucun arkasındaki bilimi paylaşmak

Ancak bir araştırmanın yalnızca sonuçlarını paylaşmak bana yeterli gelmiyor.

Veriyi nereden elde ettik? Nasıl hazırladık? Ekolojik farklılığı nasıl hesapladık? Neden Hellinger uzaklığını kullandık? Spearman korelasyonu bize ne anlatıyor? Permütasyon testlerine neden ihtiyaç duyduk? Sonuçlarımızı hangi sınırlılıklar içerisinde yorumlamalıyız?

Yıllardır ERES Biyoinformatik Akademi'de geliştirmeye çalıştığım bilimsel öğrenme yaklaşımı da bu sorular üzerine kurulu.

Biyoinformatik araçlarını kullanabilmek önemli ama kullanılan algoritmaların ardındaki mantığı anlamak, doğru bilimsel soruyu sormak ve elde edilen sonuçları biyolojik bağlamları içerisinde yorumlayabilmek çok daha önemli.

Bu nedenle araştırmanın ayrıntılı bilimsel metnini, matematiksel yöntemlerini, grafiklerini ve özgün R kodlarını ERES Akademi'de açık erişime sundum.

İlgilenen araştırmacılar ve öğrenciler çalışmanın yalnızca sonuçlarını değil, analiz sürecini de inceleyebilir, kodlardan yararlanabilir ve kendi araştırma sorularını geliştirebilirler.

[ERES Biyoinformatik Akademi: Beyond Species Richness — Bilimsel Analiz ve Açık R Kodları](https://akademi.eresbiotech.com/reference/beyond-species-richness/)

## Aslında yaptığım bütün işler birbirinden besleniyor

Dışarıdan bakıldığında Doğa Kuvvetleri, NaturaLogic ve ERES Biyoinformatik Akademi birbirinden oldukça farklı projeler gibi görünebilir.

Biri doğa ve kültür üzerine bilim iletişimi yapıyor. Diğeri bilimsel bilgiyi iş dünyasının karar süreçlerine taşıyor. Bir diğeri ise biyolojik verilerle çalışmayı ve bilimsel araştırma yöntemlerini öğrenmek isteyen insanlara ulaşıyor.

Ancak benim için hepsinin ortak bir başlangıç noktası var: Merak.

Doğa Kuvvetleri'nde bir soru soruyorum.

Bilimsel araştırma yöntemleriyle o sorunun peşine düşüyorum.

NaturaLogic'te ortaya çıkan bilginin nasıl faydaya dönüşebileceğini araştırıyorum.

ERES Akademi'de ise bu bilgiyi nasıl ürettiğimi başkalarıyla paylaşıyorum.

Bilim iletişimi, araştırma, girişimcilik ve öğrenme arasında kurmaya çalıştığım ilişki tam olarak böyle bir şey.

Ve bazen bütün bunların başlaması için bir müzede, gagasından aşağı doğru bir yılan uzandığını düşündüğünüz küçük bir kuş heykelciği görmeniz yeterli oluyor.

*Elçin Ekşi — Kasım 2026*
