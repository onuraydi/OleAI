# Test Dokümanları
Bu bölüm, OleAI bitirme projesi için hazırlanan final raporundaki **4. Test Planı** kısmının rapora sığmayan tablo ve dokümanların bir örneğini tutmak için kullanılan dosyadır.

---

## 4.3.2 Kullanılan Test Araçları:

| Katman | Araç / Teknoloji | Kullanım Amacı |
| :--- | :--- | :--- |
| **Backend Test** | xUnit / NUnit | .NET tabanlı servislerin birim (unit) ve entegrasyon testleri. |
| **Mocklama** | Moq | Bağımlılıkların izole edilmesi ve sahte nesneler oluşturulması. |
| **API Test** | Postman / Swagger | REST API uç noktalarının manuel ve otomatik testleri. |
| **Veritabanı** | SQL Server (Test DB) | CRUD işlemleri ve veri bütünlüğü testleri. |
| **Yapay Zekâ Test** | PyTest | TF-IDF, kosinüs benzerliği ve dinamik profil algoritmalarının test edilmesi. |
| **Web UI Test** | Selenium | React tabanlı web arayüzünün uçtan uca (E2E) testleri. |
| **Mobil Test** | Manuel Testler | Jetpack Compose tabanlı mobil arayüzün fonksiyonel testleri. |
| **Containerization** | Docker / Docker Compose | Test ortamının standart ve taşınabilir hâle getirilmesi. |
| **CI/CD** | GitHub Actions | Testlerin otomatik çalıştırılması ve raporlanması. |
| **Kod Kalitesi** | SonarQube | Test kapsamı, kod kalitesi ve teknik borç analizi. |

---
### 4.4.1 Kullanıcı Kayıt ve Giriş Test Senaryoları

**Use Case:** Kullanıcı sisteme kaydolur ve giriş yapar.

| Senaryo Türü | Senaryo Detayları |
| :--- | :--- |
| **Pozitif Senaryolar** | • Kullanıcı geçerli e-posta ve şifre bilgileri ile kaydolur, e-posta adresini doğrular.<br>• Kayıtlı kullanıcı doğru kimlik bilgileriyle sisteme başarılı şekilde giriş yapar.<br>• JWT token başarıyla oluşturulur ve istemciye iletilir. |
| **Negatif Senaryolar** | • Kullanıcı, sistemde kayıtlı olmayan bir e-posta ile giriş yapmaya çalışır.<br>• Kullanıcı yanlış şifre girer.<br>• Zorunlu alanlar (e-posta, şifre) boş bırakılır.<br>• Süresi dolmuş veya geçersiz JWT token ile korumalı endpoint’e erişilmeye çalışılır. |

### 4.4.2 Tarif Ekleme ve Yönetimi Test Senaryoları

**Use Case:** Kullanıcı sisteme tarif ekler ve tariflerini yönetir.

| Senaryo Türü | Senaryo Detayları |
| :--- | :--- |
| **Pozitif Senaryolar** | • Kullanıcı yeni bir tarifi başarıyla ekler.<br>• Tarif public veya private olarak işaretlenebilir.<br>• Kullanıcı kendi tariflerini listeleyebilir ve düzenleyebilir. |
| **Negatif Senaryolar** | • Zorunlu alanları (tarif adı, malzeme listesi) eksik olan tarif eklenmeye çalışılır.<br>• Yetkisiz bir kullanıcı, başka bir kullanıcıya ait private tarifi düzenlemeye çalışır.<br>• Geçersiz veri formatı ile tarif ekleme isteği gönderilir. |

### 4.4.3 Yapay Zekâ Destekli Tarif Öneri Test Senaryoları

**Use Case:** Kullanıcıya kişisel tercihlerine ve mevcut malzemelere göre tarif önerilir.

| Senaryo Türü | Senaryo Detayları |
| :--- | :--- |
| **Pozitif Senaryolar** | • Kullanıcının diyet ve beslenme tercihleri dikkate alınarak öneri sunulur.<br>• Kullanıcının “Dolabım” modülündeki malzemelere uygun tarifler önerilir.<br>• Öneri süresi belirlenen performans sınırları içinde tamamlanır. |
| **Negatif Senaryolar** | • Kullanıcının dolabında hiç malzeme bulunmaması.<br>• Kullanıcı profil verilerinin eksik olması (soğuk başlangıç durumu).<br>• Yapay zekâ servisinden geçersiz veya boş yanıt alınması. |

