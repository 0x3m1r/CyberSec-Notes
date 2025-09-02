# SSH (Secure Shell)

## Secure Shell (SSH) Protokolü Nedir?

- Güvenli olmayan bir ağ üzerinden bir bilgisayara güvenli bir şekilde komut göndermenin bir yoludur.
- SSH, cihazlar arasındaki bağlantıları doğrulamak ve şifrelemek için kriptografi kullanır.
- SSH ayrıca tünelleme veya port yönlendirme özelliği sağlar; bu, veri paketlerinin normalde geçemeyecekleri ağlardan geçmelerini sağlar.
- SSH genellikle sunucuları uzaktan kontrol etmek, altyapıyı yönetmek ve dosya aktarmak için kullanılır.

## SSH Ne Yapar?

- **Uzaktan Şifreli Bağlantılar**: SSH, bir kullanıcının cihazı ile uzaktaki bir makine arasında bağlantı kurar. Bu bağlantı üzerinden geçen verileri korumak için şifreleme kullanır. Araya giren bir kişi yalnızca anlamsız, rastgele verilerle karşılaşır - veriler şifre çözülmedikçe hiçbir anlam taşımaz.

- **Tünelleme Yeteneği**: Ağ teknolojisinde tünelleme, veri paketlerini normalde kullanamayacakları bir protokol veya yol üzerinden taşımak için kullanılan bir yöntemdir. Tünelleme, veri paketlerini ek bilgiler (headers) ile sararak hedeflerini değiştirmek suretiyle çalışır. SSH tünelleri, paketleri bir makineden diğerine göndermek için port yönlendirme (port forwarding) adlı bir teknik kullanır.

## SSH Nasıl Çalışır?

### TCP/IP
- SSH, TCP/IP protokolü üzerinden çalışır.
- SSH'ın diğer tünelleme protokollerinden farkı, TCP kullanmasıdır.

### Açık Anahtarlı Kriptografi
- SSH "güvenli"dir çünkü şifreleme ve kimlik doğrulamayı açık anahtarlı kriptografi adlı bir süreçle sağlar.
- Açık anahtarlı kriptografi, verileri şifrelemek veya imzalamak için 2 farklı anahtar kullanma yöntemidir. Anahtarlardan biri olan açık anahtar herkes tarafından kullanılabilir. Diğeri olan özel anahtar ise sahibinde gizli tutulur.
- Bu iki anahtar birbirine karşılık geldiği için, anahtar sahibinin kimliğini doğrulamak, ilgili açık anahtara karşılık gelen özel anahtara sahip olmayı gerektirir.
- Bu "asimetrik" anahtarlar, bağlantının iki tarafının, kanal üzerinden daha ileri şifreleme için ortak simetrik anahtarlar üzerinde anlaşmasını da sağlar. Anlaşma tamamlandıktan sonra, iki taraf simetrik anahtarları veri alışverişini şifrelemek için kullanır.
- Bir SSH bağlantısında, her iki tarafın da bir açık/özel anahtar çifti vardır ve her taraf diğerini bu anahtarla doğrular.

### Kimlik Doğrulama
- Açık anahtarlı kriptografi, SSH'de bağlı cihazların kimliğini doğrulasa da, güvenli bir bilgisayar yine de SSH kullanan kişinin kimlik doğrulamasını ister.

### SSH Port Yönlendirme (Tünelleme)
- Port yönlendirme, iki kişi arasında mesaj iletmeye benzer. Bob bir mesajı Alice'e gönderir, Alice de bunu Dave'e iletir. Benzer şekilde port yönlendirme, bir makinedeki IP adresi ve porta yönlendirilen veri paketlerini, başka bir makinedeki IP adresi ve porta gönderir.

### SSH Kullanımı
- Linux ve Mac işletim sistemlerinde SSH yerleşik olarak gelir. Windows makinelerde ise bir SSH istemci uygulamasının kurulması gerekebilir.
- Mac ve Linux bilgisayarlarda kullanıcılar Terminal uygulamasını açarak doğrudan SSH komutları girebilir.

## SSH Özellikleri ve Güvenlik Konuları

- SSH varsayılan olarak Port 22'yi kullanır.
- SSH erişimi genellikle bir sunucuya uygulama yükleme, veri silme, değiştirme veya çıkarma gibi yükseltilmiş ayrıcalıklarla birlikte geldiği için, kötü niyetli bir saldırganın elinde zararlı olabilir.
- SSH, özel verileri sızdırmak, güvenli bir ağda arka kapı yolları açmak ve sunucularda root erişimi elde etmek amacıyla birçok belgelenmiş saldırıda kullanılmıştır.
- SSH, port 22'yi açık bırakan güvenlik duvarlarından geçebilir ve böylece saldırganların güvenli ağların içine sızmasına olanak tanır.
- Saldırganlar ayrıca özel bilgisayarlar ve sunuculara erişim sağlamak için SSH anahtarlarını çalabilir.
- SSH anahtar yönetimi büyük kuruluşlar için ciddi bir güvenlik sorunudur; çünkü bu kuruluşların birçok sunucusu binlerce hatta milyonlarca anahtar kullanabilir ve bu anahtarları manuel olarak takip edip güncellemek neredeyse imkansızdır.
- SSH anahtarlarının süresi, açıkça iptal edilmedikçe dolmaz; bu nedenle bir saldırgan bir anahtarı ele geçirdiğinde, aylarca veya yıllarca sürekli erişim sağlayabilir.

## SSH'nin Diğer Tünelleme Protokollerinden Farkları

1. SSH ile diğer tünelleme protokolleri arasında temel farklardan biri, çalıştıkları OSI katmanıdır. GRE, IP-in-IP ve IPsec tümü ağ katmanı protokolleridir. Bu nedenle portlardan habersizlerdir ve yalnızca IP adresleri arasında çalışırlar. (SSH'nin tam OSI katmanı kesin olarak tanımlanmamıştır, ancak çoğu kaynak SSH'yi HTTP, FTP ve SMTP gibi bir katman 7/uygulama katmanı protokolü olarak tanımlar.)

2. SSH'nin TCP kullanmasıdır.

3. IPsec ise paketlerin güvenlik duvarlarından geçebilmesi için yalnızca UDP kullanır. Bu nedenle IPsec tünelleri genellikle SSH tünellerinden daha hızlıdır, ancak paketler yol boyunca kaybolabilir. GRE ve IP-in-IP hem TCP hem de UDP ile kullanılabilir.