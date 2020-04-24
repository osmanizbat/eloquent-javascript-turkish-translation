{{meta {load_files: ["code/intro.js"]}}}

# Giriş

{{quote {author: "Ellen Ullman", title: "Close to the Machine: Technophilia and its Discontents", chapter: true}

Sistemi kendi amaçlarımız için oluşturduğumuzu düşünüyoruz.  Sanki kendi imajımızla yaptığımızı zannediyoruz ama bilgisayar gerçekte bizim gibi değil. Bazı yönlerimizin basit yansımasıdır:
Bunlar mantık, düzen, kural ve netlik bölümleridir.

quote}}

{{figure {url: "img/chapter_picture_00.jpg", alt: "Picture of a screwdriver and a circuit board", chapter: "framed"}}}

Bu kitap bilgisayarlara talimatlar verme hakkındadır. Günümüzde bilgisayarlar neredeyse tornavida kadar yaygınlaşmış olsa da bundan biraz daha karmaşıktırlar ve bilgisayarlara istediklerimizi yaptırtmak her zaman kolay olmayabilir.

Eğer yapmanız gereken e-postalarınızı görüntüleme, matematiksel hesaplama yapma gibi genel, net tanımlanmış bir işlem ise ilgili uygulamayı açıp işinizi kolayca tamamlayabilirsiniz. Fakat biricik ve ucu açık işler için böyle bir uygulama muhtemelen yoktur.

İşte bu noktada programlama devreye girebilir._Programlama_
bir programı (bilgisayardan yapması istenilen kesin talimatlar listesi) inşa etme eylemidir. Bilgisayarlar aptal ve bilmiş yaratıklar olduklarından, programlama temelde sıkıcı ve sinir bozucudur.

Neyseki bu gerçeğin üstesinden gelebilir ve makinelerin anlayabildiği kavramlarla düşünme titizliğinden keyif alabilirseniz, programlamadan mükafatlanabilirsiniz. Manuel şekilde yaptığınızda sonsuza dek sürecek işleri belki de saniyeler içerisinde tamamlamanız mümkün olabilir. Programlama daha önce imkansız olan şeyleri bilgisayara yaptırabilmenin bir yoludur. Aynı zamanda soyut düşünme konusunda mükemmel bir alıştırmadır.

Programlama çoğunlukla programla dilleriyle yapılır. Bir _progemlama dili_ bilgisayarlara talimatlar vermek için tasarlanmış yapay bir dildir. İlginç bir şekilde bilgisayarlarla iletişim için bulduğumuz en etkili yöntem birbirlerimizle iletişim yöntemimizden bir çok özelliği ödünç alır. Doğal diller gibi bilgisayar dilleri de kelime ve tabirlerin farklı biçimlerde bir araya getirilerek yeni kavramları ifade etme imkanı sunarlar.

Bir noktada 1980 ve 1990 ların BASIC ve DOS gibi dil tabanlı arayüzleri, bilgisayarlarla etkileşimin ana yöntemiydi. Öğrenmesi daha kolay fakat daha kısıtlayıcı olan görsel arayüzler büyük oranda bunların yerini aldı. Nereye bakacağınızı bilirseniz bilgisayar dilleri halen varlığını sürdürmekteler. Bu dillerden biri olan JavaScript, tüm web tarayıcılarda dolayısıyla tüm cihazlarda gömülü olarak gelmektedir.  

Bu kitap bu dille işe yarar ve eğlenceli şeyler yapabilecek kadar sizi tanıştırmaya çalışacaktır.

## Programlama hakkında

JavaScript'le birlikte, programlamanın temel prensiplerini de tanıtacağım. Programlama, göründüğü kadarıyla zordur. Temel kurallar basit ve açıktır, fakat bu temeller üzerine inşa ettiğiniz programlar kendi kural ve karmaşasını doğuracak derecede karmaşıklaşma eğilimindedirler. Bir nevi kendi labirentinizi inşa ediyorsunuz ve içinde kaybolmanız an meselesi.

Bu kitabı okurken çok sıkıldığınız zamanlar olabilir. Eğer programlamada yeniyseniz çok sayıda yeni kavramla tanışmanız gerekecek. Bu kavramların bir çoğu daha sonra yeni bağlantılar kurmanızı gerektirecek şekillerde bir araya getirilecek.

Gerekli gayreti sarfetmek sizin elinizde. Kitaba devam etmekte zorlandığınızda kendi yetenekleriniz konusunda hemen bir yargıya varmayın. İyi durumdasınız ama sadece devam etmelisiniz. Bir ara verin, konuyu tekrar okuyun ve örnek program ve alıştırmaları okuyup anladığınızdan emin olun. Öğrenmek zordur, fakat öğrendikleriniz sizindir ve sonraki öğrenmelerinizi daha da kolaylaştıracaktır.

