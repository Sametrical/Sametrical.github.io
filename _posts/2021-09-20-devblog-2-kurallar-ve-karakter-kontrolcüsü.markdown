---
layout: post
title:  "Capital Waters: Dev Blog #2 - Kurallar ve Karakter Kontrolcüsü."
date:   2021-09-20 09:00:00 +0300
categories: Capital Waters
permalink: /blog-post-2
---
<p align = "left">
<a href="/Blog.html"> <- Blog Sayfasına Geri Dön </a>
</p>
<center><h3>Ön Bilgi: Kurallar</h3></center>
Posta geçmeden önce, projenin gelişim süreci boyunca uymam gereken bazı kuralları açıklamak istiyorum, sonuçta kendimi geliştirdiğim ve test ettiğim bir portfolyo projesi olacak. İlk olarak eğer **Unity**'nin içine entegre olmadığı sürece hazır assetlar ve kodlardan kaçınacağım, yani çoğu şeyi sıfırdan yazacağım. Hali hazırda 3 boyutlu modellemeci olduğum için bu modellerimiz için de geçerli, hepsini projenin gidişatına göre kendim yapma niyetindeyim. Kısacası,elimden geldiğince **Unity** Asset Store'u kullanmayacağım.
<center><h3>Karakter Kontrolcüsü: Mouse Movement System</h3></center>
Bu postumda **Unity**'nin NavMesh sistemini kullanan karakter kontrolcüsünü yapacağım, tabi şimdilik çok kompleks bir şey yapmak istemiyorum ama en azından karakterin mouse sol tık ile hareket edebilmesini istiyorum. Başlangıç olarak karakterler, çevre gibi bir çok şey için placeholder kullanacağım, **Unity** ile beraber gelen basit geometrik şekiller bu ihtiyacımızı büyük bir şekilde karşılayacak. 

Daha fazla uzatmadan **Unity Hub**'ı açıp 3D Universal Render-Pipeline şablonu ile projemizi oluşturalım.
<p align="center">
  <img width="700" height="450" src="/images/port-post2-projecttemplate.png">
</p>
<center><em>Resim 1: Proje Şablonu.</em></center>
&nbsp;

Şablon olarak URP seçmemin sebebi, performans açısından hafif olması. Oyunumun grafiklerini stilize ve gerçekçilik arasında bir yerde tutmak istiyorum, bu yüzden URP şablonu yeterli olacaktır.
Projemizi açtıktan sonra ışıklandırma assetleri hariç bütün her şeyi projemden kaldırdım, bir çoğunu sonradan kendim ekleyeceğim ve şablonla beraber gelen çoğu asseti kullanmayacağım için yer kaplamasını istemedim. Böylece projemi geliştirdikçe assetlarımı kendi kullanım standartlarıma göre düzenleyebileceğim.

Kontrolcü sistemine geçmeden önce karakterimin üstünde duracağı bir platforma ihtiyacım var, bunun için basit bir plane işimi görecek. Plane'i oluşturtan sonra ise karakterimizi temsil edecek bir kapsül oluşturdum. Yönünü belirtmek için ise ileri eksenini temsil eden bir küp koydum. Görünülüğü arttırmak içinse hepsine birer materyal atadım.

<p align="center">
  <img width="600" height="300" src="/images/port-post2-platform-karakter.png">
</p>
<center><em>Resim 2: Platform ve Temsili Karakter.</em></center>
&nbsp;

Karakterin hareketini sağlamak için NavMesh kullacağımı belirtmiştim, bu sebepten dolayı ilk önce kapsül objemi bir NavMesh Agent olarak tanımlamam gerekiyor. Kapsül objesinin Inspector kısmından Add Component diyerek NavMeshAgent komponentini objeme tanımladım.
<p align="center">
  <img width="450" height="400" src="/images/port-post2-navmeshagent.png">
</p>
<center><em>Resim 3: NavMesh Agent Komponenti</em></center>
&nbsp;

