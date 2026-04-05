# 🍈 FarmTrack Pro

> **Dashboard monitoring pertanian berbasis web** — real-time data langsung dari Google Sheets, tanpa backend tambahan.

---

## 📌 Tentang Proyek

**FarmTrack Pro** adalah aplikasi monitoring pertanian berbasis HTML single-file yang dirancang untuk memantau kondisi greenhouse (GH) secara real-time. Data diambil langsung dari **Google Sheets via Google Apps Script (GAS)**, sehingga tim lapangan dapat mengisi data di spreadsheet dan langsung terlihat di dashboard.

---

## ✨ Fitur Utama

| Fitur | Status |
|---|---|
| 📊 Dashboard Overview (Gramasi, Populasi, Status GH) | ✅ Aktif |
| ⚖️ Monitoring Gramasi per GH | ✅ Aktif |
| 🐛 Monitoring HPT (Hama Penyakit Tanaman) | 🔧 Under Maintenance |
| 💧 Monitoring Penyiraman (EC, pH, Volume) | 🔧 Under Maintenance |
| 🌱 Monitoring Semai | 🔧 Under Maintenance |
| 🧹 Sanitasi | 🔜 Coming Soon |
| 🌿 Penyemprotan | 🔜 Coming Soon |
| ⚙️ Pengaturan Standar | 🔜 Coming Soon |

---

## 🏗️ Arsitektur

```
Browser (index.html)
    │
    ├── Fetch setiap N detik
    │
    └── Google Apps Script (GAS) Endpoint
            │
            └── Google Sheets (Data Source)
                    ├── Sheet: gramasi
                    ├── Sheet: hpt
                    ├── Sheet: penyiraman
                    └── Sheet: semai
```

Tidak ada server — semua logika berjalan di browser. GAS hanya berperan sebagai **JSON API proxy** ke Google Sheets.

---

## 🚀 Cara Penggunaan

### 1. Deploy Google Apps Script

1. Buka Google Sheets kamu → **Extensions → Apps Script**
2. Paste script GAS yang sudah disiapkan
3. Deploy sebagai **Web App** (Execute as: Me, Access: Anyone)
4. Salin URL deployment

### 2. Konfigurasi `GAS_URL`

Buka `index.html`, cari baris:

```js
const GAS_URL = 'https://script.google.com/macros/s/YOUR_SCRIPT_ID/exec';
```

Ganti dengan URL deployment GAS kamu.

### 3. Buka di Browser

Cukup buka `index.html` di browser — tidak perlu web server, tidak perlu instalasi.

---

## 📂 Struktur File

```
farmtrack-pro/
├── index.html       # Seluruh aplikasi (HTML + CSS + JS dalam satu file)
└── README.md        # Dokumentasi ini
```

---

## 🔐 Akses Menu Under Maintenance

Beberapa menu dilindungi dan memerlukan **kode akses tim** untuk dibuka (contoh: HPT). Kode akses dikelola oleh admin tim data.

---

## 🛠️ Teknologi

- **Vanilla HTML/CSS/JS** — tanpa framework, tanpa build tool
- **Google Apps Script** — sebagai backend ringan
- **Google Sheets** — sebagai database
- **Font:** Plus Jakarta Sans + JetBrains Mono (via Google Fonts)

---

## 👥 Kontribusi

Proyek ini dikelola oleh **Tim Data FarmHill**. Untuk pertanyaan, pengembangan fitur baru, atau laporan bug, silakan hubungi tim internal.

---

## 📄 Lisensi

Internal use only — © FarmHill Team
