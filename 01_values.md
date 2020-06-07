# Değerler, Tipler ve Operatörler

{{quote {author: "Master Yuan-Ma", title: "The Book of Programming", chapter: true}

Makinenin altında program hareket eder, zahmetsizce genişler ve daralır. Büyük bir uyumla elektronlar saçılır ve yeniden bir araya gelir. Monitör üzerindeki biçimler sudaki dalgalanma gibidir. Cevher içeride gizlidir.

quote}}


Bilgisayarın dünyasında sadece veri vardır. Veriyi oluşturabilir, okuyabilir, değiştirebilirsiniz. Tüm bu veriler uzun bit dizileri olarak saklanır ve temelde benzerdir.  

_Bitler_ iki değer olabilen, genellikle sıfırlar ve birler olarak tanımlanan şeylerdir. Bilgisayarın içerisinde, yüksek veya düşük voltaj, güçlü veya zayıf sinyal gibi biçimlerde ya da bir CD üzerindeki parlak veya mat nokta gibi olabilirler. Her türlü soyut bilgi parçası sıfır ve birler dizisine indirgenerek bitlerle ifade edilebilir.  

Mesela 13 sayısını bitlerle ifade edebiliriz. Ondalık sayı gibidir fakat elinizde 10 adet sayma sayısı yerine yalnızca 2 sayı vardır ve sağdan sola doğru her birinin ağırlığı 2'nin kuvvetleri şeklinde artar. 13 sayısını oluşturan bitler ve her bir basamaktaki ağırlıkları şöyledir:

```{lang: null}
   0   0   0   0   1   1   0   1
 128  64  32  16   8   4   2   1
```
Yani bu ikili sayı 00001101'dir. 0 olmayan basamaklar 8, 4 ve 1'i temsil eder ve toplam 13'tür.  

## Değerler

Derya dolusu bitleri düşünün. Modern bir bilgisayarın geçici hafızasında 30 milyardan fazla bit vardır. Kalıcı hafızasında (sabit disk vb.) bunun onlarca katı olabilir.

Bu çokluktaki bit arasında kaybolmammak için onları bilgi ifade eden parçalara bölmeliyiz. JavaScript ortamında bu parçalara _değer_ denir. Tüm değerler bitlerden oluşmuş olsa da rolleri farkldır. Her bir değerin rolünü belirleyen tipi vardır. Bazı değerler sayıdır, bazıları metin veya bazıları fonksiyon vb.

Bir değer oluşturmak için sadece onun adını belirtmeniz gerekir. Bu pratik bir şeydir. Bir değer oluşturmak için yapı malzemesi bulmanız ya da ücret ödemeniz gerekmez. Sadece birini çağırırsınız ve hoop elinizdedir. Havadan oluşmazlar elbette. Her değer bir alanda bulundurulmak zorundadır ve devasa sayıda değer kullanmak istediğinizde hafıza yetmeyebilir. Neyse ki bu ancak tümüne aynı anda ihtiyacınız olduğunda bir problemdir. Bir değeri kullanmayı bıraktığınız anda dağılır ve bitleri toplanıp yeni değerlere alan açmak üzere çöpe gider. 

Bu bölümde JavaScript'teki en temel elementler olan basit veri tipleri ve bu veri tipleriyle işlem yapılabilen operatörler anlatılacaktır. 

## Sayılar

_Sayı_ tipindeki değerler tahmin edilebileceği üzere sayısal değerlerdir. Bir JavaScript programında yazılışları aşağıdaki gibidir:

```
13
```
Bunu bir programda kullandığınızda 13'ü oluşturan bit dizisi bilgisayar hafızasında yerini alır.

JavaScript'te bir sayı değeri sabit olarak 64 adet bit içerisinde tutulur. 64 bitin farklı kombinasyonları ile ifade edilebilecek  sayılar bellidir. _N_ desimal basamak ile 10^N^ farklı sayıyı ifade edebilirsiniz. Benzer şekilde 64 ikilik basamak ile 2^64^ farklı sayıyı ifade edebilirsiniz ki bu yaklaşık 18 kentilyon (18'den sonra 18 sıfır) sayı demektir. Oldukça çok.

