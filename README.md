# 🎵 Flutter Flexible dan Expanded

## 📝 Deskripsi Singkat

Project ini merupakan aplikasi Flutter yang mempelajari penggunaan widget `Flexible` dan `Expanded` untuk mengatur tata letak antarmuka aplikasi. Kedua widget tersebut digunakan untuk mendistribusikan ruang yang tersedia di antara beberapa widget anak berdasarkan nilai `flex`.

Melalui project ini, penggunaan `Flexible` dengan `FlexFit.loose` dan `FlexFit.tight` dibandingkan dengan `Expanded`. Penerapannya dilakukan pada susunan kotak berwarna serta rancangan Control Bar pemutar musik dengan lima tombol kontrol.

## 📱 Tampilan Aplikasi

Project ini mencakup beberapa contoh penerapan tata letak menggunakan Flutter:

- 🟦 Kotak biru dengan ikon jempol yang disusun menggunakan `Row`.
- 📐 Perbandingan ukuran widget berdasarkan nilai `flex`.
- 🟩 Penggunaan `Flexible` untuk menyesuaikan ruang yang tersedia.
- 🟦 Penggunaan `Expanded` untuk mengisi ruang sesuai proporsi.
- 🎵 Control Bar pemutar musik dengan lima tombol kontrol.
- 🌙 Tampilan gelap menggunakan `ThemeData.dark()` pada tugas akhir.

## 🚀 Teknologi yang Digunakan

| Teknologi | Kegunaan |
|---|---|
| Flutter | Framework untuk membangun antarmuka aplikasi |
| Dart | Bahasa pemrograman aplikasi |
| Material Design | Komponen antarmuka Flutter |
| `Row` | Menyusun widget secara horizontal |
| `Column` | Menyusun widget secara vertikal |
| `Flexible` | Mengatur penggunaan ruang oleh widget anak |
| `Expanded` | Memaksa widget anak mengisi ruang yang tersedia sesuai proporsi flex |
| `Container` | Membuat kotak dan mengatur warna, ukuran, serta tata letak |
| `Icon` | Menampilkan ikon pada antarmuka aplikasi |
| `ThemeData.dark()` | Mengatur tema aplikasi menjadi gelap |

## 🔄 Alur Kerja Aplikasi

Pengaturan tata letak dilakukan melalui kombinasi widget Flutter berikut:

```text
┌──────────────────────┐
│      main.dart       │
│   Titik Awal App     │
└──────────┬───────────┘
           ▼
┌──────────────────────┐
│     MaterialApp      │
│  Konfigurasi Aplikasi│
└──────────┬───────────┘
           ▼
┌──────────────────────┐
│       Scaffold       │
│  Struktur Halaman    │
└──────────┬───────────┘
           ▼
┌──────────────────────┐
│    Row / Column      │
│ Menyusun Widget Anak │
└──────────┬───────────┘
           ▼
┌──────────────────────┐
│ Flexible / Expanded  │
│  Mengatur Ruang Flex │
└──────────┬───────────┘
           ▼
┌──────────────────────┐
│   Container / Icon   │
│  Membentuk Tampilan  │
└──────────────────────┘
```

Nilai `flex` menentukan perbandingan alokasi ruang di antara widget yang berada pada susunan `Row` atau `Column` yang sama. Sementara itu, properti `fit` menentukan apakah widget anak boleh menggunakan ruang seperlunya atau harus mengisi ruang yang dialokasikan.

## 📂 Struktur Project

Struktur dasar project Flutter yang digunakan:

```text
demo_flexible/
│
├── android/
├── ios/
├── lib/
│   └── main.dart
│
├── test/
├── pubspec.yaml
├── pubspec.lock
└── README.md
```

Untuk percobaan kedua, project dibuat dengan nama `expanded`. Tugas Control Bar pemutar musik dapat dikembangkan dalam project Flutter tersendiri.

### `lib/main.dart`

Berisi kode utama aplikasi, mulai dari `main()`, class `MyApp`, konfigurasi `MaterialApp`, hingga penyusunan widget pada bagian `body`.

Pada percobaan `Flexible`, file ini juga memuat widget `KotakBiruJempolKecil` yang menampilkan kotak biru dengan ikon jempol.

Pada percobaan `Expanded`, file ini memuat method `_kotakUji()` untuk membentuk kotak berwarna dengan teks di dalamnya.

### `pubspec.yaml`

Berisi konfigurasi project dan dependency yang digunakan oleh Flutter.

### `README.md`

Berisi dokumentasi project, penjelasan konsep, fitur, dan cara menjalankan aplikasi.

*Catatan: Struktur di atas merupakan struktur dasar yang relevan dengan modul. Nama file tambahan dapat berbeda sesuai pengembangan tugas.*

## 🧩 Konsep Flexible dan Expanded

### 1. Flexible

Widget `Flexible` memungkinkan widget anak menyesuaikan penggunaan ruang yang tersedia berdasarkan nilai `flex`.

Contoh penggunaan:

```dart
Row(
  children: [
    Flexible(
      flex: 1,
      child: KotakBiruJempolKecil(),
    ),
    Flexible(
      flex: 3,
      child: KotakBiruJempolKecil(),
    ),
    Flexible(
      flex: 2,
      child: KotakBiruJempolKecil(),
    ),
  ],
)
```

Nilai `flex` mengatur proporsi ruang yang dialokasikan untuk setiap widget. Pada contoh tersebut, perbandingan nilai `flex` adalah 1:3:2.

Properti `fit` memiliki dua pilihan utama:

