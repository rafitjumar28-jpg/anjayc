# MonetLua Guard — Android source project

Aplikasi Android native sederhana untuk:
- Membuka file `.lua` secara lokal menggunakan Android file picker.
- Mencari pola mencurigakan terkait token/kredensial, jaringan, pencatatan input, akses file, dan eksekusi dinamis.
- Merapikan format Lua secara konservatif agar lebih mudah dibaca.
- Menyalin laporan atau hasil ke clipboard.

## Batasan penting
Scanner ini adalah pemeriksaan statis berbasis pola, bukan antivirus dan tidak membuktikan file aman. Ia dapat menghasilkan false positive maupun melewatkan perilaku berbahaya yang disamarkan. Jangan jalankan script yang belum dipercaya.

Fitur "Rapikan Lua" adalah formatter sederhana, bukan deobfuscator penuh. Ia tidak menjalankan kode, tidak mengurai seluruh grammar Lua, dan tidak bisa membuka semua string terenkripsi atau virtual machine obfuscator. Periksa hasilnya sebelum digunakan.

## Membangun APK langsung dari HP Android
Cara yang disarankan: gunakan AndroidIDE yang mendukung proyek Gradle Android.
1. Unduh dan pasang AndroidIDE dari sumber resminya.
2. Ekstrak `MonetLuaGuard-Android-Source.zip` ke folder yang mudah ditemukan.
3. Di AndroidIDE, buka folder proyek `MonetLuaGuard` (folder yang berisi `settings.gradle`).
4. Biarkan Gradle mengunduh Android Gradle Plugin dan Kotlin plugin. Internet diperlukan saat build pertama.
5. Pilih Build / Assemble Debug (nama menu bisa berbeda tergantung versi).
6. APK debug biasanya dibuat di `app/build/outputs/apk/debug/app-debug.apk`.
7. Buka APK tersebut dan izinkan pemasangan dari sumber yang digunakan bila Android memintanya.

Jika AndroidIDE meminta JDK, pilih versi JDK yang sesuai dengan Android Gradle Plugin 8.6 (JDK 17). Jika build gagal, simpan pesan error lengkap untuk diperiksa.

## Struktur
- `settings.gradle`
- `build.gradle`
- `gradle.properties`
- `app/build.gradle`
- `app/src/main/AndroidManifest.xml`
- `app/src/main/java/id/monetluaguard/MainActivity.kt`

## Privasi
Aplikasi tidak meminta izin internet dan tidak mengunggah file. File dipilih melalui Android Storage Access Framework.
