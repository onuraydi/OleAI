<div align="center">

# 🥗 OleAI — Yapay Zekâ Destekli Akıllı Tarif ve Mutfak Asistanı

**Gıda israfını önleyen, mutfak envanterinizi yöneten ve elinizdeki malzemelere göre kişiselleştirilmiş tarifler sunan uçtan uca akıllı mutfak ekosistemi.**

[![.NET](https://img.shields.io/badge/.NET%209-512BD4?style=for-the-badge&logo=dotnet&logoColor=white)](https://dotnet.microsoft.com/)
[![React](https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)](https://reactjs.org/)
[![Kotlin](https://img.shields.io/badge/Kotlin-7F52FF?style=for-the-badge&logo=kotlin&logoColor=white)](https://kotlinlang.org/)
[![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/)
[![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)](https://www.docker.com/)

[Özellikler](#temel-özellikler) • [Mimari ve Modüller](#proje-modülleri-ve-kaynak-kodlar) • [Teknoloji Yığını](#teknoloji-yığını) • [Dokümantasyon](#proje-dokümantasyonu) • [CI/CD Süreci](#mühendislik-ve-cicd-süreci)

</div>

---

## Proje Hakkında

**OleAI**, standart bir tarif uygulamasının ötesine geçerek mutfak envanterinizi (**Dolabım**) gerçek zamanlı takip eden, tüketim alışkanlıklarınızı ve damak zevkinizi öğrenen yapay zekâ destekli bir platformdur. Evdeki mevcut malzemeleri en verimli şekilde değerlendirerek gıda israfını azaltmayı ve *"Bugün ne pişirsem?"* sorusuna saniyeler içinde en optimum yanıtı vermeyi hedefler.

### Temel Özellikler

* **Yapay Zekâ Destekli Öneri Motoru:** Mevcut malzemelerinize, beslenme tercihlerinize ve geçmiş beğenilerinize göre **TF-IDF** ve **Kosinüs Benzerliği (Cosine Similarity)** algoritmalarını kullanarak en uygun tarifleri puanlar ve sıralar.
* **Akıllı Mutfak Envanteri (Dolabım):** Evdeki malzemeleri miktar ve son kullanma tarihleriyle yönetir; pişen yemeklerin ardından kullanılan gramajları stoktan otomatik düşer.
* **Otomatik Alışveriş Listesi:** Azalan veya tarif için eksik olan malzemeleri tek tıkla dinamik alışveriş listenize aktarır.
* **Sosyal Etkileşim ve Topluluk:** Kullanıcıların kendi özel tariflerini paylaşmasına, tarifleri puanlamasına ve yorumlamasına olanak tanır.
* **Kurumsal Düzeyde Güvenlik:** JWT (JSON Web Token) tabanlı kimlik doğrulama, Refresh Token mekanizması ve Rol Bazlı Erişim Kontrolü (RBAC).

---

## Proje Modülleri ve Kaynak Kodlar

OleAI, birbirinden bağımsız çalışabilen ve ölçeklenebilen 4 ana uygulama katmanından oluşmaktadır. İlgili modülün kaynak kodlarına ve kurulum yönergelerine aşağıdaki bağlantılardan ulaşabilirsiniz:

| Modül | Açıklama | Kaynak Kod / Dizin |
| :--- | :--- | :--- |
| **Backend API** | Clean Architecture prensipleriyle geliştirilmiş, iş kurallarını ve veritabanı işlemlerini yöneten merkezi RESTful API. | [Backend](https://github.com/onuraydi/OleAI-backend) |
| **AI Engine** | Tarif eşleştirme, doğal dil işleme (NLP) ve vektör uzay modellerini barındıran mikroservis. | [AI Servisi](https://github.com/onuraydi/OleAI-ai) |
| **Web İstemcisi** | Kullanıcıların büyük ekranda tarif keşfi ve kiler yönetimi yapabildiği modern, hızlı SPA (Single Page Application) arayüzü. | [Web](https://github.com/onuraydi/OleAI-web) |
| **Mobil Uygulama** | Mutfakta pratik kullanım için yerel (native) performans sunan, modern deklaratif UI tabanlı Android uygulaması. | [Mobil](https://github.com/onuraydi/OleAI-android) |

---

## Teknoloji Yığını

Sistem; sürdürülebilir, test edilebilir ve ölçeklenebilir **Clean Architecture** prensipleri temel alınarak inşa edilmiştir.

| Katman | Teknoloji ve Araçlar | İlgili Modül |
| :--- | :--- | :--- |
| **Backend** | .NET 9, ASP.NET Core Web API, Entity Framework Core | [🔗 Backend](https://github.com/onuraydi/OleAI-backend) |
| **Yapay Zekâ (AI)** | Python, FastAPI, Scikit-learn (TF-IDF, Cosine Similarity) | [🔗 AI Engine](https://github.com/onuraydi/OleAI-ai) |
| **Frontend (Web)** | React, Vite, Tailwind CSS | [🔗 Web UI](https://github.com/onuraydi/OleAI-web) |
| **Frontend (Mobil)** | Kotlin, Jetpack Compose | [🔗 Android App](https://github.com/onuraydi/OleAI-android) |
| **Veritabanı** | Microsoft SQL Server (MSSQL) | - |
| **DevOps & Altyapı** | Docker, Kubernetes, GitHub Actions | - |
| **Kalite & Test** | xUnit, Moq, Selenium, SonarQube | - |

---

## Proje Dokümantasyonu

Projenin yazılım yaşam döngüsü (SDLC) kapsamında hazırlanan tüm analiz, mimari tasarım, test ve yönetim belgelerine aşağıdan erişebilirsiniz:

| # | Doküman Başlığı | Kapsam ve İçerik Özeti | Bağlantı |
| :-: | :--- | :--- | :---: |
| **01** | **Gereksinim Analizi** | Kullanıcı Hikayeleri (User Stories), Fonksiyonel ve Fonksiyonel Olmayan Gereksinimler (FR/NFR), Risk Analizi | [📄 İncele](./GereksinimAnalizi/2.GereksinimAnaliziDocument.md) |
| **02** | **Sistem Tasarımı ve Mimari** | Sistem Mimarisi, UML Diyagramları, Veritabanı Tasarımı (ER Diyagramı), Sequence (Sıralama) Diyagramları | [📄 İncele](./SistemTasarimi/3.sistemTasarimi.md) |
| **03** | **Test Planı ve Senaryoları** | Test Stratejileri, Birim ve Entegrasyon Testleri, Detaylı Test Senaryoları (Auth, Tarif, AI, Güvenlik), Test Case Tabloları | [📄 İncele](./TestPlani/4.TestDocument.md) |
| **04** | **DevOps ve CI/CD** | CI/CD Pipeline Akışı, DevOps Mimari Diyagramı, Docker Konteynerizasyon ve Dağıtım Süreçleri | [📄 İncele](./DevOpsEntegrasyonu/5.DevOpsEngterasyonu.md) |
| **05** | **Proje Yönetimi** | Gantt Şeması, Zaman Çizelgesi, İş Paketleri, Görev Dağılımı ve Süreç Takibi | [📄 İncele](./ProjeYonetimi/6.ProjeYonetimi.md) |

---

## Mühendislik ve CI/CD Süreci

Kod kalitesini standartlaştırmak ve hatasız teslimat sağlamak amacıyla uçtan uca otomatize edilmiş bir **CI/CD pipeline** işletilmektedir:

```mermaid
graph LR
    A[📝 Kodlama & PR] --> B[⚙️ GitHub Actions CI]
    B --> C[🧪 xUnit & SonarQube Analizi]
    C --> D[🐳 Docker İmaj Üretimi]
    D --> E[🚀 Canlı Ortama Dağıtım]
