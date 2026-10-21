# 5.DevOps Entegrasyonu Dokümanları
Bu bölüm, OleAI bitirme projesi için hazırlanan final raporundaki **5. DevOps Entegrasyonu** kısmının rapora sığmayan tablo ve dokümanların bir örneğini tutmak için kullanılan dosyadır.

---

## 5.3 CI/CD Pipeline Akışı:

| Aşama | Açıklama | Kullanılan Araç / Teknoloji |
| :--- | :--- | :--- |
| **Commit** | Kod değişikliklerinin GitHub reposuna gönderilmesi. | Git / GitHub |
| **CI Tetikleme** | Commit işlemi sonrası pipeline’ın otomatik başlatılması. | GitHub Actions |
| **Build** | Uygulamanın derlenmesi ve bağımlılıkların kontrol edilmesi. | .NET Build Tools |
| **Test** | Birim testlerin (Unit Tests) otomatik olarak çalıştırılması. | xUnit |
| **Kod Kalitesi & Güvenlik** | Kodun kalite ve güvenlik açısından statik analizi. | SonarQube |
| **Containerization** | Uygulamanın Docker image hâline getirilmesi. | Docker |
| **Deploy** | Image’ın sunucu ortamına dağıtılması ve çalıştırılması. | VPS / Docker Runtime |
| **Monitoring & Logging** | Uygulamanın çalışma durumunun ve logların izlenmesi. | Prometheus, ELK Stack |


---

## 5.7 CI/CD Akış Tablosu: 

| No | Pipeline Adımı | Girdi (Input) | Gerçekleştirilen İşlem | Çıktı |
| :---: | :--- | :--- | :--- | :--- |
| **1** | **Kod Commit** | Geliştirici tarafından yapılan kod değişiklikleri | Kodun GitHub reposuna gönderilmesi (Push). | Güncellenmiş kaynak kod |
| **2** | **CI Tetikleme** | Yeni commit | Otomatik CI pipeline başlatılması (Trigger). | Aktif pipeline süreci |
| **3** | **Build** | Kaynak kod | Uygulamanın derlenmesi ve bağımlılıkların kontrol edilmesi. | Başarılı / Başarısız build sonucu |
| **4** | **Test** | Derlenmiş uygulama | Birim (Unit) testlerin otomatik olarak çalıştırılması. | Test raporları |
| **5** | **Kod Kalitesi Analizi** | Testten geçen kod | SonarQube üzerinden statik kod analizi ve Quality Gate kontrolü. | Kalite değerlendirme sonucu |
| **6** | **Güvenlik Kontrolleri** | Kod ve bağımlılıklar | Güvenlik açıkları ve riskli bağımlılıkların analizi (Vulnerability Scan). | Güvenlik onayı |
| **7** | **Containerization** | Onaylı kod | Docker image oluşturulması. | Versiyonlanmış Docker image |
| **8** | **Deploy** | Docker image | Image’ın hedef sunucu ortamına dağıtılması. | Canlıya alınmış uygulama |
| **9** | **Monitoring & Logging** | Çalışan uygulama | Performans, log ve hata takibi (Prometheus/ELK). | İzleme ve log kayıtları |

## 5.8 DevOps Pipeline Diyagramı: 

![DevOpsDiagram](DevOpsDiagram.png)