{{quote {author: "Ursula K. Le Guin", title: "The Left Hand of Darkness"}

Eylem faydasızsa bilgini arttır, bilgi faydasızsa uyu.

When action grows unprofitable, gather information; when information
grows unprofitable, sleep.

quote}}

Bir program bir çok şeydir. Programcının yazdığı bir metin parçasıdır, bilgisayarın yaptıklarını yönlendiren güçtür, bilgisayarın hafızasındaki veridir, ancak aynı hafıza alanında yapılan işlemleri de kontrol eder. Programları bilinen nesnelerle karşılaştıran benzetmeler yetersizdir. Yüzeysel olarak şöyle bir benzetme yapılabilir; birçok ayrı parça içeren ve bir bütün olarak çalışabilmesi için parçaların birbirleriyle bağlantı noktalarını ve işlemin bütünündeki rollerini dikkate almanız gereken bir makine.

Bilgisayar bu soyut makineleri barındıran fiziksel bir makinedir. Bilgisayarlar sadece çok basit düzeydekki işlemleri kendi başlarına yapabilirler. Onları kullanışlı kılan şey bu basit işlemleri çok yüksek hızla yapabilmeleridir. Bir program muazzam sayıda basit işlemi kullanarak daha karmaşık işler gerçekleştirebilir.

Bir program bir düşüncenin binasdır. İnşa masrafı, ağırlığı olmayan ve klavyede yazan ellerimizin altında yükselen. 

Fakat dikkat edilmezse bir programın boyutu ve karmaşıklığı kontrolden çıkar ve hatta yazan kişide dahi kafa karıştıran hal alabilir. Programları kontrol altında tutma programlamanın temel problemidir. Programlama sanatı karmaşıklığı kontrol etme becerisidir. Büyük program kendi karmaşıklığı içerisine bastırıldı. 

Bazı programcılar programlarında sadece küçük bir dizi, çok iyi bilinen teknikleri kullanarak bu karmaşıklığı en iyi şekilde yönetililebileceklerine inanırlar. Programlarının biçimini ve güvenli sınırlarını belirleyen katı kuralları ve iyi pratikleri vardır.

Bu sıkıcı olduğu kadar, verimsizdir de. Yeni problemlere bazen yeni çözümler gerekir. Programlama yeni ve hızlı gelişmekte olan bir alandır ve yeni yaklaşımların yer alabileceği çeşitliliğe sahiptir. Program tasarlarken birçok kötü hatalar yapılabilir fakat devam etmeli düşündüğünüz gibi yapmalısınız ki programı anlayabilesiniz. İyi bir programın nasıl olması gerektiği algısı, kuralların öğrenilmesiyle değil pratikle gelişir. 

## Dil neden önemlidir?

Bilgisayarların ortaya çıktığı ilk zamanlarda programlama yoktu.
Programlar şuna benziyordu:

```{lang: null}
00110001 00000000 00000000
00110001 00000001 00000001
00110011 00000001 00000010
01010001 00001011 00000010
00100010 00000010 00001000
01000011 00000001 00000000
01000001 00000001 00000001
00010000 00000010 00000000
01100010 00000000 00000000
```

Bu 1'den 10'a kadar sayıları toplayıp sonucu yazdıran bir program: `1 + 2 + ... + 10 = 55`. Bu basit bir farazi makine üzerinde çalışabilir. İlk bilgisayarları programlamak için çok sayıda anahtarı doğru pozisyonda ayarlamanız veya karton şeritlere delikler açıp bilgisayara yüklemeniz gerekliydi. Ne kadar sıkıcı ve hataya yatkın bir işlem olduğunu tahmin edebiliyor olmalısınız. Basit programları yazmak dahi yüksek akıl ve titizlik gerektiriyordu. Daha karmaşık programlar neredeyse akıl almaz derecedeydi.

Tabii ki bu gizemli 0'lar 1'ler dizilerini eliyle giriyor olmak programcıya güçlü sihirbazlık hisleri yaşatıyordu. Ve bunun iş memnuniyeti açısından bir değeri de olmalıydı.

