# Mitama Builder — Proyek Android

Proyek ini membungkus file HTML Mitama Builder yang sudah ada ke dalam aplikasi Android berbasis Capacitor.

## Yang disertakan
- `www/index.html`: Mitama Builder versi Responsive Fixed yang diberikan sebelumnya.
- `capacitor.config.json`: identitas aplikasi Android.
- `.github/workflows/build-apk.yml`: workflow untuk membangun APK debug melalui GitHub Actions.

## Karakteristik
- Konten HTML dibundel di dalam APK; aplikasi inti dapat dibuka tanpa internet.
- Data lokal yang disimpan oleh halaman (misalnya `localStorage`) tetap berada di penyimpanan aplikasi pada perangkat tersebut.
- Tidak ada akun, server, analitik, atau API eksternal yang ditambahkan.
- Ini adalah APK debug untuk pemasangan/pengujian, bukan APK release bertanda tangan untuk distribusi publik.

## Cara membangun APK lewat Android saja
1. Buat repository GitHub baru dan unggah seluruh isi folder proyek ini.
2. Buka tab **Actions** pada repository.
3. Pilih workflow **Build Mitama Builder APK** lalu tekan **Run workflow**.
4. Setelah selesai, buka hasil run dan unduh artifact `Mitama-Builder-debug-APK`.
5. Ekstrak ZIP artifact dan pasang `app-debug.apk` di Android. Jika diminta, izinkan instalasi dari sumber tersebut.

## Catatan teknis
- Workflow memakai Node.js 20, Java 17, Capacitor 6.2.1, dan Android Gradle build.
- APK belum dibangun atau diuji pada perangkat dari paket sumber ini.
- Untuk pembaruan aplikasi, ganti `www/index.html`, commit/push, lalu jalankan workflow lagi.
- Jangan hapus data aplikasi jika ingin mempertahankan data lokal yang tersimpan di perangkat.
