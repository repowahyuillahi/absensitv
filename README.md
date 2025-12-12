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
A: NO | B: NAMA | C: PERUSAHAAN | D: JAM_PERGI | E: JAM_PULANG | F: TUJUAN | G: TANGGAL | H: STATUS

text

#### **Sheet 2: Others**
A: NO | B: NAMA | C: KETERANGAN | D: TANGGAL_MULAI | E: TANGGAL_SELESAI | F: STATUS

text

#### **Sheet 3: Riwayat_OutOffOffice**
A: ID | B: TANGGAL | C: NAMA | D: PERUSAHAAN | E: JAM_PERGI | F: JAM_PULANG | G: TUJUAN | H: STATUS

text

#### **Sheet 4: Riwayat_Others**
A: ID | B: NAMA | C: KETERANGAN | D: TANGGAL_MULAI | E: TANGGAL_SELESAI | F: STATUS

text

#### **Sheet 5: Pesan_Display**
A: TANGGAL | B: PESAN | C: STATUS

text

#### **Sheet 6: Users**
A: USERNAME | B: PASSWORD | C: NAMA_LENGKAP | D: STATUS

text

**Isi contoh Sheet Users:**
admin | admin123 | Administrator | Aktif

text

### 2. Setup Google Apps Script

1. Di Google Sheets, klik **Extensions** → **Apps Script**
2. Copy paste kode dari `Code.gs` (lihat dokumentasi terpisah)
3. Save project
4. Deploy sebagai **Web App**:
   - Execute as: **Me**
   - Who has access: **Anyone**
5. Copy **Web App URL**

### 3. Setup File HTML

1. Clone atau download repository ini
2. Buat folder `assets/img/`
3. Letakkan file `logo.png` di folder `assets/img/`
4. Edit semua file HTML, ganti `API_URL` dengan Web App URL Anda:

const API_URL = 'https://script.google.com/macros/s/YOUR_WEB_APP_URL/exec';

text

### 4. Upload ke GitHub Pages

1. Buat repository baru di GitHub
2. Upload semua file (index.html, login.html, admin.html, assets/)
3. Enable GitHub Pages di **Settings** → **Pages**
4. Pilih branch `main` dan folder `/ (root)`
5. Save dan akses via URL yang diberikan

## 📖 Cara Penggunaan

### Login Admin
1. Buka `login.html` atau `your-github-page.com/login.html`
2. Login dengan:
   - Username: `admin`
   - Password: `admin123`

### Input Data Out Off Office
1. Login ke admin panel
2. Klik tab **"Out Off Office"**
3. Isi form dan klik **Simpan Data**
4. Data akan otomatis tampil di display TV

### Update Status Pulang
1. Di dashboard atau tab Out Off Office
2. Klik tombol **"✓ Pulang"** pada data yang sudah pulang
3. Masukkan jam pulang

### Input Data Cuti/Dinas
1. Klik tab **"Others (Cuti)"**
2. Isi form dan klik **Simpan Data**
3. Data akan otomatis tampil di display TV

### Edit Pesan Running Text
1. Klik tab **"Pesan Display"**
2. Edit atau tambah pesan
3. Klik **Simpan Semua Pesan**

### Tampilkan di TV
1. Buka `index.html` atau `your-github-page.com/index.html`
2. Full screen (tekan F11)
3. Data akan auto refresh setiap 30 detik

## 🎨 Warna Brand

- **Primary**: `#041066` (Navy Blue)
- **Secondary**: `#FFA500` (Orange)
- **Background**: `#FFFFFF` (White)
- **Surface**: `#F8F9FC` (Light Gray)

## 🔒 Security

- Password disimpan di Google Sheets (bukan database terenkripsi)
- Session-based authentication
- Logout otomatis saat tutup browser
- CORS handled by Google Apps Script

## 📱 Support Browser

- ✅ Chrome/Edge (Recommended)
- ✅ Firefox
- ✅ Safari
- ✅ Mobile browsers

## 🐛 Troubleshooting

### Login Error
- Pastikan sheet "Users" sudah dibuat
- Cek username & password benar
- Pastikan Web App deployed dengan "Who has access: Anyone"

### Data Tidak Muncul
- Cek API_URL sudah benar
- Buka Console (F12) untuk lihat error
- Pastikan Google Sheets tidak private

### Format Jam Salah
- Pastikan kolom JAM_PERGI di sheet format TIME (bukan DATETIME)
- Format yang benar: `09:24` bukan `2025-12-12 09:24:00`

## 📞 Support

Jika ada masalah atau pertanyaan, silakan buat issue di GitHub repository ini.

## 📄 License

MIT License - Free to use for personal and commercial projects.

---

**Developed with ❤️ for Tjahaja Baru**
