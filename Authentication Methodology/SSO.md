# SSO

### What is single sign-on (SSO)?

- SSO, bir kullanıcının kimlik bilgilerini (kullanıcı adı, şifre vb.) yalnızca bir kez girerek birden fazla uygulamaya erişmesini sağlayan merkezi kimlik doğrulama sistemidir.
- Genellikle kurumsal ortamlarda kullanılır; uygulamalar BT tarafından atanır ve yönetilir; uzak çalışanlar da SSO’dan faydalanır.
- Kısa örnek: Mekânda kimlik bir kez kontrol edilir – kullanıcı tekrar tekrar kimlik göstermek zorunda kalmaz; SSO da benzer şekilde tek doğrulama ile birden çok hizmete erişim sağlar.
- SSO, birçok kimlik ve erişim yönetimi (IAM) veya erişim kontrol çözümünün önemli bir parçasıdır.

### What are the advantages of SSO

- Kullanıcılar için çok daha basit ve kullanışlı olmasının yanı sıra, SSO genellikle daha güvenli kabul edilir.

* Birden fazla parola yerine tek bir parolayla tek seferlik giriş yapmak nasıl daha güvenli olabilir? SSO savunucuları şu nedenleri öne sürer:
    * **Daha güçlü parolalar** : Kullanıcıların yalnızca tek bir parola kullanmaları gerektiğinden, SSO onların daha güçlü parolalar oluşturmasını, hatırlamasını ve kullanmasını kolaylaştırır.
    * **Tekrarlayan parolaların önlenmesi**:Kullanıcıların birçok farklı uygulama ve hizmet için parola hatırlamak zorunda kaldığında “parola yorgunluğu” yaşaması olasıdır. Bu durumda kullanıcılar aynı parolayı farklı hizmetlerde tekrar kullanmaya başlar. Bu, büyük bir güvenlik riskidir çünkü kullanılan tüm hizmetlerin güvenliği, en zayıf parola korumasına sahip olan hizmetle sınırlı hale gelir
    * **Daha iyi parola politikası uygulaması**:Tek bir giriş noktası olduğunda, SSO BT ekiplerinin parola güvenliği kurallarını uygulamasını kolaylaştırır.
    * **Çok faktörlü kimlik doğrulama (MFA)**:MFA, bir kullanıcıyı doğrulamak için birden fazla kimlik faktörünün kullanılmasını ifade eder.
    * **Parola Yeniden Girişi için tek bir nokta**:Yöneticiler, belirli bir süre geçtikten sonra kullanıcıdan tekrar kimlik bilgilerini girmesini isteyebilir.Bu, oturumun hala aynı kullanıcıya ait olduğunu garanti eder.SSO ile bu kontrol tüm iç uygulamlarda merkezi olarak yapılabilir;
    * **Dahili Kimlik bilgisi yönetimi**:Normalde kullanıcı parolaları, farklı uygulama ve hizmetler tarafından uzaktan, çoğu zaman da güvenlik standartlarına uygun olmayan şekilde saklanır.SSO ile ise bu parolalar BT ekibinin daha fazla kontrol sahibi olduğu dahili bir ortamda saklanır.
    * **Parola kurtarma için harcanan zaman azalması**:BT ekipleri onlarca uygulama için parola kurtarma ve sıfırlama işlemleriyle daha az uğraşır; kullanıcılar da işlerini yapmak için farklı uygulamalara tekrar tekrar giriş yapmak zorunda kalmaz.Bu da iş verimliliğini artırma potansiyeline sahiptir.

### How does an SSO login work ?
- Bir kullanıcı SSO hizmetine giriş yaptığında, hizmet kullanıcının doğrulandığını hatırlayan bir kimlik doğrulama belirteci (authentication token) oluşturur. Bu belirteç, kullanıcının tarayıcısında veya SSO hizmet sunucularında saklanan dijital bir bilgi parçasıdır;Kullanıcı herhangi bir uygulamaya erişmek istediği zaman,uygulama SSO hizmetiyle iletişim kurar. SSO hizmeti, kullanıcın kimlik doğrulama belirtecini uygulamaya iletir ve kullanıcıya erişim izni verilir.Ancak kullanıcı henüz giriş yapmadıysa, SSO hizmeti üzerinden giriş yapması istenir.

* Çoğu SSO hizmeti, kullanıcı kimlik bilgilerini ayrı bir kimlik yönetim servisi ile karşılaştırarak çalışır.


### How do SSO authentication tokens work ?
- Bunu yalnızca belli kişilerin girebildiği özel bir etkinlik gibi düşün.Etkinliğin girişindeki güvenlik görevlilerinin bir misafiri kontrol edip onayladığını göstermek için kullandığı yöntemlerden biri, misafirin eline damga basmaktır.Aynı şekilde, her damganın belirli bir görünümü olması gerektiği gibi, kimlik doğrulama belirteçlerinin de doğru ve geçerli olduklarını garanti altına almak için kendilerine özgü iletişim standartları vardır.Kimlik doğrulama belirteçleri için kullanılan ana standart SAML'dir

### How does SSO fit into an access managment strategy ?
- SSO, kullanıcı erişimini yönetmenin yanlızca bir yönüdür.Bir kuruluşun iç sistemlerinde kullanıcı davranışlarını izlemek ve kontrol etmek için erişim kontrolü, izin kontrolü, etkinlik günlükleri ve diğer önlemlerle birlikte kullanılmalıdır.Bununla birlikte, SSO erişim yönetiminin kritik bir unsurudur. Bir sistem, kullanıcın kim olduğunu bilmzese o kullanıcın eylemlerine izin vermek ya da onları kısıtlamak mümkün değildir.