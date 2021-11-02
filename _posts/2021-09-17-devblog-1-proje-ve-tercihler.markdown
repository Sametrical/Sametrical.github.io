---
layout: post
title:  "Capital Waters: Dev Blog #1 - Proje ve Tercihler."
date:   2021-09-17 09:00:00 +0300
categories: Capital Waters
---
Öncelikle blog sayfamı okuyan herkese merhaba. Bu post Capital Waters ismini verdiğim Unity oyun projemin ilk postudur. Bu projeyi hem kendimi test etmek hem de oyun geliştiriciliği konusunda kendimi geliştirmek için bir portfolyo projesi olarak belirledim. Postlarımda genel olarak oluşturduğum assetler, karşılaştığım buglar ve çeşitli problemlere karşı ürettiğim çözümler bulunacak. 

<center><h3>Oyun Motoru</h3></center>

Oyun motoru tercihim **Unity** olacak. Nedenine gelecek olursak her ne kadar daha önce **Unreal Engine** ile aşinalığım olsada, motorun ana programlama dili olan c++ benim için kompleks ve öğrenmeside bir o kadar zor bir dil, birde bunun üstüne yetersiz dokümantasyon ve tutorial da cabası. Malesef **UE4**'ün sahip olduğu Visual Scripting(Blueprint) sistemi başta kulağa hoş gelsede bir yerden sonra kodunuz spagettiye dönüştüğü için üstünde çalışması bir hayli zor olabiliyor, en azından benim tecrübem bu yönde oldu. **Unity**'nin programlama dili olan c# hem tanıdık hem de syntaxına daha aşina olduğum bir dil ayrıca **Unity**'nin drag and drop mantığı kafama daha fazla yatıyor. Tabi birde **Unity**'nin kolayca ulaşabilinen engin tutorial olanaklarını da unutmamak gerek. Bu proje için, İki motoruda kullanmış biri olarak tercihimi **Unity** üzerinden kullanıyorum.

<center><h3>3D Programlar</h3></center>

Yaklaşık 4 senedir **Blender** üzerinden 3D modelleme yapmaktayım. Modelleme, doku tasarımı, rendering ve oyun motorlarına optimize asset oluşturma konusunda kendimi elimden geldiğince geliştirdim ve geliştirmeye devam ediyorum.

<p align="center">
  <img width="600" height="200" src="/images/port-gemi-top.png">
</p>
<center><em>Resim 1: Unreal Engine için daha önceden yaptığım 2 farklı 3 boyutlu model.</em></center>
&nbsp;

Modelleme işlerimi açık kaynak bir 3 boyutlu tasarım programı olan **Blender** üzerinden yapacağım. Blender ücretsiz olmasına karşın güçlü bir yazılım ve modelleme konusunda bir çok gereksinimi karşılayacak. Dokularımız için ise için ücretli bir program olan **Substance Painter 2019** kullanacağım, eğer dokuyu tamamen sıfırdan oluşturacaksam yine aynı firmanın bir başka ücretli yazılımı olan **Substance Designer 2020** kullanacağım. Duyguğuma göre bu yazılımları geliştiren firma **Adobe** tarafından satın alınmış. Önceden iki yazılımında "Perpetual Licence" dediğimiz,süresiz olan indie lisanslarını satın aldığım için kendimi biraz şanslı hissetmiyorum değil. Bu 2 programı kullanmamın nedeni ise inanılmaz iyi prosedürel doku işlemlerini başarıyla yapabilmeleri ve **Blender**'da dokuları dışa aktarmanın bana biraz meşakatli gelmesi. Bu sayede Low poly baking, LOD düzeni ve doku mapleri (color,normal,AO vb.) gibi konularda hatrı sayılır bir zaman kazanmayı hedefliyorum.

<center><h3>Capital Waters</h3></center>

Şimdi biraz projemizin kendisinden bahsedelim. Projemiz zaten program tercihimizden de yola çıkarsak 3 boyutlu olacak. Kamera sistemimiz ise Top-Down yani üstten bakmalı. Savaş ve dövüş mekanikleri olarak **MOBA** tarzına yakın bir mekanik düşündüm, tabi bir kaç kısmı farklı olacak, proje ilerledikçe postlarımda bu konu hakkında daha fazla bilgi vereceğim.

Oyun'u open-world düşünüyorum, ana karakterimiz bir adada başlayacak. Daha sonra adadan çıkıp dünyayı keşfetmek içinde gemi ve tekne kontrolcüsü eklemek istiyorum. Her adayı **Unity**'nin entegre Terrain sistemi ile teker teker tasarlamayı düşünüyorum, muhtemelen en çok zaman harcadığımız kısımda burası olacak. Ayrıca deniz için ayrı bir shader yazacağım, shader konusunda tecrübeliyim **Unity**'de daha önce en azından göze kötü görünmeyen bir kaç ocean shader yazmıştım.

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