Yukarıdaki programın her bir satırı tek bir komut içeriyor. Basit İngilizce'yle şöyle yazılabilir:

 1. 0 sayısını 0. hafıza alanına kaydet.
 2. 1 sayısını 1. hafıza alanına kaydet.
 3. 1\. hafıza alanınındaki sayıyı 2. hafıza alanına kaydet.
 4. 2\. hafıza alanınındaki sayıdan 11 çıkar.
 5. Eğer 2. hafıza alanındaki sayı 0 ise işleme 9. satırdan devam et.
 6. 1\. hafıza alanındaki sayıyı 2. hafıza alanına ekle.
 7. 1\. hafıza alanındaki sayıya 1 ekle
 8. 3\. adımdan devam et.
 9. 0\. hafıza alanındaki sayıyı yazdır. 

0'lar v 1'ler çorbasından daha okunaklı olsa da yine de oldukça karışık. Direktfiler ve hafıza alanları için sayılar yerine isimler kullanmak işe yarar.  

```{lang: "text/plain"}
 Set “total” to 0.
 Set “count” to 1.
[loop]
 Set “compare” to “count”.
 Subtract 11 from “compare”.
 If “compare” is zero, continue at [end].
 Add “count” to “total”.
 Add 1 to “count”.
 Continue at [loop].
[end]
 Output “total”.
```
Bu noktada programın nasıl çalıştığını görebiliyor musunuz? İlk iki satırda iki hafıza alanının başlangıç değerleri veriliyor. `total` değişkeni hesaplama sonuçlarının toplanması için kullanılacak ve `count` değişkeninde o sırada işlem yapılan sayı takip edilecek. `compare` geçen satırlar belki de en tuhaf olanlar. Program `count` değişkenini 11 ile kıyaslayarak sonlanması gerekip gerekmediğine karar veriyor. Farazi makinemiz biraz ilkel olduğu için sadece bir sayının 0'a eşit olup olmadığını kıyaslayaarak karar verebiliyor. Bu yüzden `compare` adlı hafıza alanını `count - 11` sonucunu hesaplamak ve buna göre karar vermek için kullanıyor. Sonraki iki satırda `count` değeri sonuca ekleniyor ve `count` değeri 11 olana dek her seferinde 1 arttırılıyor.

Aynı programın JavaScript'le yazılışı:

```
let total = 0, count = 1;
while (count <= 10) {
  total += count;
  count += 1;
}
console.log(total);
// → 55
```
Bu şekli biraz daha ilerleme sağlıyor. En önemlisi artık programın ileriye ve geriye nasıl atlaması gerektiğini belirtmemiz gerekmiyor. `while` yapısı bunu hallediyor. Verilen koşul doğru olduğu müddetçe süslü parantezler içerisindeki bloğu çalıştırmaya devam eder. `count <= 10` olarak verilen bu koşul “_count_ 10'dan küçük veya eşitse” anlamındadır. Bu sayede geçici bir değişken tutup sıfırla kıyaslamamıza gerek kalmıyor. Programlama dillerinin güçlü yönlerinden biri de bu gibi gereksiz detayları bizim için halletmeleridir.

`while` döngüsü bittikten sonra programın sonunda sonucu yazdırmak için `console.log` fonksiyonu kullanılıyor.
 
Eğer bir aralıktaki sayılardan bir liste oluşturan`range` adlı bir fonksiyonumuz ve listedeki sayıları toplayan `sum` adlı bir fonksiyonumuz olsaydı programımız şöyle de olabilirdi.

```{startCode: true}
console.log(sum(range(1, 10)));
// → 55
```
Bu hikayede anlatılmak istenen, bir program uzun veya kısa, okunaklı veya okunaksız olarak farklı şekillerde ifade edilebilir. Programın ilk şekli ileri derecede anlaşılmazken, son şekli neredeyse İngilizce gibi: 1'den 10'a kadar olan sayıların toplamını yazdır. ([Sonraki bölümlerde](data) `sum` ve `range` gibi fonksiyonların nasıl tanımlanacağını göreceğiz.) 

İyi bir programlama dili, bilgisayarın yapması gereken eylemleri programcının daha yüksek seviyede ifade edebilme imkanlarını sunar. Detaylardan kurtararak `while` ve `console.log` gibi kullanılışlı yapılar sağlar ve sum ve range gibi kendi fonksiyonlarınızı tanımlamanızı ve farklı biçimlerde kolayca bir araya getirmenize izin verir.


## JavaScript nedir?

JavaScript 1995 yılında web sayfalarına programlar eklemek üzere Netscape Navigator web tarayıcısı içinde ortaya çıktı. Daha sonra diğer bir çok web tarayıcıda da kullanılmaya başlandı. Her kullanıcı eyleminde web sayfasının yeniden yüklenmesine gerek olmayan modern web uygulamalarının geliştirebilmesine imkan sağladı. Geleneksel web sitelerine çeşitli etkileşimli ve akıllı özelliklerin eklenmesinde de JavaScript kullanıldı. 

