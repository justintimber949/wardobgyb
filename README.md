# 🏥 Matahari Ward Board

Web app sederhana untuk memantau denah kamar dan data pasien di Bangsal Matahari (Obgyn) — dibuat khusus untuk kebutuhan koas/dokter jaga yang butuh gambaran cepat status kamar tanpa perlu backend/server.

**100% static** — cukup dibuka lewat browser, tanpa instalasi, tanpa database eksternal. Semua data tersimpan di `localStorage` browser kamu sendiri.

🔗 **Live demo:** `https://<username-kamu>.github.io/<nama-repo>/`

---

## ✨ Fitur

- **Denah visual interaktif** — layout kamar sesuai denah asli (VK1-4 & VK Iso, 1A, 1B, 2A, 3A, 3B, 3C), tiap kotak berwarna sesuai DPJP pasien di dalamnya.
- **Detail pasien per kamar** — nama, umur, tanggal masuk, diagnosis, catatan, dan status kelahiran bayi (lengkap dengan JK, BB/PB, APGAR, cara lahir).
- **Panel Pasien Aktif** — daftar scrollable semua pasien yang sedang dirawat di Matahari, bisa dicari/filter berdasarkan nama, kamar, atau DPJP.
- **Perhitungan H- otomatis** — hari rawat (H1, H2, dst) dihitung otomatis dari tanggal masuk, tidak perlu update manual.
- **Bangsal lain** — daftar pasien untuk HCU, VIP, IGD, Amarilis, CVCU, Edelweis, Orchid, ICU, Krisan, Mawar, Teratai (tanpa denah, cukup list).
- **History log** — setiap perubahan status kamar/pasien otomatis tercatat dengan timestamp. History bisa **diedit** atau **dihapus** manual per entri, atau dibersihkan semua sekaligus.
- **Mode gelap/terang** — toggle dengan satu klik, preferensi tersimpan otomatis.
- **Copy Ringkasan** — salin rekap semua pasien aktif ke clipboard dalam satu klik (berguna untuk serah terima jaga).
- **Print-friendly** — tampilan otomatis berubah jadi tabel bersih siap cetak saat kamu print halaman.
- **Export / Import JSON** — backup dan restore seluruh data kapan saja.

---

## ⚠️ Penting: soal penyimpanan data

Data disimpan di **localStorage** browser — artinya:

- ✅ Data akan tetap ada meskipun kamu tutup tab/browser dan buka lagi nanti, **selama pakai browser & device yang sama**.
- ❌ Data **tidak otomatis muncul** kalau kamu buka dari device lain (HP vs laptop) atau browser lain (Chrome vs Safari) — karena localStorage bersifat lokal per-browser, bukan disimpan di cloud/server.
- ❌ Data bisa **hilang** kalau kamu clear cache/data browser, uninstall browser, atau ganti device.

**Rekomendasi:** klik tombol **"⬇️ Export JSON"** secara rutin (misalnya tiap selesai update data) untuk backup ke file. Kalau data hilang atau pindah device, tinggal **"⬆️ Import JSON"** file backup tadi untuk restore semua data.

---

## 🚀 Cara Pakai

1. Buka link web app (lihat di atas, atau `index.html` langsung kalau dijalankan lokal).
2. **Klik kotak kamar** di denah untuk membuka detail — isi DPJP, nama pasien, umur, tanggal masuk, diagnosis, catatan.
3. Kalau bayi sudah lahir, centang **"💕 Bayi sudah lahir"** untuk membuka form detail bayi.
4. Klik **"Simpan"** untuk menyimpan, atau **"Kosongkan"** untuk mengosongkan kamar (data pasien sebelumnya otomatis masuk history).
5. Untuk bangsal lain (HCU, VIP, dst), klik **"+ Tambah pasien"** di section masing-masing.
6. Gunakan kotak pencarian di panel "Pasien Aktif" untuk cari cepat berdasarkan nama/kamar/DPJP.
7. Klik **"📋 Copy Ringkasan"** untuk menyalin rekap semua pasien ke clipboard.
8. Klik **"🖨 Print"** untuk mencetak laporan dalam format tabel.
9. Klik **"🌙 Mode Gelap"** di pojok toolbar untuk ganti tema.
10. **Jangan lupa export data secara berkala** untuk backup!

---

## 🛠️ Struktur Proyek

```
.
├── index.html      # seluruh aplikasi (HTML + CSS + JS dalam satu file)
└── README.md
```

Karena semuanya dalam satu file HTML, tidak ada proses build/instalasi. Tinggal buka `index.html` di browser, atau hosting lewat GitHub Pages.

---

## 📝 Kustomisasi

Beberapa hal yang bisa diubah langsung di `index.html` kalau perlu:

- **Nama DPJP** — cari objek `DPJP` di bagian `<script>`, ubah nama sesuai kebutuhan.
- **Layout kamar** — cari objek `ROOM_LAYOUT`, posisi (x, y, w, h) tiap kamar bisa disesuaikan kalau denah berubah.
- **Bangsal lain** — cari array `OTHER_SECTIONS` untuk menambah/menghapus daftar bangsal.

---

## 📄 Lisensi

Bebas dipakai dan dimodifikasi untuk keperluan pribadi/edukasi.