Şimdi karakterimizi asıl hareket ettirecek kısmı geldik, character movement script. Oyunum üstten bakmalı olduğu için Raycast adı verilen bir sistem kullanmam gerekiyor. Yani kameramızdan sürekli platforma vuran bir ışın olacak ve her mouse tıkında karakterin bu noktaya hareket etmesini sağlayacağım. **Unity** dokümantasyonuna iyice bir göz gezdirtikten ve bir kaç tutorialdan sonra, işlemin çokta zor olmadığını anladım. İstediğim sonucu elde etmem yaklaşık 10-15 dk dakika sürdü. Hatta ekstra olarak deneme amaçlı, "shift" tuşuna basıldığında karakteri fareyi takip edecek şekilde kendi etrafında döndürme özelliğini de ekledim.

<Strong>Kodum bu şekilde:</strong>

{% highlight csharp %}
using System.Collections.Generic;
using UnityEngine;
using UnityEngine.AI;

public class CharacterMovement : MonoBehaviour{

NavMeshAgent agent;
Transform player;
public float playerMovementSpeed = 5f;

    void Start()
    {
        agent = GetComponent<NavMeshAgent>();
    }
     void Update()
    {
    RaycastHit hit; 
    Ray ray = Camera.main.ScreenPointToRay (Input.mousePosition); 
    // Kameradan platforma giden ışını fare pozisyonuna storela.
    bool mouseHoldDown = Input.GetMouseButton(0);
    // Sol fare tıkını boolean değişkenine eşitle.
            
        if (Physics.Raycast(ray, out hit, Mathf.Infinity))
            {
                if (Input.GetMouseButtonDown(0) || mouseHoldDown == true ) 
                // Mouse sol tıka basılırsa ile karakteri ışının vurduğu noktaya hareket ettir, basılı tutulduğu sürece hareket etmeye devam et.
                    {
                    agent.speed = playerMovementSpeed; 
                    agent.SetDestination(hit.point);
                    }
                if (Input.GetKey("left shift"))  
                // Sol shift basılı tutulduğunda karakteri yüzü fare pozisyonuna bakacak bir şekilde kendi etrafında döndür.
                {
                    agent.speed = 0f;   
                    this.transform.LookAt( new Vector3(hit.point.x, transform.position.y, hit.point.z));
                }
                
            }
    }
}
{% endhighlight %}
&nbsp;
<center><h3>Kamera: Cinemachine</h3></center>
&nbsp;
Karakterimiz için kamera ve takip sistemi olarak **Unity** ile birlikte gelen **Cinemachine** aracını kullanacağım. Böylece kamera için kod yazmaktan kurtulmuş oluyorum ve üzerinde değişliklik yapmakta bir o kadar kolaylaşıyor. **Unity** ile beraber geldiği içinde kendime koyduğum kuralları çiğnememiş oluyorum.

Cinemachine ile bir yapay kamera oluşturup, ana kameraya bağladım ve body seçeneğinden framing transposer seçtim; nerdeyse hepsini denedim ama üstten bakış için en iyisi buydu. Follow kısmına daha önce oluşturduğumuz Capsule objesini tanımlayınca, kameramız karakterimizi takip etmeye başladı. 
<p align="center">
  <img width="1115" height="422" src="/images/port-post2-cinemachine.png">
</p>
<center><em>Resim 4: Cinemachine Komponenti.</em></center>
<center><h3>Sonuç:</h3></center>
<p align="center">
<iframe src="https://giphy.com/embed/qG6ryrtK2FbXoVItQ6" width="480" height="270" frameBorder="0" class="giphy-embed" allowFullScreen></iframe><p><a href="https://giphy.com/gifs/qG6ryrtK2FbXoVItQ6"></a>
<center>Okuduğunuz için teşekkürler, bir sonraki postta görüşmek üzere hoşçakalın.</center>

<br/>
<br/>
<p align = "center">
<a href="/blog-post-1"> <- Önceki </a>
&nbsp;|&nbsp;
<a href="/blog-post-3">Sonraki -></a>
</p>
<p align = "left">
<a href="/Blog.html"> <- Blog Sayfasına Geri Dön </a>
</p> 
<p align = "right">
<em><small>Dilek, görüş ve sorularınız için web sitemin iletişim bölümünden ulaşabilirsiniz.</small></em>
</p>
<p align = "right">
<em><small>- Samet</small></em>
</p>