### 4.4.4 “Dolabım” Modülü ve Malzeme Yönetimi Test Senaryoları

**Use Case:** Kullanıcı malzemelerini yönetir ve stok takibi yapar.

| Senaryo Türü | Senaryo Detayları |
| :--- | :--- |
| **Pozitif Senaryolar** | • Kullanıcı dolabına yeni malzeme ekler.<br>• Bir tarif yapıldığında, ilgili malzemelerin miktarı otomatik olarak düşer.<br>• Tükenen malzemeler alışveriş listesine otomatik olarak eklenir. |
| **Negatif Senaryolar** | • Negatif miktarda malzeme eklenmeye çalışılır.<br>• Mevcut olmayan bir malzeme güncellenmeye çalışılır.<br>• Yetkisiz erişim ile başka kullanıcıya ait dolap verilerine ulaşılmaya çalışılır. |

### 4.4.5 Sosyal Etkileşim Test Senaryoları

**Use Case:** Kullanıcılar tarifler üzerinde etkileşim kurar.

| Senaryo Türü | Senaryo Detayları |
| :--- | :--- |
| **Pozitif Senaryolar** | • Kullanıcı bir tarife yorum yapar.<br>• Kullanıcı bir tarifi beğenir, beğenmez veya favorilere ekler.<br>• Yorumlar ilgili tarif altında doğru şekilde listelenir. |
| **Negatif Senaryolar** | • Boş veya çok uzun yorum gönderilmeye çalışılır.<br>• Yetkisiz kullanıcı yorum yapmaya çalışır.<br>• Silinmiş bir tarife etkileşim yapılmaya çalışılır. |

### 4.4.6 Performans ve Güvenlik Test Senaryoları

**Use Case:** Sistem performans ve güvenlik gereksinimlerini karşılar.

| Senaryo Türü | Senaryo Detayları |
| :--- | :--- |
| **Pozitif Senaryolar** | • Aynı anda çok sayıda kullanıcının öneri alabilmesi.<br>• Şifrelerin güvenli şekilde hash’lenerek saklanması.<br>• Yetkilendirme kontrollerinin doğru çalışması. |
| **Negatif Senaryolar** | • Yetkisiz erişim denemeleri.<br>• Aşırı istek (rate limit) durumları.<br>• Hatalı veya manipüle edilmiş istek payload’ları. |

### 4.4.7 Yapay Zekâ Modeli Doğrulama Test Senaryoları

**Use Case:** Yapay zekâ modelinin doğruluğu ve tutarlılığı.

| Senaryo Türü | Senaryo Detayları |
| :--- | :--- |
| **Doğrulama** | • Kullanıcının beğeni geçmişine göre önerilerin zamanla kişiselleşmesi.<br>• Beğenilmeyen tarif türlerinin önerilerden uzaklaştırılması.<br>• Yeni kullanıcılar (cold-start) için genel ve dengeli önerilerin sunulması.<br>• Kullanıcı malzeme listesi değiştiğinde öneri sonuçlarının güncellenmesi. |

### 4.4.8 Sınır Durumları (Edge Case) Test Senaryoları

**Use Case:** Sistemin uç koşullardaki davranışı.

| Senaryo Türü | Senaryo Detayları |
| :--- | :--- |
| **Sınır Durumları** | • Kullanıcının dolabında yalnızca tek bir malzeme bulunması.<br>• Çok büyük veri setleri ile tarif önerisi alınması.<br>• Aynı tarife kısa sürede tekrar tekrar etkileşim yapılması.<br>• Uzun süre kullanılmayan kullanıcı profilleri. |

### 4.4.9 Yetkilendirme ve Rol Bazlı Test Senaryoları

**Use Case:** Rol ve yetki kontrolleri.

| Senaryo Türü | Senaryo Detayları |
| :--- | :--- |
| **Yetkilendirme** | • Kullanıcının yalnızca kendi private tariflerini düzenleyebilmesi.<br>• Public tariflerin tüm kullanıcılar tarafından görüntülenebilmesi.<br>• Token süresi dolduğunda erişimin engellenmesi.<br>• Yetkisiz kullanıcıların korumalı servis uç noktalarına erişememesi. |
---

## 4.5.1 Kullanıcı Kayıt ve Giriş Test Case’leri

