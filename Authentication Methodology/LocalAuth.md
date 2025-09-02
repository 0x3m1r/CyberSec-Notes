# LOCALAUTH

---

## **Power Pages – Kullanıcı Kimlik Doğrulama ve Kayıt Notları**

### **1. Temel Kavramlar**

* **Power Pages**, ASP.NET Identity API üzerine kurulu kimlik doğrulama sunar (OWIN çerçevesi ile).
* Kimlik doğrulama türleri:

  * **Yerel (Local)**: Kullanıcı adı ve şifre
  * **Dış (External/Sosyal)**: Üçüncü taraf kimlik sağlayıcıları
  * **İki faktörlü doğrulama (2FA)**: E-posta veya güvenlik kodu ile ek doğrulama

---

### **2. Kullanıcı Kayıt ve Kimlik Doğrulama**

* **Yeni kullanıcı:**

  * Yerel hesap oluşturabilir (kullanıcı adı + şifre)
  * Dış sağlayıcı ile giriş yapabilir
  * Davetiye kodu ile önceden hazırlanmış iletişim kaydına bağlanabilir
* **Geri gelen kullanıcı:**

  * Yerel veya dış hesap ile giriş yapabilir
  * Şifre sıfırlama ve 2FA kullanabilir

**İlgili ayarlar:**

* LocalLoginEnabled, ExternalLoginEnabled, OpenRegistrationEnabled, InvitationEnabled, RememberMeEnabled, ResetPasswordEnabled, TwoFactorEnabled

---

### **3. Şifre İşlemleri**

* **Şifre sıfırlama:** Onaylı e-posta ile reset token gönderilir
* **Şifre politikası:** Büyük/küçük harf, rakam, özel karakter ve minimum uzunluk ile kontrol edilir
* **Kullanıcı adı:** Belirlendikten sonra değiştirilemez

---

### **4. E-posta Onayı**

* Yeni veya değiştirilen e-posta **onaylanmamış** kabul edilir
* Kullanıcı doğrulama e-postası ile onay tamamlar
* Birincil e-posta (emailaddress1) doğrulama için kullanılır

---

### **5. İki Faktörlü Kimlik Doğrulama (2FA)**

* Onaylı e-posta veya güvenlik kodu ile ek doğrulama
* Tarayıcı hatırlanabilir, sonraki girişlerde kod istenmez
* Her kullanıcı hesabı için ayrı etkinleştirilir

---

### **6. Dış Hesap Yönetimi**

* Kullanıcı birden fazla dış kimliği hesabına bağlayabilir
* Bağlanan kimliklerden herhangi biri ile giriş yapılabilir
* Kimlikler tekil kalarak bağlantıdan çıkarılabilir

---

### **7. Hesap Kilitleme ve Güvenlik**

* Belirli sayıda başarısız girişte kullanıcı hesabı geçici kilitlenir
* Kilit süresi ve maksimum başarısız giriş sayısı ayarlanabilir

---

### **8. Cookie ve Oturum Yönetimi**

* ApplicationCookie ile kimlik doğrulama ve oturum süreleri belirlenir
* CookieHttpOnly, CookieSecure, ExpireTimeSpan, SlidingExpiration gibi ayarlar ile güvenlik sağlanır
* TwoFactorCookie: 2FA oturum yönetimi

---

### **9. Kayıt (Registration) Ayarları**

* Enabled: Tüm kullanıcı kayıtlarını aç/kapat
* OpenRegistrationEnabled: Her ziyaretçi kayıt olabilir
* InvitationEnabled: Davetiye kodu ile kayıt
* CaptchaEnabled: Kayıt sayfasında güvenlik doğrulaması

---

### **10. Özet Notlar**

* **Yerel hesap**: Kullanıcı adı + şifre
* **Dış hesap**: Sosyal veya üçüncü taraf sağlayıcı
* **2FA**: E-posta veya güvenlik kodu ile ek doğrulama
* **Şifre politikası**: Güçlü şifre zorunlu, parola sıfırlama mevcut
* **Davetiye kodu**: Önceden hazırlanmış iletişim kaydına bağlanmak için kullanılır
* **Profil sayfası**: Hesap yönetimi, e-posta doğrulama, dış kimlik bağlama