JavaScript'in Java programlama diliyle çok alakası olmadığını vurgulamak gerekir. Pazarlama kaygıları bu isim benzerliğinde etkili olmuştur. JavaScript ortaya çıktığında Java dilinin güçlü şekilde reklamı yapılmakta ve popülerliği artmaktaydı. Birileri bu rüzgarı arkasına almanın iyi bir fikir olacağını düşündü ve JavaScript ismi böyle kaldı.

Netscape dışında da kullanılmaya başlandıktan sonra, JavaScript desteklediğini iddia eden çeşitli yazılımların aynı dili konuşmalarını sağlamak için, dilin nasıl çalışması gerektiğini tarif eden standartlar belirlendi. Uluslararası Ecma organizasyonunun bu standartlaşmayı yapması sonrası buna ECMAScript standardı dendi. Pratikte ECMAScript ve JavaScript aynı dilin iki farklı adı olarak birbiri yerine kullanılabiliyor. 

JavaScript hakkında _korkunç_ şeyler söyleyecek olanlar vardır. Bunların çoğu da doğrudur. JavaScript'le ilk defa bir şey yazmam gerektiğinde kısa sürede ondan nefret ettim. Yazdığım herşeyi kabul ediyordu fakat benim kastettiğimden bambaşka bir anlamda yorumluyordu. Bu, ne yaptığımı bilmiyor olmamla çok alakalıydı elbette fakat burada gerçek bir mesele var: JavaScript absürt bir liberallikte, verilen herşeyi kabul ediyor. Bu tasarımın arkakasındaki ana fikir yeni başlayanlar için JavaScript'le programlamayı kolaylaştırmaktı. Hakikatte çoğunlukla programlarınızdaki hataları bulmanızı zorlaştırır çünkü sistem onları size göstermez.

Bu esnekliğin avantajları da vardır gerçi. Daha katı dillerde kullanımı mümkün olmayan birçok farklı tekniğe imkan sağlar. Örneğin [10. Bölün](modules)'de göreceğiniz üzere, JavaScript'in bazı yetersizliklerini aşmada da kullanılabilir. Dili iyice öğrendikten ve onunla bir süre çalıştıktan sonra, JavaScript'i gerçekten _sevmeyi_ öğrendim.  

JavaScript'in çeşitli versiyonları vardır. Yükselişe geçtiği  yaklaşık 2000 - 2010 yılları arasında yaygın olarak desteklenen ECMAScript 3. versiyonuydu. Bu süre zarfında, dilde radikal iyileştirmeler ve eklentiler planlanan iddialı 4. versiyonun çalışmaları devam ediyordu. Yaşayan ve yaygın bir dilde bu derece radikal değişikliklere gitmenin politik güçlükleri ortadaydı. 2008 yılında 4. versiyonun çalışmaları durduruldu ve 2009'da sadece tartışma konusu olmayan bazı iyileştirmelerle çıkacak olan 5. versiyona yol açıldı. Sonra 2015'te, 4. versiyonda planlanan bazı özellikleri de içeren 6. versiyon geldi. O zamandan beri her yıl küçük yeni güncellemeler gelmektedir.  

Dilin gelişiyor olması web tarayıcıların sürekli ayak uydurmak zorunda olması demek ve eğer eski bir web tarayıcı kullanıyorsanız bütün özellikleri desteklemiyor olabilir. Dili tasarlayanlar eski programların çalışmasını aksatacak yeni değişiklikler yapmama konusunda dikkatlidirler. Bu sayede yeni web tarayıcılar eski programları halen çalıştırabilmektedir. Bu kitapta JavaScript'in 2017 versiyonunu kullanıyorum.

