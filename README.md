# Ruang (Android)

Port Android dari desain "ruang." — Kotlin + Jetpack Compose (Material 3).

## Cara menjalankan
1. Buka folder ini di Android Studio (Ladybug atau lebih baru). Gradle wrapper dibuat otomatis saat sync.
2. Jalankan di perangkat fisik (emulator biasanya tidak punya sensor langkah).
3. Di tab **Langkah**, tekan **Izinkan** untuk izin aktivitas fisik dan notifikasi.

## Isi
- **Beranda**: sapaan, check-in suasana hati, kartu latihan napas, jurnal singkat.
- **Langkah**: kartu target + cincin progres, diagram per jam, ringkasan mingguan, sakelar laporan malam.
- **Pencatatan langkah**: sensor `TYPE_STEP_COUNTER`, disampel tiap jam lewat WorkManager dan saat aplikasi dibuka; selisihnya disimpan per jam.
- **Notifikasi 21.00**: WorkManager dengan jeda awal sampai pukul 21.00, menjadwal ulang dirinya sendiri tiap malam. Ketuk notifikasi membuka tab Langkah.

## Catatan
- Waktu WorkManager tidak presisi ke menit; notifikasi bisa tiba beberapa menit dari 21.00 (hemat baterai).
- Langkah hanya tercatat sejak aplikasi pertama kali dijalankan (bacaan pertama jadi titik awal).
- Target langkah default 9.000 (`StepStore.goal`); belum ada layar untuk mengubahnya.
- Tab Jurnal dan Profil masih placeholder.