| ID | Test Adı | Girdi (Input) | Beklenen Çıktı | Gerçekleşen Çıktı | Durum |
| :--- | :--- | :--- | :--- | :---: | :---: |
| **TC-01** | Geçerli kullanıcı kaydı | Geçerli e-posta, şifre | Kayıt başarılı | — | — |
| **TC-02** | Eksik alanla kayıt | Boş e-posta | Hata mesajı dönmeli | — | — |
| **TC-03** | Geçerli giriş | Doğru e-posta/şifre | JWT token üretilir | — | — |
| **TC-04** | Yanlış şifre | Yanlış şifre | Giriş reddedilir (401/403) | — | — |
| **TC-05** | Kayıtsız kullanıcı | Kayıtsız e-posta | Giriş reddedilir (User not found) | — | — |
| **TC-06** | Süresi dolmuş token | Expired JWT | 401 Unauthorized hatası | — | — |

---

### 4.5.2 Tarif Ekleme ve Tarif Yönetimi Use Case’leri

| ID | Test Adı | Girdi (Input) | Beklenen Çıktı | Gerçekleşen Çıktı | Durum |
| :--- | :--- | :--- | :--- | :---: | :---: |
| **TC-07** | Tarif ekleme | Geçerli tarif verisi (Ad, malzeme, vb.) | Tarif başarıyla eklenir | — | — |
| **TC-08** | Eksik tarif alanı | Tarif adı veya malzeme listesi boş | İşlem reddedilir, hata mesajı döner | — | — |
| **TC-09** | Tarif güncelleme | Geçerli güncelleme verisi | Tarif başarıyla güncellenir | — | — |
| **TC-10** | Private tarif erişimi | Yetkisiz kullanıcı (sahibi olmayan) | Erişim engellenir (403 Forbidden) | — | — |
| **TC-11** | Tarif silme | Sahibi olan kullanıcı isteği | Tarif sistemden silinir | — | — |

---

### 4.5.3 Yapay Zekâ Destekli Tarif Önerisi Test Case’leri

| ID | Test Adı | Girdi (Input) | Beklenen Çıktı | Gerçekleşen Çıktı | Durum |
| :--- | :--- | :--- | :--- | :---: | :---: |
| **TC-12** | Malzemeye göre öneri | Dolap verisi (Mevcut malzemeler) | Malzemelere uygun tarif listesi | — | — |
| **TC-13** | Diyet tercihine göre öneri | Kullanıcı tercihi (Örn: Vejetaryen) | Tercihe uyumlu (et içermeyen) tarifler | — | — |
| **TC-14** | Cold-start kullanıcı | Profil veya geçmiş veri yok | Popüler/Genel tarif önerileri | — | — |
| **TC-15** | Boş malzeme listesi | Malzeme girişi yok | Kullanıcıyı yönlendiren mesaj | — | — |
| **TC-16** | AI servisi boş cevap | AI servisinden Null/Timeout yanıtı | Sistem çökmemeli, kontrollü hata mesajı | — | — |

---

### 4.5.4 “Dolabım” Modülü Test Case’leri

| ID | Test Adı | Girdi (Input) | Beklenen Çıktı | Gerçekleşen Çıktı | Durum |
| :--- | :--- | :--- | :--- | :---: | :---: |
| **TC-17** | Malzeme ekleme | Geçerli malzeme verisi | Malzeme dolaba eklenir | — | — |
| **TC-18** | Negatif miktar | Miktar: -5 | İşlem reddedilir, hata mesajı döner | — | — |
| **TC-19** | Tarif sonrası stok düşümü | Tarif "Yapıldı" olarak işaretlenir | Kullanılan malzemeler stoktan düşülür | — | — |
| **TC-20** | Tükenen malzeme | Malzeme miktarı 0'a düşer | Malzeme otomatik olarak alışveriş listesine eklenir | — | — |
| **TC-21** | Yetkisiz dolap erişimi | Başka kullanıcı ID'si ile istek | Erişim engellenir (403 Forbidden) | — | — |

---

### 4.5.5 Sosyal Etkileşim Test Case’leri

| ID | Test Adı | Girdi (Input) | Beklenen Çıktı | Gerçekleşen Çıktı | Durum |
| :--- | :--- | :--- | :--- | :---: | :---: |
| **TC-22** | Yorum ekleme | Geçerli yorum metni | Yorum başarıyla eklenir ve listelenir | — | — |
| **TC-23** | Boş yorum | "" (Boş karakter dizisi) | İşlem reddedilir, uyarı verilir | — | — |
| **TC-24** | Tarif beğenme | Like isteği gönderimi | Beğeni sayısı artar (Counter +1) | — | — |
| **TC-25** | Silinmiş tarife yorum | Silinmiş tarif ID'sine yorum isteği | Hata mesajı döner (404 Not Found) | — | — |

