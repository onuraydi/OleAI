# Gereksinim Analizi Dokümanları
Bu bölüm, OleAI bitirme projesi için hazırlanan final raporundaki **2. Gereksinim Analizi** kısmının rapora sığmayan tablo ve dokümanların bir örneğini tutmak için kullanılan dosyadır.

---

## 2.5 Kullanıcı Hikayeleri

### 2.5.1 Temel Kullanıcı Hikayeleri

| ID | Hikaye Adı | Rol | Öncelik | Bağımlılık | Amaç & İş Değeri | Kabul Kriterleri |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **US-01** | Kullanıcı Kayıt ve Kimlik Doğrulama | Son Kullanıcı | High | Yok | **Amaç:** Sisteme güvenli erişim<br>**Değer:** Kişiselleştirilmiş ve güvenli deneyim | • Kayıt ve giriş yapılabilmeli<br>• Güvenli kimlik doğrulama<br>• Yetkisiz erişim engeli |
| **US-02** | Mutfak Envanteri (Dolabım) Yönetimi | Son Kullanıcı | High | US-01 | **Amaç:** Malzemeleri tanımlamak<br>**Değer:** Önerileri kişiselleştirmek | • Malzeme ekleme/silme/güncelleme<br>• Malzemelerin öneride kullanımı |
| **US-03** | Yapay Zekâ Destekli Yemek Önerisi | Son Kullanıcı | High | US-02 | **Amaç:** Uygun tarif önerileri almak<br>**Değer:** Karar süresini azaltmak, israfı önlemek | • Mevcut malzemeleri dikkate alma<br>• Eksik malzemeleri belirtme<br>• Tercihlere uygunluk |

---

### 2.5.2 AI ve Kişiselleştirme Odaklı Senaryolar

| ID | Hikaye Adı | Rol | Öncelik | Bağımlılık | Amaç & İş Değeri | Kabul Kriterleri |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **US-04** | Beslenme Tercihlerinin Tanımlanması | Son Kullanıcı | High | US-01 | **Amaç:** Tercihleri sisteme tanımlamak<br>**Değer:** Uygunsuz içeriklerin elenmesi | • Tercihleri güncelleyebilme<br>• Önerilerin tercihlere uyması |
| **US-05** | Kullanıcı Davranışına Göre Öneri Kalitesi | Son Kullanıcı | Medium | US-03 | **Amaç:** Etkileşime göre isabetli öneri<br>**Değer:** Uzun vadede kişiselleştirme | • Beğeni/etkileşim analizi<br>• Sonuçların zamanla iyileşmesi |
| **US-06** | Yetersiz Veride Alternatif Öneri | Son Kullanıcı | Medium | US-02, US-03 | **Amaç:** Eksik veride bile öneri almak<br>**Değer:** Kullanıcıyı sistemde tutmak | • Veri yetersizliği tespiti<br>• Alternatif/en yakın tarif sunumu |

---

### 2.5.3 Sosyal ve İçerik Odaklı Senaryolar

| ID | Hikaye Adı | Rol | Öncelik | Bağımlılık | Amaç & İş Değeri | Kabul Kriterleri |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **US-07** | Tarif Görüntüleme ve Filtreleme | Son Kullanıcı | Medium | US-01 | **Amaç:** Hızlı ve düzenli erişim<br>**Değer:** Kullanıcı deneyimi iyileştirme | • Tarif filtreleme<br>• Detayların açık sunumu |
| **US-08** | Tarif Ekleme ve Paylaşma | İçerik Üreten | Medium | US-01 | **Amaç:** İçeriği sisteme kazandırmak<br>**Değer:** İçeriğin zenginleştirilmesi | • Tarif ekleyebilme<br>• Herkese açık/özel paylaşım |

---

### 2.5.4 İstisnai ve Hata Senaryoları

| ID | Hikaye Adı | Rol | Öncelik | Bağımlılık | Amaç & İş Değeri | Kabul Kriterleri |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **US-09** | Uygun Tarif Bulunamaması Durumu | Son Kullanıcı | Low | US-03 | **Amaç:** Öneri yoksa bilgilendirilmek<br>**Değer:** Kullanıcı memnuniyeti | • Açık bilgilendirme<br>• Alternatif aksiyonlar |

---

### 2.5.5 Yönetim ve Denetim Senaryoları

| ID | Hikaye Adı | Rol | Öncelik | Bağımlılık | Amaç & İş Değeri | Kabul Kriterleri |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **US-10** | Kullanıcı ve İçerik Yönetimi | Admin | Medium | US-01 | **Amaç:** Sistem düzeni ve güvenliği<br>**Değer:** Platform sürdürülebilirliği | • Kullanıcı/içerik yönetimi<br>• Gerektiğinde müdahale |

---

## 2.6 Gereksinim Analizi 

### 2.6.1 Fonksiyonel Gereksinimler


