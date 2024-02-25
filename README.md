# C++-Kursu-Notları-

17 Şubat 2024 11. C++ Dersinden Notlar;
 
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
```
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
```
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

```
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

```
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

```
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

```
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

```
int main()
{
  // expr ==> std::string nesnesi
  // L value
  // R value ==> PR Value U X Value
}
```

Eğer string nesnesi anlamına gelen ifade R value expression ise bu ifadenin yürütülmesinden sonra bu nesneyi kullanacak bir kod yok demek. 
Ama ifade L value ise ifade persistent demektir. 

```
// std::string str{expr};
```
Derleyici bu ifadenin value kategorisinin L value olduğunu anlarsa str için function overload resolution ile copy constructorı çağıracak. Ama derleyici bu ifadenin compile time’da R value olduğunu anlarsa str için move constructor’ı çağıracak. 


Diyelim ki siz bir fonksiyon yazmak istiyorsunuz ve fonksiyonun parametresini referans yapmak istiyorsunuz. 

```
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

```
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

```
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

```
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

```
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


```
class Myclass{
private:
  int ar[400];
  double d[200];
};
```

Böyle bir sınıf için move constructor ile copy constructor arasında bir maliyet farkı olmaz ? hayır olmaz.

```
int main()
{

  string str(20000, 'A');
  std::string s(str);
}
```
Str ifadesi L value. 
Peki str için için copy constructor mu çağrılacak yoksa move constructor mı ? copy constructor. Diyelim ki ben bilerek isteyerek str’nin kaynağını çalmak istiyorum. O zaman kaynağını çalabilmem için copy constructor yerine move constructor’ın çağrılması gerekir. Ama move constructorın çağrılması için de argümanın R value expression olması gerekir. 

```
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

```
class Myclass {

};
```
Bu sınıfın herhangi bir special member functionu bildirilmiş durumda mı ? Hayır. Eğer sınıfın hiçbir special member function’u bildirilmemişse derleyici tüm special member functionları implicitly declared eder. 

```
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


```
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


```
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

```
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

```
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
Sınıfın bütün special member functionları var. 


2. Grup sınıf biçimi de var. Bu sınıflara move only type deniyor. Bunlar taşımaya açık ama kopyalamaya kapalı sınıflar. Yani bunların kopyalanması istenmiyor. Ya kopyalanması semantik açıdan doğru değil ya da kopyalanmasının bazı sakıncaları var.
   
Mesela unique_ptr sınıfı 

mesela std::ostream sınıf 

mesela std::thread sınıfı

```
int main()
{
  using namespace std;
  unique_ptr<int> x(nex int);
  auto y =move(x);
}
```

Taşımaya açık, kopyalamaya kapalı. 
Kendi sınıfımı taşımaya açmak istersem ne yapmam gerekiyor ? 

```
class Nec{
public:
    Nec(const Nec&) = delete;
    Nec& operator = (const Nec&) =  delete;
    Nec(Nec&&);
    Nec& operator = (Nec&);
};

```
Move only type

```
class Nec{
public:
    Nec(Nec&&);
    Nec& operator = (Nec&);
};

```

- Copyable & moveable
- Non copyable but movable ( move only type)
- Non copyable & non movable

```
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

```
struct Myclass{
    Myclass(const Myclass&) = delete;
    Myclass& operator= (const Myclass&) = delete;
};

```
Bu sınıf hem kopyalamaya hem de taşımaya karşı kapalı. 

```
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

```
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

```
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

```
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

```
class Myclass{
};

int main()
{
  int ival = 10;
  Myclass m;
  m = ival;
}

```

Sentaks hatası. Çünkü atama operatörünün sağ operandı int türden ama atama operatörünün sol operandı Myclass türünden. Int türden Myclass türüne örtülü dönüşüm yok. 

```
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

Derleyici atama operatörünün sağ operandının int türden olduğunu görünce bu atamanın yapılabilmesi için int’i örtülü olarak Myclass sınıfı türünden bir nesneye dönüştürdü. 

```
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
User defined conversion deniyor.

explicit constructor
