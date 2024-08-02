# C++-Kursu-Notları-


# 13 Ocak 1. C++ Dersinden Notlar; 

2011 yılından önceki C++’a ancient c++ diyenler de var. 
Modern c++ deniyor, bundan sonraki standardlara. Her yeri standard dile yeni araçlar ekliyor, bazı değişiklikler yapılıyor, deprecate ediliyor ve dilden çıkarılıyor. 

Dilin temel 2 niteliği var. 
Sentaksı (dilin kurallarına ilişkin)
Semantik hatası (anlamsal kısmı)

Birincil amaç c++ developer olmak, domainden bağımsız. 

Ileri C++’da idiomatic yapılar anlatılıyor. 
C++ verim odaklı bir dil. İşlemci zamanını iyi bir şekilde kullanabileceğimiz bir dil. Bunu sağlıyor aslında. 


Bir programlama dilinin mükenmmel olduğunu iddia eden biri varsa ya aptaldır ya da size bir şey satmaya çalışıyordur. Her programlama dilinin iyi ve kötü yönleri var. 
Linus torvalds c++’a düşman. Çok kötü bir dil olduğunu söylüyor. Ken Thompson da aynısını söylüyor. Allen key 
Hiçbir dil mükemmel değil fakat c++ bir gerçek. Kullanıldığı alanlarda bir hakimiyeti var. Bu diller çok uzun süre varlıklarını devam ettirecekler. Ekosistemleri çok geniş. 

Optimizasyon çok geniş bir konu. Optimizasyon derken birden fazla kavram işin içine giriyor. Compiler optimization, hayati bir önem taşıyor. As if rule ne demek ? observable behavior ne demek ? Çok çok önemli. 
Compiler optimization şu demek ? c ve c++ derleyicileri sizin yazdığınız kodları farklı şekilde ele almış olabilirler. Çalıştırılabilir program gözlenebilirlik açısından bir fark meydana getirmiyorsa istediği değişikliği yapabilir. Derleyici daha etkin assembly veya makine kodu üretebilmek için optimizasyonlar yapıyor. Derleyicilerin optimizer modülü yapıyor bunu. 

LTO aracı var, link time optimization
İşlemci tarafından yapılan optimizasyonlar da var. 
Derleme zamanında yapılan optimizasyonlar var. 
Link zamanında yapılan optimizasyonlar var. 

Mikro düzeyde optimizasyon bizim işimiz değil. 

C++ ağırlıklı olarak generic programlama dili, türden bağımsız olması demek. Derleyici derleme aşamasında kod seçme avantajına sahip. Bir konteynırda tutulan öğeleri başka bir yere kopyalamak gerekiyor. Kopyalama işlemini memcpy fonksiyonuna çağrı yapacak bir koda dönüştürebiliyor. 
Dilin bu şekilde araçları var. 

Konteyner veri yapılarını temsil eden sınıflara verilen isim. 
Kesinlikle hakim olmanız gereken bir şey var ; Terminoloji. 
Undefined behavior, value category, implementation defined behavior gibi vs.
C++’dan bahsedelim. 
Const correctness nedir bunu bir araştır. 

C++ ayrı bir disiplin. Ayrı bir uzmanlık alanı. Çok ciddi bir yatırım. 160 saatlik bir de ileri c++ kursu var. 
Dilin küçüklüğü büyüklüğü derken neyi kastediyoruz ? Araç sayısını kastediyor Necati hoca. Çok fazla araca sahip olmasının sebebi de multi paradigm olması. 

C++ dili nesne yönelimli programlama dili demek yanlıştır.  C++’ın temel varlık nedenlerinden biri çok paradigmalı olması. 
Prosedürel olmalı
Nesne yönelimli programlama
Fonksiyonel programlama
Generic programlama

Multi paradigm bir dildir. Bu sebepten dolayı araç sayısı çok fazla. C++’ı zorlaştıran nedenlerden biri bu. 
C++ dilinin oluşturduğu şöyle bir anksiyete var. İşlemi gerçekleştirmek için alternatif çok fazla. 

Türkiye’de C++’ın en çok kullanıldığı domain gömülü yazılım. 
Dilin büyük olmasının 2. Niteliği standard kütüphanesinin büyüklüğü. Standard kütüphane de sürekli büyüyor. 