| ID | Başlık | Açıklama | İlişkili Hikaye |
| :--- | :--- | :--- | :--- |
| **FR-01** | Kullanıcı Kayıt ve Kimlik Doğrulama | Sistem, kullanıcıların güvenli bir şekilde kaydolmasına ve kimlik doğrulama işlemlerini gerçekleştirmesine olanak sağlamalıdır. | US-01 |
| **FR-02** | Kullanıcı Profil Yönetimi | Sistem, kullanıcıların profil bilgilerini görüntüleyebilmesine ve güncelleyebilmesine imkân tanımalıdır. | US-01, US-04 |
| **FR-03** | Mutfak Envanteri (Dolabım) Yönetimi | Sistem, kullanıcıların sahip oldukları gıda malzemelerini ekleyebilmesine, güncelleyebilmesine ve silebilmesine olanak sağlamalıdır. | US-02 |
| **FR-04** | Yapay Zekâ Destekli Yemek Önerisi | Sistem, kullanıcının tanımladığı malzemeleri ve tercihlerini dikkate alarak yemek önerileri üretmelidir. | US-03 |
| **FR-05** | Eksik Malzeme Bilgilendirmesi | Sistem, önerilen tariflerde eksik olan malzemeleri kullanıcıya açık ve anlaşılır bir şekilde göstermelidir. | US-03 |
| **FR-06** | Beslenme Tercihi ve Kısıt Filtreleme | Sistem, kullanıcı tarafından tanımlanan beslenme tercihlerini ve kısıtlarını öneri sürecine dâhil etmelidir. | US-04 |
| **FR-07** | Kullanıcı Etkileşimlerinin Analizi | Sistem, kullanıcıların tarifler üzerindeki etkileşimlerini (görüntüleme, beğeni vb.) analiz edebilmelidir. | US-05 |
| **FR-08** | Alternatif Öneri Üretimi | Sistem, yeterli veri bulunmadığında (yetersiz veri durumu) alternatif veya en yakın tarif önerilerini sunabilmelidir. | US-06 |
| **FR-09** | Tarif Görüntüleme ve Filtreleme | Sistem, tariflerin kullanıcı tarafından belirlenen kriterlere göre görüntülenmesine ve filtrelenmesine olanak sağlamalıdır. | US-07 |
| **FR-10** | Tarif Ekleme ve Paylaşma | Sistem, kullanıcıların kendi tariflerini ekleyebilmesine ve bu tarifleri herkese açık veya özel olarak paylaşabilmesine imkân tanımalıdır. | US-08 |
| **FR-11** | Uygun Tarif Bulunamaması Durumu | Sistem, uygun tarif üretilemediği durumlarda kullanıcıyı bilgilendirmeli ve alternatif aksiyonlar sunmalıdır. | US-09 |
| **FR-12** | Yönetici (Admin) İşlevleri | Sistem, yetkili yöneticilerin kullanıcıları ve içerikleri yönetebilmesine olanak sağlamalıdır. | US-10 |

---

### 2.6.2 Fonksiyonel Olmayan Gereksinimler


| ID | Kategori | Gereksinim Detayları ve Kriterler |
| :--- | :--- | :--- |
| **NFR-01** | Performans | • Sistem, kullanıcı taleplerine makul süreler içerisinde yanıt vermelidir.<br>• Yapay zekâ öneri işlemleri, kullanıcı deneyimini olumsuz etkilemeyecek şekilde optimize edilmelidir. |
| **NFR-02** | Güvenlik | • Kullanıcı verileri güvenli şekilde saklanmalıdır (Encryption).<br>• Kimlik doğrulama ve yetkilendirme mekanizmaları (OAuth, JWT vb.) uygulanmalıdır.<br>• Yetkisiz erişimler engellenmelidir. |
| **NFR-03** | Ölçeklenebilirlik | • Sistem, artan kullanıcı ve veri hacmine (High Load) uyum sağlayabilecek şekilde tasarlanmalıdır.<br>• Mimari yapı, yeni özelliklerin eklenmesine (Extensibility) olanak tanımalıdır. |
| **NFR-04** | Kullanılabilirlik | • Kullanıcı arayüzü sade, anlaşılır ve kullanıcı dostu (User-friendly) olmalıdır.<br>• Teknik bilgisi sınırlı kullanıcılar için dahi öğrenme eğrisi düşük olmalıdır. |
| **NFR-05** | Bakım Yapılabilirlik | • Sistem modüler bir mimariye (Microservices veya Modular Monolith) sahip olmalıdır.<br>• Kod yapısı okunabilir, standartlara uygun ve sürdürülebilir olmalıdır. |
| **NFR-06** | Güvenilirlik | • Sistem beklenmeyen durumlarda kararlı davranış sergilemelidir (Fault Tolerance).<br>• Hata durumlarında kullanıcı nazikçe bilgilendirilmelidir. |
| **NFR-07** | Taşınabilirlik | • Sistem, mobil (iOS/Android) ve web platformlarında tutarlı (Responsive/Cross-platform) bir deneyim sunmalıdır. |

---

### 2.6.3 Gereksinim İzlenebilirlik Matrisi

