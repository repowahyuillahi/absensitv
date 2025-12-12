# 📺 Sistem Absensi Digital Tjahaja Baru

Sistem informasi digital untuk menampilkan data absensi karyawan yang keluar kantor (Out Off Office) dan data cuti/dinas luar kota di layar TV.

## 🎯 Fitur

### Display TV (`index.html`)
- ✅ Tampilan Out Off Office (nama, perusahaan, jam pergi, tujuan)
- ✅ Tampilan Others (cuti/dinas luar kota)
- ✅ Running text (marquee) untuk pengumuman
- ✅ Auto refresh setiap 30 detik
- ✅ Responsive untuk berbagai ukuran layar
- ✅ Status indicator (online/offline)

### Admin Panel (`admin.html`)
- ✅ Dashboard dengan statistik
- ✅ Input data Out Off Office
- ✅ Input data Others (Cuti)
- ✅ Update status pulang
- ✅ Kelola pesan running text
- ✅ Lihat riwayat data dengan filter
- ✅ Login system dengan autentikasi

### Login System (`login.html`)
- ✅ Autentikasi via Google Sheets
- ✅ Session management
- ✅ Password protection

## 🚀 Cara Install

### 1. Setup Google Sheets

Buat Google Spreadsheet baru dengan 5 sheet:

#### **Sheet 1: OutOffOffice**
