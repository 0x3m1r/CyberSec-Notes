# Siber Güvenlikte Bluetooth : 

## Bluetooth Saldırılarını Anlamak:
* Bluetooth cihazları, birbirine bağlanmak için optik bir görüş hattını korumak zorunda değildir çünkü bu teknoloji, bağlantıyı radyo dalgalarıyla gerçekleştirir.
* Bluetooth, her yerde erişilebilen lisanssız, düşük güçlü GHz spektrumunu kullanır.
* Başlıca Özellikleri : 
    * Düşük Güç tüketimi
    * Kolay pil kullanımı
    * Makul maliyet
* Bluetooth Low Energy (LE), doğrudan bağlantıdan yayın yapmaya ve en son olarak mesh yapısına kadar çeşitli iletişim topolojilerini destekleyerek güvenilir, büyük ölçekli cihaz ağlarının geliştirilmesini mümkün kılar.
* Yaygın Bluetooth Saldırıları : 
    * bluejacking
        * Açıklama: Yakındaki cihazlara, kullanıcı onayı olmadan kısa mesaj (vCard/servis daveti) göndermek; genelde spam/nuisance amaçlıdır.
        * Etki: Rahatsızlık, kullanıcı dikkatini dağıtma; veri sızdırma sağlamaz.
        * Korunma: Cihazı görünmez (non-discoverable) yap, bilinmeyen bağlantı isteklerini reddet.
    * Bluesnarfing
        * Açıklama: Zayıf veya yanlış yapılandırılmış servis protokollerini (ör. OBEX) kullanarak rehber, SMS, takvim gibi verilere yetkisiz erişim.
        * Etki: Hassas veri sızıntısı (kişiler, mesajlar, dosyalar).
        * Korunma: Yazılım/firmware güncellemeleri, servisleri kapat, güçlü kimlik doğrulama ve şifrelemeyi zorunlu kıl.
    * eavesdropping (dinleme)
        * Açıklama: Bluetooth trafiğini pasif olarak dinleyip alınan veriyi çözmeye çalışma—özellikle şifreleme yoksa veya zayıf anahtar kullanılıyorsa etkili.
        * Etki: Gizli verilerin (ses, dosya, metadata) açığa çıkması
        * Korunma: Zorunlu şifreleme, güçlü anahtarlar, güncel protokol implementasyonları.
    * DoS
        * Açıklama: Özel paketler, yoğun trafik veya protokol sınırlarının kötüye kullanımıyla hizmetin devre dışı bırakılması veya cihazın çökertilmesi.
        * Etki: Cihazın bağlantı sağlayamaması, pil tüketiminde artış veya çökme.
        * Korunma: Güncellemeler, rate limiting, gereksiz servisleri kapatma.

    * Virüsler ve solucanlar
        * Açıklama: Dosya paylaşımı veya servis açıkları yoluyla cihazlara yayılan malware; otomatik bulaşabilen telefon solucanları örneği vardı.
        * Etki: Veri hırsızlığı, cihaz kontrolü, kendi kendine yayılma.
        * Korunma: Gelen dosyaları doğrula/yalnızca güvenilir kaynaklardan kabul et, güncel antivirüs ve OS yamalarını uygula.
    * BrakTooth Saldırı Ailesi
        * Açıklama: Çeşitli Bluetooth yığınlarındaki (stacks) protokol uygulama hatalarını hedefleyen zafiyetler topluluğu; hedef hem BR/EDR hem BLE olabilir.
        * Etki: DoS, kimlik taklidi, yetkisiz erişim veya potansiyel uzak kod yürütme (vendor/implementasyona bağlı).
        * Korunma: Üretici yamalarını uygula, gereksiz profilleri kapat, güncel Bluetooth yığını kullan.
        * BlueSmacking
            * Açıklama: L2CAP/benzeri protokollere gönderilen özel paketlerle hizmeti engelleme (DoS).
            * Korunma: Yama, paket boyutu/istek sınırları.
        * BlueBugging
            * Açıklama: Eski cihazlarda uzaktan komut çalıştırma/telefon kontrolü sağlayan zafiyet seti (ör. SMS gönderme, rehberi okuma).
            * Korunma: Eski protokolleri/kötü yapılandırılmış servisleri devre dışı bırak, güncelle.
        * Bluetooth Low Energy Spoofing Attacks (BLESA)
            * Açıklama: Yeniden bağlanma (reconnection) sırasında kimlik doğrulama hatalarını kullanarak saldırganın eşlenik cihaz gibi davranması.
            * Korunma: Yeniden bağlanmada güçlü doğrulama, vendor yamaları.
        * Bluetooth Impersonation Attacks (BIAS)
            * Açıklama: Eşleştirilmiş bir cihazın kimliğini taklit edip güvenli bağlantı kurulmuş gibi davranma zaafiyeti.
            * Korunma: Güçlü eşleştirme yöntemleri (numeric comparison/LE secure) ve yamalar.
        * KNOB
            * Açıklama: Anahtar pazarlığı sırasında şifreleme anahtarının zayıflatılmasına yol açan zaafiyet; böylece dinleme kolaylaşır.
            * Korunma: Minimum anahtar uzunluğu zorunluluğu, güncelleme.
        * BLURtooth
            * Açıklama: BR/EDR ile LE arasındaki anahtar paylaşımı/etkileşimlerdeki zafiyetleri kullanarak taklit/ortadaki-adam (MITM) veya bağlantı ele geçirme.
            * Korunma: Vendor yamaları, farklı taşıyıcılar arasındaki anahtar yönetimini güçlendirme.

