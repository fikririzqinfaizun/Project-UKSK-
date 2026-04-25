# Sistem Monitoring Suhu Berbasis IoT Menggunakan ESP32

Project ini merupakan simulasi sistem monitoring suhu berbasis IoT menggunakan ESP32, sensor DHT22, LCD I2C, dan relay. Sistem membaca nilai suhu, kemudian menampilkan hasilnya pada LCD dalam bentuk status kondisi lingkungan.

## Komponen yang Digunakan

- ESP32 DevKit
- Sensor DHT22
- LCD I2C 16x2
- Relay Module
- Kabel jumper
- Wokwi sebagai simulator

## Rangkaian Pin

### DHT22 ke ESP32

| DHT22 | ESP32 |
|---|---|
| VCC | 3V3 |
| SDA / DATA | GPIO 15 |
| NC | Tidak disambungkan |
| GND | GND |

### LCD I2C ke ESP32

| LCD I2C | ESP32 |
|---|---|
| VCC | 5V |
| GND | GND |
| SDA | GPIO 21 |
| SCL | GPIO 22 |

### Relay ke ESP32

| Relay | ESP32 |
|---|---|
| VCC | 5V |
| GND | GND |
| IN | GPIO 18 |

## Alur Kerja Sistem

1. ESP32 mulai menjalankan program.
2. Sensor DHT22 membaca data suhu dan kelembaban.
3. Data suhu dikirim ke ESP32 melalui pin GPIO 15.
4. ESP32 memproses nilai suhu.
5. LCD menampilkan nilai suhu dan status kondisi.
6. Jika suhu kurang dari 25°C, status menjadi **LEMBAB**.
7. Jika suhu berada pada 25°C sampai 30°C, status menjadi **NORMAL**.
8. Jika suhu lebih dari 30°C, status menjadi **PANAS**.
9. Ketika status **PANAS**, relay akan aktif.
10. Sistem mengulang pembacaan suhu setiap beberapa detik.

## Kategori Kondisi Suhu

| Suhu | Status |
|---|---|
| < 25°C | LEMBAB |
| 25°C - 30°C | NORMAL |
| > 30°C | PANAS |

## Cara Menjalankan di Wokwi

1. Buka website Wokwi.
2. Buat project baru menggunakan ESP32.
3. Tambahkan komponen DHT22, LCD I2C, dan relay.
4. Hubungkan pin sesuai tabel rangkaian.
5. Masukkan kode program ke file `sketch.ino`.
6. Tambahkan library yang dibutuhkan.
7. Klik tombol **Start Simulation**.
8. Ubah nilai suhu pada sensor DHT22 untuk melihat perubahan status.

## Library yang Digunakan

Tambahkan library berikut pada file `libraries.txt`:

## Fitur Sistem
Membaca suhu menggunakan DHT22
Menampilkan suhu pada LCD I2C
Menampilkan status LEMBAB, NORMAL, atau PANAS
Mengaktifkan relay saat suhu panas
Dapat dijalankan melalui simulasi Wokwi

##Kesimpulan
Sistem ini dapat digunakan sebagai simulasi monitoring suhu berbasis ESP32. Dengan bantuan sensor DHT22, ESP32 dapat membaca suhu lingkungan dan menentukan kondisi berdasarkan batas suhu yang telah ditentukan.

Link Wokwi :
https://wokwi.com/projects/462242158213689345

```txt
DHT sensor library
LiquidCrystal I2C
