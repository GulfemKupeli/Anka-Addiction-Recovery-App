<p align="center">
  <img src="icon.png" width="120" alt="Anka app icon" />
</p>

# Anka — Sigara ve Alkol Bağımlılığından Kurtulma Uygulaması

*Yargılamayan, sadece yanında olan bir bağımlılık desteği uygulaması.*

> Bu repo, App Store gereksinimi olan gizlilik politikası sayfasını barındırmak ve projeyi tanıtmak içindir; kaynak kodu burada yer almaz.

## Problem

Sigara veya alkol bırakmaya çalışan biri çoğu zaman üç şeyle baş başa kalır: istek (craving) anında elinde somut bir araç olmaz, ilerlemesini gözle görülür şekilde takip edemez, ve tek dayatılan yol "ya tamamen bırak ya da hiç" olur — alkolde kontrollü azaltmayı tercih edenler için uygun bir orta yol genelde yok.

## Çözüm

Anka, kullanıcının kendi hedefini seçmesine izin veren (alkolde "tamamen bırak" ya da "kontrollü azalt"), craving anında nefes ve topraklama egzersizleri + güvenlik ağı (acil durum kişileri) sunan, ilerlemeyi gün sayacı/tasarruf/rozet/12 haftalık takvimle somutlaştıran ve sürçme anında suçlamak yerine yeniden başlatan, tamamen cihazda çalışan (gizlilik öncelikli, hesap gerektirmeyen) bir mobil destek uygulaması.

## Ekran Görüntüleri

_TestFlight build'i sonrası eklenecek._

## Özellikler

- Sigara ve alkol için ayrı takip; alkolde **tamamen bırak** / **kontrollü azalt** hedef seçimi ve haftalık içki bütçesi
- Gerçek zamanlı gün/saat/tasarruf sayaçları ve sağlık kazanım zaman çizelgesi (sigara: 11, alkol: 8 kilometre taşı)
- **İstek anı SOS** modalı: nefes egzersizi, 5 duyu (grounding) egzersizi, acil durum kişisi arama önerisi
- Suçlamayan **relapse (sürçme)** akışı — sayaç sıfırlanır, önceki streak motive edici şekilde gösterilir
- Günlük **check-in**: ruh hâli, craving şiddeti, tetikleyiciler, not — geçmiş kayıtlar günlük (diary) görünümünde
- 16 rozetli ilerleme sistemi + 12 haftalık renkli ilerleme takvimi (heatmap)
- Mood–craving korelasyon içgörüsü ve en sık tetikleyici analizi
- Anlık rozet bildirimleri, özelleştirilebilir günlük hatırlatma, haftalık özet bildirimi
- Paylaşılabilir ilerleme kartı
- Türkçe / İngilizce tam dil desteği (cihaz diline göre otomatik seçilir)
- **%100 yerel veri saklama** — hesap yok, hiçbir veri sunucuya gönderilmiyor

## Mimari

Tek katmanlı, sunucusuz bir mobil mimari:

```
App.tsx
 └─ AppProvider (React Context + AsyncStorage)
     └─ RootNavigator
         ├─ OnboardingScreen (ilk kurulum)
         └─ Bottom Tabs: Anasayfa · Check-in · İstatistik · Ayarlar
```

Bildirimler (günlük hatırlatma, rozet kutlamaları, haftalık özet) `expo-notifications` ile tamamen cihazda zamanlanır; push altyapısı kullanılmaz, hiçbir cihaz token'ı bir sunucuya gönderilmez.

## Teknoloji Yığını

| Katman | Teknoloji |
|---|---|
| Framework | React Native + Expo SDK 54 |
| Dil | TypeScript |
| Navigasyon | React Navigation (bottom tabs) |
| Depolama | AsyncStorage (tamamen yerel) |
| Bildirimler | expo-notifications (yerel zamanlama) |
| Görsel paylaşım | react-native-view-shot + expo-sharing |
| Build / Dağıtım | EAS Build · EAS Submit |

## Durum

🚧 Aktif geliştirme — TestFlight doğrulaması ve App Store gönderimine hazırlanıyor.

## Gizlilik

Tüm kullanıcı verisi sadece cihazda saklanır, hiçbir hesap oluşturulmaz. Detaylar: [Gizlilik Politikası](https://gulfemkupeli.github.io/Anka-Addiction-Recovery-App/privacy-policy.html)

## Geliştirici

Gülfem Küpeli — gulfemkupeli@gmail.com