| ID | Gereksinim Tanımı | Tür | İlgili US | Sistem Bileşeni | Öncelik | Doğrulama Yöntemi |
| :--- | :--- | :---: | :---: | :---: | :---: | :--- |
| **FR-01** | Kullanıcı kayıt ve kimlik doğrulama işlemleri | Fonksiyonel | US-01 | Backend | Yüksek | Senaryo Testi |
| **FR-02** | Kullanıcı profil bilgilerinin görüntülenmesi/güncellenmesi | Fonksiyonel | US-01, US-04 | Backend | Orta | Fonksiyonel Test |
| **FR-03** | Mutfak envanterinin (Dolabım) yönetilmesi | Fonksiyonel | US-02 | Backend | Yüksek | Senaryo Testi |
| **FR-04** | Yapay zekâ destekli yemek önerilerinin üretilmesi | Fonksiyonel | US-03 | AI / Backend | Yüksek | Model Çıktı Analizi |
| **FR-05** | Eksik malzeme bilgisinin kullanıcıya sunulması | Fonksiyonel | US-03 | Backend | Orta | Senaryo Testi |
| **FR-06** | Beslenme tercihleri ve kısıtların sürece dâhil edilmesi | Fonksiyonel | US-04 | AI / Backend | Yüksek | Fonksiyonel Test |
| **FR-07** | Kullanıcı etkileşimlerinin analiz edilmesi | Fonksiyonel | US-05 | AI / Backend | Orta | Veri Analizi |
| **FR-08** | Yetersiz veri durumunda alternatif önerilerin sunulması | Fonksiyonel | US-06 | AI | Orta | Senaryo Testi |
| **FR-09** | Tariflerin görüntülenmesi ve filtrelenmesi | Fonksiyonel | US-07 | Backend / Frontend | Yüksek | Kullanıcı Testi |
| **FR-10** | Kullanıcıların tarif ekleyebilmesi ve paylaşabilmesi | Fonksiyonel | US-08 | Backend | Orta | Fonksiyonel Test |
| **FR-11** | Uygun tarif bulunamadığında kullanıcı bilgilendirilmesi | Fonksiyonel | US-09 | Backend | Orta | Senaryo Testi |
| **FR-12** | Yönetici (admin) işlemlerinin gerçekleştirilmesi | Fonksiyonel | US-10 | Backend | Düşük | Yetki Testi |
| **NFR-01** | Sistem performansının kabul edilebilir yanıtta olması | Fonk. Olmayan | – | Backend / AI | Yüksek | Performans Testi |
| **NFR-02** | Kullanıcı verilerinin güvenliğinin sağlanması | Fonk. Olmayan | – | Backend | Yüksek | Güvenlik Testi |
| **NFR-03** | Sistemin ölçeklenebilir mimariye sahip olması | Fonk. Olmayan | – | Sistem Geneli | Orta | Mimari İnceleme |
| **NFR-04** | Sistemin kullanıcı dostu ve erişilebilir olması | Fonk. Olmayan | – | Frontend | Orta | Kullanılabilirlik Testi |
| **NFR-05** | Sistemin bakım yapılabilir ve modüler olması | Fonk. Olmayan | – | Sistem Geneli | Orta | Kod İncelemesi |
| **NFR-06** | Sistemin güvenilir ve hataya dayanıklı çalışması | Fonk. Olmayan | – | Backend | Orta | Hata Senaryosu |
| **NFR-07** | Web ve mobil platformlarda tutarlı çalışması | Fonk. Olmayan | – | Frontend | Orta | Platform Testi |

---

## 2.7 Use Case Diyagramı:

![useCaseDiagram](OleAIUseCaseDiagram.png)

---

## 2.8 Risk Analizi ve Önleme Stratejileri: 

| ID | Risk Tanımı | Risk Türü | Olasılık | Etki | Risk Seviyesi | Önleme / Azaltma Stratejisi |
| :--- | :--- | :--- | :---: | :---: | :---: | :--- |
| **R-01** | Yapay zekâ modelinin yetersiz veya hatalı öneriler üretmesi | Teknik | Orta | Yüksek | **Yüksek** | Modelin iteratif olarak iyileştirilmesi, alternatif öneri mekanizması geliştirilmesi. |
| **R-02** | Kullanıcıdan alınan verilerin eksik veya hatalı olması | Operasyonel | Yüksek | Orta | **Yüksek** | Veri doğrulama kontrolleri, kullanıcı yönlendirmeleri. |
| **R-03** | Sistem performansının yoğun kullanımda düşmesi | Teknik | Orta | Yüksek | **Yüksek** | Ölçeklenebilir mimari, performans testleri. |
| **R-04** | Kullanıcı verilerinin güvenliği ile ilgili açıklar | Güvenlik | Düşük | Çok Yüksek | **Yüksek** | Güçlü kimlik doğrulama, erişim kontrolü, güvenli veri saklama. |
| **R-05** | Kullanıcıların sistemi terk etmesi (düşük benimseme) | Kullanıcı Deneyimi | Orta | Orta | **Orta** | Kullanıcı dostu arayüz, kişiselleştirilmiş öneriler. |
| **R-06** | Proje kapsamının kontrolsüz şekilde genişlemesi | Yönetimsel | Orta | Orta | **Orta** | Net kapsam tanımı, gereksinimlerin önceliklendirilmesi. |

---




