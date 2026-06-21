# EduAir OTA Firmware

Implementasi pembaruan firmware ESP32 menggunakan metode Over-The-Air (OTA) berbasis Arduino IoT Cloud pada proyek EduAir — sistem deteksi asap dan gas untuk lingkungan sekolah.

## Deskripsi

Praktikum ini mensimulasikan pembaruan firmware dari Versi 1 ke Versi 2 pada perangkat ESP32 menggunakan platform Arduino IoT Cloud. Proses unggah firmware dilakukan melalui USB sebagai simulasi mekanisme OTA.

## Hardware

- ESP32 DevKit V1 (DOIT)
- Sensor MQ-2 (smoke/gas detector)
- Kabel USB

## Software

- Arduino IDE
- Arduino IoT Cloud
- Library: ArduinoIoTCloud, Arduino_ConnectionHandler

## Variabel Cloud

| Nama | Tipe | Keterangan |
|------|------|------------|
| deviceStatus | String | Status perangkat |
| firmwareVersionCloud | String | Versi firmware aktif |
| otaCounter | int | Counter update tiap interval |
| smokeLevel | int | Nilai sensor MQ-2 (dummy) |
| ledState | bool | Kontrol LED |

## Perbedaan V1 dan V2

| Aspek | V1 | V2 |
|-------|----|----|
| Versi | 1.0.0 | 2.0.0 |
| Interval counter | 10 detik | 5 detik |
| Status | V1 Online | V2 Online - OTA OK |
| Upload | USB (pertama) | USB (simulasi OTA) |

## Cara Penggunaan

1. Clone repository ini
2. Isi `arduino_secrets.h` dengan kredensial WiFi dan device key
3. Buka `Untitled_jun21a.ino` di Arduino IDE
4. Upload Firmware V1 → verifikasi di Serial Monitor
5. Ganti kode dengan Firmware V2 → upload ulang
6. Cek perubahan di Serial Monitor dan dashboard Arduino IoT Cloud

## Struktur File
EduAir_OTA/

├── Untitled_jun21a.ino   # Sketch utama

├── thingProperties.h     # Variabel cloud (auto-generated)

├── arduino_secrets.h     # Kredensial (jangan di-push!)

└── README.md

## Catatan

- Jangan upload `arduino_secrets.h` ke repository publik
- Tambahkan `arduino_secrets.h` ke `.gitignore`

## Tim

- Capstone Project: EduAir
- Program Studi D3 Teknik Komputer
- Universitas Komputer Indonesia (UNIKOM)
- Mata Kuliah: Teknologi IoT & Pemrograman Mobile
- Dosen: Dr. Agus Mulyana, M.T.
