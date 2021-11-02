---
layout: post
title:  "Capital Waters: Dev Blog #1 - Proje ve Tercihler."
date:   2021-09-17 09:00:00 +0300
categories: Capital Waters
---
Öncelikle blog sayfamı okuyan herkese merhaba. Bu post Capital Waters ismini verdiğim Unity portfolyo projemin ilk yazısıdır. Postlarımda genel olarak sıfırdan oluşturduğum assetler, karşılaştığım buglar ve çeşitli problemlere karşı ürettiğim çözümler bulunacak.

<center><h3>Oyun Motoru</h3></center>

Oyun motoru tercihim **Unity** oldu. Öncelikle benim için bu tercihin nedenlerini açıklakmak istiyorum. Birincisi, her ne kadar daha önceden **Unreal Engine 4** oyun motoruna aşinalığım olsa da, motorun ana programlama dili olan c++'ın motor için olan kütüphanesi için eğitim materyali eksikliği yaşadığımdan dolayı, tercih etmedim. Maalesef **UE4**'ün sahip olduğu Visual Scripting(Blueprint) sistemi başta kulağa hoş gelse de, bir yerden sonra kod spagettiye dönüştüğü için kod üzerinde çalışması bir hayli zor olabiliyor. En azından benim tecrübem bu yönde oldu. **Unity**'nin programlama dili olan c#, benim sentaksına daha aşina olduğum bir dil. Ayrıca **Unity**'nin drag and drop mantığı kafama daha fazla yatıyor. Tabi bir de **Unity**'nin kolayca ulaşılabilinen engin tutorial olanaklarını da unutmamak gerek. Bu proje için, iki motoruda kullanmış biri olarak tercihimi **Unity** üzerinden kullanıyorum.

<center><h3>3D Programlar</h3></center>

Yaklaşık 4 senedir **Blender** üzerinden 3 boyutlu modelleme yapmaktayım. Modelleme, doku tasarımı, rendering ve oyun motorlarına optimize asset oluşturma konusunda kendimi elimden geldiğince geliştirdim ve geliştirmeye devam ediyorum.

<p align="center">
  <img width="600" height="200" src="/images/port-gemi-top.png">
</p>
<center><em>Resim 1: Unreal Engine için daha önceden yaptığım 2 farklı 3 boyutlu model.</em></center>
&nbsp;

Modelleme işlerimi açık kaynak bir 3 boyutlu tasarım programı olan **Blender** üzerinden yapacağım. Blender ücretsiz olmasına karşın güçlü bir yazılım. Modelleme konusundaki bir çok gereksinimimi karşılayacak. Dokular için ise ücretli bir program olan **Substance Painter 2019**'u kullanacağım. Eğer dokuyu tamamen sıfırdan oluşturmam gerekiyorsa, yine aynı firmanın bir başka ücretli yazılımı olan **Substance Designer 2020**'yi kullanacağım. Duyduğuma göre bu yazılımları geliştiren firma **Adobe** tarafından satın alınmış. Önceden, iki yazılımın da "Perpetual Licence" dediğimiz süresiz olan indie lisanslarını satın aldığım için kendimi biraz şanslı hissetmiyorum değil. Bu iki programı kullanmamın nedeniyse prosedürel doku işlemlerinin üstesinden başarıyla gelebilmeleri. Açıkçası bir de **Blender**'da dokuları dışa aktarmanın bana biraz meşakatli gelmesi de var ki bu programlar bu konuda da çok yetenekli. Bu sayede low poly baking, LOD düzeni ve doku mapleri (color,normal,AO vb.) gibi konularda hatrı sayılır bir zaman kazanmayı hedefliyorum.

<center><h3>Capital Waters</h3></center>

Şimdi biraz projemizin kendisinden bahsedelim. Projemiz zaten program tercihimizden de yola çıkarsak 3 boyutlu olacak. Kamera sistemimiz ise Top-Down yani üstten bakmalı olacak. Savaş ve dövüş mekanikleri olarak **MOBA** tarzına yakın bir mekanik düşündüm, tabi birkaç kısmı farklı olacak. Proje ilerledikçe postlarımda bu konu hakkında daha fazla bilgi vereceğim.

&nbsp;
<h4>Oyunun Özellikleri</h4>

1. Proje açık dünya olacak.
2. Açık dünyada keşfedilebilir bir çok ada olacak.
3. Ana karakter oyuna önceden tasarlanıp, belirlenmiş bir ada kolonisinde başlayacak.
4. Ana karaktere özel bir ada(Ana üssümüz bu ada olacak).
5. Deniz için custom ocean shader.
&nbsp;
<p align="center">
  <img width="600" height="200" src="/images/port-ocean-shader.png">
</p>
<center><em>Resim 2: Unity için yaptığım 2 farklı ocean shader.</em></center>
<em>- Shaderin video halini görmek için</em> **[<em>tıklayın!</em>](https://www.youtube.com/watch?v=jlR_CDT9T44)**
&nbsp;

Şimdilik scope-creep dediğimiz olayı yaşamamak için projemi kısıtlı tutmak istiyorum. Baştan hedefimi çok yüksek tutup burn-out riskini göze almayacağım. Projeyi genel hatlarıyla açıkladığımı varsayıp, bu postu burada bitirmek istiyorum. Bir sonraki postta projemizin kuralları, kullanılacak assetler konusuna gireceğim ve en azından ana karakterimizin kontrülcüsü ve kamera takip sistemini ekleyeceğim. Okuduğunuz için teşekkürler, bir sonraki postta görüşmek üzere hoşçakalın.
&nbsp;


&nbsp;
<center><h1>SON</h1></center>