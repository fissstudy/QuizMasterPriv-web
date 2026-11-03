# QuizMaster

Website kuis pribadi responsif untuk HP, menggunakan HTML/CSS/JavaScript + Firebase Authentication dan Cloud Firestore.

## Fitur
- Daftar dan masuk akun dengan email/password.
- Buat kuis sendiri (4 opsi A-D), pembahasan, mata pelajaran, dan durasi.
- Simpan kuis dan hasil ke database online.
- Timer otomatis, navigasi nomor, penanda soal terjawab.
- Acak soal dan pilihan jawaban.
- Nilai otomatis, ulasan jawaban, pembahasan.
- Statistik pribadi, riwayat, papan peringkat.

## Setup Firebase (wajib, gratis pada paket Spark sesuai batas penggunaan)
1. Buka https://console.firebase.google.com lalu buat project.
2. Tambahkan aplikasi Web (ikon `</>`), salin konfigurasi Firebase.
3. Buka `firebase-config.js`, ganti semua nilai `ISI_...` dengan konfigurasi project kamu.
4. Firebase Console → Authentication → Get started → Sign-in method → aktifkan **Email/Password**.
5. Firebase Console → Firestore Database → Create database.
6. Buka tab Rules, salin isi file `firestore.rules`, lalu klik Publish.
7. Hosting lokal: jalankan server statis (contoh VS Code Live Server). Modul Firebase tidak berjalan baik jika `index.html` dibuka langsung dengan `file://`.

## Upload ke GitHub Pages
1. Buat repository GitHub baru.
2. Upload `index.html`, `style.css`, `app.js`, `firebase-config.js`.
3. Settings → Pages → Deploy from branch → pilih `main` dan `/root`.
4. Buka URL GitHub Pages yang diberikan.

## Catatan penting
- Jangan bagikan file konfigurasi berisi kunci rahasia server. Firebase Web API key memang digunakan di aplikasi browser; keamanan data ditentukan oleh Authentication dan Firestore Rules.
- Rules contoh ini mengizinkan pengguna login membaca kuis/hasil untuk mendukung papan peringkat, tetapi hanya pemilik yang boleh mengubah atau menghapus dokumennya. Karena itu jangan masukkan data pribadi sensitif.
- Papan peringkat menampilkan 10 hasil tertinggi dari seluruh pengguna yang login.
- Fitur AI belum dihubungkan ke layanan AI eksternal karena membutuhkan API dan backend yang aman. Jangan menaruh API key AI di JavaScript frontend.