JavaScript'in kullanıldığı tek platform web tarayıcılar değildir.
MondoDB ve CouchDB gibi bazı veritabanlarında script ve sorgulama dili olarak JavaScript kullanılır. Çeşitli masaüstü ve sunucu programlama platformları, özellikle Node.js projesi ([20. Bölüm](node)'ün konusu), JavaScript'i web tarayıcılar dışındaki ortamlarda kullanım imkanı sağlar.


## Kodlar hakkında

_Kod_ programı oluşturan metindir. Kitap birçok kod içermektedir. Kod okuyup yazmak programlamayı öğrenmenin ayrılmaz bir parçasıdır. Kod örneklerinin sadece üzerinden geçmeyip, dikkatlice okuyup anlamaya çalışın. Başlangıçta bu yavaş ve karmaşık gelebilir fakat çabucak kavrayacağınıza eminim. Alıştırmalar için de aynısı söz konusu. Gerçekten çalışan bir çözüm yazmadan anladığınızı düşünmeyin.

Alıştırma çözümlerinizi bir JavaScript yorumlayıcı üzerinde denemenizi öneririm. Bu sayede yaptığınız şeyin çalışıp çalışmadığını görebilirsiniz. Deneyimlemenin cazibesiyle alıştırmaların ötesine geçmenizi umarım.

Bu kitabı web tarayıcınızda okurken, bütün alıştırmaları üzerine tıklayarak düzenleyebilir ve çalıştırabilirsiniz.

Eğer kitaptaki programları kitabın sitesi dışında bir ortamda çalıştırmak isterseniz bazı noktalara dikkat etmelisiniz. Çoğu örnek, özel bir gereksinimi olmayan bağımsız uygulamalardır ve herhangi bir JavaScript ortamında çalışacaktır. Fakat ileriki bölümlerdeki çoğu kodlar belirli bir JavaScript ortamı (Web tarayıcı veya Node.js) için yazılmıştır ve sadece o ortamda çalışabilirler. Ek olarak bazı bölümler büyük programlar içerir ve buradaki bazı kodların diğer bazı kodlara ve harici dosyalardaki kodlara bağımlılığı vardır. [Sandbox](https://eloquentjavascript.net/code) sayfasından, her bölümdeki kodlar için gerekli scriptlere ve diğer dosyalara ulaşılabilir.

## Genel bakış

Bu kitap kabaca üç kısımdan oluşmaktadır. İlk 12 bölümde JavaScript dili incelenir. Sonraki yedi bölümde web tarayıcılar ve web tarayıcıların JavaScript ile programlanması hakkındadır. Son iki bölüm de farklı bir JavaScript programlama ortamı olarak Node.js'e ayrılmıştır.

Kitapta gerçek programlama hakkında fikir edinebileceğiniz beş _proje bölümü_ bulunmaktadır. Sırasıyla, bir [kurye robot](robot), bir [programmlama dili](language), bir [platform oyunu](game), bir [piksel boyama programı](paint) ve bir [dinamik websitesi](skillsharing) geliştirilmesi üzerinde çalışacağız.

Dil ile ilgili ilk dört bölümde JavaScript'teki temel yapılar tanıtılıyor. [Kontrol yapıları](program_structure) (girişte gördüğünüz `while` vb.), [fonksiyonlar](functions) (kendi yazacağınız yapı blokları) ve [veri yapıları](data) tanıtılıyor. Bunlardan sonra basit programları yazabileceksiniz. Sonra [5.](higher_order) ve [6.](object) bölümlerde daha _soyut_ kodlar yazarak karmaşıklığı kontrol altına alabilmeniz için fonksiyonları ve nesneleri kullanacağınız teknikleri öğreneceksiniz.

[İlk proje bölümü](robot)'ünden sonra, [hata yönetimi ve hata çözme](error), [düzenli ifadeler](regexp) (metinlerle çalışmada önemli bir araç), [modülerlik](modules) (karmaşıklığı önlemede önemli bir konu) ve [asenkron programlama](async) (zaman alan olayları yönetme) bölümleriyle devam ediliyor. [İkinci prpje bölümüyle](language) kitabın ilk kısmı tamamlanıyor.

İkinci kısımda [13.](browser) bölümden [19.](paint) bölüme kadar, web tarayıcıda JavaScript'le kullanılabilecek araçlar anlatılıyor. Nesnelerin ekranda nasıl gösterileceğini ([14.](dom) ve [17.](canvas)bölümler), kullanıcı girdilerine yanıt ([15. bölüm](event)) ve network iletişimini ([18. bölüm](http)) öğreneceksiniz. Yine bu kısımda da iki proje bölümü yer alıyor.  

Daha sonra [20.](node)bölümde Node.js anlatılacak ve [21.](skillsharing) bölümde Node.js kullanılarak küçük bir web sitesi geliştirilecek.

## Tipografik düzen

Bu kitapta program kodları `monospaced` fontla gösterilecektir. Örnek:

```
function factorial(n) {
  if (n == 0) {
    return 1;
  } else {
    return factorial(n - 1) * n;
  }
}
```

Bazen o kodun beklenen çıktısı hemen sonraki satırda, // -> karakterlerinden sonra gösterilecektir.

```
console.log(factorial(8));
// → 40320
```

Bol şans!
