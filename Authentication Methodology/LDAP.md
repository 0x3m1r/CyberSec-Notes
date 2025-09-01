# LDAP

### LDAP (Lightweight Directory Access Protocol) Nedir ?
- LDAP, uygulamaların kullanıcı bilgilerini hızlı bir şekilde sorgulamasını sağlayan bir protokoldür. Örneğin, ofisinizde bir kişi iki şey yapmak ister: Yeni işe alınan birine e-posta göndermek ve bu konuşmanın bir kopyasını yeni bir yazıcıdan yazdırmak. LDAP, bu iki adımın mümkün olmasını sağlar.
- Şirketler,Kullanıcı adları, parolalar, e-posta adresleri,yazıcı bağlantıları ve diğer statik verileri dizinlerde sakar.LDAP,bu veriler erişmek ve onları yönetmek için açık ve satıcıdan bağımsız bir uygulama prtokolüdür.LDAP aynı zamanda kimlik doğrulama işlemlerini de gerçkeleştirebilir;böylece kullanıcılar tek seferde oturum açarak sunucuda birçok farklı dosyaya erişebilir.

* LDAP bir protokol olduğu için dizin programlarının nasıl çalışacağını belirlemez.Bunun yerine, kullanıcıların ihtiyaç duydukları bilgiyi çok hızlı bulmalarını sağlayan bir dil biçmidir.

* LDAP satıcıdan bağımsızdır ve farklı dizin programlarıyla kullanılabilir. Tipik olarak bir dizin şu tür verilere sahiptir:
    * Tanımlayıcı (Descriptive): Bir varlığı tanımlamak için ad, knunm gibi birdeb fazla nokta bir araya gelir.
    * Statik (Static): Bilgiler çok değişmez ve değişitiğinde değişimler genllikle küçük olur.
    * Değerli (Valuable): Dizin içinde saklanan veriler, temel iş fonksiyonları için kritik öneme sahiptir ve sıkça kullanılır.

* Bazı durumlarda LDAP, iş gününde diğer sistemlerle birlikte kullanılır. Örneğin, çalışanlar yazıcılara bağlanmak veya parolaları doğrulamak için LDAP kullanabilir. Daha sonra e-posta için Google’a geçebilirler; bu durumda LDAP’a ihtiyaç duyulmaz.

---

* Bir LDAP sorgusu tipik olarak şu adımları içerir:
    * Oturum bağlantısı: KUllanıcı, LDAP portu üzerinden sunucuya bağlanır.
    * İstek: KUallanıcı, örneğin bir e-posta sorgusu gibi bir sorguyu sunucuya gönderir.
    * Yanıt: LDAP protokolü dizini sorgular, bilgiyi bulur ve kullanıcıya iletir.
    * Tamamlama: KUllanıcı LDAP portundan bağlantıyı keser.

- Herhangi bir arama başlamadan önce,LDAP kullanıcının kimliğini doğrulamalıdır.Bunun için 2 yöntem mevccuttur:
    * Simple (Basit): Doğru kullanıcı adı ve parola kullanıcının sunuya bağlanmasını sağlar.
    * Simple Authentication and Security Layer (SASL): Kerberos gibi ikincil bir hizmet, kullanıcı bağlanmadan önce kimlik doğrulama yapar.Gelişmiş güvenlik gerektiren şireketler için iyi bir seçenek olabilir.

* Bazı sorgular şirket içinde başlarken, bazıları mobil cihazlardan veya ev bilgisayarlarından başlar. LDAP iletişiminin çoğu şifrelenmeden veya karıştırılmadan gönderildiği için güvenlik sorunlarına yol açabilir. Bu nedenle çoğu şirket, LDAP mesajlarının güvenliğini sağlamak için Transport Layer Security (TLS) kullanır.


* LDAP ile kullanıcılar çeşitli işlemler yapabilir:
    * Add (Ekleme) : Veritabanına yeni bir dosya ekleme
    * Delete (Silme) : Veritabanından bir dosya silme
    * Search (Arama) : Veritabanında bir şeyi bulmak için sorgu başlatama
    * Compare (Karşılaştırma): iki dosyayı benzerlik veya fark açısından inceleme.
    * Modify (Değiştirme): Mevcut bir kayıtta değişiklik yapma.

---

### LDAP Terimleri 
* Data models : Dizin içinde hangi tür bilgiler bulunur? Modeller, LDAP içindeki farklı boyutları anlamanıza yardımcı olur. Örneğin genel bilgiler (object class), isimler (her öğenin benzersiz referansı), fonksiyonlar (veriye erişim şekli) ve güvenlik (kullanıcıların kimlik doğrulama sürecindeki hareketleri).
* Distinguished Name (DN – Ayırt Edici Ad): Her kaydın benzersiz kimliği olup, bilgi ağacı içindeki konumu da tanımlar.
* Modifications (Değişiklikler): LDAP kullanıcılarının bir kayda ait verileri değiştirmek için yaptığı istekler. Tanımlı değişiklik türleri ekleme, silme, değiştirme ve artırmadır.
* Relative Distinguished Name (RDN – Göreceli Ayırt Edici Ad): DN’leri birbirine bağlamanın ve göreceli konumu belirtmenin bir yolu.
* Schema (Şema): LDAP’ı destekleyen kodlama yapısıdır. Sunucuda yer alan her öğenin formatını ve özelliklerini tanımlamak için bu dil kullanılır.
* URLs: Sunucunun adresi ve portunu içeren, bir grup tanımlayabilen, konum sağlayabilen veya bir işlemi başka bir sunucuya yönlendirebilen veri dizisi.
* Uniform Resource Identifier (URI – Tekdüzen Kaynak Tanımlayıcı): Bir kaynağı tanımlayan karakter dizisi.


### LDAP ve Active Dİrectory
- Bazı kişiler LDAP ve Active Directory’yi birbirinin yerine kullanır ve bu alışkanlık büyük karışıklığa yol açar. Bu iki araç birlikte çalışır, ancak kesinlikle aynı şey değildir.
- Active Directory, bilgisayarlar, yazıcılar ve kullanıcılar gibi BT varlıklarını düzenlemek için kullanılan özel bir dizin aracıdır. Microsoft ürünü olarak, Windows ortamında yaygın şekilde kullanılır. Windows tabanlı bir ağda çalıştıysanız, bu sistem bazı verilerin temelini oluşturur.
- LDAP, Active Directory’yi okuyabilen bir protokoldür, ancak Linux tabanlı diğer programlar da dahil olmak üzere farklı yazılımlarla da kullanılabilir. Satıcıdan bağımsız bir protokol olduğu için, Windows ile ilgisi olmayan ürünlerle çalışmak için de kullanılabilir.

* Yani LDAP ve Active Directory, kullanıcıları desteklemek için birlikte çalışır. Ancak birbirleriyle rekabet etmezler ve tam olarak aynı işi yapmazlar.