![image](https://github.com/user-attachments/assets/64528c63-e0d7-43a4-9f78-71a2ba304bb1)

C++ 11, modern C++’ın başlangıç noktası
Minimal C++ bizim için C++ 17

Modern C++ ne getirdi ? 
Bir kere dilde kod yazmak daha kolay hale geldi. Dil büyüdü ama daha kolay hale geldi. Derleyici daha fazla iş yükleyen araçlar eklendi. Dilin çekirdek sentaksında yapılan değişikliklerle kod yazmak daha kolay hale geldi. 
Derlenen kodlar daha verimli hale geldi. Efficiency arttı. 
C++ 98’e göre yazılmış bir kodu modern c++’ı destekleyen bir derleyicide derlediğinizde kodda bir değişiklik yapmadığınız halde daha hızlı çalışıyor. 


Güvenlik ( kodlama hatası yapma riski), azaldı. Modern araçlar programcının yapabileceği hataların riskini de azalttı. Eskiye göre azalttı. 

Kod kalabalığı (verbosity).
Bizim minimal base’imiz C++17

Legacy kod (miras kod), yazılan eski kodlar. Code base eski c++ ile yazılmış. Zaten çalışıyor, dokunma. Modern c++’a aktarmak için risk almak istemiyorlar firmalar. 

Yeni bir projeye başlarken tercihimiz C++ 20 olmalı. 
C++ 23 henüz derleyiciler tarafından implement edilmedi. 

Dile eklenen araçlar olduğu gibi dilden çıkarılan araçlar da var. 
Deprecation, önce bir sentaks özelliği deprecate ediliyor.  Standard diyor ki, bu araç ileriden dilden tamamen kaldırılabilir. Bu bir tavsiye, sen en iyisi kullanma. 

gets - deprecate edildi ve dilden kaldırıldı. (C programlama dilinde.)

cppreference sürekli kullanılması gereken bir site. Cppreference’nin dili standardlar kadar ağır ve formal değil. 
 
Derleyiciler backward compatibility ile geriye dönük uyumluluk sağlıyorlar. 
Standardın ne söylediği ayrı derleyicinin tutumu ayrı. 

C++ dilinin %70’ine hakim olduğunu söylüyor, Bjarne Stroustrup. 
C minimalist bir dil. Poor man’s language 😀

İyi bir öğrenme metodolojisi + sistematik bir çalışma, başarının sırrı. 
İyi bir C++ kodu yazmak apayrı bir konu. 

Kod kalitesi ile ilgili yol gösterebilecek çok fayda araç var. Mesela SonarQube
Gerçekten o toolları küçümsemek istemiyorum ama bu biraz da programcının bilgi seviyesi ile ilgili. 

Başlangıçta dilin ismi C++ değildi. 
C with classes’dı. 
Amacı C’ye ilaveler yaparak dilin gücünü yükseltmek. 
Zaman içinde Hem C diline hem C++ diline yapılan eklemeler ile arasındaki uyuşmazlıklar arttı. Ayrışmalar arttı. 
C dili ile C++ dili arasındaki farklılıklar 

Önemli terimler; 

Observable behavior 
Undefined behavior ile compiler optimization arasındaki ilişki nedir ? 

Undefined behavior nedir ? tanımsız davranış, kodun niteliği. Kodu niteleyen bir durum. Derleyicinin herhangi bir şekilde hiçbir garanti olmadan istediği şekilde kod üretebilir. Kabul edilebilir bir kod değil, ne olacağının bir garantisi yok. Kod çalışırken kodun programcının istediği gibi çalışması da ihtimaller dahilinde. Tanımsız davranış her şey olabilir demek. 
All bets are off. Öngörülebilir bir senaryo yok.
Race condition, iyi huylu olabilir, tanımsız davranış olmayabilir. 
Data race, tanımsız davranış kesinlikle. 

Yeni tanımsız davranış durumları da standarda sonradan eklenebilir. 
C++ 17 öncesinde tanımsız davranış olan kod C++ 17’den sonra defined code olabilir. 
Tanımsız davranış durumunda, monitörden dumanlar çıktığını görmüşlüğüm var. 

NULL pointerı dereference etmek….
İşaretli tam sayı türlerinde taşma.. İşaretsiz tam sayı türlerinde taşma tanımsız davranış olmaz. Lojik bölme idi sanırım, bu şekilde kontrol var. 

C++ dilinde de tanımsız davranışları öğrenicez. 
Tanımsız davranışın felsefesi ne ? bütün davranışların tanımlı olması programlama dilinin genelliğini bozan bir özellik. 
Tanımsız davranış compiler optimization ile önemli bir ilişki içinde. 
C ve C++ derleyicileri, compiler optimization sürecinde optimizasyon tekniklerini yaparken kodda tanımsız davranış olmamasına güveniyor. 

Derleyicilerin switchleri var. Debug sürecinde optimizasyon yapılmasını istemeyiz. Derleyicinin yaptığı optimizasyonu görebilmek için assembly bilmek gerekir. Godbolt’da kullanabilirsin. 

Unspecified behavior (belirlenmemiş davranış): 

Bir hata durumu olmak zorunda değil. Unspecified behavior, derleyici farklı şekilde kod üretme şansına sahip. Öyle de üretebilir böyle de üretebilir. Unspecified behavior’a göre kod yazıyorsunuz bunun bilincinde olarak yazman lazım. 

![image](https://github.com/user-attachments/assets/3df8f71f-5061-4bb4-bded-d748ee7f5af1)

Run time’da f2 daha önce çağrılır mı ? çarpma operatörünün önceliği toplama operatörünün önceliğinden daha yüksek diye. 
Bu yanlış.

Hangisinin daha önce çağrılacağı konusundan bir garanti yok.  Bunun farkında olmadan yazarsan lojik hata olmuş oluyor. Hangisinin çağrıldığının bir önemi yoksa sorun yok. 

Derleyici 2 farklı şekilde kod üretebilir. 
Derleyicinin x biçiminde kod ürettiğine güvenerek kod yazdıysanız ama y biçimde kod ürettiyse bu lojik hata. 

Implementation defined behavior,

Her implementation defined behavior bir unspecified behaviordur. Tam tersi geçerli değil 😀
Seçimini dokümante etmek zorundadır. 
Farklı derleyici aynı seçeneği tercih edip aynı kodu üretmiş olmayabilir. 




C’de 3 tane char türü var. 
signed char
unsigned char 
char

Implementation defined, derleyiciye bağlı. 


C++’ın içinde bir C çekirdeği var. C++’ın içindeki C çekirdeği, bu C çekirdeği better C. Bjarne’nin tanımı ile. 

C ile C in C++, eskiden aralarındaki uyuşmazlık daha azdı. Standartlar ile uyumsuzluklar arttı. 

C ve C++’da statik tür sistemine sahip. 
Python gibi bir dilde yazdığınızı düşünelim. Değişkenlerin tuttuğu değerlerin türü dinamik olarak değişiyor. Bildirimlerle değişkenlerin ne türde değer tutacağını söylemiyorsunuz. Dinamik olarak değişiyor. 

Statik tür sistemine sahip olması derleyicinin, çeviri aşamasında derleyicin yaptığı kontroller artırıyor ve hataların derleme zamanında tespit edilmesini sağlıyor. Dinamik tür sistemine sahip programlama dillerinde bu hatalar run time’da tespit edilebiliyor. 

Statik tür kontrolü
Weak
Strength 

C++ çok daha sıkı bir tür kontrolü uygular.
C dilinin kurallarına göre legal olan derleyicinin diagnostic vermesi gerekmeyen durumlarda C++ derleyici uyarı verebilir. 

![image](https://github.com/user-attachments/assets/92559c0c-99a1-4a85-a9a2-849aa5a3981e)

C’de legal 
C++’da sentaks hatası. 
C++’ın küçük bir dil olma kaygısı olmadığı için kontroller daha sıkı.  
C deki tür kontrolü zayıf, C++’da güçlü. 


```c++
‘A’ , character constant
```
Bu ifadenin türü ne ? C’de işaretli int türü. 
C++’da bu ifadenin türü char. 

Farklı kurallar içeriyor. 



```c++
int * = malloc(n*sizeof(int));

```

C’nin kurallarına aykırı bir durum var mı ? hayır. 
Malloc fonksiyonuna yapılan çağrıdan elde edilen geri dönüş değeri türü void* ama initialize edilen int * 
Tür dönüştürme operatörü kullanmak zorunda değilsiniz. Örtülü dönüşüm var. 

C++’da sentaks hatası. void* türünden int* türüne örtülü dönüşüm yok. 

```c++
char str[4] = “mert”;

```

C’de sentaks hatası yok. Null terminated by stream değil. Dolayısıyla bu diziyi kullanırken sonunda null karakteri olmadığını bilerek kullanırsan sıkıntı yok. Aksi taktirde ub

C++’da bu kod direkt sentaks hatası. Null karakter bir karakter sabiti, değeri 0 olan bir karakter sabiti. 


Fonksiyon Tanımlamaları: 

C’de implicit int kuralı geçerli. 
C++’da bu sentaks hatası. C++’da implicit int hiçbir zaman geçerli olmadı. İmplicit int C++’da geçerli değil. 

C programlamada

```c++
unsigned x = 5; 
unsigned int x = 5; yazmak arasında hiçbir fark yok. 

```
int unsigned yazsan da aynı. 
Aynısı C++’da da geçerli. Burada bir farklılık yok. 


C’de old style function denilen eskiden gelen ama derleyicilerin halen destekleri bir fonksiyon tanımlama sentaksı var. 

```c++
double foo(a,b,c)
double a,b,c;
{
	return a + b + c;
}

```
Bazı programcılar böyle bir tanımlama sentaksı olduğunun bile farkında değiller. Buna old style function definition deniyor. C’de geçerli, backward compatibility için geçerli.

C++’da old style function definition asla olmadı. 

```c++
foo(a,b,c)
{
	return a + b + c;
}

```
Bu kod C’de geçerli.Enteresan 😀  İmplicit int var. 


# 14 Ocak 2. C++ Dersinden Notlar; 

C++ içindeki C ile bağımsız C arasındaki sentaks düzeyindeki farklılıklarını incelemeye başladık. 
Old style function definition sentaksı C dilinde hala geçerli, derleyicilerin geriye dönük uyumluluk sağlaması sebebiyle (backward compatibility). Eski kodlarda karşımıza çıkabilir. 
C++ dilinde hiçbir zaman geçerli olmadı. 

İmplicit int C++ dilinde geçerli değil. C’de de kaldırıldı ama backward compatibility adına derleyiciler hala destek veriyor. 

Derleyici bir ismi arayıp name lookup yapıp o ismi bulamazsa sentaks hatası. 

```c++

int main(void)
{ 	
	foo(3,5);
}
```
C dilinde derleyici uyarı verir. 
Compiler Diagnostic: foo undefined, assuming extern returning int


Dolayısıyla sentaks hatası oluşturmuyor. Fakat C++ dilinde bu kural hiçbir zaman geçerli olmadı. 
Eğer derleyici tarafından aranıp bulunamıyorsa doğrudan sentaks hatası. 
Derleyici burada name lookup hatası verecek. 

Name lookup (isim arama): 
Derleyici bir ismi arayıp bulamazsa normalde sentaks hatası olması gerekir. Fakat o ismin fonksiyon çağrı operatörünün operandı olduğunu gördüğünde bureadkai ismin bir başka modülde bildirimiş (external tanımlanmış) bir fonksiyon ismi olduğunu varsayıyor. Buna default function decleration deniyor. Bu istediğimiz bir özellik değil. C'nin eski zamanlarında kalmış bir özellik. 
Derleyici bu kod için C dilinde sadece bir uyarı verir. 
Compiler Diagnostic: foo undefined, assuming extern returning int
Bu şu demek aslında C’de. C dili diyor ki, eğer böyle bir bildirim yoksa default function declaration aslında şu demek. Derleyici sanki böyle bir fonksiyonun bildiriminin varlığına güveniyor. 

C++ dilinde bu kural hiçbir zaman geçerli olmadı. C++ dilinde bir isim neyin ismi olursa olsun derleyici tarafından aranıp bulunamıyorsa doğrudan sentaks hatası. Fonksiyon çağrı operatörünün operandı olması bu durumu değiştirmiyor. 
C++ derleyicisi burada name lookup hatası verecek. 

```C++
void foo();
```
Bu function prototype. 
Bu bildirimde foo fonksiyonun kaç tane parametre değişkeni olduğu söyleniyor ? 
C dilinde bir fonksiyonun bildiriminde veya tanımında parametre parantezinin boş bırakılması fonksiyonun parametre değişkenine sahip olmadığı anlamına gelmiyor. Fonksiyon parametre değişkeni hakkında bilgi verilmiyor sadece. Fonksiyonun parametre değişkeni yok anlamı söz konusu değil. 

```C++
void foo(void);
```
Bu fonksiyonun parametre değişkeni yok. 


C dilinde fonksiyon bildirimlerinde parametre parantezinin içinin boş bırakılması ile void yazılması arasında fark var. C++ dilinde böyle bir fark yok. C++ dilinde boş bırakmakla, void anahtar kelimesini yazmak arasında hiçbir fark yok. 

void foo() → foo’nun parametre değişkenleri hakkında bilgi verilmediği anlamına geliyor C programlama dilinde. 
C++’da parametre değişkeni olmadığı anlamına geliyor. 






































# 11 Şubat 10. C++ Dersinden Notlar; 

constructor initializer list CIL
Member initializer list MIL
constructor sınıfın non static veri elemanlarını initialize ediyordu.
Constructorın içinde ana bloğunun içinde veri elemanları kullandığıız zaman onlar hayata gelmiş durumda. 

Mümkün olduğunca elemanları initialize etme görevini üstlenmesi gerektiğini söyledik. 
constructor sınıfın non static veri elemanlarını initialize eder. 

Constructorın ana bloğunun için veri elemanları kullandığınız zaman onlar hayata gelmiş durumda. Myclass sınıfın constructorlarından biri, program akışı buraya geldiğinde tüm veri elemanları hayata gelmiş demektir. Ilk değer vermiyorsunuz atama yapıyorsunuz.

```c++
class Myclass{

public:
	Myclass()
	{
		mx =
	}
};

```
Elemanları initialize etme görevinin constructora verilmesi iyi bir fikirdir. 

Elemanların ilk değer alma sırasını belirleyen kriter, sınıf içindeki bildirim sırasıdır. Bildirim sırasını korumakta fayda var. Özellikle elemanlar birbirini initialize etmede kullanılıyorsa yanlış bir sıralama bazı veri elemanlarının çöp değerle kullanılması sonucunu doğurabilir. 

Önemli sentaks öğelerinden biri daha default member initializer, eğer veri elemanları derleme zamanında hangi değerle hayata gelecekleri belliyse in class initializer sentaksını kullanıyoruz. Bu ilk değer verme değil, eğer derleyicinin yazdığı default constructor ya da bizim yazdığımmız constructucor herhangi bir şekilde bu veri elemanını initialize etmezse default olarak bu değerle initialization kodunun eklenmesini istiyoruz. 

```c++
class Myclass{

public:
private: 
	int mx{10};
};

```

```c++
class Myclass{

public:
private: 
	int mx = 10; 
};

```

Parantez tokeni burada kullanılamıyor. 
Default member initializer modern c++ ile dile eklenen araçlardan biri. 
Ilk defa special member functions terimini kullandık. 

Special member functions, sınıfların özel üye fonksiyonları. 
Bu kategorideki fonksiyonların kodları belirli şartlar sağlandığında derleyici tarafından yazılabiliyor. Derleyicinin özel üye fonksiyonunun kodunu yazmasına o fonksiyonu default etmesi denir. 
Special member functions, öyle fonksiyonlar ki defaulted by the compiler. Kodları derleyici tarafından yazılır. 

6 tane özel üye fonksiyon var. 4’ü eskiden de vardı ama 2 tanesi modern C++ ile dile eklendi. 
İsminde move geçenler C++ 11 ile dile eklendi.

Sınıfların özel üye fonksiyonları : 
- Default ctor
- Destructor
- Copy ctor
- Move ctor ( Modern cplusplus ile eklendi) (C+11 standardı ile dile eklendi)
- Copy assignment
- Move assignment ( Modern cplusplus ile eklendi)(C+11 standardı ile dile eklendi)


Durumları (Stateleri) ne olabilir ? 

User declared -> fonksiyonun programcı tarafından bildirilmesi 
İmplicitly declared -> programcı tarafından yapılan bir bildirim olmamasına rağmen derleyicinin dilin kurallarına dayanarak fonksiyonun bildirimini yapması
Not declared -> fonksiyonun olmaması

User declared olması durumunda programcı tanımlamak üzere bildirimini yapmış olabilir, bildirimini derleyici yapsın diye yapmış olabilir, bildirimini bunu çağırmak sentaks hatası olsun diye yapmış olabilir
İmplicitly declared olması durumunda derleyici örtülü olarak fonksiyonu bildirmiş olabilir. 

Bu fonksiyonlara ilişkin aldığınız hata mesajlarına dikkat etmeniz gerekiyor. 

Taşıma semantiği ile de ilk defa karşılaşıcaz. R value referansın varlığı büyük ölçüde taşıma semantiği ile ilgili. 
En çok yanlış anlaşılan konulardan biri taşıma semantiği. Mülakatlarda da çıkar. 

Copy Constructor:  (kopyalayan kurucu işlev) 
Sınıfın bir üye fonksiyonu ama özel bir üye fonksiyonu. Belirli şartlar sağlandığında derleyici bizim yerimize copy constructor kodunu yazacak. Copy constructor default edilebilen bir özel üye fonksiyonu çünkü special member function. 
- Derleyici örtülü olarak bildirip kendisi default edebilir 
- User declared olur ama ben derleyicinin kendisi yazmasını isteyebilirim

Neden buna copy constructor deniyor ? cpp de öyle yerler var ki bir sınıf nesnesi hayata değerini aynı türden bir başka sınıf nesnesinden alarak hayata geliyor.  

Elinizde bir sınıf nesnesi var fakat siz yeni bir sınıf nesnesi hayata getirmek istiyorsunuz, aynı state de aynı değere sahip bir nesne olsun. Mustafa değerini necatiden alarak hayata gelsin. Bu en sık kullanılan nesne oluşturma biçimlerinden biri. Hayata getirilecek nesnenin değerini başka bir sınıftaki nesneden alıyor. 

Biri açık initialization sentaksı. 

Nec y;

Nec x = y; 
x için çağrılacak fonksiyon copy constructor’dur. 
Her nesne hayata geldiğinde constructor ile hayata getiriliyor. Ama değerini aynı türden başka bir nesneden alarak hayata geliyorsa onun için çağrılacak fonksiyon copy constructor. 

Boolean sorular; 

Burada hayata gelen nesne hangisi ? x
Copy constructor hangisi için çağrılacak ? x


Copy constructor’un x’i hayata getirirken onu y’nin değeriyle hayata getirmesi için y’ye de erişmesi lazım değil. İşte bu yüzden copy constructor’un bir parametresi olması gerekiyor. Y’yi alabilecek bir parametresi olması gerekiyor. 
Burada y değişecek mi ? y’yi değiştirmeye yönelik bir işlem yok. Y’yi salt okuma amaçlı erişicem. Yani const L value reference parametre idealdir yani. 

```c++
class Nec {
public:
	Nec(const Nec& other)
	{
	mx // x’in mx’i;
	}
}

```

Bu şekilde bildirilen bir fonksiyon sınıfın copy constructor’ı
Bu fonksiyonun içinde this kimin adresi olacak ? x’in 

copy constructorun çağrılacağı diğer senaryolar, copy initialization yapabildiğimiz gibi direkt initialization sentkasını da kullanabiliriz 

```c++
class Nec {
public:
	Nec(const Nec& other);
	
}

Nec x1 = y;
Nec x2(y);
Nec x3{y};

```
x1 , x2,x3 copy constructor ile hayata gelecek. 

auto x1 = y;

auto x2 (y);

auto x3{y};

Bu şekilde de yazılabilir. 

cc —:> copy constructor 

cctor —> copy constructor

cc sadece bu senaryoda mı çağrılıyor ? bir nesnenin değerini bir başka nesneden alarak hayata geldiği senaryolardan biri de fonksiyon çağrıları. 

```c++
class Nec {
 //..
}

void foo(Nec x)
{
}

int main()
{
Nec nec;
foo(nec);
}
```

Bu fonksiyonun çağrılması durumunda -başka bir özel durum yoksa, ileride ele alacağımız-  fonksiyonun parametre değişkeni hayata değerini aynı sınıf türünden bir nesneden alarak gelmeyecek mi ? cc çağrılacak. İşte cc’nun çağrılacağı en tipik senaryolardan biri 
Bir fonksiyonun parametresinin sınıf türünden olması ve o fonksiyonun bir sınıf türünden bir L value expression ile çağrılması argüman olarak. 

Bir klasik durum daha var. 
Diyelim ki bu seferde tam tersi fonksiyonun geri dönüş değeri bir sınıf türünden. Siz bu fonksiyonun return statement’inde return ifadesi olarak bir sınıf nesnesi kullanıyorsunuz. Eğer bu durumda derleyici ileride göreceğimiz önemli bir optimizasyonu yapacak durumda değilse bu fonksiyonun geri dönüş değerininin çağrılan koda aktarılması için cc çağrılacak. 

```c++
class Nec {
 //..
}

Nec bar()
{
	return nec; 
}

int main()
{
Nec mynec = bar();
}
```
cc special member function olduğu için kodu derleyici tarafından yazılabilir. 

Bir sınıfın kodunu yazalım. 

```c++

class Nec {
public: 
	Nec()
	{
	std::cout << “Nec default ctor this : << this <<’\n’;
	}
	
	~Nec()
	{
	std::cout << “Nec destructor this : << this <<’\n’;
	}
};

int main()
{
	Nec x;
}

```

Aynı adres. 

Ama şimdi bakın. 

```c++
class Nec {
public: 
	Nec()
	{
	std::cout << “Nec default ctor this : << this <<’\n’;
	}
	
	~Nec()
	{
std::cout << “Nec destructor this : << this <<’\n’;
	}
};

int main()
{
	Nec x;
	{
	Nec y = x; 
	}
std::cout << “main devam editor\n”;
(void)getchar();
}
```

Default cc x için çağrıldı. 
This pointerları aynı değil. Y nesnesi için destructor çağrıldı. 
Main bloğunun sonunda x’in destructoru çağrılacak. 

Peki y nasıl hayata geldi ? cc ile. Ee peki ben cc ben yazmadım. Derleyici yazdı. Derleyici default etti. 
Sınıfın special member functionları bazı şartlar sağlandığında derleyici tarafından örtülü olarak bildirilip tanımlanabiliyor. 

cc’u kendim tanımlasaydım bizim tanımladığımız çağrılacaktı. 

```c++
#include <iostream>


class Nec {
public:
   Nec()
   {
   std::cout << "Nec default ctor this :" << this <<'\n';
   }


   Nec(const Nec& other)
   {
   std::cout << "Nec copy ctor this :" << this <<'\n';


   }
  
   ~Nec()
   {
   std::cout << "Nec destructor this :"  << this <<'\n';
   }
};


int main()
{
   Nec x;
   {
   Nec y = x;
   }
std::cout << "main devam editor\n";
(void)getchar();
}

```
Derleyici belirli koşullar sağlandığında sınıfın özel üye fonksiyonlarının kodunu yazıyor. 
Eğer bir fonksiyonun kodunu derleyici default ederse derleyici nasıl bir kod yazıyor ? 

Bu soruyu her bir özel üye fonksiyonu için sorduğumda ve cevapladığımda şu yapıyı kullanıcaz. 
```c++
class Myclass {
public:
	Myclass()
	{
//derleyici kodu buraya yazıyor.
	}
private:
	T tx;
	U ux;
	W wx;
};
```
Derleyici sınıfa default cc’yı kendisi yazarsa derleyicinin kendisi yazdığı special member function olan default copy constructor sınıfın public, non static, inline üye fonksiyonu. 

dc sınıfın her zaman public, non static, inline üye fonksiyonu. (default constructor)
Derleyicinin yazdığı dc, sınıfın veri elemanlarını default initializer ediyor. 

Eğer derleyici bir sınıfın bir özel üye fonksiyonunu örtülü olarak bildirip tanımlama girişiminde bulunduğunda eğer dilin kurallarını çiğneyen bir durum oluşursa derleyici default edeceği özel üye fonksiyonu delete edilmiş olarak bildirir.

```c++
Myclass = delete();
```
Ya elemanlar default initialize edilemiyorsa ? elemanlardan biri const ise ? sentaks hatası oluşacak. Derleyici delete edilmiş olarak bildirilecek. 

```c++
class Myclass {
	const int x ;
};
```
Bu kodda bir sentaks hatası var mı ? Hayır

Bu sınıfın default constructorı deleted edilmiş durumda. Derleyici implicit declared durumda, x’i default initialize ediyor ama const nesneler default initialize edilemediği için sentaks hatası oluşacak. 

Ne zaman sentaks hatası alırım ? delete edilmiş fonksiyon çağrıldığında. 
```c++
class Myclass {
	const int x ;
};

int main()
{
Myclass m;
}
```
Attempting to reference a deleted function

class Myclass {
	int &r;
};
```c++
int main()
{
Myclass m;
}
```
Burada da aynı durum geçerli. 


Sentaks hatası olmasının sebebi Caner’in default constructorunun private olması. 

Eğer siz sınıfa herhangi bir constructor bildirirseniz derleyici default constructorı bildirmez. Bu bir kural. Tasarımsal bir kural. 

```c++
class A{
public:
	A(int);
}

```
A sınıfın default constructoru hakkında ne söylersiniz ?
Cevap yok . neden çünkü ben bir copy constructor yazdım. 

```c++
class A{
public:
	A(const A&);
}

```

Bu constructora ne deniyor ? 
Copy constructor. bu sınıfın default constructoru var mı ? hayır yok. 
Ben bir constructor bildirirsem derleyici default constructor implicitly declared yapmıyor. 

Destructorun not declared olma ihtimali yok. 

Bir fonksiyonun delete edilmesi onun olmadığı anlamına gelmiyor, var olduğu anlamına geliyor ama onun çağrılması sentaks hatası. 

Copy constructor’a geri dönelim. 

Sınıfın özel üye fonksiyonunu derleyici yazarsa, derleyicinin yazdığı özel üye fonksiyon derleyici tarafından keyfi bir şekilde yazılamıyor. 
Derleyici dilin kurallarına uygun olarak yazmak zorunda. 

Eğer bir derleyici bir sınıfın bir özel üye fonksiyonunu örtülü olarak bildirip tanımlama girişiminde bulunduğunda dilin kurallarını
çiğneyen bir durum oluşursa derleyici default edeceği özel üye fonksiyonunu delete edilmiş olarak bildirir. 
Acaba derleyici sınıf için nasıl bir copy constructor yazıyor ? derleyicinin yazdığı copy constructor sınıfın non static, public, inline fonksiyonu. 


```c++
class Myclass {
public:
	Myclass(){}
	Myclass(const Myclass& other) : tx(other.tx), ux(other.tx), wx(other.wx){}
private:
	T tx;
	U ux;
	W wx;
};
```
Derleyicinin yazdığı copy constructor sınıfın veri elemanlarını copy constructor ediyor. Sınıfın veri elemanlarının copy constructor edilmesi demek eğer bunlar sınıf türünden değilse diğer nesnenin değerini alıyor. 

Rule of zero —--> sıfır kuralı : 
Sınıfın özel üye fonksiyonları var. Bu fonksiyonların kodunu derleyici bizim için yazabiliyor. Bizim için yazmasına default etmesi deniyor. Derleyicinin bu fonksiyonları nasıl yazacağının kuralı belli mi ? evet, belli. Eğer derleyicinin yazdığı kod, işimize geliyorsa bunların hiçbirini bildirmiyorsunuz, hepsini derleyiciye bırakıyoruz. Bırakın derleyici default etsin demek. Derleyicinin yazmasını tercih ediyorum. Derleyicinin yazdığı kod her zaman daha iyi. Buna rule of zero deniyor. 


Kopyalama semantiği ; 
Value type şu anlamda kullanılıyor. 

Eğer bir nesne bir value type türündense o zaman o nesneye başka bir nesnenin değerini atadığımızda bunlar arasında bir bağlantı olmaz. Her nesnenin değeri kendine. 

x = y; 

X ile y arasında bir bağlantı yok. 
x’i değiştirirsek y değişmez. 
y’yi değiştirirsek x değişmez. 

std::string bir value type mi ? evet

```c++
std::string s1{"guven unel"};
std::string s2 = s1;
s1 = "remzi kaya";
```

S2’nin değeri değişmiyor. 

Konudan bağımsız not; 
```
Bir sınıfın elemanı kedi türünden olamaz. Kendi türünden pointer ve referans olabilir. 
```

```c++
class Date{

public:
	Date(int day, int mon, int year) : day_(day), mon_(mon), year_(year) { }
	//
private:
	int day_;
	int mon_,
	int year_;
};

int main()
{
	Date dx{11,2,2024};
	Date dy = dx; 
}
```
dy için sınıfın hangi fonksiyonu çağrılacak ? copy constructor. 
Sınıfın copy constructrunu derleyici yazıyor. Bana bir zararı var mı ? hayır. 
dy nesnesi dx nesnesi ile aynı değeri sahip. 

```c++
class Date{

public:
	Date(int day, int mon, int year) : day_(day), mon_(mon), year_(year) { }
	//
private:
	int day_;
	int mon_,
	int year_;
};

int main()
{
	Date dx{11,2,2024};
	Date dy = dx;
	dx.print();
	dy.print(); 
}
```
Aynı değerleri yazdıracak. 
Kendimiz copy  constructoru yazsaydık şöyle yazardık. Run time da trace edebilmek için yazarız. 

```c++
class Date{

public:
	Date(int day, int mon, int year) : day_(day), mon_(mon), year_(year) { }
	Date(const Date% other) : day_(other.day_), mon_(other.mon_), year_(other.year_) { };
	void print()const
 	{
		std::cout << day_ << mon_ << year__ <<'\n';
	}

};
```
Yazmama gerek yok. 
Sınıfların çok büyük çoğunluğu Date gibi sınıfları. Copy constructor yazmana gerek yok. Sınıfların çok büyük çoğunluğu için rule of zero’ya bağlı kalacağız. 
Neden copy constructor yazmayayim ? derleyicinin yazdığı kod işimize gelmiyorsa. Senin yazdığın cc benim başımı belaya sokar diyorsan kendin yazmalısın. 

Bazı sınıfların şöyle implement edilmesi bir mecburiyet. 

Standart kütüphanenin string sınıfını kendimiz yazdığımızı düşünelim. Acaba standart kütüphanenin string sınıfı nasıl bir sınıf ?? 
String sınıfı türünden bir nesnenin değeri bir yazı. 
Bu yazı nerede tutuluyor ? dinamik bir bellek alanında tutuluyor. Heap’de tutuluyor. 
String sınıfını detaylı da öğrenicez. 
Siz bir string sınıfı oluşturduğunuz zaman heap’den bir bellek alanı allocate ediliyor ve o bellek nesnesinin adresini tutan bir pointer var. Bu pointer string nesnesinin veri elemanı. 


![image](https://github.com/Mserhatarslan/Cplusplus/assets/63358327/be32be04-5171-4fef-9274-ad6c0f526234)

str nesnesinin veri elemanı olan pointerları kullanarak yazıya erişiyoruz. 
Aslında 3 tane pointer var. 
Pointerlardan bir tanesi allocate edilen bellek bloğunun adresini tutuyor. Diğeri, yazının uzunluğunun elde edilmesi için en son adresi tutuyor. Diğeri allocate edilen bellek bloğunun sonunu gösteriyor. 

![image](https://github.com/Mserhatarslan/Cplusplus/assets/63358327/984110dd-eaa7-4646-9742-fe493534f93c)


Kodunu da yazalım. 
std::string str{“necati ergin c++ eğitimi veriyor”};
std::string s2 = str; 
S2 için copy constructor çağrılacak değil mi ? evet. 
Bu sınıfın kodunu ben yazıyor olsaydım bu sınıfın copy constructorını derleyicinin yazımına bıraksaydım derleyicinin yazdığı copy constructor sınıfın veri elemanlarını diğer nesnenin veri elemanlarından kopyalayacaktı değil mi ? evet. Ama bu felaket olur. Value type kalmaz mı. Bunun pointerları buna kopyalanır. Yani her iki nesne de aynı bellek bloğunu gösterir hale gelir. Bu durumda str nesnesi vasıtasıyla yazıyı değiştirdiğimiz s’nin de yazısı değişir.value type özelliği kalmaz. Bu şekilde de implemente edilirse programın çalışma zamanında oluşacak tanımsız davranışlar yüzünden dangling pointerlar yüzünden başım ciddi derde girer. Sınıfınızın veri elemanları handlerlar ise yani pointer veya referans gibi varlıklarsa onların doğrudan kopyalanması başka bir semantik yapı oluşturuyor. Değerlerini aynı hale getiriyor ama değerlerini birbirine bağlı kılıyor. 

Str nesnesinin destructorı çağrıldığında kaynağı geri vermesi gerekir. Str nesnesinin hayatı bitti ama s2 nesnesi hala hayatta. Bu bellek alanı free edilmiş olur. S2’nin elemanı olan pointerlar dangling hale gelir. 
Tanımsız davranış olmaması için
value type’ın korunması için

Benim nasıl bir copy constructor yazmam gerekir? 
Pointerlar kopyalanmayacak. S2 ayrı bir allocation yapacak. Üstelik allocate ettiği bellek bloğuna diğer nesne için allocate edilmiş bellek bloğundaki öğeleri kopyalayacak. Yani pointerları kopyalama yerine kaynak edinip pointerların gösterdiği kaynakları kopyalayacak. 

Derleyiciye bırakırsak derleyicinin yaptığı kopyalamaya  shallow copy ( sığ kopyalama) denir. Sadece pointerı kopyalıyor. 
Gerçekte olması gereken pointerların kopyalanması değil, pointerların gösterdiği varlıkların kopyalanması gerekiyor. Buna da deep copy deniyor. 

İşte bu durumda copy constructoru kendimiz yazmalıyız. Aksi halde başımız cidde dertte. 
Ama bu durumların üretimde karşılaşılması çok seyrek. 

```c++
class Person{
private:
	std::string name;
	std::string surname;
	std::string address;  
};
```
Şu şekilde yazarsan güvenebilirsin. Ama bunun yerine 

```
class Person{
private:
	char* pname;
	char* psurname;
	char* paddress;  
};
```
Şimdi derleyicinin yazdığı copy constructor felaket olur. 

copy constructoru kendimiz yazmamız gerektiğimiz bir senaryo yaratalım. Profesyonel düzeyde olmayacak. 
Copy constructorun neden programcı tarafından yazılması gerektiğini anlamak için yazıyoruz. 

cstring == Null terminated byte stream ( null karakter olduğunu belirtiyor yanının sonunda)

Burada hoca kod örneği yazdı. class Sentence ; yazzzzz. 

1:53 dakika. 

Dangling pointer kullanmış olduk burada bu da tanımsız davranış. Buradaki kodu yaz….

value type’ı da bozuyor. 
Derleyicinin yazdığı copy constructor işimizi burada bozuyor. Nereden baksanız problem. 

Deep copy yapmamız gerekir burada, diğer nesnenin kaynağını kopyalamicaz kendimiz yeni kaynak oluşturmamız gerekiyor. 

Eğer sizin sınıfınızın elemanı ya da elemanları handellarsa tipik olarak deep copy yapmanız gerekiyor. 

Eğer copy constructor’ı kendiniz yazıyorsanız sınıfın diğer elemanlarının da copy constructor edilmesinden siz sorumlusunuz. 
Copy constructorı kendiniz yazıyorsanız artık sınıfın tüm non static veri elemanlarının hayata getirilmesinden siz sorumlusunuz. 


Böylece copy constructorun varlık nedenini bu örnekte daha iyi gördük. Artık böyle bir Copy constructorun varlığı value type olma varlığını bozmadı ve programın çalışma zamanında tanımsız davranış durumları oluşmadı. —-> kendimiz yazdık copy constructoru

Bir sınıf nesnesinin değerini bir başka sınıf nesnesinden alarak hayata gelmesi başka, hayatta olan bir sınıf nesnesine bir başka sınıf nesnesinin atanması başka. 

```c++
class Nec
{
};

Nec x;
Nec y;

x = y; 
```
x’de y’de zaten hayatta. Bu assignment, initialization değil. 

Atama bir nesnenin değerini değiştirme semantiğidir. 
Ama yine value type özelliğinin bozulmaması gerekiyor. X’i değiştirdiğimde y değişmeyecek, y’yi değiştirdiğimde x değişmeyecek. Yapışık ikizler olmayacak. C++’da burada çok önemli kurallar var. 

Hayatta olan bir sınıf nesnesine atama yapıldığında atama operatörünün sağ tarafındaki ifade L value expression ise bu atama sınıfın bir özel üye fonksiyonuna çağrı yapılması sonucu doğuruyor. Bu üye fonksiyonun ismi copy assignment.

copy assignment, operator overloading dediğimiz bir mekanizmanın da bir bileşeni olduğu için bu işi yapan fonksiyonun ismi özel bir şekilde oluşturulmak zorunda. 

x=y; dediğimizde derleyici aslında şu şekilde ele alınacak derleyici tarafından 
x.operator = (y);

Burada çağrılan fonksiyon sınıfın üye fonksiyonu mu ? evet
Non static üye fonksiyonu mu ? evet
Special member function mu ? evet
Special member function olması bu fonksiyonun kodunun derleyici tarafından yazılabileceği anlamına geliyor mu ? evet
Bu fonksiyonun içinde this pointerını kullansam kimin adresini kullanmış olurum ? x

```c++

using namespace std;
int main()
{
	string name1{"serhat"};
	string name2{"arslan"};
	name2 = name1; 

}
```

Burada şimdi copy assignment mı çağrılacak ? kesinlikle. 
Yani bu kodu böyle yazmakla şöyle yazmak arasında hiçbir fark yok. 

```c++
using namespace std;
int main()
{
	string name1{"serhat"};
	string name2{"arslan"};
	name2 = name1; 
 	name2.operator= (name1); 
}
```
Siz böyle yazsanız bile derleyici aşağıdaki gibi bir fonksiyon çağrısına dönüştürüyor. Operator overloading. 
String bir value type burada. 




# 17 Şubat 2024 11. C++ Dersinden Notlar;
 
Sınıfların özel üye fonksiyonları belirli koşullar sağlandığında derleyici tarafından kodları yazılabilen yani default edilebilen fonksiyonlar. Bunlar sınıf nesnelerinin hayata gelmesi, hayatının bitmesi ve kopyalanması ile ilgili fonksiyonlar. 6 tane fonksiyonumuz var. 

- default constructor 
- destructor
- copy constructor 
- copy assignment 
- move constructor 
- move assignment
 
Bunlar derleyici tarafından yazılırsa kodlarının nasıl yazıldığı konusunda kurallar var. 
Ve önemli bir kuralda şu, derleyici bu fonksiyonları örtülü bildirildiği (implicit declared) için default etme sürecinde bir sentaks hatası oluşan durumla karşılaşırsa tanımlayacağı fonksiyonu dilin kurallarına göre delete ediyor. 

Hep şöyle bir pattern kullandık. 
```c++
class Myclass {
private:
	T tx;
	U ux;
//…
}
```
Derleyici tarafından yazılan default constructor sınıfın veri elemanlarını default initialize ediyor. Eğer default initialization mümkün değilse derleyici örtülü olarak bunu tanımlıyorsa delete edecek. 

Derleyicinin yazdığı copy constructor sınıfın veri elemanlarını copy construct ediyor. 
Derleyicinin yazdığı move constructor sınıfın veri elemanlarını move construct ediyor. 

Taşıma semantiği hakkında ekstra Not; 

```
* std::move:

Bir lvalue ifadesini rvalue ifadesine, rvalue ifadesini ise yine rvalue ifadesine çeviren yardımcı bir fonksiyondur.

move == static_cast<T &&>(y) gibi bir dönüşüm gerçekleşiyor diyebiliriz.

Ne zaman kullanılmalı?

Bir nesne bir daha kullanılmayacaksa o zaman taşıma işlemi yapılmalıdır.
```
```c++
class Myclass {
public:
  Myclass(const Myclass& other) : tx(other.tx), ux(other.ux) { }
  Myclass(Myclass&& other) : tx(std::move(other.tx)), ux(std::move(other.ux)) { }
  Myclass& operator = (const Myclass& other){
  tx = other.tx;
  ux = other.ux;
  }

Myclass& operator= (Myclass&& other)
{
  tx = std::move(other.tx);
  ux = std::move(other.ux);

  return *this;
}

private:
  T tx;
  U ux;
//....
}

```

Derleyicinin yazdığı tüm special member functionların sınıfların non static, public, inline olma garantisi var. 

Her zaman en fazla ciddiye almamız gereken ilke,  rule of zero. Derleyicin yazdığı special member functions bizim işimizi görüyorsa bırakın derleyici yazsın. Ama örneğin sınıfın veri elemanları handle olduğu için yani referans veya pointer olması durumunda kendinizin de yazmanız gerekebilir. 


En çok yanlış öğrenilen konularından biri taşıma semantiği, 

Bir fonksiyonun parametresinin sağ taraf referans olması doğrudan bir taşıma olduğu anlamına gelmiyor. 

```c++
#include <iostream>

class Nec {
....
};

void foo(Nec&& r)
{
}

int main()
{
  Nec mynec;
  foo(std::move(mynec));
}
```
Nec nesnesini taşımız olmuyoruz, taşıma semantiği ile. 

Taşıma semantiği ile taşımak için aşağıdaki gibi olması lazım. 

```c++
#include <iostream>

class Nec {
....
};

void foo(Nec&& r)
{
  std::move(r);
}

int main()
{
  Nec mynec;
  foo(std::move(mynec));
}
```
Sağ taraf değerine cast edilip bu ifade ile bir nesneye atama ya da kopyalama yapmamız gerekiyor. 

```c++
#include <iostream>

class Nec {
....
};

void foo(Nec&& r)
{
  Nec x = std::move(r);
}

int main()
{
  Nec mynec;
  foo(std::move(mynec));
}
```
Şimdi x için move constructor çağrılacak. Yani maindeki Mynec’in kaynağını çalan 11. satırda oluşturulan x değişkeni için çağrılan move constructor. 


Diyelim ki taşıma ile kopyalama arasında ciddi bir maliyet farkı olan sınıf olsun. Mesela standard kütüphanenin string sınıfı böyle. String sınıfı türünden bir nesne özel bir optimizasyon yapılmıyorsa tuttuğu yazıyı allocate edilmiş bir bellek alanında heap’de tutuyor.
String nesnelerinin kopyalanması ile taşınması arasında bir maliyet farkı var mı ? şüphesiz. 

```c++
int main()
{
  using namespace std;
  string s1(20000, 'A');
  auto s2 = s1;
}
```
Bu durumda s2 için, sınıfın copy constructorı çağrılır. Copy constructor da 200 bin baytlık bir bellek bloğunu allocate edecek. Deep copy yapacak yani diğer nesnenin bellek alanından kendi allocate ettiği bellek alanına kopyalama yapacak. Ama şimdi hayata gelen nesne için copy constructor değil move constructor çağrılırsa kopyalama yapmak yerine diğer nesnenin kaynağını çalacak. 


Genel olarak şöyle bir yapı oluşturuluyor. 

L value ile R value arasındaki fark ne ? 
L value expression persistent bir nesne demek. O ifadeden sonra o sınıf nesnesinin halen kullanılma ihtimali var demek. 

```c++
int main()
{
  // expr ==> std::string nesnesi
  // L value
  // R value ==> PR Value U X Value
}
```

Eğer string nesnesi anlamına gelen ifade R value expression ise bu ifadenin yürütülmesinden sonra bu nesneyi kullanacak bir kod yok demek. 
Ama ifade L value ise ifade persistent demektir. 

```c++
// std::string str{expr};
```
Derleyici bu ifadenin value kategorisinin L value olduğunu anlarsa str için function overload resolution ile copy constructorı çağıracak. Ama derleyici bu ifadenin compile time’da R value olduğunu anlarsa str için move constructor’ı çağıracak. 


Diyelim ki siz bir fonksiyon yazmak istiyorsunuz ve fonksiyonun parametresini referans yapmak istiyorsunuz. 

```c++
void func(const std::string& other)
{
  std::string sval = other; 
}
int main()
{
}
```

Bu durumda sval için copy constructor mı çağrılacak yoksa move constructor mı ? 
Copy constructor çağrılacak. 
Ben bu fonksiyonu R value olan bir string nesnesi ile çağırsam R value olmasına rağmen kaynağı çalar mı ? Hayır. 

```c++
void func(const std::string& other)
{
  std::string sval = other; 
}
int main()
{
  // func(//R value); 
}
```

Peki şimdi benim ne yapmam gerekiyor ?  function overloading’den faydalanıyoruz. 

```c++
void func(const std::string& other)
{
  //
  std::string sval = other;
}

void func(const std::string&& other)
{
  //
  std::string sval = std::move(other);
}

```
Yukarıdaki func fonksiyonu kopyalama yapar, aşağıdaki func fonksiyonu çalma yapar. 
Ben func fonksiyonuna bir string nesnesi anlamına gelen bir ifade ile çağrı yapsam derleyici bu ifadenin value kategorisinin L value kategori olduğunu gördüğünde yukarıdaki func fonksiyonu çağrılacak ve kopyalama yapılacak. Ama derleyici ifadenin R value olduğunu gördüğünde function overload resolution ile aşağıdaki func fonksiyonu çağrılacak ve kaynak çalınacak. 


Vector sınıfı dinamik dizi sınıfı. Vector sınıfının push_back isimli bir fonksiyonu var(sondan ekleme yapmak için) Fakat push_back’in 2 tane overload’u var. 

```c++
// vector
int main()
{
    //push_back(const T&);
    //push_back(T&& r);

    //vec.push_back(arg);

```
move overload. Peki neden böyle yapmışlar? Elimde bir vector nesnesi varsa onun push_back fonksiyonunu çağırdığımda argüman L value expression ise hangisi çağrılacak ? Yukarıdaki. Peki tahmin edin yukarıdakinin kodu nasıl ? vector’un allocate ettiği bellek alanından nesneyi sınıfın copy constructor una çağrı yaparak oluşturacak. Ama ifade R value ise alttaki push back çağrılacak.sınıfın copy constructor’ı değil move constructor’ı çağrılacak.  

Birkaç tane daha kritik nokta var. 
Taşıma semantiği her zaman ciddi bir kar sağlar mı maliyet açısından ? şüphesiz hayır. 

```c++
class Myclass{

private:
  std::vector<int> mvec;
  std::list<int> mlist;
  std::string mstr;
};

```
Myclass sınıfı için bu sınıfın copy constructor ile move constructor’ı arasında bir maliyet farkı olur mu ? 

Dağlar denizler kadar fark olur. 
Neden çünkü derleyicin yazdığı copy constructor hayata getireceği nesnenin vectorunu, listini, stringini copy construct edecek. 

Oysa move constructor olsaydı diğer nesnenin vectorunu, listini, stringini çalacaktı. 
Maliyet açısından çok çok büyük bir fark var. 


```c++
class Myclass{
private:
  int ar[400];
  double d[200];
};
```

Böyle bir sınıf için move constructor ile copy constructor arasında bir maliyet farkı olmaz ? hayır olmaz.

```c++
int main()
{

  string str(20000, 'A');
  std::string s(str);
}
```
Str ifadesi L value. 
Peki str için için copy constructor mu çağrılacak yoksa move constructor mı ? copy constructor. Diyelim ki ben bilerek isteyerek str’nin kaynağını çalmak istiyorum. O zaman kaynağını çalabilmem için copy constructor yerine move constructor’ın çağrılması gerekir. Ama move constructorın çağrılması için de argümanın R value expression olması gerekir. 

```c++
int main()
{

  string str(20000, 'A');
  std::string s(std::move(str));
}
```
Bilerek ve isteyerek move cast yapıyoruz.  s str’nin kaynağını çaldı. 
Str’nin destructorı çağrıldığında destructor kaynağı geri vermeyecek. Verirse s zor duruma düşer. 

Burada str halen hayatta. Str’nin kaynağı çalınmış durumda. Str’nin bu noktadaki durumuna moved-from state diyoruz. Nesnelerimiz hayatta ama kaynakları çalınmış durumda. 


C++ standardı şöyle bir garanti veriyor, moved from statindeki nesneler valid statededir.(geçerli durumdadır) invariant holds
Geçerli durum şu demek,  nesnenin invaryantları tutuyor. 
Special member functionlar bazı koşullar sağlandığında derleyici tarafından default edilebilen fonksiyonlar. Hangi durumda derleyici sınıfın special member function’unu implicitly declared eder ?
Ders sonunda verilecek tabloda bu sorunun cevabı bulunacak. 

```c++
class Myclass {

};
```
Bu sınıfın herhangi bir special member functionu bildirilmiş durumda mı ? Hayır. Eğer sınıfın hiçbir special member function’u bildirilmemişse derleyici tüm special member functionları implicitly declared eder. 

```c++
class Nec {

};

class CNec {
public:
    CNec() = default;
    ~CNec() = default;
    CNec(const CNec&) = default;
    CNec(CNec&&) = default;
    CNec& operator= (const CNec&) = default;
    CNec& operator= (CNec&&) = default;
};
```
Yukarıdaki 2 sınıf arasında hiçbir fark yok. Derleyici bütün üye fonksiyonları default edecek. 


```c++
class Nec {
    Nec(int);
};

class CNec {
public:
    ~CNec() = default;
    CNec(const CNec&) = default;
    CNec(CNec&&) = default;
    CNec& operator= (const CNec&) = default;
    CNec& operator= (CNec&&) = default;
};
```
Derleyici default ctor’u tanımlamadı. Default ctor’u yok. İki kod arasında bir fark yok. 


```c++
class Nec {
    ~Nec();
};

class CNec {
public:
    CNec() = default;
    CNec(const CNec&) = default;
    CNec& operator= (const CNec&) = default;
    ~CNec();  
};
```
Siz sınıfa destructor bildirdiğiniz  zaman move memberlar not declared . Sınıfın move memberları yok. 


Eğer siz sınıfa copy constructor bildirirseniz ; 

```c++
class Nec {
     Nec(const Nec&);
};

class CNec {
public:
    // default ctor not declared
    ~CNec() = default;
    CNec(const CNec&);
    CNec& operator= (const CNec&) = default;
    // move members not declared
};
```
Eğer siz sınıfa copy assignment bildirirseniz ; 

```c++
class Nec {
     Nec& operator = (const Nec&);
};

class CNec {
public:
     CNec() = default; 
    ~CNec() = default;
    CNec(const CNec&) = default; //!!!!!!
    CNec& operator= (const CNec&);

};
```

Dikkat ; 
Eğer bir sınıf için destructor, copy ctor, copy assignment bu fonksiyonlardan birini bildirirseniz 
Derleyici move memberları bildirmez yani bu durumda move memberlar not declared durumdadır. 
Sınıfa copy constructor yazarsanız derleyici destructor’ı ve  copy assignment’ı kendisi yazıyor. Sınıfa destructor yazarsanız derleyici copy assignmentı ve copy constructor’ı kendisi yazıyor. Sınıfa copy assignment yazarsanız derleyici destructor ve copy constructor’ı kendisi yazıyor. Aslında bunun sentaks hatası olması gerekir ama backward compatibility adına derleyiciler durumdan vazife çıkartarak yazıyor. Çok tehlikeli bir durum. Asla asla asla bir sınıfa destructor bildirdiğiniz zaman copy constructor ve copy assignment yazılmasından siz sorumlusunuz. Derleyiciye bırakırsan felakete yol açar. Destructoru siz yazıyorsanız demek ki geri vermeniz gereken bir kaynak var demektir..  O zaman destructor bir kaynağı geri veriyorsa derleyicinin yazdığı copy constructor ve copy assignment shallow copy yapacak bu da felakete neden olacak. 


Big 3,  biri yazılıyorsa diğer ikisinin de yazılması gerekir. 


Bir sınıfa bir move member bildirirsek derleyici copy memberları delete eder. 
Bildirilmeyen move member not declared durumdadır. 

Destructor’ın not declared olduğu bir senaryo yok. Delete edildiği bir senaryo da yok. Her zaman var. 

Taşıma semantiğininin standarlarına eklenmesindeki en büyük etkenlerden biri howard hinnant 

![image](https://github.com/Mserhatarslan/Cplusplus/assets/63358327/d7769d44-670a-4983-9118-0f05dd2fa80f)

![image](https://github.com/Mserhatarslan/Cplusplus/assets/63358327/6a5be079-fa2e-47a8-854b-dea7865c385b)

![image](https://github.com/Mserhatarslan/Cplusplus/assets/63358327/014d0e19-676a-4de4-87eb-f3f4c60150a8)

Aşağıdaki görselde bir sınıfın hangi durumlarda tanımlanırsa derleyici hangi özel üye fonksiyonlarını yazacak, silecek veya tanımlamıyacak bunlar gösterilmiştir.



![image](https://github.com/Mserhatarslan/Cplusplus/assets/63358327/d286f5f8-3e9e-41e0-9959-4fab07137473)

Karşımıza çıkacak olan sınıfların tipik olarak yapısı şöyle; 

1) Sınıfın bütün special member functionları var. 


2)  Grup sınıf biçimi de var. Bu sınıflara move only type deniyor. Bunlar taşımaya açık ama kopyalamaya kapalı sınıflar. Yani bunların kopyalanması istenmiyor. Ya kopyalanması semantik açıdan doğru değil ya da kopyalanmasının bazı sakıncaları var.
   
Mesela unique_ptr sınıfı 

mesela std::ostream sınıf 

mesela std::thread sınıfı

```c++
int main()
{
  using namespace std;
  unique_ptr<int> x(nex int);
  auto y =move(x);
}
```

Taşımaya açık, kopyalamaya kapalı. 
Kendi sınıfımı taşımaya açmak istersem ne yapmam gerekiyor ? 

```c++
class Nec{
public:
    Nec(const Nec&) = delete;
    Nec& operator = (const Nec&) =  delete;
    Nec(Nec&&);
    Nec& operator = (Nec&);
};

```
Move only type

```c++
class Nec{
public:
    Nec(Nec&&);
    Nec& operator = (Nec&);
};

```

- Copyable & moveable
- Non copyable but movable ( move only type)
- Non copyable & non movable

```c++
int main()
{
  using namespace std;
  mutex mtx;
  mutex mx = mtx;
}
```
Sentaks hatası çünkü mutex sınıfı => non copyable & non movable
String sınıfı hem copyable hem movable 

Bir sınıfı kopyalamaya ve taşımaya kapatmak için copy constructur’ı copy assignment’ı delete etmeniz yeterli. 

```c++
struct Myclass{
    Myclass(const Myclass&) = delete;
    Myclass& operator= (const Myclass&) = delete;
};

```
Bu sınıf hem kopyalamaya hem de taşımaya karşı kapalı. 

```c++
class Myclass{
};

Myclass foo()
{
  Myclass mx;
  //....
  return mx;
}
```
Otomatik ömürlü bir nesne bir fonksiyonun return ifadesi olduğunda fonksiyonun geri dönüş değeri sınıf türündense özel bir dönüşüm yapılıyor.  L value’den X value’ya bir dönüşüm yapılıyor. 

# Temporary Objects (Geçici Nesneler) 

Öyle nesneler var ki kod içinde bir değişken ismi kullanılmamış olmasına karşın kullanılan bir nesne var. Böyle nesnelere geçici nesne diyoruz. Geçici nesnelerin değer kategorisi prvalue expression'dır.


Geçici nesne oluşturmanın yolu türü yazmak sonra
Direct initialization sentaksı ile
Value initialization sentkası ile
List initialization sentaksı ile 
Constructora gönderilecek argümanları oluşturmak. 
Myclass()
Myclass{ }
Myclass{12}
```
Mint(13); //Mint türünden geçici nesne
```

```c++
class Myclass {
public:
    Myclass() { std::cout << "default ctor\n"; }
    Myclass(int) { std::cout << "Mclass(int)\n"; }
    ~Myclass() { std::cout << "destructor\n"; }
};

int main()
{
    Myclass mx;
    mx = Myclass{13};
    (void)getchar();
}

// default ctor
// Mclass(int)
// destructor

// destructor
```

Program getchar fonksiyonuna geldiği zaman destructor çağrıldı. Bu bize Myclass{13} şeklinde oluşturduğumuz geçici nesnenin derleyici tarafından üretilip daha sonra sonlandığını göstermektedir.

Geçici nesne oluşturmaya yönelik ifadeler L value expression değildir. PR value expression’dur. Geçici nesnelerin değer 

Normalde temporary object bulunduğu ifadenin yürütülmesinden sonra hayatı bitiyor ama temprary object’i bir referansa bağlarsanız bu durumda artık geçici nesnenin hayatı referans olan ismin scope una endeksleniyor. Bu şekilde geçici nesnelerinin hayatlarını uzatabiliriz. Buna life extension denilmektedir. 
Geçici nesnelerin pr value expression olduğunu ve sol taraf ve sağ taraf referansına bağlanabileceğini gördük. İsimlendirilmemiş nesneler olduğu için gereksiz yere isim alanına bir isim enjekte etmemiz konusunda yardım oluyor. Ve içinde bulundukları ifade yürütüldükten sonra hayatları bitiyor, kaynakları boş yere bloke etmiyorlar. 

Taşıma semantiğinden de faydalanmış oluruz aslında. 

```
std::string(100000, 'A');
```

Siz bunu bir nesneye atadığınız zaman taşıma semantiği devreye girecekti, taşıma semantiği de kaynağını çalacaktı . Bu nesneyi isimlendirmiş olsaydık kaynak çalmak yerine kaynağının kopyalanmasına sebep olacaktık. Bu da bizim istediğimiz bir durum değil. 
```
const Myclass& r = Myclass{13};
Myclass&& rx = Myclass{13};
```
Yukarıdaki kodda geçici olarak oluşturduğumuz kodu const sol taraf referansı değerine veya sağ taraf referansı değerine bağlayarak life extension yapmış olduk.

# Mandatory copy elision

Kopyalamanın ortadan kaldırılması anlamında. Kopyalamanın olmaması. 
C++17 öncesi derleyicinin yaptığı bir optimizasyondu. C++17 ile zorunlu hale geldi. Artık dilin bir kuralı. 
C++17 öncesinde bu bir optimizasyondu. Eğer bu bir optimizasyon olsaydı halen ben bu sınıfın copy constructor’ını delete etsem sentaks hatası olurdu. Sınıf kopyalamaya karşı kapatılmış. Optimizasyon başka dilin kuralı başka. 

C++17 standardında herhangi bir hata olmaz. Sınıfın kopyalamaya karşı kapatılmış olmasına rağmen fonksiyonun parametresinin Myclass sınıfı olması durumunda bir sentaks hatası olması. İşte bu duruma C++17 ile birlikte mandatory copy elision denir. 

Eğer bir fonksiyonun parametresi bir sınıf türünden ise ve siz bu fonksiyonu bir PR value expression ile çağırırsanız fonksiyonun parametresi için copy constructor çağrılmayacak. 

PR value expression C++17 ile birlikte bir nesne değil. Ne zaman nesne haline gelecek ? Onun nesne hale gelmesini sağlayan bir bağlamda kullanıldığında. Nesnenin oluşturulmasına temporary materialization deniyor. 

Artık bu bir optimizasyon değil, dolayısıyla ister release sürümünde derleyin ister debug sürümünde derleyin hiçbir şekilde derleyici hiçbir şekilde copy constructorı çağıramaz. Copy constructor delete edilse bile. 

Tipik olarak derleyiciler debug modunda optimizasyonları disable edebilirler. 
2. Tipik biçimi, fonksiyonların geri dönüşleri 

Eğer fonksiyonların geri dönüş değerleri bir sınıf türündense fakat fonksiyonun return ifadesi bir PR value expression ise bu durumda yine copy constructor çağrılmayacak. 

Mandatory copy elision durumları ; 

Fonksiyonun parametresinin sınıf türünden olması
Fonksiyonun geri dönüş değerinin sınıf türünden olması ve geri dönüş değeri ifadesinin PR value expression olması 

2. Senaryo için kullanılan terim , Return value optimization (RVO) ; 
Yani derleyicinin kopyalamayı engelleyecek şekilde doğrudan nesneyi fonksiyonun geri dönüş değerinin yazılacağı bellek alanında oluşturması 

```c++
// RVO
Myclass foo()
{
  return Myclass{};
}
int main()
{
  Myclass m = foo(); // mandatory copy elision uygulanır
}
```
Copy elision olması garanti altında. Delete edilmiş olsa dahi garanti altında. 

Named return value optimization (NRVO) ; 
Bu hala bir optimizasyon. Debug modda bu optimizasyon derleyici tarafından disable edilebilir. 

```c++
std::string get_str()
{
std::string str;

return str;
}

int main()
{
  auto s = get_str();
}
```
Burada kopyalama da yok taşıma da yok. S nesnenin kendisi. 
Hikaye şu ; 

Aslında bu fonksiyon çağrıldığı zaman çağıran kod bu fonksiyona bir argüman geçiyor biz görmesek de. Bu argüman fonksiyonun geri dönüş değerinin yazılacağı bellek adresi. 
Yani aslında bu fonksiyon fonksiyonun geri dönüş değerinin nerede oluşturulacağını kendisine gelen bir argümandan anlıyor assembly düzeyinde. 

Derleyici de durumdan vazife çıkararak diyor ki, madem benim fonksiyonun geri dönüş değerini bir yere kopyalamam gerek diyor o zaman bu nesneyi doğrudan bana gelen adreste oluşturayim diyor. Bu halen bir optimizasyon.  

Return value optimization ile named return value optimization arasındaki fark ne ? 



Return value optimization da return value ifadesi doğrudan PR value expression. 

Named return value optimization da isimlendirilmiş bir nesne var. 

Return value optimization artık copy elision’a tabi, derleyici bunu yapmak zorunda. 


Kopyalama da yok taşıma da yok. Çok önemli bir optimizasyon. Copy constructor’un delete edilmiş olması return value optimization’u engellemiyor. 

Named return value optimization da copy constructor’ın delete edilmesi sentaks hatası. Mandatory değil. 

NRVO neden önemli ? 
Copy’den de move’dan da daha iyi. Maliyet sıralaması şöyle;

- NRVO
- Move constructor
- Copy Constructor
En iyi senaryo, nrvo 
Eğer nrvo yapılamazsa move constructor çağrılacak. 

NRVO çok önemli bir optimizasyon. 

return x; 

Normalde siz fonksiyonun return statement’ini yazdığınız zaman derleyici return ifadesinin değerini bir adrese yazıyor, o adreste bir nesne oluşturuyor. Fonksiyonu çağıran kodda o return slote taki nesneyi kendi değişkenine kopyalıyor. 

NRVO devreye girdiği zaman derleyici nesneyi kopyalama işlemini elimine ediyor. 
Halen bir optimization. Copy constructor delete edildiğinde sentaks hatası olur. Yani bu optimizasyon mandatory değil, derleyici bunu yapamayabilir. 

Conversion constructor (dönüştüren kurucu işlev) 

Bir sınıfın parametreli bir constructorı temel varlık nedeninin yanı sıra örtülü dönüşümde de kullanılıyor. Bu yüzden böyle contructorlara conversion constructor deniyor. 

```c++
class Myclass{
};

int main()
{
  int ival = 10;
  Myclass m;
  m = ival;
}

```

Sentaks hatası. Çünkü atama operatörünün sağ operandı int türden ama atama operatörünün sol operandı Myclass türünden. Int türden Myclass türüne örtülü dönüşüm yok. Tür uyuşmazlığı var. Derleyicin verdiği sentaks hatasına bakalım; 
```
There is no acceptable conversion
```

```c++
class Myclass{
public:
  Myclass();
  Myclass(int);
};

int main()
{
  int ival = 10;
  Myclass m;
  m = ival;
}
```
Legal. 

Derleyici atama operatörünün sağ operandının int türden olduğunu görünce bu atamanın yapılabilmesi için int’i örtülü olarak Myclass sınıfı türünden bir nesneye dönüştürdü. Yani aslında derleyicin yaptığı dönüşüm şöyle bir koda karşılık geliyor ; (Sembolik olarak) 

```c++
class Myclass{
public: 
    Myclass() { };
    Myclass(int x)
};

int main()
{

  int ival = 10; 
  Myclass m;
  m = ival; 

}
```
Böyle olduğunu kanıtlayalım. int parametreli constructor'da bu fonksiyonun çağrıldığını gösteren bir yazı yazdırsam basit bir şekilde kanıtlyabiliriz. 

```c++
class Myclass{
public: 
    Myclass() { };
    Myclass(int x)
    {
      std:cout << "Myclass(int x) x = " << x << "\n";
    }
};

int main()
{

  int ival = 10; 
  Myclass m;
  m = ival; 

}
```

Standart outputa x ve onun değeri olan 10 değerini basar. 
Buradaki constructor kendi görevinin yanı sıra int türden bir ifadeyi Myclass  sınıfı türüne denüştürdü. Bu tür dönüşümlere User defined conversion deniyor.(UDC) 


Aşağıdaki kodda getchar çağrısından önce destructor çağrılacak mı ? 

```c++
class Myclass{
public: 
    Myclass() { };
    ~Myclass()
    {
      std:cout << "Myclass destructor this  = " << this << "\n";
    }

    Myclass(int x)
    {
      std:cout << "Myclass(int x) x = " << x << "\n";
    }
};

int main()
{

  int ival = 10; 
  Myclass m;
  m = ival;
  (void)getchar();

}
```
Kesinlikle çağrılacak. 


```c++
class Myclass{
public: 
    Myclass()
    {
    std:cout << "default  constructor    = "  << "\n";

    };
    ~Myclass()
    {
      std:cout << "Myclass destructor this  = " ;
    }

    Myclass(int x)
    {
      std:cout << "Myclass(int x) x = " << x << "\n";
    }

    Myclass& operator = (const Myclass&)
    {
    	  std:cout << "copy assignment   = "  << "\n";
           return *this; 

     }

    Myclass& operator = (Myclass&&)
    {
    	  std:cout << "move assignment   = "  << "\n";
           return *this; 

     }	

};

int main()
{

  int ival = 10; 
  Myclass m;
  m = ival;

}
```

Kodun çıktısı 

```
default  constructor
Myclass(int x) x = 10
move assignment
Myclass destructor
Myclass destructor
```

Myclass m değişkeni için default constructor çağrıldı. 
m= ival satırındaki atamada derleyici int türden Myclass sınıfı türüne dönüşüm yapabilmek için sınıfın int parametreli constructoruna çağrı yaptı. Fakat bu atamada artık derleyicinin oluşturduğu nesne bir PR value expression geçici nesne olduğu için atamayı da sınıfın move assignment fonksiyonu yaptı. 

İşte böyle constructorlara dönüşüm sağladığı için explicit constructor deniyor. Buraya dikkat !!! Dert açabilir. 

Eğer sınıfın böyle bir constructoru varsa artık int türden Myclass sınıfı türüne dönüşüm bekleyen her yerde derleyici durumdan vazife çıkararak bu constructorı çağırarak dönüşümü gerçekleştirecek. 

```c++
class Myclass {

public:
	Myclass();
	Myclass(int);
};

void foo(Myclass);

int main()
{
	Myclass m;
	m = 5;
	int mi = 17;
	foo(mi);
}

```
Yanlışlıkla, bilerke isteyerek değil m değişkenini argüman olarak göndermek yerine mi değişkenini argüman olarak gönderdiğinizde sentaks hatası olmasını beklerken bu sentaks hatası olmayacak. 
Çünkü dilin kuralları gereği int parametreli constructora çağrı yaparak bir geçici nesne oluşturacak. 

```c++
class Myclass {

public:
	Myclass();
	Myclass(int);
};

void foo(Myclass);

Myclass bar()
{
	int i = 5;
	return i;
}

int main()
{
	Myclass m;
	m = 5;
	int mi = 17;
	foo(mi);
}

```

bilerek ya da bilmeyerek yanlışlıkla i değişkenini return ifadesi yapsam sentaks hatası olacak mı ? Hayır. Derleyici yine int parametreli constructora güvenerek örtülü dönüşüm yapacak. Çok tehlikeli. 

Conversion constructor dikkatli kullanılmalıdır. 

```c++
class Myclass {

public:
	Myclass();
	Myclass(int);
};

int main()
{
	Myclass m;
	m = true; 
	m = 3.4;
	m = 'A';
}

```

m = true, m = 3.4; m = 'A'; ifadeleri malesef legal. Dİlin çok önemli bir kuralı devreye giriyor. 

user defined conversion olmayan dilin kurallarına geçerli olan dönüşümlere standard conversion denir. 

user defined conversion
standard conversion

Eğer bir dönüşüm örtülü olarak önce standard conversion ondan sonra user defined conversion şeklinde yapılıyorsa derleyici bu dönüşümü yapmak zorunda. 


Eğer bir dönüşüm örtülü olarak önce user defined conversion ondan sonra standard conversion şeklinde yapılıyorsa derleyici bu dönüşümü yapmak zorunda. 

bool'tan int'e dönüşüm var => standard conversion 
int => Myclass  => user defined conversion


udc + udc = derleyici bu dönüşümü yapmaz. 

# 25 Şubat 2024 14. Ders 

Dünkü dersimizde operator overloading konusuna giriş yaptık. Kısa bir hatırlatma; 


Sınıf nesneleri operatörlerin operandları olduğunda derleyici operatöün operandı olmuş sınıf nesnesini bir fonksiyonun çağrısına dönüştürüyor. Bu mekanizmaya operator overloading deniyor. 

Amaç, kolay kod yazmak, okunabilirliği artırmak. 
İç içe fonksiyon çağrıları yapmak yerine programın çalışma zamanında ilave bir maliyet getirmeden sınıf nesnelerini operatörlerin bulunduğu ifadelerde kullanmak kodun yazılmasını, okunmasını kolaylaştırıyor. 
Kritik 2 nokta var; 
Run time’a yönelik bir araç seti değil. Programın çalışma zamanına ilave bir yük getirmiyor. Derleme zamanına yönelik bir araç seti. 

Operator overloadin’de kurallara uyulmak zorunda. Derleyici derleme zamanında kontrol ediyor bu kuralları. 10 civarında kural var. 

2 ayrı yol var. Operator overloading’in gerçekletirilebilmesi için.

Bir free functiın oluşturmak (global fonksiyon)  —> global oeprator function
Bir sınıfın non static üye fonksiyonu olarak tanımlamak —> member operator function

Static üye fonksiyonlar operator overloading sentaksında kullanılmıyorlar. 

İlk kural , operator overloading’den bahsedebilmemiz için söz konusu operatörün C++’ın operator setinde bulunması gerekiyor. 

X @ y —> olmayan operatörün yüklemesi olmaz. 

Operator kümesinde olmayan bir operatör yüklenemez. 
Her operator overloading’e açık değil. Overload edilmeyen operatörler var. Overload edilemeyen operatörler ; 

. (member selection dot) 

:: (scope resolution operator)

? : ( ternary operator) 

sizeof 

.*  ( C’de yok, C++’da var bu operator) 

typeid 



-> bu operator overload edilebiliyor  ve çok da sık kullanılıyor. 

[] 


Bu operatorler overload edilebiliyor. 


Bazı operatörlerin overload edilebilmesi başka, üretimde yaygın olarak kullanılması bambaşka. Mesela lojik ve operatörü overload edilebilir ama kullanım alanları çok sıra dışı senaryolar için söz konusu olabilir. 

Operatörün kullanımının intuitive olması gerekir. 
Client kod bunu kullanırken yadırgamayacak. Yeni başlayan programcıların sezgisel olmayan, doğal durmayan overloadinglerden uzak durması gerekiyor. Yani bir çağrışım mekanizmasının söz konusu olması gerekiyor. 

// myfighter  & enemy_fighter 

Hiçbir çağrışım yok. 

// image >> filter 

Kuvvetli bir çağrışım yok.

Amaç client kodu kullananların işini kolaylaştırmak. 

Bazı operatörler ise sadece member operator function olarak overload edebiliyorlar. 

Bu operatörler için free function yolu kapalı. 

Mesela susbscript operatörü  -> [ ]

Fonksiyon çağrı operatörü -> ( ) 

Atama operatörü -> = 

Arrow operator -> ->

Member function olmak zorunda. 


Operator overload olabilmesi için operatörün operandlarından en az birinin bir sınıf türünden ya da bir enum türünden olması gerekiyor.  

Unary operator ise operandının 
Binary operator ise operandlarından en az birinin bir sınıf türünden ya da enum türünden olması gerekiyor. 

Operator fonksiyonları keyfi biçimde isimlendirilemiyorlar. 
Operator fonksiyonun isimleri operator keyword’ünü içermek zorunda. Bundan sonra hangi operatörü overload ediyorsa o operatörünün tokenı gelmek zorunda. 

operator!
operator+ 
operator<< gibi.
Operatörlerin arity’si değiştirilemez. Kastedilen operatörün unary ya da binary olması. 
Yani binary operatörü binary operator olarak overload etmek zorundasınız. 
Unary operatörü unary operator olarak overload etmek zorundasınız. 
Derleyici bunu compile time’da kontrol ediyor. Kurala uyulmazsa sentaks hatası. 

Ne demek bu ? 
 Örneğin x ve y sınıf nesneleri olsun. 

```
x>y  
> operatörü binary operator ( 2 operand aldığı için) 
Binary operator olarakk overload edilmesi gerek. 
```

Biz bunu global fonksiyon olarak overload etmek istiyorsak bu fonksiyon aslında şöyle bir fonksiyon olacak. 

bool operator>(const Myclass&, const Myclass&)
Derleyici bu fonksiyonu çağıracak. Bu fonksiyona operatörümüzün sol operandını ve sağ operandını sırasıylr fonksiyonun 1. Ve 2. Parametrelerine argüman olarak gönderilecek. Yani şöyle bir fonksiyon çağrısı gerçekleşecek. 

operator(x,y) 


Ama bu global operator fonksiyonu değil de member operator function olarak overload edilseydi bu durumda derleyici binary operatorün sol operandını fonksiyonun çağrıldığı nesne olarak alacaktı. Yani fonksiyon içinde this pointerı sol operandın adresi olacaktı yani *this x olacak.  Onun > fonksiyonuna çağrı yapacaktı ve y’yi aegüman olarak gönderecekti. 


x > y x.operator(y) 

Binary operatörler global operatör fonksiyonu olarak overload edildiğinde fonksiyonun kaç tane parametre değişkeni olmalı ? 2 
Ama üye operator fonksiyonu olduğunda 1 tane parametresinin olması gerekiyor. 
```
class Nec {
public: 
	bool operator>(const Can&, const Can&)const; 
};
```
Sentaks hatası çünkü 2 adet parametre değişkeni var. 1 tane olması gerekir. Üye operator fonksiyonu çünkü. Parametre değişkeni olmasaydı da sentaks hatası. 

Aynı fonksiyonu bu sefer global operator fonksiyonu olarak overload ediyorum. 

class Nec {
public: 
};
bool operator>(const Can&); 

Geçerli değil çünkü 2 parametresinin olması gerekiyor. 
Derleyicinin verdiği diagnostic; 

Binary ‘operator >’ has too few parameters

Operatorlerin arity’sini korumak zorundasınız. 

Bazı tokenların 2 ayrı operator görevi  vardır. 
+x -> sign operator 
 a+ b -> addition

-i -> sign operator 
a - b -> subtraction operator 

& -> address of operator 
x & y -> bitwise and operator 

* ptr  -> dereferencing operator 
a * b -> çarpma operatoru 

Dolaysıyla bunları binary veya unary olarak overload ettiğimizde farklı operatorleri overload etmiş oluyoruz. 



Şimdi gelelim unary operatörlerin kullanımına. Global operator fonksiyonu olmaları durumunda örneğin x bir sınıf nesnesi ise derleyici operand olan ifadeyi fonksiyona argüman olarak gönderecek. 
!x   operator!(x) 

Member operator function olarak overload edildiğinde derleyici operatörün operandı olan ifadeyi *this nesnesi olarak alacak.  Yani o nesnesin operator fonksiyonunu çağıracak. Fonksiyonun parametre değişkeni olmamalı. 
```c++
class Nec {
public: 
	bool operator!();
};
```
Member operator function 

İstisnasız tüm operatör fonksiyonları isimleri ile çağrılabilir. 
Öyle yerler var ki, isimleri ile çağırmayı  tercih edebiliyoruz ya da mecbur kalıyoruz. 

x + y                       x.operator+(y) —-> member operator function
x + y 		        operator+(x,y) —> global operator function

Biri hariç hiçbir operator fonksiyonu varsayılan argüman alamaz. Varsayılan argüman mekanizması kapatılmış. Hangisi hariç ? fonksiyon çağrı operatörü. 
```c++
class Nec {
Public: 	
	Nec operator+(int x = 5) ;
}; 
```
Sentaks hatası. 

```c++
class Nec {
Public: 	
	Nec operator()(int x = 5)const ;
}; 
```
Sentaks hatası değil. 

Operator overloading mekanizmasında operatörlerin önceliğini ve öncelelik yönünü değiştiremezsiniz. 


priority / precedence
Associativity ( left or right) 

```c++
class Nec {
public: 
};
Nec operator+(const Nec&, const Nec&); 
Nec operator-(const Nec&, const Nec&); 
Nec operator>>(const Nec&, const Nec&); 

Nec operator*(const Nec&, const Nec&); 
int main()
{
	Nec n1, n2, n3, n4, n5; 
	n5 = ((n1 + (n2 * n3)) - n1) >> n4;  // derleyici bu şekilde ele alacak kodu
};
```
Global operator function olduğunu düşünelim. 
Üye operator fonksiyonu kullanımamış.

En yüksek öncelikle operator çarpma operatörü. Sonra toplama ve çıkarma operatörleri aynı öncelik seviyesinde ama soldan sağa (left associativity) 
Bu kod legal. 

Bütün operator fonksiyonları isimleriyle çağrılabilir. Hadi yapalım. 


n5.operator= (operator>>(operator-(operator+(n1, operator*(n2,n3)), n1), n4);

Bu şekilde de yazılabilir. İsimleriyle çağırdık. 

Şimdi üye operator fonksiyonu olarak ele alalım. 

```c++
class Nec {
public: 
	Nec operator+(const Nec&); 
Nec operator-(const Nec&,); 
Nec operator>>(const Nec&); 

Nec operator*(const Nec&); 

};
int main()
{
	Nec n1, n2, n3, n4, n5; 
	n5 = ((n1 + (n2 * n3)) - n1) >> n4;  // derleyici bu şekilde ele alacak kodu
n5.operator= (n1.operator+(n2.operator*(n3)).operator-(n1).operator>>(n4));
};
```

Operatörlerin öncelik seviyesi ve yönünü değiştiremeyiz. 

Neden global operator fonksiyonu da var ? o zaman şunu sağlama imkanı kalmazdı. 

x + 5 


X bir sınıf nesnesi ama 5 bir sınıf nesnesi değil. 5 primitive türden. 
Bunu şöyle bir çağrıya dönüştürebiliriz. 
x. operator(5); 
Peki şöyle olsaydı ? 

5 + x 
5.operator+(x)
Member operator function artık kullanılamaz. Global operator function burada devreye giriyor. 
Başka bir nokta daha var. 
Diyelim ki size ait olmayan bir sınıf var. Ama siz de başka bir sınıf oluşturuyorsunuz. 
```
class Nec {
public: 
}; 

class Erg
{
}; 

```
Diyelim ki Nec sınıfı türünden bir nesne ile Erg sınıfı türünden bir nesneyi toplamak istiyorsunuz. O zaman sol operand Nec sınıfı türünden olmak zorunda. O zaman Nec’in member function olmak zorunda. Ama Nec sınıfı bizim değil ki. Bana ait değil, zaten var. Ben Erg sınıfını yazıyorum. Şimdi hala global bir operator fonksiyonu yazabilirim. 

```
>>? operator+(const Nec&, const Erg&)
```

Global operator fonksiyonu öyle yerler var ki, olmak zorunda. Bazı yerlerde iş programcının tercihine kalabilir. Üye operatör fonksiyonu mu olsun global operatör fonksiyonu mu. Ama bazı yerlerde  global operatör fonksiyonu olmak zorunda. 

Başka bir örnek, int türden bir değişkenin değerini formatlı olarak standard output’a yazdırmak istersem operator overloading’den faydalanıyorum. 
```c++
int x = 5; 
cout << x; 
cout.operator<<(x); 
```
Çok basit bir sınıf yazalım. 
```c++

class Counter{
public: 
	Counter(int x = 0) : mx{0}  {}
private:
	Int mx; 
}; 

Int main()
{
	cout << Counter {47};     (1)

}
```

(1) : şimdi üye operatör fonksiyonu olsaydı bu hangi sınıfın üye operatör fonksiyonu olmalıydı ? cout hangi sınıf türündense onun, o sınıfın ismi ostream. Ama ostream sınıfı bana ait değil. Standard kütüphanenin kodu. Standard kütüphanede yapılan değişiklikler tanımsız davranış niteliğinde. Ama global operator fonksiyonuna yazabilirim. 

```c++
class Counter{
public: 
	Counter(int x = 0) : mx{0}  {}
friend std::ostream& operator<<(std::ostream& os, const Counter& c) //hidden friend
{
	return os << ‘(‘ << c.mx<<’)’;
}
private:
	Int mx; 
}; 



Int main()
{
	cout << Counter {47} << “ali” <<Counter{98}; 

}
```

Global operator fonksiyonu gerekiyor bazı durumlar için. 


Fonksiyonların geri dönüş değerlerinin türünün ne olması gerektiğini belirleyen semantik yapıdır. O sınıf neyi temsil ediyor ? 

```c++
class Date{
	operator+(int days)const; 
operator-(const Date&)const; 
}; 

```
tarih + gün = tarih olması gerekir geri dönüş değerinin 

tarih - gün =  gün olması gerekir geri dönüş değerinin
Tarih karşılaştırmasında bool olması gerekir geri dönüş değerinin

Fonksiyonun geri dönüş değerinin türü problem domeini ile ilgili. 

Fonksiyonun geri dönüş değerinin türü referans türü olmalı mı ?

m1+m2 —> PR value

m1.operator+(m2)

Toplama çarpma çıkarma giib operatör fonksiyonlarının geri dönüş değeri türünün L value referans olmaması gerekiyor. L value yaparsanız semantik olarak yanlış olacağı gibi kime referans olacak bu ? saçma. 
Otomatik ömürlü nesneye referans döndüremeyeceğimize göre tanımsız davranış olur. 
Referans türü yaparsanız bir nesneye referans olması gerekir. 
Eğer operatör doğal olarak operatörün oluşturudğu ifade PR value expression ise operatörün oluşturdğu ifadenin değeri aslında biziö fonksiyonun geri dönüş değeri olduğuna göre bu durumda fonksiyonun geri dönüş değerinin value type, referans türü olmaması gerekiyor. 
Ama her operatör için böyle değil. 

x=y 
++y
x+=y
*ptr
a[4]

Bu ifadelerin hepsi L value expression, bu ifadelerin value kategorisi L value

Bunların hepsi bir fonksiyon çağrısı, fonksiyon çağrı ifadesinin L value exp olması için fonksiyon geri dönüş türünün L value expr olması gerekir. 

Fonksiyonun mutability açısından deeğerlendirilmes; 
Toplama operatörünün bir side effect’i yoktur. ( yan etkisi) 
x+y
Yan etkisinin olmaması demek bu işlemden x ve y değişmeyecek. Bu operatör global operator fonksiyonu ise referans semantiği ile argümanlarını alıyorsa kesinlikle parametrlerinin const L value reference olması gerekir. 

T operator+(const T&, const T&); 


T operator+( T&, T&);  sentaks hatası olmazdı ama çok kaba olurdu. Dikkat etttt…


Eğer bu üye operator fonksiyonu ise; 
x.operator+(y) 
X’in değişmeyeceğini gösteren nedir ? 

```c++
class Nec{
public: 
	operator+(const Nec&)const;            
};
```

Const correctness açısından böyle. 

x+= y; 
Bu işlemden y değişmeyecek, x değişecek

```c++
class Nec{
public: 
	operator+(const Nec&);            
};

```
x const member function değil. Çünkü değişecek. 

Operator fonksiyonları overload edilebilir. Yani function overloading ile operator overloading birlikte kullanılabilir. 

Standard kütüphaneden operator overloading örnekleri; 
String sınıfı en tipik örneklerden biri. 


Referans semantiği neden var ? pointer semantiği ile assembly düzeyinde aynı ama dil katmanında farklı. Eğer referans semantiği olmasaydı operator overloading olamazdı. 

Sınıf nesneniz var. 

Myclass m1,m2; 
m1 + m2; 

Referans semantiğini zorunlu kılan operator overloading mekanizması. 

```c++
class Myclass{
Public: 
	Myclass& operator=(const Myclass&);
	Myclass& operator+(const Myclass&);
};

Int main()
{
	Myclass m1, m2; 
	m1+= m2;
};

```
Böyle bir mekanizma var. Artı eşittir operatörünü de implemente etmeniz gerekir. 

=========================================
Global operatör fonksiyonu mu olsun üye operatör fonksiyonu mu ?
Programcının kararı 2 yönde de olabilir. Şöyle bir ilke var. 
Simetrik operatörleri overload ederken global operatör fonksiyon kullanılabilir. 
a + b
b + a

İkisi aynı anlama geliyorsa, aynı soyutlama ise global operatör fonksiyonu.
Global operatör fonksiyonu olması dönüşümlere de izin veriyor. Birinci operandın sınıf türünden olmaması durumunda constructor da explicit değilse dönüşüme izin veriyor. 


Sınıf nesnesini değiştiren operatörleri üye operatör fonksiyonu yapılabilir. 

Simetri bozuluyorsa çözüm çoğunlukla üye operatör fonksiyonu. 

mydate - ndays

Tarihten gün çıkartılır ama günden tarih çıkarılmaz. Simetri söz konusu değil. Üye operatör fonksiyonu kullan. Programcıların uyduğu ilkelerden biri. 

Gerçekten bir sınıf oluşturalım ve overloading ile ilgili kodu yazalım. 
Fraction f1 {2,7}; 

int eşdeğeri nesneleri int türden değişkenler gibi kullanılan sınıf oluşturucaz. Bu tür sınıflar c++ dilinde çok popüler. Buna light wrapper sınıfları deniyor.. 
Yani tam sayı ya da gerçek sayı türünü doğrudan kullanmak yerine onu bir sınıfla ifade ediyorsunuz ve o sınıf türünden nesneleri kullanıyorsunuz. C++ bu konuda çok başarılı bir dil. Böyle sarmalayıcı sınıflar zero cost abstraction denen sınıf maliyetle implemente edebiliyorlar. 

Ilave bir maliyeti yok demek. 
Modern c++ ile dile eklenen bir kütüphane var, chrono kütüphanesi. Tarih zaman işlemleri ile ilgili kütüphane. Değerleri süre olan türler. Aslında ben bir saniye değerini bir tam sayı değeri ile ifade edebilirim. Fakat bir saniye değerini şöyle ifade etmiş chrono kütüphanesi. 
2 farklı kodu inceleyelim. 

long long msx = 848484954; 


Milliseconds ms{3283883}; 

Milliseconds’un kendisi bir tür. 
Derdini daha iyi ifade ediyor, tür dönüşümlerini daha iyi kontrol etmenizi sağlıyor. exception handling konusunda daha başarılı. 
Düşünün ki assembly kodu aynı. Interface’e kazandırmış oluyoruz. Derleyicilerin uyguladığı compile time’daki optimizasyonlar zero cost abstraction’a destek veriyor. 

Zero cost abstraction olmasını sağlayan ; 
Dilin araçları
Derleyicinin yaptığı optimizasyonlar

Strong type adında bir kavram var. Belirli yerlerde primitive türlerini kullanmak yerine primitive türlerin sarmalayan strong type olarak nitelenen primitive türlerin yerine geçen sınıf türlerini kullanmak büyük avantajlar sağlıyor. Maliyet artışı olmadan dilin adeta seviyesini sağlıyor. Daha yüksek seviyede daha yüksek soyutlama ile kod yazma imkanı veriyor ama maliyet açısından herhangi bir maliyeti olmuyor. 

Her abstraction zero cost değil. Özellikle nesne yönelim programlama tarafındaki soyutlamalar maliyetli soyutlamalar. 

```c++
class Myclass{
//….
public: 
	Void foo();
}; 

int main()
{
	Myclass* p = new Myclass; 
	////
	delete p; 
}

class Myclass{
//….
}; 

int main()
{
	std::unique_ptr<Myclass> p(new Myclass);
	p->bar(); 
	
}

```

Assembly düzeyinde hiçbir farklılık yok. Storage ihtiyacı aynı. Bu da bir wraple. Myclass pointerını sarmalıyor. Yani diyor ki, Myclass pointerını doğrudan kullanma. Bu sınıfı kullan, bu sınıf Myclass pointerını kontrollü bir şekilde kullanmana izin verecek interface oluştursun. Bu da mesela bir zero cost abstraction. 

Burada fonksiyon çağrı maliyeti var, nasıl zero cost abstraction olabilir ? inline expansion. 
Burada tamamen zero cost abstraction’a destek olan optimizasyon, inline expansion. 

int eşdeğeri nesneleri int türden değişkenler gibi kullanılan sınıf oluşturucaz.
include koruması, multiple inclusion guard ile header dosyasının oluşturulmasına başlandı 
#pragma once → standard değil. 

cint.h file; 
```c++
#if !defined CINT_H
#define CINT_H

class Cint{

public:
	Cint() = default; 
	explicit Cint(int val) : mval{val} { };
private: 
	int mval{}; 



};

#endif
```



main.cpp file;

```c++
#include “cint.h”

Int main()
{
	Cint c1 

}

```

Formatlı giriş çıkış işlemleri
Formatlı giriş çıkış fonksiyonları : printf, scanf 
Formatsız giriş çıkış fonksiyonları : fread, fwrite

Formatlı demek, çıktının veya girdinin bir yazı olması demek. 3

Aksi yönde karar almanızı gerektirecek bir durum söz konusu değilse, formatlı giriş çıkış işlemleri için operator left shift ve operator right shift fonksiyonları yazıyorsunuz. Yani bitsel sola kaydırma ve bitsel sağa kaydırma operaötlerini overload ediyorsunuz. 

Neden böyle yapıyoruz ? standard kütüphane bu opearötleri overload ettiği için. 
Generic programlama tarafında bu çok çok önemli . Türden bağımsız bir kod. 
Generic kod derleyicinin yazacağı kod demektir. 

C++’ın giriş çıkış kütüphanesi o kadar çok araç kullanılıyor kombine halinde.
Generic programming, object oriented programming, functional programming. 

İsmi ostream ve istream adında sınıflar var. Bunları tür eş isimleri, type alias


std::cout nesnesinin türü ostream
Std::cin nesnesinin türü istream

```c++
void foo(std::ostream); 
int main()
{
	foo(std::cout);
}; 
```

Sentaks hatası. Bu sınıf kopyalamaya kapatılmış bir sınıf. Kopyalama semantiği ile bir fonksiyona geçmem mümkün değil. O zaman bu nesneyi bu fonksiyona geçmek için referans semantiğini kullanıyorum. 

```
void foo(std::ostream& os); 
int main()
{
	foo(std::cout);
}; 

class 0stream{

public: 
	0stream& operator<<(int) 
	0stream& operator<<(double) 

};

int main()
{
	int ival{4}; 
	double dval{4.5};
	cout << ival <<dval; 
	cout.operator<<(ival).operator<<(dval);
}
```

Yukarıdaki cout ile aşağıdaki cout arasında hiçbir fark yok. Hem function overloading hem operator overloading. 




cint.h file;

```c++

#if !defined CINT_H
#define CINT_H

#include <ostream> 
#include <istream> 
class Cint{

public:
	Cint() = default; 
	explicit Cint(int val) : mval{val} { };
	friend std::ostream& operator<<(std::ostream&os, const Cint& c) 
	{
		return os  << ‘(‘ << c.mal << ‘)’;  // one liner function
		

	}


	friend std::istream& operator>>(std::istream& is, Cint& c) 
	{
		return is >> c.mval; 

	}

	friend Cint operator+(const Cint& c1, const Cint& c2) 
	{
		return Cint{c1.mval + c2.mval}; 
	}
	
private: 
	int mval{}; 
};

#endif
```

main.cpp file;

```c++
#include “cint.h”

Int main()
{
	Cint c1 {35}, c2{4}, c3{56},c4; 
	cout << c1 << c2 <<c3; 
	operator<< (operator<<(operator<<(cout, c1), c2) ,c3); 
	cout << “tam sayi giriniz :”; 
	cin >> c4; 
	Std:cout << “girilen sayi” << c4; 
	cout << c1 + c2;  


}

```

Başlık dosyasında bir using bildirimi asla yapma. Çok kaba bir hata. Standard kütüphanenin öğelerini kendi başlık dosyanda kullancağın zaman nitelenmiş isim olarak kullan. Std::ostream gibi. 

C++20 standardı ile yeni bir kütüphane eklendi. Formatlı  Giriş çıkış işlemlerini iostream kütüphanesi ile yapmak yerine format kütüphanesi ile yapmak çok ciddi bir fark yaratıyor. 

std:: format kütüphanesi, araştır. 


cout << x 

Cout nesnesi stream’i temsil ediyor.  Biz x’i stream’e veriyoruz. Burada kullanılan fiil, insert fiili. 

x’i streame insert ediyorsunuz. O yüzden operator left shift fonksiyonuna bir çıkış akımına  yazdırmak için overload eden fonksiyonlara inserter demek de popüler olarak yaygın. 


cin>> x
Stream’den karakterleri alıyor o karakterleri kullanarak x’e set ediyor. Extracter deniyor popüler olarak. 

Kalıtım mekanizmasından bahsetti hoca, yazmadım. 

Generic programlama: 
Ben birden fazla tür için söz konusu olabilecek bir operasyonu bşrş fonksiyon halinde ifade etmem gerekiyor. Burada ayrı ayrı kodlar yazmak yerine derleyiicye kod yazdırmayı sağlayan ayrı bir kod formu kullanabiliyırum. C++’ın gerçek gücü burada. Türden bağımsızlık. Derleyiciye compile time’da kod yazdırıyoruz. C derleyicinden farklı olarak sadece derleme işlemi yapan bir progrma eğil derleyici aynı zamanda bizim için kod yazan bir program. 

Derleyiciye kod yazdıran kod —-> meta code 
Template dediğimiz araç seti ile yapılıyor. 

```c++
template <typename T>
void func(T x)
{
	std::cout << x; 
}



int main()
{
	func(12); 

}
```




# 2 Mart 2024 15. Ders

Operator overloading konusuna giriş yapmıştık. Tipik olarak aritmetik operatörler, binary aritmetik operatörler global, free fonksiyon olarak overload ediliyorlar. Binary simetrik operatörleri global fonksiyon olarak overload edilmeli olarak kabul ediliyor. Fonksiyonun friend olup olmaması 2 açıdan önem taşıyor. 
1) Friend olduğu zaman sınıfın içinde inline olarak tanımlayabiliyoruz
2) Böyle friend fonksiyonlara hidden friend deniyor. 
ADL dediğimiz kuralla bir ilişkisi var. Bazı avantajlar sağlıyor. 
Formatlı giriş çıkış işlemleri için bitsel sola kaydırma ve sağa kaydırma operatörlerinin overload edillmesini gördük. 

```c++
class Cint {

public:
	Cint() = default;
	explicit Cint(int val) : mcal{val} { }
	friend std::ostream& operator<<(std::ostream& os, const Cint& c)
	{
		return os << '(' << c.mal << ')';
	}
	friend std::istream& operator>>(std::istream& is, Cint& c)
	{
		return is >> c.mval;
	}

	friend Cint operator+(const Cint& c1, const Cint& c2)
	{
		return Cint{c1.maval + c2.mval};
	}

private:
	int mval{};
};
```
Namescape ve ADL 
Friend olmasının önemli sonucu sınıfın private bölümüne erişme hakkı olması. 

İşlemli atama operatörleri tipik olarak sınıf nesnesini değiştirdikleri için sınıfın üye fonksiyonu olma eğiliminde. Atama operator fonksiyonları üye fonksiyon olmak zorunda. Sınıf nesnesini değiştirdikleri için const üye fonksiyon olmamaları gerekiyor. 

Burada kullanılan ilginç bir teknik var; 

```c++
Cint& operator +=(const Cint& r) 
{
	mval += r.mval;
	return *this;
}
```
(atama operatörü ile oluşturulan ifadeler L value expression’dur) .
Toplama operatörünü şöyle de overload edebilirdik. 

```c++
friend Cint& operator +=(const Cint& c1, const Cint& c2) 
{
	Cint temp{c1};
Temp += c2;
	Return temp;
}


```

Olası avantajlarından biri sınıfın private bölümüne erişme mecburiyeti artık yok. 
Bunu biraz daha kompakt halde yazabiliriz. Daha şık. 

```c++
friend Cint& operator +=(const Cint& c1, const Cint& c2) 
{
	return Cint{c1} += c2; 

}
```

Derleyicinin optimizasyonunu artırabiliyor. Efficiency açısından bir fark var. 

Bu yazım biçimde scot neyers’ın efficiency c++ kitabında önerdiği bir yazım biçimi. 

Bir de işaret operatörünü değinelim. Onu da overload edebiliyoruz. 

Karşılaştırma operatörleri; operator overloading de en önemli grup karşılaştırma operatörleri. 
Aslında 2 gruba ayrılıyor. C programlamadan zaten biliyoruz. 

==     !=                      ( equality operators) 

>     >=          <          <= ( relational operators)

Bu iki grup arasında operatör önceliği açısından relational operatörler equality operatörlerinden daha yüksek öncelikli. Karşılaştırma operatörleri binary operatörler ve yan etkileri yok bu operatörlerin. 
A == b 
Ne a değişecek ne de b değişecek. 

Karşılaştırma operatörleri bool türden değer üretirler. Geri dönüş değerlerinin de bool olması doğal olanı.  Önermeler ile sorular soruyoruz aslında. A b’den büyük mü gibi ? 

2 tane sınıf nesnesini bu operatörrlerle karşılaştırma yapsam bu operatörler overload edilmemiş ise sentaks hatası. 

Client kodların bu işlemleri yapabilmesini istiyorsak 6 tane karşılaştırma operatörünü overload etmemiz gerekiyor. Fakat C++20 standardı ile çok şey değişti. Bu araç karşılaştırma operatörlerinin kullanımında büyük avantajlar ve kolaylıklar sağlıyor. Problemlİ durumları daha kolay handle ediyor. 

Bu operatörünün ismi three way comparison operator, 3 yollu karşılaştırma operatörler
< = > 
Bu operatörü overload ettiğimiz derleyici karşılaştırma operatörleri ile oluşturulmuş ifadeleri belirli kurallar çerçevesinde bu operatörün kullanıldığı ifadeler dönüştürüyor. 
Bu da bizim karşılaştırma operatörleri için ayrı ayrı kod yazmamızı ortadan kaldırıyor. Üstelik bazı avantajları da var. 

x > 5    ( x bir sınıf nesnesi) 
5 > x

Derleyici bu operatörün oveload edilmesi durumunda operandlarını yerlerini  değiştirecek şekilde kodu ele alabiliyor. 
C++20 standardı ile three way comparison operatörünü kullanmak çok avantajlı. İleride görücez. Çok önemli bir araç.  Her ne kadar resmi ismi three way comparison operatör olsa da popüler ismi spaceship operatörü de deniyor. 
Bunları üstelik default edebiliyorsunuz, C++20 öncesinde default bildirimi sadece special member function için geçerliydi, ama c++20 sonrası bu fonksiyonun da default bildirimini yapabiliyorsunuz, derleyici kodu kendisi yazıyor. 

Standard kütüphane de değişikliğe uğradı, C++20 öncesinde kütüphane ayrı ayrı overload ediyordu. Artık bu operatörlerin ayrı ayrı overload edilmesi yerine space shift operatörü overload ediliyor. 

Çok sık kullanılan bir teknik, sınıfların çok büyük çoğunluğu için 2 tane operatörünün standart kütüphane açısından çok büyük önemi var. Özel bir öneme sahip. 
Her ne kadar 6 tane karşılaştırma operatörümüz olsa da 2 tanesinin özel bir yeri var. 
operator <
operator == 

Diğerlerine göre daha önemli olmasının birkaç tane nedeni var. 
Birisi standard kütüphanenin kullanımı. Standard kütüphane bazı öğelerinde generic programlama tarafında bu operatörleri kullanıyor. 

Container, veri yapılarını temsil eden sınıflar. 
Set kütüphanesi, tipik olarak ikili arama ağacı. Değerle erişimin, logaritmik karmaşıklıkla gerçekleştirildiği veri yapısı. 

a < b 

a > b       ========================   b < a
a >= b       ========================   !(a < b)
a <= b ============================  !(b<a)

Türlerin çoğu için elinizde küçüktür işlemini yapacak bir araç varsa, diğer relational operatörleri küçüktür yoluyla ifade edebilirim. Bu da kod tekrarını engellemiş olurum, derleyiciye de optimizasyon imkanı sunarım. 
 Dolayısıyla karşılaştırma operatörlerini overload ederken en çok kullanılan teknik bu. Küçüktür operatörünün kodunu yaz ister global operator function olsun ister member operator function olsun ama diğerleri küçüktür operatörüne çağrı yaparak işini gerçekleştirsin. 

a == b                           !(a < b) && !(b < a)        bu şekilde de ifade edilebilir. 

a != b               !(a==b) 


Aşağıdaki operatörlerin overload edilmesini görücez. 

++

- -
  
[ ]

*ptr 

ptr->func

Function call operator

Typecast


++
- - 
Bu operatörlerin overload edilmesi ilginç. 

++x    x++ 
- - x     x - -
(Biraz hatırlatma) 

++x 
y++

Her 2 operatör de yan etki olarak operandı olan nesneyi değiştiriyorr. Operandlarının L value expression olması gerekir C’de. 

Operatörlerin ürettiği değer farklı 
++x → nesne değerinin 1 fazlası
y++ -> nesnenin kendi değeri

C++ tarafında ise, bu operatörlerin ön ek formunun L value expression oluşturması, son ek formunun R value PR value expression oluşturması. 
Dolayısıyla    ++x bu ifade L value expression
x++ ifadesi R value expression

Şöyle bir problem var. Dilin operatör overloading mekanizmasını oluşturan standard komite üyeleri şöyle bir çözüm bulmak zorundalar. 


Peki, ++ ön ek ve son ek olması durumunda farklı semantik yapıya sahip olduğuna göre bunların implementasyonunun ayrı olması gerekiyor. Üretilen değer farklı olduğuna göre farklı kodlar olmalı. 

++x için ayrı bir kod x++ için ayrı kodlar.

Ama bu operatorler unary operatorler. 
Ister ön ek ister son ek olsun ikisi de unary operator olduğu ikisi için ayrı bir tanım yapmak overloading kurallarını çiğneyecek. imza farklılığı olmayacak yani. 

Burada bir kural uydurmak zorundalar. 
Derleyicinin hangi fonksiyonun ön ek hangi fonksiyonun son ek olduğunu anlaması için. 

Eğer siz bu fonksiyonları sınıfın üye fonksiyonu olarak yazarsanız unary operator olduğu için parametre değişkeninin olmaması gerekiyor. 

Cint& operator++() —> ön ek artı artı operatoru //prefix    ( paramatresi yok) Geri dönüş değeri L value 

Cint operator++(int) —> son ek artı artı operatoru  // postfix (derleyici 0 değerini argüman olarak ele alacak) dummy int parametresi olacak. Geri dönüş değeri sınıf türünden olacak.  


Index operatörü 

a[b]  , *(a+b) ifadesi ile aynı
b[a]  , *(b+a) ifadesi ile aynı. 

```c++
int main()
{

int a[]= { 3,7,3,4,6,7};

for (int i = 0; i < 6; ++i)
{
	std::cout << a[i] << i[a] << *(a+i) << *(i+a) << ‘\n’;

}
```

x bir sınıf nesnesi
derleyici x[2] gibi bir ifadeyi bir fonksiyon çağrısına dönüştürecek. 
Member operation function olmak zorunda.  Global operatör fonksiyonu olarak overload edilmesi sentaks hatası. 

x[2]  ===> x.operator[] (2)   —-> derleyici bu şekilde ele alacak. 
Array like 
Pointer like

Standart kütüphanede köşeli parantez operatörünün hangi sınıflar için overload edildiğine bakalım; 

Vector sınıfı 

String sınıfı

Array sınıfı 

Iterator sınıfı

Smart pointer sınıfları 

Hepsinin ortak özelliği array like, pointer like sınıflar olması. Böyle bir interface sunan sınıflar. 

Sınıfın üye operatör fonksiyonu olmak zorunda → köşeli parantez operatörü, L value expression oluşturması gerekiyor 

Köşeli parantez operatörünün geri dönüş değeri türü her zaman L value referans olması gerekir. 

ar[4] = 5; 
ar.operator[ ](4) = 5, 

Sanki bir dizinin 4 indisli elemanına 5 değerini atamışız gibi bir görüntü var ama aslında bu fonksiyonun geri dönüş değeri olan nesneye biz bu değeri atıyoruz. 

Standart kütüphaneden birkaç örnek verelim. Mesela string sınıfı. 

```c++
int main()
{
	using namespace std; 
string name {“serhat arslan”};

for(size_t i{]; i < name.length(); ++i)
{
	cout << name[i]<< ‘ ‘ ; 
	cout << name.operator[](i)<< ‘ ‘ ; 
}
}
```
Yazının karakterine eriştiriyor. 

İkisi arasında bir fark yok. 

Köşeli parantez operatörü ile ilgili önemli bir detay var. Aynı durum diğer sınıflar için de geçerli. 

```c++
#include <isotream>
#include <vector>
#include <string>

int main()
{
	using namespace std;
	const string name{"Kaya"};
	auto c = name[3];
	name[2]='r';
}

```
Const overloading. 
Sınıf nesnemizin kendisi const ise köşeli parantez operatörü ile eriştiğimiz nesnenin const olması gerekir. 

```c++
#include <isotream>
#include <vector>
#include <string>

class String {
public:
	String();
	String(const char *p);
	char& operator[](std::size_t idx);
	const char& operator[](std::size_t idx)const;
};

int main()
{
	using namespace std;
	String s("necati");
	s[2] = 'A';
}

```
Const olmayan üye fonksiyonu çağrılacak ve değiştirebilicem. 
Nesnem const olsaydı function overload resolution kurallarına göre const ile tanımlanan fonksiyon çağrılacaktı ve sentaks hatası olacaktı. Anlamadım 😀

```c++
#include <isotream>
#include <vector>
#include <string>

class String {
public:
	String();
	String(const char *p);
	char& operator[](std::size_t idx);
	const char& operator[](std::size_t idx)const;
};

int main()
{
	using namespace std;
	const String s("necati");
	s[2] = 'A';
}

```
Sentaks hatası. 
Köşeli parantez operatör fonksiyonuna örnek verelim. 


C dizilerini sarmalayan bir sınıf oluşturmak. 
int a[4] yerine Array x(4) bunun gibi bir sınıf oluşturmak istiyorum. 
Std::array zaten bu şekilde. 

std::array<int,5> ar;   // array sınıfını kullanmanın bir sürü avantajı var, ilave maliyeti yok. 

Biz biraz daha primitive düzeyde kod yazalım.

```c++
class Array{
public: 
	explicit Array(std::size_t n) : msize{}, mp{new int[n]}
 { 
std::memset(mp, 0, n* sizeof(int));
} 
	Std::size_t size()const
{
	return msize; 
}

	void sort();

	int& operator[](std::size_t idx)
{
	return mp[idx];
}

	const int& operator[](std::size_t idx)const
{
	return mp[idx];
}

private:
	std::size_t msize; 

	int * mp; 
};

int main()
{
Array a1(12);
for ( size_t i = 0; i< a1.size();++i)
{
	a1i] = i; 
}
}
```
İşin içine sınıf nesneleri girince a[i] ile i[a] aynı anlamda değil. Bu pointerlar için böyle. 

```c++
int main()
{
	using namespace std;
	string name{"necati"};
	auto c1 = name[3];
	auto c2 = 3[name];
}

```

Geçerli değil. Sınıf nesneleri için bunu legal kılmanın doğrudan bir yolu yok. 

* ptr dereferencing operatörü 
ptr -> member selection arrow operatorü 

Bu operatörlerin overload edilmesi için Pointer like veya smart pointer sınıflar olmalı. Smart pointer, dinamik ömürlü nesnelerin hayatlarını kontrol etmek için kullandığımız sınıf nesneler. 

C’den gelen bir çağrışımı var. 

*ptr 
Eğer bir adresi içerik operatörünün operandı yaparsanız o adresteki nesneye erişirsiniz. 

ptr ->func()
Bir yapı pointerını ok operatörünün operandı yaparsanız aslında bu pointerın gösterdiği nesneye erişip onun veri elemanını kullanırsınız. 

ptr ‘nin kendisi bir pointer değil ama pointermış gibi kullanılacak, içerik operatörünün operandı yaptığımda sözde gösterdiği nesneye eriştirecek bizi. Bunu yapmanın tek yolu içerik operatörünü overload etmek. 

*ptr 
Yani derleyici eğer ptr bir sınıf nesnesi ise yukarıdaki kodu aşağıdaki kod gibi ele alacak. 
ptr.operator*()

Dereferencing operatörü L value bir ifade oluşturur.  Fonksiyonun geri dönüş değeri türü L value referans

Ok operatörü biraz problemli. 
Kural biraz farklı. 

```c++
class Pointer {
public: 
	Pointer(int *ptr) : mp{ptr}   { } 
	int& operator*()
	{
		Std::cout << “pointer::operator*\n”;
		return *mp; 
	}
private: 
	int* mp; 
};

int main()
{
	int x = 10; 
	Pointer p{&x}; 
	cout <<*p<<’\n’; 
	cout << p.operator() << ‘\n’; 
	++*p; 
}
```

Kod legal. 
Derleyici bu ifadeyi p’nin operator içerik fonksiyonuna yapılan çağrıya dönüştürdü.

```c++
cout <<*p<<’\n’; 
cout << p.operator() << ‘\n’; 
```

*p ifadesi aslında p’nin gösterdiği nesne demek C’de. bu fonksiyon çağrılıyor bu fonksiyon referans semantiği ile sınıfın private veri elemanı olan mp’nin gösterdiği nesneyi döndürüyor. 

Ama şimdi bakınız. Ok operatöründe durum farklı. Neden duru farklı ? çünkü ptr->func() ifadesinin geçerli olması için kural uydurmak gerekiyor. Neden ? bu durumda ptr öyle bir pointer olacak ki siz ptr->func(9 dediğinizde ptr’nin gösterdiği sınıf nesnesinin func isimli fonksiyonu çağrılacak. Bunu sağlayacak bir mekanizmaya ihtiyaç var. 

Ok operatörü binary bir operator. 2 tane operandı var. 
Normalde binary operator sınıfın üye fonksiyonu olması durumunda olsa olsa sağ operandı olan ifadenin bu fonksiyona argüman olarak gönderilmesi gerekir değil mi ? evet. Ama bu da faydalı bir senaryoya dönüşmez. O yüzden şöyle bir kural uydurmuşlar. 

Ptr’nin bir sınıf nesnesi olduğunu düşünelim. Diyelim ki bu sınıfın ismi smart pointer. 


SmartPointer ptr; 

ptr->func(), 

Derleyici böyle bir sınıf nesnesinin ok operatörünün operandı olduğunu gördüğünde sınıfın ok operatör fonksiyonu olup olmadığına bakıyor. Bu arada ok operatör fonksiyonu global operator fonksiyonu olarak overload edilemiyor. Üye operatör fonksiyonu olması şart. 

Derleyici böyle bir ifadeyi şuna dönüştürüyor. 
ptr->func(), 

ptr.operator->()->func(); 

Eğer ptr bir sınıf nesnesi ise ve ok operatörünün operandı olmuşsa her ne kadar burada ok operatörü burada overload edilmiş olsa da derleyici, ok operatör fonksiyonuna yapılan çağrıdan elde edilen geri dönüş değerini ifadedeki okun sol operandı yapıyor. Yani aslında biz ok operator fonksiyonuna çağrı yaparak ifade içindeki ok operatörünün sol operandı olan ifadeyi oluşturmuş oluyoruz. 

Bu durumda böyle bir ifadenin legal olması için ok operator fonksiyonunun geri dönüş değeri türünün address olması gerekir. Ancak adres olacak ki ok operatörünün operandı olabilsin. 

O yüzden sınıfların ok operatör fonksiyonları hemen her zaman pointer olan fonksiyonlardır. Böylece sınıf nesnesi ok operatör fonksiyonunun operandı olduğunda derleyici bunu şöyle bir ifadeye dönüştürür. 

ptr.operator->()->func(); 

Eğer sınıfın ok operator fonksiyonu üye fonksiyon ise - ki böyle olmak zorunda- bu durumda ok operatör fonksiyonunun kaç tane parametre değişkeninin olması lazım ? cevap 0 . argüman göndermeden çağrı yapıyorum. Parametre değişkeninin olmaması gerekiyor. 

Arrow member selection operatörü normalde binary bir operator olmasına karşın unary operatormüş gibi overload ediliyor. 

Üye fonksiyon olmak zorunda
Parametre değişkeni olmayacak 

Hoca burada standard kütüphaneden örnekler gösterdi. 

Memory başlık dosyasındaki ismi unique_ptr olan sınıf türünden bir nesne oluşturucam. 

```c++
class Myclass{
public:
	void foo()
	{
		std:.cout<< "Myclass::foo()\n";
	}
};

int main()
{
	using namespace std;
	unique_ptr<Myclass> uptr(new Myclass);
	uptr->foo();
	uptr.operator->()->foo();
}

```
Derleyici 23. Satırdaki ifadeyi 24. Satırdaki ifadeye dönüştürüyor. 

Ok operatör fonksiyonunun geri dönüş değerinin pointer olması gerekiyor. 

Sözde bir smart pointer sınıfı yazalım. 
Amacımız dinamik ömürlü bir Cİnt nesnesinin ömrünü kontrol eden bir smart pointer sınıfı yazalım 

Fonksiyon çağrı operatörünün overload edilmesi; 
En önemli operator overloading’, 
C++’ın generic programlama tarafına geçtiğimizde fonksiyon çağrı operatörünün overload edilmesinin ne kadar devleştiğini görücez. C++’ın en önemli araçlarından biri. 

Fonksiyon çağrı operatörünü overload edilmesinin fayda sağlaması generic programlama ile birlikte kullanıldığında mümkün oluyor. 



En ilginç en sık en önemli overloading örneği; 

func(4) 
C olsaydı bu şöyle olabilirdi.

a) Func bir fonksiyonun ismi ve burada çağrılan fonksiyon ismi func olan fonksiyon

b) Fonksiyonel makro da olabilirdi. Ön işlemci program burada bir replacement yapabilir

c) Func’ın bir function pointer olması. Func bir fonksiyon değil fonksiyon adresi tutan bir değişken. Ve bu da aslında pointerın değişkenin değeri olan adresteki fonksişyon çağrıldı olabilir.

C++ ‘da ise böyle bir ifade karşılığı bir fonksiyonun ç.ağrılmasını mümkün olan birden fazla seçenek var. 
Fakat bu seçenkler içinde yukarıdaki seçenekler de söz konusu olabilir. Fakat C’de olmayan C++’da olan ayrı bir mekanizma var. 
Func bir sınıf nesnesinin ismi olabilir, bir object bir instance olabilir. Bu durumda sınıf nesnesi fonksiyon çağrı operatörünün operandı olduğu için derleyici bunu sınıfın fonksiyon çağrı operatör fonksiyonuna çağrıya dönüştürebilir. Yani func’ı *this olacak kullanacak, operator fonksiyon çağrı fonksiyonuna çağrı yapacak. 

func.operator() (4) 

Ilk parantez fonksiyonun ismini oluşturan parantez. Fonksiyon çağrı operator fonksiyonu member operator function olmak zorunda. Global operator fonksiyonu olamaz. 
Biz önce bu fonksiyonlara ilişkin sentaks kurallarını inceleyeceğiz. 

Fonksiyon çağrı operator fonksiyonu; 

```c++
class Myclass{
public:
	void operator() ()
{
	std::cout <<”Myclass::operator() () this = “ << this << ‘\n’; 
}
}; 

int main()
{
Myclass m; 
std::cout <<&m<<’\n’; 
m(); 
m.operator()(); // böyle de çağrılabilir

}
```
Kodun çıktısı; 

```
&m = 0095F81B
Myclass::operator()() this = 0095F81B

```

Bu fonksiyonun parametresi olabilir, olmayabilir, birden fazla olabilir. Geri dönüş değeri istediğiniz şekilde seçilebilir.  Const olabilir, non cost olabilir. 


```c++

class Myclass{
Public:
	Int operator()(int x) const
{
	return x *3; 
}; 

int main()
{
	Myclass m; 
std::cout<<m(45) << ‘\n’; 
}
```

Overload da edilbilir. 

```c++
class Myclass {
public:
	void operator()(int) { std::cout << "int\n";}
	void operator()(char) { std::cout << "char\n";}
	void operator()(float) { std::cout << "float\n";}
	void operator()(bool) { std::cout << "bool\n";}
};

int main()
{
	Myclass m;
	m(1);
	m('2');
	m(3.f);
	m(4>5);
}
```
C++ terminolojisi; 
f() 
Eğer bir ifade bir isim fonksiyon çağrı operatörünün operandı olduğunda bir fonksiyonun çağrılması sonucunu doğuruyorsa bu ismin ilişkin olduğu varlığa callable denir.
f bir sınıf nesnesi de olabilir. 

Functor class (functor) 
Function object class (function object) 

Bir sınıf fonksiyon çağrı operatörünü overload ediyorsa functor ya da function object deniyor. Standard kütüphane de çokça geçiyor. 

C++ dilinin en önemli arçalarından biri derleyiciye kod yazdıracak kodu yazdırabilmemiz. Derleyiciye kod yazdıran kodlara template deniyor. 

Derleyiciye kod yazdıran kodlar şu kategorilerden birine ilişkin olabiliyor. 
Function template
Variable template
Class template
Alias template 
concept 

Derleyiciye kod yazdırma aracı modern C++’ın en önemli araçlarından biri. 
```c++

template <typename F>
void func(F x) 
{

}
```

Derleyiciye fonksiyon kodu yazdıran kod. 
Derleyicinin yazacağı fonksiyonun parametre değişkeninin türü compile time’da belli olacak. 
Derleyiciye yazacağı fonksiyonda kullanacağı türün ne olduğunu söylemeye yönelik mekanizmaya template argument deniyor. 

F nasıl bir tür olabilir ?
Function pointer
Değilse f bir sınıf türüyse bu durumda bu durumun legal olması için f’nin fonksiyon çağrı operatörünü overload etmiş bir sınıf türünden nesne olması gerekir değil mi ? evet. 
Işte generic programlama tarafında en çok kullandığımız araç bu. 
