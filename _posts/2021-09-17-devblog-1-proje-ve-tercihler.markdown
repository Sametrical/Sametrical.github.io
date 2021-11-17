---
layout: post
title:  "Capital Waters: Dev Blog #1 - Proje ve Tercihler."
date:   2021-09-17 09:00:00 +0300
categories: Capital Waters
---
<p align = "left">
<a href="/Blog.html"> <- Blog Sayfasına Geri Dön </a>
</p>

Öncelikle blog sayfamı okuyan herkese merhaba. Bu post Capital Waters ismini verdiğim Unity portfolyo projemin ilk yazısıdır. Postlarımda genel olarak sıfırdan oluşturduğum assetler, karşılaştığım buglar ve çeşitli problemlere karşı ürettiğim çözümler bulunacak. Postları genel olarak kısa tutup, daha sık post atmak istiyorum. Böylece her postumun 2000 kelimelik bir essay olmasından kaçınmak istiyorum.

<center><h3>Oyun Motoru</h3></center>

Oyun motoru tercihim **Unity** olacak. **Unity**'nin programlama dili olan c#, önceki zamanlarda aldığım çeşitli kurslardan dolayı benim sentaksına daha aşina olduğum bir dil. Tabi bir de kolayca ulaşılabilinen engin tutorial olanakları ve sahip olduğu geniş topluluğu unutmamak gerek. **Unreal Engine 4** kullandığım vakitlerde, en çok problemini yaşadığım konu da buydu, motorun ana progralama dili olan c++'da, motor için olan dokümantasyon ve tutorial eksiği. **UE4** dokümantasyonunda nerdeyse her olgu **Visual Scripting(Blueprints)**'e göre tasarlanmış. Başta inanılmaz bir sistem gibi gelsede, sonraları kodumun spagettiye dönmesinden dolayı konvensiyonel scriptinge nazaran daha fazla karmaşıklaştığını fark ettim. Bu yüzden 2 motoruda kullanmış biri olarak tercihimi **Unity** yanından kullanıyorum.

<center><h3>3D Programlar</h3></center>

Yaklaşık 4 senedir **Blender** üzerinden 3 boyutlu modelleme yapmaktayım. Modelleme, doku tasarımı, rendering ve oyun motorlarına optimize asset oluşturma konusunda kendimi elimden geldiğince geliştirdim ve geliştirmeye devam ediyorum.

<p align="center">
  <img width="600" height="200" src="/images/port-gemi-top.png">
</p>
<center><em>Resim 1: Unreal Engine 4 için daha önceden yaptığım gemi ve top modeli.</em></center>
&nbsp;

Blender açık kaynak ve ücretsiz olmasına karşın çok güçlü bir yazılım ve her güncellemede güçlenmeye devam ediyor. Modelleme konusundaki bir çok gereksinimimi karşılayacak. Dokular için ise ücretli bir program olan **Substance Painter 2019**'u kullanacağım. Eğer dokuyu tamamen sıfırdan oluşturmam gerekiyorsa, yine aynı firmanın bir başka ücretli yazılımı olan **Substance Designer 2020**'yi kullanacağım. Duyduğuma göre bu yazılımları geliştiren firma **Adobe** tarafından satın alınmış. Önceden, iki yazılımın da "Perpetual Licence" dediğimiz süresiz olan indie lisanslarını satın aldığım için kendimi biraz şanslı hissetmiyorum değil. Bu iki programı kullanmamın nedeniyse prosedürel doku işlemlerinin üstesinden başarıyla gelebilmeleri. Açıkçası bir de **Blender**'da dokuları dışa aktarmanın bana biraz meşakatli gelmesi de var ki bu programlar bu konuda da çok yetenekli. Bu sayede low poly baking, LOD düzeni ve doku mapleri (color,normal,AO vb.) gibi konularda hatrı sayılır bir zaman kazanmayı hedefliyorum.

[<center> <img src="/images/blender-features-reel-2.93.png"></center>](https://www.youtube.com/watch?v=fxNlpQYRz7s)
<center><em><small>Kullandığım Blender versiyonu hakkında bilgi sahibi olmak için : Blender 2.93 LTS - Features Reel Showcase</small></em></center>
&nbsp;
<center><h3>Capital Waters</h3></center>

Şimdi biraz projemizin kendisinden bahsedelim. Projemiz zaten program tercihimizden de yola çıkarsak 3 boyutlu olacak. Kamera sistemimiz ise Top-Down yani üstten bakmalı olacak. Savaş ve dövüş mekanikleri olarak **MOBA** tarzına yakın bir mekanik düşündüm, tabi birkaç kısmı farklı olacak. Render pipeline olarak Universal Render-pipeline kullanacağım. Proje ilerledikçe postlarımda bu konular hakkında daha fazla ayrıntı vereceğim.
&nbsp;
<h4>Oyunun Özellikleri</h4>

1. Proje açık dünya olacak.
2. Açık dünyada keşfedilebilir bir çok ada olacak.
3. Ana karakter oyuna önceden tasarlanıp, belirlenmiş bir ada kolonisinde başlayacak.
4. Ana karaktere özel bir ada(Ana üssümüz bu ada olacak).
5. Deniz için custom ocean shader.
&nbsp;
<p align="center">
  <img width="600" height="250" src="/images/port-ocean-shader.png">
</p>
<center><em>Resim 2: Unity'de başka bir proje için yaptığım 2 farklı ocean shader.</em></center>
<em>- Shaderin video halini görmek için</em> **[<em>tıklayın!</em>](https://www.youtube.com/watch?v=jlR_CDT9T44)**
&nbsp;

Şimdilik scope-creep dediğimiz olayı yaşamamak için projemi kısıtlı tutmak istiyorum. Baştan hedefimi çok yüksek tutup burn-out riskini göze almayacağım. Projeyi genel hatlarıyla açıkladığımı varsayıp, bu postu burada bitirmek istiyorum. Bir sonraki postta projemizin kuralları, kullanılacak assetler konusuna gireceğim ve en azından ana karakterimizin kontrülcüsü ve kamera takip sistemini ekleyeceğim. Okuduğunuz için teşekkürler, bir sonraki postta görüşmek üzere hoşçakalın.
&nbsp;

<center><h1>-SON-</h1></center>

<p align = "center">
<a href="/Blog.html"> <- Geri Dön </a>
&nbsp;|&nbsp;
<a href="/capital/waters/2021/09/20/devblog-2-kurallar-ve-karakter-kontrolcüsü.html">Sonraki -></a>
</p>
<p align = "right">
<em><small>Dilek, görüş ve sorularınız için bana web sitemin iletişim bölümünden ulaşabilirsiniz.</small></em>
</p>
<p align = "right">
<em><small>- Samet</small></em>
</p>
