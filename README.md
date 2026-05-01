# 🐧 NewKernelFeed - Linux Çekirdek Sürüm Takip Sistemi

Bu proje, [kernel.org](https://www.kernel.org/) üzerindeki yayını takip eden bir **monitoring aracı** ve **bilgi portalıdır**. 
Amacımız, Linux çekirdeklerinin gelişim sürecini takip eden geliştiriciler ve sistem yöneticileri için en güncel kararlı (stable) sürümleri, uzun süreli destek (longterm) durumlarını ve kritik yamaları tek bir yerde sunmaktır.

Proje içeriği; kernel.org yayın sayfasının otomatik taramasını yapan bir Python botunu ve güncel sürüm dağılım verilerini içerir.

> **Son Güncelleme:** 26 Nisan 2026  
> **Mevcut Ana Sürüm:** **v7.0.2** (Stable)

---

## 📊 Mevcut Sürüm Dağılımı

Aşağıdaki tablo, projenin son tarandığı anda **kernel.org** üzerinde bulunan aktif sürümlerin özeti olarak sunulmuştur. Bu veri yapısı, hangi LTS serisinin devam ettiğini belirlemek için temel alınır.

| Kapsam | Sürüm Ailesi | En Son Yama | Yayın Tarihi | Destek Durumu / Planlanan EOL |
| :--- | :---: | :---: | :---: | :--- |
| 🔵 **Mainline** | `v7.0.x` | **7.0.2** | 2026-04-27 | ✅ Aktif Geliştirme |
| 🟠 **LTS** | `6.18.x` | 6.18.25 | 2026-04-27 | ⏳ Aralık 2028'e kadar |
| 🟠 **LTS** | `6.12.x` | 6.12.84 | 2026-04-27 | ⏳ Aralık 2028'e kadar |
| 🟡 **LTS** | `6.6.x` | 6.6.136 | 2026-04-27 | ⏳ Aralık 2027'e kadar |
| 🟡 **LTS** | `6.1.x` | 6.1.169 | 2026-04-18 | ⏳ Aralık 2027'e kadar |
| 🟥 **EOL Yaklaşan**| `5.15.x` | 5.15.203 | 2026-04-18 | ⚠️ Aralık 2026 (Son) |
| 🟥 **EOL Yaklaşan**| `5.10.x` | 5.10.253 | 2026-04-18 | ⚠️ Aralık 2026 (Son) |

---

## 🚀 Linux 7.0 Sürümü İncelemesi

Linux çekirdeğinin yeni ana sürümü olan **7.0**, özellikle altyapı uzmanları için önemli değişiklikler barındırmaktadır. Bu sürüm geçiş sürecinde öne çıkan yenilikler şunlardır:

*   💾 **XFS Self-Healing:** XFS dosya sistemi artık meta veri bozulmalarını tespit edebilir ve işlem sırasında bu hataları otonom bir şekilde onarabilir.
*   🛠 **Gelişmiş Hata Raporlama:** Dosya sistemleri arasındaki standart dışı hata raporlama mekanizmaları, tek bir çatı altında toplamak amacıyla yenilenmiş bir I/O çerçevesi ile desteklendi.
*   ☁️ **Derleme Zamanı Analizi:** Clang statik analiz araçları derleme süreçlerine entegre edilerek potansiyel hataların kod çalışma aşamasına gelmeden yakalanması sağlandı.
*   ⚡ **Swap Performansı:** Sanal bellek (swap) yönetimi iyileştirilerek sistem kaynaklarının daha efektif kullanımı hedeflendi.

---

## 🤖 Auto-Kernel-Monitor (Otomasyon Aracı)

Bu depoda yer alan Python betiği, kernel.org üzerinden gelen yeni sürüm bilgilerini algılar ve ilgili istemcilere bildirim göndermek üzere yapılandırılmıştır.

### ✨ Özellikler
- 🔍 **Akıllı Tarama:** `kernel.org/releases.html` sayfasını tarar.
- 📉 **Gürültü Azaltma:** Sadece tamamlanmış `.tar.xz` paketlerini yakalar (RC adaylarını göz ardı eder).
- 🔄 **Semantic Versioning:** Sürümleri matematiksel sıraya göre (örn: v7.0 > v6.18) doğru listeler.
- ⚙️ **Kolay Kurulum:** Bağımlılıklar minimal tutulmuştur.

### 🛠 Kurulum ve Kullanım

Sisteminizde Python 3.8+ yüklü olmalıdır.

**1. Depoyu Klonlayın:**
```bash
git clone https://github.com/kullanici/yenikernelfeed.git
cd yenikernelfeed