### Gotchalar / dikkat edilmesi gerekenler:

* Pek çok saldırı, zayıf/legacy eşleştirme veya eski Bluetooth yığını implementasyonlarını hedef alır — güncelleme en etkili savunmadır.
* Kullanılmadığı zaman Bluetooth’u kapatmak ve cihazı görünmez yapmak, basit ama etkili ilk adımdır.Güvenlik/uyumluluk arttıkça bazı kullanışlılık (otomatik yeniden bağlanma, kolay eşleştirme) kısıtlanabilir; değerlendirme yaparken risk/konfor dengesini göz önünde bulundur.

## Basitçe Bluetooth nedir ?
- Kabloların kullanımı ortadana kaldıran Bluetooth, kısa mesafelerde cihazlar arsında radyo frekansı kullanrak iletiim sağalayan kablosuz bir teknolojidir.Bluetooth genelikle mobil cihazları kulaklık, araökar veya akıllı buzdolapları gibi sabit ya da durağan cihazlara bağlamak için kullanılır.
* Bu teknoloji, çevre birimlerinde karışık kablolar gerektiren işleri kolaylaştırmıştır. Bluetooth dalgalarının kısa menzilli olması ve sürekli frekans değiştirmesi sayesinde, hacker’ların sinyali dinlemesi zordur.
    * Hacker’ların sinyali ele geçirmesini önlemek için Bluetooth, sürekli frekans değiştiren “frequency hopping spread spectrum” yöntemini kullanır.
* Bluetooth cihazları 2.4 gigahertz dalga boyuna sahip ultra yüksek frekanslı radyo dalgaları kullanır.

## Bluetooth Nasıl Çalışır ?
Bluetooth, düşük güçlü ve kısa mesafeli bir radyo iletim sistemi olarak 2,40 GHz ile 2,48 GHz arasındaki radyo frekans bandında iyonize olmayan elektromanyetik dalgaları kullanır. Verileri Bluetooth ile aktarılabilir bir formata dönüştürmek için, Bluetooth sinyali önce bir codec adı verilen sıkıştırma mekanizmasını kullanan yazılım tarafından işlenir. Komşu cihazları birbirine “eşleştirmek” (pair) veya bağlamak için Bluetooth, kısa menzilli radyo dalgalarını kullanır. Bluetooth özellikli cihazlardaki bir bilgisayar çipi sinyal gönderir ve böylece cihazlar birbirini tanıyabilir.
* Bluetooth menziline gelince, maksimum iletişim mesafesi ortam ve cihaz sınıfına göre değişir.
    * Sınıf 1 cihazlar: Maksimum 100 metre
    * Sınıf 2 cihazlar: Maksimum 10 metre
    * Sınıf 3 cihazlar: Maksimum 1 metre