Bilgisayar hafızası önceleri daha küçüktü ve insanlar büyük sayıları 8'lik veya 16'lık bit grupları ile ifade etmek zorunda kalıyorlardı. Büyük sayılarda kazara bu alanın dışına _taşma_ çok kolaydı. Günümüzde cebimize sığan büyüklükteki bilgisayarlarda dahi oldukça büyük hafıza bulunmaktadır. Böylece 64 bitlik parçalar halinde hafızayı kullanabilir ve astronomik büyüklükteki sayılar dışında taşma sorunları konusunda rahat olabilirsiniz.

JavaScript sayı tipine 18 kentilyondan küçük tüm tam sayılar sığmaz aslında. Negatif sayılar da bu bitler içerisinde tutulduğundan bir bit sayının negatif veya pozitif olduğunu belirlemek için kullanılır. Diğer bir mesele de tam sayı olmayan diğer sayıların 64 bit ile ifade edilebilmesidir. Bunun için bazı bitler ondalık işaretinin yerini tutmak için kullanılır. Tutulabilecek asıl en büyük tam sayı 8 katrilyon civarındadır (15 sıfır) ki hala oldukça büyük.

Kesirli sayılar noktalı olarak yazılır. 

```
9.81
```
Çok büyük ya da çok küçük sayıları bilimsel notasyonla _e_ ve ardından sayının eksponentini ekleyerek te yazabilirsiniz.

```
2.998e8
```
Bu 2.998 × 10^8^ = 299,800,000 demektir.

Bahsi geçen tam sayılarla (integer da denir) yapılan hesaplamaların kesinliği garantidir. Kesirli sayılarla hesaplamalar maalesef her zaman kesin sonuç vermeyebilir. π (pi) sayısının sonlu sayıda basamakla kesin olarak gösterilemediği gibi, birçok sayının da kesinliği 64 bite sığdırırken kayna uğrar. Bu bir kusurdur fakat bu durum yalnızca belirli bazı durumlarda pratik problemlere yol açar. Önemli olan bu durumun bilincinde olmak ve kesirli sayıları kesin değil yaklaşık değer olarak kullanmaktır.

### Aritmetik

Sayılarla yapılan temel işlem aritmetiktir. Toplama veya çarpma gibi aritmetik işlemler girdi olarak iki sayı alır ve çıktı olarak bunlardan yeni bir sayı üretir. JavaScript'te bu işlemler şuna benzer:

```
100 + 4 * 11
```

`+` ve `*` işaretlerine _operatör_ denir. İlki toplama ikincisi çarpma içindir. Bir operatör iki değer arasına konularak işleme konur ve yeni bir değer ortaya çıkar.

Fakat bu örnek "4 ile 100'ü topla ve sonucu 11 ile çarp" anlamına mı gelir yoksa çarpma toplama işleminden önce mi yapılır? Tahmin ettiğiniz gibi önce çarpma gerçekleşir. Fakat matematikte olduğu gibi toplamayı paranteze alarak bunu değiştirebilirsiniz.

```
(100 + 4) * 11
```
Çıkarma `-`, bölme `/` operatörleriyle yapılır.

Çoklu işlemler parantezle ayrılmamışsa işlem sırası operatör önceliğine göre belirlenir. Yukarıdaki örnekte çarpmanın toplamadan önce geldiği görülmektedir. `/` operatörü `*` ile eşit önceliğe sahiptir. Aynı şekilde `+` ve `-` de. `1 - 2 + 1` işlemindeki gibi eşit önceliğe sahip birden fazla operatör ard arda geldiği zaman işlem sırası soldan sağa doğrudur: `(1 - 2) + 1`.  

Öncelik kuralları konusunda endişeniz olmasın. Kararsız kaldığınız zaman hemen parantez kullanın. 

Pek tanıdık olmayabileceğiniz bir aritmetik operatör daha vardır. `%` işareti _kalanı_ bulma işlemlerinde kullanılır. `X % Y` işlemi `X`'in `Y`'ye bölümünden kalanı verir. Örneğin `314 % 100`'ün sonucu `14`, `144 % 12`'nin sonucu `0`. Kalan operatörünün önceli sırası çarpma ve bölme ile aynıdır. Bu opeatöre _modulo_ dendiğini de sık sık göreceksiniz.

### Özel sayılar

JavaScript'te sayı olarak kabul edilen fakat sayı gibi davranmayan üç özel değer vardır.

