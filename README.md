# Metronom Android

Klasik mekanik metronom görünümünü Android'e taşıyan, ses zamanlamasını `AudioTrack` PCM örnek saatinden alan özgün bir Kotlin + Jetpack Compose uygulaması.

## Özellikler

- 20–300 BPM
- PCM örnek konumlarına bağlı hassas `AudioTrack` motoru
- Ölçünün ilk vuruşunda ayrı aksan sesi
- Sese senkron mekanik sarkaç
- BPM sürgüsü, `+` / `−`, doğrudan sayı girişi ve Tap Tempo
- Hazır 2/4, 3/4, 4/4 ve 6/8 ölçüleri
- Payı ve paydası ayrı girilebilen özel ölçü: 7/8, 9/8, 10/8 ve 1–32 arası diğer değerler
- Ses aç/kapat ve sessiz kullanımda görsel vuruş çerçevesi
- Uygulama içi yüksek, bozulmasız çıkış kazancı

> Uygulama ses örneğini dijital sınıra yakın üretir ve `AudioTrack` kazancını tam seviyede tutar. Telefonun medya sesini zorla değiştirmez; son duyulan seviye cihazın medya sesine ve hoparlörüne bağlıdır.

## Ekran görüntüleri

![Metronom çalışırken](docs/screenshots/metronom-v0.2.0-running.png)

![Özel ölçü girişi](docs/screenshots/custom-meter-dialog.png)

## Gereksinimler

- Android Studio'nun güncel kararlı sürümü
- JDK 17 veya üzeri
- Android SDK 37
- Android Build Tools 36
- Gradle Wrapper 9.6.0 (projeye dahildir)

## Derleme

Projeyi Android Studio ile açın veya terminalde:

```bash
./gradlew assembleDebug
```

Üretilen APK:

```text
app/build/outputs/apk/debug/app-debug.apk
```

Kalite kontrolü:

```bash
./gradlew lintDebug testDebugUnitTest
```

## Özel ölçü kullanımı

1. Ana ekranda **ÖZEL ÖLÇÜ • \*/\*** düğmesine dokunun.
2. Pay alanına ölçüdeki vuruş sayısını yazın: örneğin `7`, `9` veya `10`.
3. Payda alanına vuruş birimini yazın: örneğin `8`.
4. **UYGULA** düğmesine dokunun.

Motor pay kadar vuruş üretir ve her ölçünün ilk vuruşunu aksanlı çalar.

## Proje yapısı

```text
app/src/main/java/com/emre/metronom/
├── MainActivity.kt
├── audio/MetronomeEngine.kt
└── ui/
    ├── MetronomeScreen.kt
    └── theme/Theme.kt
```

## Sürüm

Güncel sürüm: **0.2.0** (`versionCode 2`). Değişiklikler için [RELEASE.md](RELEASE.md) dosyasına bakın.

## Gizlilik

Uygulama hesap, reklam, analitik veya ağ bağlantısı kullanmaz. Metronom işlemleri cihaz üzerinde gerçekleşir.

## Lisans

Depo herkese açık yayımlanmadan önce proje sahibinin tercih ettiği lisans ayrıca eklenmelidir.
