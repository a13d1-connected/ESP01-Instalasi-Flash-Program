# ESP01 - Instalasi dan Flash Program

![Platform](https://img.shields.io/badge/Platform-ESP8266-blue)
![IDE](https://img.shields.io/badge/IDE-Arduino%20IDE-00979D)
![Level](https://img.shields.io/badge/Level-Pemula-green)
![Bahasa](https://img.shields.io/badge/Bahasa-Indonesia-red)

Tutorial langkah demi langkah untuk memasang lingkungan pengembangan **ESP01 (ESP8266)** di Arduino IDE, lalu mengunggah (*flash*) program pertama berupa **Blink LED**.

## 📺 Video Tutorial

Tonton panduan lengkapnya di YouTube:
👉 [Klik di sini untuk menonton](https://www.youtube.com/watch?v=GlhpVptKNek&t=29s)

## 📋 Daftar Isi

- [Perlengkapan](#-perlengkapan)
- [Langkah-Langkah](#-langkah-langkah)
- [Catatan Penting](#-catatan-penting)
- [Troubleshooting](#-troubleshooting)
- [Link Pembelian](#-link-pembelian)
- [Ikuti Kami](#-ikuti-kami)

## 🧰 Perlengkapan

| No | Perlengkapan | Keterangan |
|----|--------------|------------|
| 1 | PC / Laptop | Windows (tutorial ini memakai Device Manager) |
| 2 | ESP01 | Modul WiFi berbasis ESP8266 |
| 3 | USB to TTL Programmer ESP01 | Untuk menghubungkan ESP01 ke USB dan mode flash |

## 🚀 Langkah-Langkah

### 1. Download dan Instal Arduino IDE

Unduh Arduino IDE dari situs resmi: <https://www.arduino.cc/en/software>, lalu instal seperti biasa.

### 2. Masukkan URL Preferences Board ESP8266

Buka **File → Preferences**, lalu tempel URL berikut pada kolom **Additional boards manager URLs**:

```
http://arduino.esp8266.com/stable/package_esp8266com_index.json
```

Klik **OK**.

### 3. Instal Board ESP8266 di Board Manager

1. Buka **Tools → Board → Boards Manager**
2. Cari `esp8266`
3. Pilih **esp8266 by ESP8266 Community**, lalu klik **Install**
4. Tunggu hingga proses selesai

### 4. Periksa Port COM ESP01 di Device Manager

1. Pasang ESP01 ke USB to TTL programmer, lalu colokkan ke PC/laptop
2. Buka **Device Manager → Ports (COM & LPT)**
3. Catat nomor port yang muncul, misalnya `COM3`

> Jika port tidak muncul, instal driver **CH340** atau **CP2102** sesuai chip pada programmer Anda.

### 5. Pilih Board Generic ESP8266 Module

Buka **Tools → Board → esp8266 → Generic ESP8266 Module**.

### 6. Pilih Port

Buka **Tools → Port**, lalu pilih port yang sama dengan yang tertera di Device Manager.

### 7. Buka Contoh Blink LED

Buka **File → Examples → 01.Basics → Blink**.

### 8. Klik Upload

Klik tombol **Upload** (ikon panah ➜). Tunggu hingga muncul pesan **Done uploading**. Jika berhasil, LED biru pada ESP01 akan berkedip.

## ⚠️ Catatan Penting

- Pada ESP01, LED biru terhubung ke **GPIO1 (TX)**. Karena itu, `Serial` sebaiknya tidak dipakai bersamaan dengan Blink.
- Untuk masuk ke **mode flash**, pin **GPIO0** harus terhubung ke **GND** saat ESP01 dinyalakan. Sebagian besar USB to TTL programmer ESP01 sudah menangani hal ini secara otomatis (atau lewat saklar/tombol).
- Gunakan catu daya **3.3V**. Jangan menghubungkan ESP01 ke 5V karena dapat merusak modul.
- Setelah selesai flash, lepas ESP01 dari mode flash (GPIO0 tidak lagi ke GND), lalu reset agar program berjalan.

## 🛠️ Troubleshooting

| Masalah | Solusi |
|---------|--------|
| Port COM tidak muncul | Instal driver CH340/CP2102, coba kabel atau port USB lain |
| Upload gagal (`espcomm_sync failed`) | Pastikan ESP01 dalam mode flash (GPIO0 ke GND), cek posisi pemasangan ESP01 pada programmer |
| LED tidak berkedip setelah upload | Keluarkan dari mode flash lalu reset/cabut-colok ulang |
| Board ESP8266 tidak ditemukan | Periksa kembali URL di Preferences dan koneksi internet saat instal board |
| Upload sering gagal di tengah proses | Turunkan **Upload Speed** ke `115200` di menu Tools |

## 🛒 Link Pembelian

Beli ESP01 dan USB to TTL programmer di sini:
👉 [Shopee - Link Pembelian Terpercaya](https://s.shopee.co.id/1gIPv5W8xi)

## 🌐 Ikuti Kami

**a13d1 Connected**

| Platform | Akun |
|----------|------|
| YouTube | [a13d1 Connected](https://www.youtube.com/@a13d1-connected) |
| Instagram | [a13d1-connected](https://www.instagram.com/a13d1connected?utm_source=qr&stkn=MWlzNTg0dmc1eWJqcg==) |
| TikTok | [a13d1connected](https://www.tiktok.com/@a13d1connected) |

## 🤝 Kontribusi

Menemukan kesalahan atau punya saran perbaikan? Silakan buka **Issue** atau kirim **Pull Request**.

## 📄 Lisensi

Proyek ini dirilis di bawah lisensi [MIT](LICENSE).

---

⭐ Jika tutorial ini bermanfaat, jangan lupa beri **Star** pada repository ini dan subscribe channel YouTube kami!