---

### 4.5.6 Performans ve Güvenlik Test Case’leri

| ID | Test Adı | Girdi (Input) | Beklenen Çıktı | Gerçekleşen Çıktı | Durum |
| :--- | :--- | :--- | :--- | :---: | :---: |
| **TC-26** | Eşzamanlı kullanıcı yükü | 100 eşzamanlı istek (Concurrent Request) | Sistem yanıt verir, çökme veya timeout olmaz | — | — |
| **TC-27** | Yük altında AI öneri | Aynı anda çoklu öneri isteği | Yanıt süresi kabul edilebilir seviyede kalır (Örn: <3sn) | — | — |
| **TC-28** | Şifre güvenliği | Veritabanı kontrolü (Plain password girişi) | Şifre hash’lenerek (Argon2/BCrypt) saklanır | — | — |
| **TC-29** | Yetkisiz endpoint erişimi | Token olmadan korumalı kaynağa istek | 401 Unauthorized hatası döner | — | — |
| **TC-30** | Rate limit ihlali | Belirlenen sürede çok sık istek | İstekler sınırlandırılır (429 Too Many Requests) | — | — |
| **TC-31** | Manipüle edilmiş payload | Bozuk veya zararlı JSON verisi | İstek reddedilir (400 Bad Request) | — | — |

---

### 4.5.7 Yapay Zekâ Modeli Doğrulama Test Case’leri

| ID | Test Adı | Girdi (Input) | Beklenen Çıktı | Gerçekleşen Çıktı | Durum |
| :--- | :--- | :--- | :--- | :---: | :---: |
| **TC-32** | Kullanıcı öğrenme etkisi | Tekrarlı beğeni geçmişi | Öneriler kişiselleşir ve kullanıcının zevkine yaklaşır | — | — |
| **TC-33** | Negatif geri bildirim etkisi | Beğenilmeyen tarifler | Benzer tariflerin önerilme sıklığı azalır | — | — |
| **TC-34** | Cold-start önerisi | Yeni kullanıcı (Geçmiş veri yok) | Dengeli, popüler ve genel öneriler sunulur | — | — |
| **TC-35** | Malzeme değişim etkisi | Güncellenmiş dolap envanteri | Öneriler yeni malzemelere göre anında güncellenir | — | — |
| **TC-36** | Profil tercihi etkisi | Diyet tercihi (Örn: Glütensiz) | Sadece tercihe uyumlu tarifler listelenir | — | — |
| **TC-37** | Zaman etkisi (time decay) | Eski etkileşimler vs. Yeni etkileşimler | Güncel tercihler daha yüksek ağırlıkla değerlendirilir | — | — |

---

### 4.5.8 Edge Case (Sınır Durumu) Test Case’leri

| ID | Test Adı | Girdi (Input) | Beklenen Çıktı | Gerçekleşen Çıktı | Durum |
| :--- | :--- | :--- | :--- | :---: | :---: |
| **TC-38** | Tek malzemeli dolap | Dolapta sadece 1 malzeme var | Sistem uyarı verir veya tek malzemeli basit öneri sunar (Hata vermez) | — | — |
| **TC-39** | Çok büyük veri | 100+ malzeme girişi | Sistem performansı korunur, yanıt süresi uzamaz | — | — |
| **TC-40** | Tekrarlı beğeni | Aynı tarife art arda beğeni isteği | Tutarlılık korunur (Spam koruması devreye girer veya işlem tek sayılır) | — | — |

---

### 4.5.9 Güvenlik ve Yetkilendirme Test Case’leri

| ID | Test Adı | Girdi (Input) | Beklenen Çıktı | Gerçekleşen Çıktı | Durum |
| :--- | :--- | :--- | :--- | :---: | :---: |
| **TC-41** | Token olmadan erişim | Header'da Bearer Token yok | 401 Unauthorized hatası döner | — | — |
| **TC-42** | Rol ihlali | Yetkisiz kullanıcı (Örn: User -> Admin paneli) | Erişim reddedilir (403 Forbidden) | — | — |
| **TC-43** | Token süresi dolması | Süresi geçmiş (Expired) JWT | Erişim engellenir, yeniden giriş istenir (401) | — | — |



















