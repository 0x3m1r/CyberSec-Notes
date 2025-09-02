# SSL SERTİFİKALARI

## SSL Sertifikası Nedir?
SSL sertifikaları, web sitelerinin HTTPS protokolü kullanmasını sağlayan dijital sertifikalardır. HTTPS, HTTP'ye göre daha güvenli bir iletişim sağlar. Bir SSL sertifikası, web sitesinin kaynak sunucusunda barındırılan bir veri dosyasıdır. Bu sertifikalar:

- SSL/TLS şifrelemesini mümkün kılar
- Sitenin genel anahtarını (public key) içerir
- Sitenin kimliğini ve ilgili bilgileri barındırır

Kaynak sunucuyla iletişim kurmaya çalışan cihazlar, bu sertifikaya başvurarak genel anahtarı alır ve sunucunun kimliğini doğrular. Özel anahtar (private key) ise gizli tutulur ve güvenli bir şekilde saklanır.

## SSL Sertifikaları Nasıl Çalışır?
SSL sertifikaları, tek bir veri dosyası içinde aşağıdaki bilgileri içerir:

* Sertifikanın verildiği alan adı
* Hangi kişi, kuruluş veya cihaza verildiği
* Hangi sertifika otoritesi tarafından verildiği
* Sertifika otoritesinin dijital imzası
* İlişkili alt alan adları
* Sertifikanın veriliş tarihi
* Sertifikanın son kullanma tarihi
* Genel anahtar (özel anahtar gizli tutulur)

SSL için kullanılan genel ve özel anahtarlar, verileri şifrelemek ve imzalamak için kullanılan uzun karakterli dizilerdir. Genel anahtarla şifrelenen veriler yalnızca özel anahtarla çözülebilir.

Sertifika, bir web sitesinin kaynak sunucusunda barındırılır ve siteye erişmek isteyen cihazlara gönderilir. Çoğu tarayıcı, kullanıcıların SSL sertifikasını görüntülemesine olanak tanır. Örneğin Chrome'da bu, URL çubuğunun solundaki kilit simgesine tıklanarak yapılabilir.

## Web Siteleri Neden SSL Sertifikasına İhtiyaç Duyar?
1. **Şifreleme** - Güvenli veri transferi sağlar
2. **Kimlik Doğrulama** - Site kimliğini doğrular
3. **HTTPS** - Güvenli bağlantı standardını destekler

## Web Siteleri SSL Sertifikasını Nasıl Elde Eder?
Bir SSL sertifikasının geçerli olabilmesi için, alan adının bunu bir sertifika otoritesinden (CA) alması gerekir. CA, SSL sertifikalarını üreten ve dağıtan, güvenilir üçüncü taraf bir kuruluştur. CA, kendi özel anahtarıyla sertifikayı dijital olarak imzalar; bu da istemci cihazların sertifikayı doğrulamasını sağlar. Çoğu CA, SSL sertifikası vermek için ücret talep eder.

## Kendinden İmzalı SSL Sertifikası Nedir?
Teknik olarak, herkes kendi genel-özel anahtar çiftini oluşturarak ve gerekli bilgileri ekleyerek kendi SSL sertifikasını oluşturabilir. Bu tür sertifikalara "kendinden imzalı sertifikalar" (self-signed certificates) denir. Bu sertifikalardaki dijital imza bir CA'dan (sertifika otoritesinden) değil, doğrudan web sitesinin kendi özel anahtarından gelir.