İlk ikisi `Sonsuz` ve `-Sonsuz` pozitif ve negatif sonsuzluğu ifade eder. `Sonsuz - 1` de sonsuzdur ve bunun gibi. Sonsuzluk bazlı hesaplamalara çok fazla güvenmeyin. Matematiksel olarak bu çok sağlıklı değildir ve diğer bir özel sayı olan `NaN` ile sonuçlanması çok olasıdır.

`NaN` sayı tipine ait bir değer olmasına rağmen "sayı olmayan" anlamında kullanılır. `0 / 0`, `Infinity - Infinity` ya da anlamlı bir sonuç vermeyen diğer sayısal işlemlerde `NaN` sonucunu alırsınız.


## Strings

Sıradaki temel veri tipi _string_'tir. Stringler metinleri ifade etmek için kullanılır. İçeriği tırmak içerisine yazılarak tanımlanır.

```
`Down on the sea`
"Lie on the ocean"
'Float on the ocean'
```
Örnekte de görüldüğü gibi tek, çift ya da ters tırnak kullanabilirsiniz. Stringin başlangıç ve bitişinde aynı tırnak olmak kaydıyla.

Hemen hemen herşeyi tırnak içine koyabilirsiniz ve JavaScript bunları string değer olarak kabul eder. Fakat bazı karakterler biraz zordur. Tırnak içerisine tırnak koymanın güçlüğünü tahmin edebilirsiniz. String ters apostrof (`` ` ``) içerisinde yazıldığında _Yenisatır_ ([enter]{keyname} tuşuna basıldığında çıkan) karakteri doğrudan kullanılabilir. 

String içerisinde bu gibi karakterleri kullanabilmek için şu yöntem kullanılır: ters bölü (`\`) karakteri görüldüğünde bundan sonra özel bir karakter yazıldığı anlaşılır. Buna _escape_ karakteri denir. Önünde ters bölü olan bir tırnak işareti o string değerini bitişini ifade etmez, stringin içerisine dahil olur. Ters bölüden sonra `n` karakteri geliyorsa bu yeni satır olarak yorumlanır. Benzer şekilde `\t` tab karakterini ifade eder. Aşağıdaki stringe bakın:

```
"Bu ilk satır\nBu da ikinci satır"
```

Bunun asıl içeriği aslında şudur:

```{lang: null}
Bu ilk satır
Bu da ikinci satır
```

Özel bir karakteri göstermek dışında `\` karakterininin kendisini yazmanız gereken durumlar olabilir. İki ters slaş karakterini arka arkaya yazdığınızda yalnızca biri gösterilir. '_Yeni satır karakteri şöyle yazılır `"`\n`"`._' cümlesi şöyle yazılır: 

```
'Yeni satır karakteri şöyle yazılır \"\\n\".'
```

String değerler de bilgisayar içerisinde bit dizisi olarak tutulur. JavaScript bunu _Unicode_ adlı standarda göre gerçekleştirir. Standarda göre Yunanca, Arapça, Japonca, Ermenice vs. diğer dillerdekiler de dahil, varsayılan tüm karakterler numaralandırılmıştır. Her bir karaktere karşılık bir numara varsa string veri tipi bu numaralar dizisi olarak tanımlanabilir. Ve JavaScript'in yaptığı da budur. Fakat burada bir sıkıntı vardır: JavaScript her bir karakter 16 bit kullanır ki bu da 2^16^ farklı karakter demektir. Fakat Unicode standardında şu an için bunun yaklaşık iki katı farklı karakter vardır. Bundan dolayı emoji gibi bazı karakterler JavaScript'te iki birim karakter alanı yer tutar. [5. Bölüm](higher_order#code_units)'de bu konuya tekrar geri döneceğiz.

Stringlere bölme, çarpma veya çıkarma işlemi uygulanamaz fakat `+` operatörüyle birlikte kullanılabilirler. Bu toplama işlemi değildir fakat iki stringi birleştirir. Aşağıdaki satır `"birleştir"` kelimesini üretir:
```
"bir" + "leş" + "tir"
```  
String değerlere uygulanabilecek işlemlerle ilgili bazı fonksiyonlar (_metot_) da vardır. [4. Bölüm](data#methods)'de bunlardan da bahsedeceğim.

Stringlerin çift veya tek tırnak içerisinde yazılmasında pek fark yoktur. Tek fark string içerisinde geçen hangi tipteki tırnak işaretlerinin escape edileceği ile ilgilidir. Ters apostrof içerisinde yazılan, şablon yazım olarak ta ifade edilen stringlerin başka bazı becerileri de vardır. Birden fazla satırda yazılabilmelerinin yanında, bu stringlerin içerisine başka değerler de gömüebilir. 

```
`100'ün yarısı ${100 / 2}'dir`
```
Şablon yazım bir stringte `${}` içerisinde yazdığınız ifade JavaScript tarafından yorumlanıp stringe dönüştürülerek stringe yerleştirilir. Örmekteki string _100'ün yarısı 50'dir_ sonucunu verir. 

## Tekli operatorler

Tüm operatörler sembol şeklinde değildir. Bazıları kelimeler şeklinde yazılır. Örnek olarak `typeof` operatörü kendisine verilen değerin tipini verir.

```
console.log(typeof 4.5)
// → number
console.log(typeof "x")
// → string
```

Kod örneklerinde işlem sonuçlarını görmek için `console.log` metodunu kullanacağız. [Sonraki bölümde](program_structure) bununla alakalı daha fazla bilgiler verilecek.

Görmüş olduğunuz diğer operatörler iki değer alırlarken, `typeof` sadece tek değer alır. İki değer alan operatörlere _binary (ikili)_, tek değer alanlara _unary (tekli)_ operatörler denir. Eksi operatörü hem ikili hem de tekli olarak kullanılabilir.

```
console.log(- (10 - 2))
// → -8
```

## Boolean değerler

"Evet" ve "hayır" ya da "açık" ve "kapalı" gibi sadece iki olasılıklı değerler oldukça kullanışlıdır. Bu amaçla JavaScript'te sadece true ve false değerleri olan _Boolean_ tipi vardır. 

### Kıyaslama

Boolean değer üretmenin bir yolu şöyledir:

```
console.log(3 > 2)
// → true
console.log(3 < 2)
// → false
```
`>` ve `<` işaretleri bildiğimiz "büyüktür" ve "küçüktür" sembolleridir. Bunlar ikili operatörlerdir. Kullanıldıkları ifadenin doğru olup olmamasına bağlı olarak Boolean bir değer üretirler.

Stringler de aynı şekilde kıyaslanabilir.

```
console.log("Aardvark" < "Zoroaster")
// → true
```

Stringlerin sıralanışı aşağı yukarı alfabetiktir fakat sözlük sıralaması gibi değildir. Büyük harfler küçük harflerden "küçük'tür", yani`"Z" < "a"`. Ayrıca "!", "-" vb. alfabetik olmayan karakterler de sıralamaya dahil edilir. JavaScript stringleri kıyaslarken soldan sağa doğru tüm karakterleri tek tek Unicode koduna göre karşılaştırır.

`>=` (büyük eşittir), `<=` (küçük eşittir), `==` (eşittir) ve `!=` (eşit değildir) de benzer diğer operatörlerdir

```
console.log("Itchy" != "Scratchy")
// → true
console.log("Apple" == "Orange")
// → false
```

JavaScript'te kendisine eşit olmayan tek bir değer vardır o da `NaN` ("sayı değildir").

```
console.log(NaN == NaN)
// → false
```
`NaN` anlamsız bir hesaplamanın sonucunu belirtir ve _başka_ bir anlamsız hesaplamanın sonucuyla eşit değildir.

### Mantıksal operatörler

Boolean değerlerin kendisine uygulanabilecek bazı işlemler de vardır. JavaScript üç mantıksal operatörü destekler: _ve_, _veya_ ve _değil_. Bunlar Booleanlar ile mantık yürütmede kullanılabilir.

`&&` operatörü mantıksal _ve_'yi ifade eder. İkili bir operatördür ve yalnızca verilen her iki değer de true ise true sonuç verir. 

```
console.log(true && false)
// → false
console.log(true && true)
// → true
```

`||` operatörü mantıksal _veya_'yı ifade eder. Verilen değerlerden her hangi biri doğru olduğunda doğru sonuç verir. 

```
console.log(false || true)
// → true
console.log(false || false)
// → false
```
_Değil_ operatörü ünlem işareti (`!`) olarak yazılır. Verilen değerin zıddını döndüren tekli bir operatördür. `!true` ifadesi `false` ve `!false` ifadesi `true` sonuç verir.

Boolean operatörleri aritmetik veya diğer operatörlerle birlikte kullanmak gerektiğinde ne zaman perantez kullanmak gerektiği belirsizdir. Pratikte şu sıralamayı bilmeniz genellikle işinizi görecektir: `||` en düşük öncelikli, sonra `&&`, daha sonra kıyaslama operatörleri (`>`, `==`, vb.) ve diğerleri. Bu sıralama aşağıdaki gibi ifadelerin mümkün olan en az parantezle yazılabileceği şekilde seçilmiştir:

```
1 + 1 == 2 && 10 * 10 > 50
```
Göreceğimiz son mantıksal operatör ikili veya tekli olmayan, üç değerle işlem yapılan _ternary_ (üçlü) operatörüdür. Soru işareti ve iki nokta üstüste karakterleri kullanılarak şöyle yazılır:

```
console.log(true ? 1 : 2);
// → 1
console.log(false ? 1 : 2);
// → 2
```
Buna _koşullu_ operatör veya üçlü tek operatmr olması dolayısıyla _ternary_ operatör denir. ? işaretinin solundaki değer, diğer iki değerden hangisinin seçileceğini belirler. True olduğunda ortadaki, false olduğunda sondaki değer seçilir.

## Boş değerler

`null` ve `undefined` şeklinde yazılan iki özel değer vardır. Anlamlı bir değerin olmaması durumunu ifade etmede kullanılırlar. Değer olmakla birlikte her hangi bir bilgi içermezler.

Anlamlı bir sonuç üretmeyen bir çok işlem `undefined` sonucunu verir çünkü işlem sonucunda bir değer çıkmak zorundadır.

`undefined` ve `null` arasındaki fark JavaScript'in tasarımındaki kazara bir durum dolayısıyladır ve genellikle çok önemi yoktur. Bu değerlerle ilgilenmeniz gerektiğinde çoğunlukla her ikisini de aynı anlamda kullanmanızı öneririm.

## Otomatik tip dönüşümleri
Giriş bölümünde, garip sonuçlar üretse de JavaScript'in kendisine verilen her programı kabul ettiğinden bahsetmiştim. Bu duurum aşağıdaki ifadelerde net şekilde gösterilmektedir: 

```
console.log(8 * null)
// → 0
console.log("5" - 1)
// → 4
console.log("5" + 1)
// → 51
console.log("five" * 2)
// → NaN
console.log(false == 0)
// → true
```
Bir operatöre yanlış tipte değer verildiğinde JavaScript bazı kurallara göre onu sessizce gerekli tipe dönüştürür. Bazen bu beklemediğiniz bir tip olabilir. Buna _tip zorlaması_ denir.  İlk satırdaki `null` `0`, ikinci ifadedeki `"5"` `5` (stringten sayıya) olur. Hatta üçüncü ifadede `+` operatörü sayıları toplamadan string birleştirme işlemi yapmaya çalışır. Böylece `1` `"1"`'e (sayıdan stringe) dönüşür.  

Bir sayıyla eşleşmeyen birşey (`"five"` ya da `undefined` vb.) sayıya dönüştürüldüğünde `NaN` sonucunu elde edersiniz. `NaN` kullanılan aritmetik işlemlerin sonucu da `NaN` olacağından beklenmedik yerde bu sonucu aldığınızda hatalı bir tip dönüşümü işlemini araştırmalısınız.

Aynı tipteki değerleri `==` ile kıyasladığınızda sonucu tahmin etmek zor değildir: `NaN` olmamak kaydıyla her iki değer de aynıysa true sonucunu alırsınız. Fakat tipler farklı olduğunda JavaScript ne yapması gerektiğini belirlemek için karmaşık bir takım kuralları kullanır. Çoğu zaman değerlerden birini diğerinin tipine dönüştürmeye çalışır. Değerlerden biri `null` veya `undefined` olduğunda ancak diğer değer de `null` veya `undefined` ise true sonucunu verir.

```
console.log(null == undefined);
// → true
console.log(null == 0);
// → false
```

Bu çoğu zaman kullanışlı bir özelliktir.  Bir değişkenin gerçek bir değeri olup olmadığını test etmek istediğinizde onu `==` veya `!=` operatorlerini kullanarak `null` ile karşılaştırabilirsiniz.

Fakat ya bir değişkenin kesin şekilde `false` değerine işaret ettiğini test etmek istediğinizde? Otomatik tip dönüşümü dolayısıyla `0 == false` ve `"" == false` gibi ifadeler de true'dur. Bu gibi tip dönüşümlerinin yapılmamasını istediğiniz durumlar için iki operatör daha vardır: `===` ve `!==`. İlki bir değerin diğeriyle kesin şekilde eşit mi olduğunu test eder. İkincisi bir değerin diğeriyle kesin şekilde eşit olmadığını test eder. Yani `"" === false` ifadesi de beklendiği gibi false'tur.

Beklenmedik tip dönüşümlerinden sakınmak için üç karakterli kıyaslama operatörlerini kullanmanızı öneririm. Fakat iki tarafın da tiplerinin aynı olduğundan eminseniz daha kısa olan kıyaslama operatörlerini kullanmanızda bir sakınca yoktur. 

### Mantıksal operatörlerle kısa devre

`&&` ve `||` mantıksal operatörler farklı tipteki değerleri tuhaf bir yolla kullanırlar. 
Ne yapacağına karar vermek için sol taraftaki değeri Boolean tipine dönüştürürler fakat operatörün türüne ve tip dönüşümünün sonucuna göre soldaki değerin orjinal halini veya sağdaki değeri döndürürler.

Örneğim `||` opeatörü true'ya dönüştürülebiliyorsa solundaki değeri, dönüştürülemiyorsa sağındakini döndürür. Değerler Boolean olduğunda beklenen etki budur ve diğer tipler için de benzer bir durum gerçekleşir.

```
console.log(null || "user")
// → user
console.log("Agnes" || "user")
// → Agnes
```

Varsayılan bir değere geri dönme yöntemi olarak bu özelliği kullanabiliriz. Boş olması muhtemel bir değer söz konusu olduğunda ardına `||` ve varsayılan bir değer ekleyebilirsiniz. Eğer öndeki değer false'a dönüştürülebilirse varsayılan değer kullanılacaktır. String ve sayı tipierinin boolean tipine dönüşüm kuralları şöyledir:  `0`, `NaN` ve boş string (`""`) `false`, diğer tümü `true` sayılır. Yani  `0 || -1` `-1` sonucunu verir, `"" || "!?"` ise `"!?"`.

`&&` operatorü de diğer yönde benzer şekilde çalışır. Soldaki değer false'a dönüşebilen bir değerse soldaki, değilse sağdaki döndürülür.

Bu iki operatörün diğer bir önenmli özelliği de sağdaki değerin yalnızca gerekli olduğunda değerlendirilmesidir. `true || X` örneğinde `X` her ne olursa olsun sonuç true olacaktır ve `X` asla değerlendirilmeyecektir. `false && X` ifadesinde de aynı şekilde sonu false olur ve `X` dikkate alınmaz. Buna _short-circuit evaluation_ denir.

Ternary (koşullu) operatör de benzer şekilde çalışır. İkinci ve üçüncü değerlerden yalnızca seçilen değerlendirilir.

## Özet

Bu bölümde JavaScript'te dört tip değeri gördük: sayılar, stringler, Boolean ve tanımsız değerler.
Bu tip değerler adı yazılarak (`true`, `null`) ya da değeri yazılarak (`13`, `"abc"`) oluşturulurlar. Operatörleri kullanarak değerleri bir araya getirebilir ve dönüştürebilirsiniz. Aritmetik işlemler için ikili operatörleri (`+`, `-`, `*`, `/`, `%`), string birleştirme (`+`), kıyaslama (`==`, `!=`, `===`, `!==`, `<`, `>`, `<=`, `>=`) ve mantıksal (`&&`, `||`) opeatörleri gördük. Ayrıca çeşitli tekli (unary) operatötleri (`-` sayının negatifi, `!` mantıksal zıddı, tip belirlemek için `typeof`) ve koşulun sonucuna göre iki değerden birini seçmek için üçlü (`?:` ternary) operatörünü gördük.

Bu JavaScript'i bir hesap makinesi gibi kullanma becerisini verir fakat daha fazlasını değil. [Sonraki bölüm](program_structure)'de bu ifadeleri bir araya getirerek basit programlara başlayacağız. 
