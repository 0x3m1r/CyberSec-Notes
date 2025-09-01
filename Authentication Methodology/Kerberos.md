
# Kerberos Authentication Definition

- Geleneksel yöntemlerde kullanıcı bilgisayar sistemine erişmek istediği zaman şifresini girmesi lazım bu auth yönteminde ki challenge eğer hacker şifreye sahipse kullanıcının identity sini alıp organizasyonun networküne sızabilir.

* ***Kerberos***, kullanıcılar ile internet arasında bir geçit sağlayan bir sistem veya yönlendiricidir.Bu nedenle, siber saldırganların özel bir ağa girmesini önlemeye yardımcı olur.Son kullanıcılar ile çevrimiçi olarak ziyaret ettikleri web siteler arasında aracılık yaptığı için bir "aracı" sunucu olarak adlandırılır.

### Kerberos Nedir ?

* Kerberosun arkasındaki fikir, kullanıcıları doğrularken parolaların internet üzerinden gönderilmesini engellemektir.
* DNS ile aynı dönem çıktı
* Windows ta dahil bir çok popüler işletim sistemi kerberosu yerleşik olarak barındırır.


### Kerberosun Avantajı

1. Mature : Kerberos uzun süredir Kullanılması onun güvenlik açısından ne kadar yeterli olduğunu göstermektedir (Bundan pek emin değilim bence saçma bir çıkarım)
2. Moder Dağıtık sistem gereksinimlerini karşılar
3. Mimari açıdan sağlamdır
4. Popüler işletim sistemlerine entegre edilmiştir.
5. Erişim KOntrolü : Kerbereos kimlik doğrulama protokolü etkili bir erişim kontrolü sağlar.Kullanıcıların tüm oturum açma kayıdını tutmak ve güvenlik politikalarının uygulanmasını sağlamak için tek bir noktadan yararlanır
6. Karşılıklı kimlik doğrulama
7. Sınırlı bilet ömrü : kerberostaki her biletin zaman damgaları ve yaşam süresi vardır: Kilik doğrulamanın süresi yöneticiler tarafından kontrol edilir
8. Yeniden kullanılabilir auth
9. Güvenlik

### Kerberosun zayıf yöneleri
1. Tek hata noktası : KDC başarısız olursa, tüm auth süreci çalışmaz hale gelir. Bu da sistemi kırılgan hale getirir.
2. Her ağ hizmeti için ayrı bir kerberos anahtarı gerekmesi : Farklı ana bilgisayar adları gerektiren ağ hizmetleri, kendi Kerberos anahtar setlerine ihtiyaç duyar.Bu da kümeleme (cluster) ve sanal barındırma (virtual hosting) senaryolarında zorluklar yaratabilir.
3. Katı zaman gereksiimleri : Ana makinelerin tarih ve saat ayarlarının önceden tanımlanmış sınırlar içinde senkornize edilmesi gerekir. Aksi takdirde, biletlerin sınırlı geçerliliği nedeniyle kimlik doğrulama başarısız olur.


### Kerberos auth nasıl çalışıyor ?
* Kerberos, kullanıcı kimliklerini doğrulamak ve teyit etmek için simetrik anahtar kriptografisi ve bir anahtar dağıtım merkezi (KDC) kullanır.Bir KDC üç bileşenden oluşur:
    * Kullanıcıyı hizmet sunucusuna (SS) bağlayan bir bilet verme sunucusu (TGS)
    * Tüm doğrulanmış kullanıcıların parola ve kimlik bilgilerini saklayan bir kerberos veritabanı
    * İlk kimlik doğrulamayı gerçekleştiren bir kimlik doğrulama sunucusu (AS)

* Auth sırasında kerberos, her oturum için özel bileti son kullanıcının cihazında saklar.Parola yerine kerberos uyumlu bir hizmet bu bileti arar.
* Kerberos Auth, bir KDC 'nin bir hizmeti , ana bilgisayar veya kullanıcıyı doğrulamak için yetkilendirdiği bir ortam olan kerberos alanında (realm) gerçekleşir

* Kerberos kimlik doğrulama çok adımlı bir süreçtir ve şu bileşenlerden oluşur:
    * Kullanıcı adına hizmet talebi başlatan istemci
    * Kullanıcının erişmek istediği hizmeti barındıran sunucu
    * İstemci kimlik doğrulamasını gerçekleştirne AS. Eğer kimlik doğrulama başarılı olursa, istemciye bir bilet verme bileti (TGT) veya kullanıcı kimlik doğrulama jetonu verilir; bu, istemcinin doğrulandığınının kanıtıdır.
    * AS, TGS ve kerberos veritabanından oluşan KDC
    * Hizmet biletlerini veren TGS uygulaması


### Kerberos Protokol akışına genel bakış

- Kerberos protokol akışı 3 gizli anahtar içerir: İstemci/kullanıcı hash'ı, TGS gizli anahtarı ve SS gizli anahtarı. Temel protokol akışı adımları şunlardır:

1. Başlangıç İstemci Kimlik Doğrulama İsteği : Protokol akışı, istemcinin etki alanına giriş yapmasıyla başlar.Bu adımda kullanıcı, AS'den TGT veya kimlik doğrulama jetonu isterçTGT isteği Kerberos KDC'ye gönderilir.
2. İstemci Kimlik Bilgilerinin Doğrulanması : KDC, şifrelenmiş bir oturum anahtarı ve TGT gönderebilmek için kullanıcıların kimlik bilgilerini doğrulamalıdır.AS, veritabanında TGS ve istemcinin varlığını kontrol eder.Eğer ikiside mevcut ise AS gizli nahtarı üretir. Ayrıca, kullanıcının gizli anahtarı ile şifrelenmiş bir oturum anahtarı (SK1) ve istemcinin ağ adresi, kimliği (ID), zaman damgası, yaşam süresi ve SK1’i içeren bir TGT oluşturur. Ardından TGS gizli anahtarı bileti şifreler.
3. Mesajın şifre çözümü : İstemci, TGT ve SK1'i çıkarmak ve mesajın şifresini çözmek için kullanıcı hash'ini veya gizli anahatrını kullanır, ardından TGS'yi doğrulayan bir auth oluşturur
4. TGT Kuallanılarak Erişim isteği : İstemci daha sonra, doğrulayıcı ve çıkarttığı TGT'yi TGS'ye göndererek SS'den bir bilet talep eder.
5. Dosya sunucusu için bilet oluşturulması : TGS gizli anahtarı, istemciden gelen TGT'nin şifresini çözmek ve SK1’i çıkarmak için kullanılır. TGS ayrıca doğrulayıcının şifresini çözer, bunun istemci kimliği ve ağ adresiyle eşleştiğini doğrular ve zaman damgasını kullanarak TGT’nin süresinin dolmadığından emin olur.Tüm kontroller başarılı olursa, KDC hedef sunucu ve istemci için paylaşılan bir hizmet oturum anahtarı (SK2) üretir. Daha sonra istemci ağ adresi, kimlik, zaman damgası ve SK2’yi içeren bir hizmet bileti oluşturulur. Bu bilet sunucunun gizli anahtarıyla şifrelenir. İstemci ise SK1 ile şifrelenmiş SK2 ve hizmet biletini alır.
6. Dosya Bileti ile Kİmlik Doğrulama : İstemci, mesajın şifresini SK1 ile çözerek SK2’yi çıkarır. Bu işlem sonucunda istemci kimliği, ağ adresi ve zaman damgasını içeren, SK2 ile şifrelenmiş yeni bir doğrulayıcı üretilir. İstemci daha sonra hizmet biletini ve bu yeni doğrulayıcıyı hedef sunucuya gönderir.
7. Hedef Sunucunun Şifre Çözümü ve Kİmlik Doğrulaması : Kerberos protokolünün son adımında, hedef sunucu hizmet biletinin şifresini çözerek SK2’yi sunucunun gizli anahtarıyla çıkarır. SK2, doğrulayıcının şifresini çözmek için kullanılır ve istemcinin ağ adresi ile kimliğinin hizmet bileti ve doğrulayıcıyla eşleştiği kontrol edilir. Tüm kontroller başarıyla tamamlandığında sunucu, istemciye kendisiyle karşılıklı kimlik doğrulamasının başarıyla yapıldığını bildiren bir mesaj gönderir.


### KIerberos Hacklenebilir mi ?
* Kerberos da diğer tüm güvenlik modelleri gibi %100 saldırıya karşı dayanıklı değildir. Yaygın olarak kullanılan bir kimlik doğrulama protokolü olduğu için ssaldırganların bunu delmenin bir yolunu buldular. En yaygın yöntemler ŞUnlar : 
    1. Pass the Ticket : Bu yöntemde saldırgan, oturum anahtarını sahte olarak üretir ve sahte kimlik bilgileri kullanır. Hacker’lar, etki alanı erişimi veya bir hizmete erişim sağlamak için sahte “golden ticket” veya “silver ticket” oluştururlar.
    2. Credential Stuffing or Brute Force : Bu yöntem, bir kullanıcının parolasını tahmin etmek için otomatik ve sürekli denemelerden oluşur. Çoğu saldırı, bilet verme ve ilk biletleme hizmetini hedef alır.
    3. Encryption Downgrade : Bu saldırı, skeleton key adlı kötü amaçlı yazılım kullanılarak yapılır. Siber saldırgan yönetici erişimine sahipse, bu kötü amaçlı yazılım Kerberos’u devre dışı bırakabilir.
    4. DC Shadow Attack : Bu saldırı, hacker’ların kendi etki alanı denetleyicilerini (DC) kurmak için gerekli erişimi elde etmesiyle gerçekleşir. Bu, sisteme daha fazla sızmak için kullanılır.