* çoğu cihaz için Bluetooth bağlantısının menzili yaklaşık 10 metredir.

* Bluetooth teknolojisinin güvenliğini artıran çeşitli entegre öğeler şunlardır:
    * Adaptive Frequency Hopping (Uyarlanabilir Frekans Atlama): Bluetooth’un frekans atlaması 79 kanallı 2.4 GHz ISM bandını kullanır ve saniyede 1600 atlama yapabilir. Mevcut frekanslar atlanır. Bu özellik, parazit ve müdahaleyi azaltır.
    * Eşleştirme (Pairing): Eşleştirme, cihazlar arasında iletişime izin verir. Eşleştirme talebi yapılabilmesi için cihazın BD_ADDR adresi bilinmelidir. BD_ADDR, önceki iki bölümde açıklanan şekilde, tarama veya önceki eşleştirme bilgisi ile belirlenir.
    * Görünmezlik (Undetectibility): Cihazlar, tarama denemelerine yanıt verebilmek için tespit edilemez olmalıdır. Cihazın 48 bitlik BD_ADDR adresi de gizlenir.
    * E0 Cipher Suite: Şifreleme genellikle akış şifreleme (stream cipher) kullanır ve anahtar uzunluğu 128 bittir.

## WiFi ile Bluetooth Arasındaki farkları nelerdir ?
* Wi-Fi, cihazları internete bağlamak için bir Wi-Fi yönlendirici (router) kullanan kablosuz bir teknolojidir.Bilgisayarlar, tabletler, cep telefonları ve dizüstü bilgisayarlar gibi cihazlara internet erişimi sağlamak için bir internet servis sağlayıcı, Wi-Fi sinyalini yönlendiriciye iletir. Bu cihazlar arasında veri akışı olduğunda bir WLAN (Kablosuz Yerel Alan Ağı) oluşur. Ağın kapsama alanı genellikle 50–90 metre arasındadır.
* Bluetooth ve Wi-Fi, her ikisi de iletişim için radyo dalgalarını kullanır, ancak farklı amaçlara hizmet eder ve farklı özelliklere sahiptir. Wi-Fi cihazları internete bağlamak için kullanılırken, Bluetooth esas olarak kısa mesafeli veri aktarımı için kullanılır;
* Bluetooth, FHSS (Frequency Hopping Spread Spectrum) teknolojisi sayesinde sinyallerin yakın çevredeki diğer sinyallerle etkileşime girmesini engeller.
* Wi-Fi ağlarının menzili genellikle Bluetooth bağlantılarından daha geniş olmasına rağmen, Bluetooth kablo ihtiyacını ortadan kaldırır ve elektronik cihazlar arasında iletim için erişilebilir bir görüş hattı sağlar. Wi-Fi, veri aktarımında sinyalin bant genişliğini artırmak için sinyali parçalara böler ve bu parçaları farklı radyo frekansları üzerinden gönderir. Wi-Fi, 2,4 GHz ve 5 GHz frekansları arasında çalışır.

## Bluetooth WiFi Kullanıyor mu ?
Hayır. Bluetooth veri iletimi için Wi-Fi kullanmaz. Radyo sinyalleriyle çalıştığı için internet bağlantısı veya Wi-Fi’ye gerek yoktur. Ancak çoğu Bluetooth cihazı aynı zamanda internete bağlanabilir.

## Bluetooth Saldırılarını Önlemenin Yolları

* İlk eşleştirmeyi güvenli bbir ortamda yapmak
* Kullanılmadığında Bluetooth'u kapatmak
* Yetkisiz cihazlardan gelen bağlantı taleplerini reddetmek
* Eşleştirme ve bonding prosedürlerini doğru yönetmek
* Cihazlarda güncel güvenlik yamalarını uygulamak