- `FlexFit.loose`: widget anak boleh menggunakan ruang sesuai kebutuhannya.
- `FlexFit.tight`: widget anak harus mengisi ruang yang dialokasikan kepadanya.

### 2. Expanded

Widget `Expanded` merupakan bentuk khusus dari `Flexible` yang menggunakan `FlexFit.tight` secara default. Dengan demikian, widget anak mengisi ruang yang dialokasikan berdasarkan nilai `flex`.

Contoh penggunaan:

```dart
Column(
  children: [
    Container(
      height: 150,
      color: Colors.amber,
    ),
    Expanded(
      flex: 1,
      child: Container(
        color: Colors.blue,
      ),
    ),
  ],
)
```

Pada contoh tersebut, kotak biru mengisi ruang vertikal yang tersisa setelah widget normal dan kebutuhan tata letak lainnya diperhitungkan.

### 3. Perbedaan Flexible dan Expanded

| Aspek | Flexible | Expanded |
|---|---|---|
| Pengaturan `fit` | Dapat menggunakan `loose` atau `tight` | Menggunakan `tight` secara default |
| Ukuran widget anak | Dapat menyesuaikan kebutuhan jika menggunakan `loose` | Mengisi ruang yang dialokasikan |
| Penggunaan | Tata letak yang membutuhkan fleksibilitas | Tata letak yang perlu mengisi ruang tersedia |
| Properti `flex` | Mendukung | Mendukung |

## 🎵 Tugas Control Bar Pemutar Musik

Tugas akhir pada modul menerapkan `Row`, `Expanded`, dan `Flexible` untuk menyusun lima tombol kontrol musik pada bagian bawah layar menggunakan properti `bottomNavigationBar` pada `Scaffold`.

### Fitur utama

- 🔀 **Shuffle** — ikon `Icons.shuffle`.
- ⏮️ **Previous** — ikon `Icons.skip_previous`.
- ▶️ **Play** — ikon `Icons.play_circle_fill`.
- ⏭️ **Next** — ikon `Icons.skip_next`.
- 🔁 **Repeat** — ikon `Icons.repeat`.

### Pengaturan tata letak

- Menggunakan `ThemeData.dark()` untuk menerapkan tema gelap.
- Menggunakan `Container` dengan padding horizontal 8 dan vertikal 10.
- Menggunakan `Colors.black54` sebagai warna latar Control Bar.
- Menggunakan `Expanded` untuk mendistribusikan ruang pada tombol Shuffle, Previous, Next, dan Repeat.
- Menggunakan `Flexible(flex: 2, fit: FlexFit.tight)` pada tombol Play agar memperoleh alokasi ruang lebih besar.
- Menggunakan warna putih pada semua ikon.

Pengaturan tersebut menghasilkan Control Bar dengan susunan tombol yang proporsional dan tombol Play yang lebih menonjol.

*Catatan: tombol-tombol ini merupakan elemen antarmuka. Fungsi pemutaran musik belum menjadi bagian dari spesifikasi tugas pada modul.*

## ▶️ Cara Menjalankan Project

Pastikan Flutter SDK dan Android Studio sudah terpasang serta emulator atau smartphone telah tersedia.

### 1. Masuk ke folder project

Untuk percobaan Flexible:

```bash
cd demo_flexible
```

Untuk percobaan Expanded, masuk ke folder project `expanded`.

### 2. Install dependency

```bash
flutter pub get
```

### 3. Periksa perangkat

```bash
flutter devices
```

### 4. Jalankan aplikasi

```bash
flutter run
```

Aplikasi juga dapat dijalankan melalui tombol Run (▶) pada Android Studio setelah memilih perangkat yang digunakan.

## 🎯 Konsep yang Dipelajari

Project ini membantu memahami beberapa konsep dasar Flutter:

- Penggunaan widget `Flexible` dan `Expanded`.
- Perbedaan `FlexFit.loose` dan `FlexFit.tight`.
- Penggunaan properti `flex`.
- Penyusunan widget menggunakan `Row` dan `Column`.
- Penggunaan `Container` untuk membuat elemen antarmuka.
- Pengaturan warna, ukuran, dan ikon.
- Penggunaan `Scaffold` dan `bottomNavigationBar`.
- Penerapan tema gelap menggunakan `ThemeData.dark()`.
- Pengaturan tata letak antarelemen agar tetap proporsional.

## 🛠️ Pengembangan Selanjutnya

Project ini dapat dikembangkan lebih lanjut dengan:

- Menambahkan fungsi Play dan Pause.
- Menambahkan informasi judul lagu dan nama penyanyi.
- Menambahkan gambar album.
- Membuat indikator progres pemutaran lagu.
- Menambahkan pengaturan volume.
- Mengatur ukuran ikon berdasarkan kebutuhan antarmuka.
- Menyesuaikan tata letak untuk berbagai ukuran layar.

## 📚 Tujuan Pembelajaran

Project ini bertujuan untuk memahami bagaimana widget `Flexible` dan `Expanded` digunakan untuk mengatur ruang dalam tata letak Flutter.

Melalui percobaan kotak berwarna dan Control Bar pemutar musik, perbedaan perilaku kedua widget dapat diamati secara langsung.

```text
Mengenal Flexible dan Expanded
             ↓
Memahami Properti flex dan fit
             ↓
Membandingkan loose dan tight
             ↓
Menyusun Widget dengan Row / Column
             ↓
Menerapkan pada Control Bar Musik
             ↓
Menghasilkan Tata Letak Proporsional
```

## 👨‍💻 Project

**Flutter Flexible dan Expanded**

Dibangun menggunakan:

**Flutter + Dart + Material Design**
