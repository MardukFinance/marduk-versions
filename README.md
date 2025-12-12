# Marduk Versions Repository

Merkezi versiyon yönetim reposu. Tüm Marduk Finance projeleri (Flutter, Backend, Web) için versiyon bilgilerini tek bir yerden yönetir.

## Versiyonlama Standardı

Bu repo **Semantic Versioning (SemVer) 2.0.0** standardını kullanır:

- **MAJOR**: Uyumsuz API değişiklikleri
- **MINOR**: Geriye uyumlu yeni özellikler
- **PATCH**: Geriye uyumlu hata düzeltmeleri

Format: `MAJOR.MINOR.PATCH` (örn: `1.2.3`)

## Yapı

### Flutter Projesi (mardukfinance)

Flutter projeleri için versiyon formatı: `VERSION+BUILD_NUMBER` (örn: `1.0.0+67`)

- **versionString**: Semantic version (1.0.0)
- **build**: Build number (67)
- **fullVersion**: Tam versiyon string (1.0.0+67)

#### Platform Özel Bilgiler

- **iOS**: 
  - `versionName`: CFBundleShortVersionString
  - `buildNumber`: CFBundleVersion
- **Android**: 
  - `versionName`: versionName
  - `versionCode`: versionCode (integer, her zaman artmalı)
- **Web/MacOS/Windows/Linux**: Standart versiyon ve build numarası

### Backend Projesi

- **version**: Semantic version
- **apiVersion**: API versiyonu (v1, v2, vb.)

### Web Projesi

- **version**: Semantic version

## Kullanım

### Versiyon Güncelleme

1. `versions.json` dosyasını düzenleyin
2. İlgili projenin versiyon bilgilerini güncelleyin
3. `lastUpdated` alanını güncel tarih/saat ile güncelleyin
4. `releaseNotes` alanına değişiklik notlarını ekleyin

### Versiyon Artırma Kuralları

- **PATCH (1.0.0 → 1.0.1)**: Bug fix, küçük düzeltmeler
- **MINOR (1.0.0 → 1.1.0)**: Yeni özellikler, geriye uyumlu değişiklikler
- **MAJOR (1.0.0 → 2.0.0)**: Breaking changes, büyük değişiklikler

### Build Number

Flutter projelerinde build number her build'de artmalıdır:
- iOS: CFBundleVersion
- Android: versionCode (her zaman artan integer)

## Örnek Versiyon Güncellemesi

```json
{
  "version": {
    "major": 1,
    "minor": 1,
    "patch": 0,
    "build": 68,
    "versionString": "1.1.0",
    "fullVersion": "1.1.0+68"
  },
  "lastUpdated": "2024-01-15T10:30:00Z",
  "releaseNotes": {
    "tr": "Yeni özellikler eklendi",
    "en": "New features added"
  }
}
```

## Notlar

- Tüm tarih/saat değerleri ISO 8601 formatında (UTC)
- Release notes hem Türkçe hem İngilizce olarak tutulur
- Android versionCode her zaman artan bir integer olmalıdır
- iOS buildNumber string olarak tutulur ama genelde integer değer kullanılır

