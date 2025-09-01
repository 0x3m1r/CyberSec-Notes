# RADIUS


### RADIUS (Remote Authentication Dial-İn User Service) Nedir ?
- Uzaktan erişim sunucularının, çevirmeli bağlantı kullanıcılarını doğrulamak ve onların talep ettikleri sistem veya hizmete erişim yetkilerini onaylamak için merkezi bir sunucu ile iletişim kurmasını sağlayan istemci-sunucu tabanlı bir protokol ve yazılımdır.


* RADIUS, bir şirketin kullanıcı profillerini tüm uzak sunucuların paylaşabileceği merkezi bir veritabanında tutmasına olanak tanır.
* Merkezi bir veritabanına sahip olmak daha iyi güvenlik sağlar; çünkü şirket, tek bir yönetim noktasından tüm ağa uygulanabilecek bir politika oluşturabilir. Ayrıca merkezi veritabanı, ağ erişimi veya internet servis sağlayıcısı için faturalandırmada kullanım takibini kolaylaştırır ve ağ istatistiklerini tutmayı sağlar.
* Günümüzde ise RADIUS, kablosuz ağlar, Ethernet ağları ve internet üzerinden diğer uzaktan kullanıcı erişim yöntemleri dahil olmak üzere farklı türdeki ağlarda uzaktan erişim için yaygın olarak kullanılmaktadır.


### RADIUS Kimlik Doğrulama Nasıl Çalışır ?
- RADIUS protokolünde, uzak ağ kullanıcıları ağlarına bir ağ erişim sunucusu (NAS) aracılığıyla bağlanır.NAS, uzak kullanıcı hakkında kimlik doğrulama, yetkilendirme ve yapılandırma bilgilerini almak için kimlik doğrulama sunucusuna sorgu gönderir.
* Diğer istemci-sunucu uygulamalarında istemci genellikle bireysel bir kullanıcı iken, RADIUS’ta istemci ağa erişim sağlayan NAS sistemleridir ve kimlik doğrulama sunucusu ise RADIUS sunucusudur.

* RADIUS protokolünde erişim sunucuları, RADIUS sunucusunun istemcisi gibi davranır. RADIUS protokolü, uzak kullanıcıların ağa bağlandığı sunuculara merkezi kimlik doğrulama hizmeti sağlar. Uzak kullanıcı erişim kimlik doğrulama sunucusu türleri şunları içerebilir:
    * Çevirmeli Sunucular (Dial-İn servers): Modem havuzları aracılığıyla kurumsal vya ISP ağlarına erişimi yönetir
    * Sanal özel ağ (VPN) sunucuları: Uzak kullanıcıların özel bir ağa güvenli bağlantı kurma isteklerini kabul eder.
    * Kablosuz erişim noktaları: KAblosuz istemcilerin ağa bağlanma isteklerini kabul eder.
    * Kablosuz erişim noktaları: Kablosuz istemcilerin ağa bağlanma isteklerini kabul eder.
    * Yönetilen ağ erişim anahtarları (Managed switches): 802.1x kimlik doğrulama protokolünü uygulayarak uzak kullanıcıların ağa erişimini yönetir.
* Son kullanıcılar, kimlik doğrulama sırasında RADIUS sunucusuyla doğrudan değil, yalnızca NAS aracılığıyla dolaylı olarak etkileşime girer.
* Bir son kullanıcı uzak ağa bağlanmak için bağlantı başlattığında, NAS kimlik doğrulama sunucusuyla bir RADIUS değişimini başlatır.
* Uzak kullanıcı bir NAS üzerinden bağlantı başlattığında, istek kullanıcının kimliğini (ID), parolasını ve IP adresini içerebilir. NAS, ardından kimlik doğrulama isteğini RADIUS sunucusuna gönderir.

## RADIUS Sunucuları Nasıl Kullanılır?
- RADIUS, kimlik doğrulamayı iki yöntemle gerçekleştirir.
    * Password Authentication Protocol (PAP): RADIUS istemcisi, uzak kullanıcının kimlik (ID) ve parolasını RADIUS kimlik doğrulama sunucusuna iletir. Eğer kimlik bilgileri doğruysa, sunucu kullanıcıyı doğrular ve RADIUS istemcisi uzak kullanıcının ağa bağlanmasına izin verir.
    * Challenge Handshake Authentication Protocol (CHAP): "Üç yönlü el sıkışma" olarak da bilinen CHAP kimlik doğrulaması, istemci ve sunucun paylaşılan şifrelenmiş bir gizli anahtar kullanmasına dayanır. PAP'a kıyasla daha güvenli kabul edilir çünkü kimlik doğrulama değişimlerini şifreler ve oturum ortasında tekrarlanan kimlik doğrulamaları yapacak şekilde yapılandırılabilir.
* Bir RADIUS proxy istemcisi, kimlik doğrulama isteklerini başka RADIUS sunucularına iletecek şekilde yapılandırılabilir. Bu proxy’ler, büyük veya coğrafi olarak dağınık ağlarda merkezi kimlik doğrulama imkânı sağlar.
* RADIUS protokolü, birçok ağ ürünü içine entegre edilmiş, olgun bir kimlik doğrulama protokolüdür. Ayrıca yetkilendirme ve muhasebe için dizin hizmeti yazılımlarıyla da bütünleşir. Örneğin, Microsoft’un Network Policy Server (NPS) ürünü RADIUS’u uygular ve Microsoft Active Directory ile entegre çalışır.