# 🐧 NewKernelFeed - Linux Çekirdek Sürüm Takip Sistemi

Bu proje, [kernel.org](https://www.kernel.org/) üzerindeki yayını takip eden bir **bilgi portalıdır**. 
Amacımız, Linux çekirdeklerinin gelişim sürecini takip ederek sunmaktır.

> **Son Güncelleme:** 1 Mayıs 2026 
> **Mevcut Ana Sürüm:** **v7.0.3** (Stable)

---

## 📊 Mevcut Sürüm Dağılımı

Aşağıdaki tablo, projenin son tarandığı anda **kernel.org** üzerinde bulunan aktif sürümlerin özeti olarak sunulmuştur.

| Kapsam | Sürüm Ailesi | En Son Yama | Yayın Tarihi | Destek Durumu / Planlanan EOL |
| :--- | :---: | :---: | :---: | :--- |
| 🔵 **Mainline** | `v7.0.x` | **7.0.3** | 2026-04-30 | ✅ Aktif Geliştirme (Stable) |
| ⚪ **Mainline** | `v7.1-rc` | **7.1-rc1** | 2026-04-26 | 🚧 Beta Döngüsü (RC) |
| 🟠 **LTS** | `6.18.x` | 6.18.26 | 2026-04-30 | ⏳ Aralık 2028'e kadar |
| 🟠 **LTS** | `6.12.x` | ... | ... | ⏳ Aralık 2028'e kadar |
| 🟡 **LTS** | `6.6.x` | ... | ... | ⏳ Aralık 2027'e kadar |
| 🟡 **LTS** | `6.1.x` | ... | ... | ⏳ Aralık 2027'e kadar |
| 🟥 **EOL Yaklaşan**| `5.15.x` | **5.15.203** | 2026-04-XX | ⚠️ Aralık 2026 (Son) |
| 🟥 **EOL Yaklaşan**| `5.10.x` | **5.10.253** | 2026-04-XX | ⚠️ Aralık 2026 (Son) |

> **Not:** Linux çekirdeği 6.19 serisi normal ana hat döngüsünü tamamlamış (`[EOL]`) olup artık desteklenmemektedir. 7.0.3, bu boşluğu dolduran en güncel stabil yapıdır.

---

## 🚀 Linux 7.0 Sürümü İncelemesi

Linux çekirdeğinin yeni ana sürümü olan **7.0** (ve bunu izleyen 7.0.x yamaları), özellikle altyapı uzmanları için önemli değişiklikler barındırmaktadır. Bu sürüm geçiş sürecinde öne çıkan yenilikler şunlardır:

*   💾 **XFS Self-Healing:** XFS dosya sistemi artık meta veri bozulmalarını tespit edebilir ve işlem sırasında bu hataları otonom bir şekilde onarabilir.
*   🛠 **Gelişmiş Hata Raporlama:** Dosya sistemleri arasındaki standart dışı hata raporlama mekanizmaları, tek bir çatı altında toplamak amacıyla yenilenmiş bir I/O çerçevesi ile desteklendi.
*   ☁️ **Derleme Zamanı Analizi:** Clang statik analiz araçları derleme süreçlerine entegre edilerek potansiyel hataların kod çalışma aşamasına gelmeden yakalanması sağlandı.
*   ⚡ **Swap Performansı:** Sanal bellek (swap) yönetimi iyileştirilerek sistem kaynaklarının daha efektif kullanımı hedeflendi.

---

## 🤖 Otomasyon Aracı

Bu depoda yer alan Python betiği, kernel.org üzerinden gelen yeni sürüm bilgilerini algılar ve ilgili istemcilere bildirim göndermek üzere yapılandırılmıştır.

### ✨ Özellikler
- 🔍 **Akıllı Tarama:** `kernel.org/releases.html` sayfasını tarar.
- 📉 **Gürültü Azaltma:** Sadece tamamlanmış `.tar.xz` paketlerini yakalar (RC adaylarını göz ardı eder).
- 🔄 **Semantic Versioning:** Sürümleri matematiksel sıraya göre (örn: v7.0 > v6.18) doğru listeler.
- ⚙️ **Modern Desteği:** Linux 7.x serisi dahil tüm güncel sürümleri tanır.
