# FTP

- FTP (**F**ile **T**ransfer **P**rotocol), bir veri yığınının - ASCII,EDCDIC ve binary- bir uç aygıttan diğerine iletimi için kullanılmaktadır.

- Bir dosyayı FTP kullanarak başka bir TCP/IP ağı üzerindeki kullanıcıya yollamak için o ağdaki bilgisyarlarda geçerli bir kullanıcı ismi ve şifresi gerekmektedir. Birçok FTP sunucusu,Kullanıcı ismi ve parola olmadan erişim için "anonim FTP" desteği verir


- Ağ açısından bakıldığı zaman **FTP** nin 2 çeşidir vardır
    - **Aktif FTP**: istemci,suncunun 21 numaralı portundan kontrol bağlantısı kurarak FTP sunucusuna bağlanır.Bu durumda istemci komut satırına düşer ve ls ve get komutlarını buradan gönderir.Tüm veri aktarım bağlantısı sunucu üzerinden 20 numaralı porttan gerçekleştirilir.İstemci ls komutunu çalıştırdığında geri dönen cevap sunucunun 20 numaralı portundan değil 21 numaralı portundan gerçekleşir. Daha sonra sunucu kaynak portunu 20 yapacak şekilde değiştirir ve dosya aktraımına devam eder.
    - **Pasif FTP**:Pasif FTP, değişik sebeplerden dolayı sistemde meydana gelen ftp promblemlerine sunucu tarafında çözüm bulmak amacıyla çıkarılmış FTP çeşididir. İstemci, 21 numaralı porttan önce kontrol bağlantısı kurararak FTP sunucusuna bağlanır. Aktif bağlantıdaki gibi istemci ne zaman veri aktarımı gerçekleitrmeye başlarsa istemciden yeni bir port açılır. İstemci,sunucuya PASV komutu gönderir. Bu komut sonucunda sunucuda da yeni bir port açılır. Böylece veri aktarımı istemcinin en son açtığı port ile sunucunun en son açtığı port arasında gerçekleşir.Bu yöntem genelde bağlantı filtreleme ve güvenlik duvarı gibi problemleri ortadan kaldırmaya yönelik geliştirilmiştir.