# NFC (Near Field Communication)

## NFC nasıl çalışır?
NFC, kısa menzilli (yaklaşık 4 cm) radyo frekansı iletişimi teknolojisidir (13.56 MHz) ve RFID'in bir alt kümesi olarak çalışır. Üç çalışma modu vardır:
- Reader/Writer: Cihaz, pasif NFC etiketlerini okur veya yazar.  
- Card Emulation: Cihaz, temassız bir kart gibi davranarak ödeme veya erişim sistemleriyle iletişim kurar.  
- Peer-to-Peer: İki cihaz arasında küçük veri paketleri paylaşılır (ör. eşleştirme veya hızlı paylaşım).

NFC pasif etiketlerle düşük güç tüketimiyle çalışabilir; mobil ödemelerde ise kart bilgileri cihazda doğrudan saklanmaz, güvenlik katmanları kullanılır.

## Kullanım alanları
- Temassız ödemeler (Apple Pay, Google Pay, Samsung Pay)  
- Erişim kartları ve bina/araç girişleri  
- Toplu taşıma geçiş sistemleri  
- Cihaz eşleştirme (Bluetooth/Wi‑Fi için hızlı eşleştirme)  
- Ürün etiketleri, bilgisel QR kod alternatifleri, envanter takibi

## Hızlı sorun giderme
1. NFC'nin açık olduğundan emin olun.  
    - iPhone: Ayarlar veya Denetim Merkezi'nden NFC ayarlarını kontrol edin.  
    - Android: Ayarlar > Bağlı cihazlar > Bağlantı tercihleri > NFC.  
2. Cihazı yeniden başlatın.  
3. Kılıf/metal engelleri çıkarın; etiketin doğru yerde olduğundan emin olun.  
4. Yazılım güncellemelerini kontrol edin.  
5. Başka bir etiket veya cihaz ile test ederek kaynağı izole edin.  
6. Ağ/bağlantı ayarlarını sıfırlamayı düşünün.  
7. Sorun devam ederse üretici veya operatör desteğine başvurun.

## NFC güvenli mi?
Genel olarak temassız ödemeler manyetik şeritli kartlara göre daha güvenlidir:
- Tokenizasyon: Gerçek kart bilgileri yerine tek kullanımlık veya cihaz‑bağımlı token kullanılır; çalınsa bile işe yaramaz.  
- Cihaz doğrulaması: Mobil ödemeler genellikle biyometrik veya PIN ile yetkilendirilir (Touch ID, Face ID, PIN).  
Ancak dikkat edilmesi gereken noktalar:
- Olası tehditler: Eavesdropping (hafif risk, kısa menzil nedeniyle sınırlı), relay saldırıları (ek önlemler gerekebilir) ve fiziksel cihaz hırsızlığı.  
- Öneriler: Cihaz kilidini etkin tutun, tanımadığınız etiketleri okumayın, şüpheli ödeme hareketlerini bankaya bildirin.

## EMV ile NFC farkı
- EMV: Chip tabanlı ödeme standardıdır (Europay, Mastercard, Visa). Temassız ödemede çip verisi kullanılır.  
- NFC: İletişim yöntemidir; EMV bilgileri NFC üzerinden iletilebilir. Yani EMV bir ödeme standardı, NFC ise iletişim kanalıdır — birlikte çalışabilirler.

## Neden NFC kabul etmeli/tercih etmeli?
- Güvenli: Tokenizasyon ve cihaz doğrulaması sayesinde kart bilgileri korunur.  
- Hızlı ve kullanışlı: Temassız işlemler kasada bekleme süresini azaltır.  
- Geniş destek: Modern telefonlar ve POS cihazları tarafından yaygın olarak desteklenir.  
- Temassız ve hijyenik: Fiziksel temas gerektirmez.

Kısa not: NFC cihazın modeline ve işletim sistemine göre farklı davranabilir; kurulum ve sınırlamalar için üretici dokümantasyonuna bakın.
