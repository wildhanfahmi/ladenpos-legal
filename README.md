# Halaman Legal Laden POS

Dua halaman ini wajib punya URL publik agar aplikasi bisa lolos review Google Play.

| Berkas | Didaftarkan di Play Console |
|---|---|
| `kebijakan-privasi.html` | Kebijakan privasi (App content → Privacy policy) |
| `hapus-akun.html` | Data safety → **Account deletion URL** |
| `index.html` | Halaman depan, menautkan keduanya |

Syarat Google: keduanya harus bisa dibuka **tanpa login** dan tanpa redirect ke
halaman yang meminta autentikasi.

## Yang perlu dijaga saat aplikasi berubah

- **Klaim "tidak menyimpan data pembeli".** Per 30 September 2026 skema basis
  data memang tidak punya tabel pelanggan. Begitu aplikasi mulai menyimpan nama
  atau nomor HP pembeli, bagian *"Yang TIDAK kami kumpulkan"* di
  `kebijakan-privasi.html` WAJIB diperbarui. Klaim privasi yang tidak akurat
  adalah masalah kepatuhan, bukan sekadar teks usang.
- **Daftar izin perangkat.** Saat ini hanya Bluetooth (printer termal) dan
  internet. Menambah izin kamera/lokasi berarti halaman ini harus menyebutkannya.
- **Tenggat 7 hari kerja** untuk permintaan hapus akun lewat email adalah
  komitmen ke pengguna dan ke Google. Turunkan hanya bila sanggup dipenuhi.
- **Daftar data yang terhapus** di `hapus-akun.html` mengikuti FK `ON DELETE
  CASCADE` dari tabel `tenants`. Menambah tabel ber-`tenant_id` baru berarti
  daftar itu ikut bertambah.
- **Tanggal berlaku** di kedua halaman diperbarui setiap kali isinya berubah.

Dokumen ini disusun dari skema basis data yang ada, bukan nasihat hukum.
