# ARIS-HENDRADIAN-UTAMA-125490009-TUGAS-UAS-INSTRUMENTASI-ITERA-2025
Perancangan Sistem Instrumentasi Multi-Sensor untuk Monitoring dan Kontrol Tangki Otomatis Menggunakan Arduino

Proyek ini merupakan implementasi sistem instrumentasi berbasis Arduino Uno untuk melakukan monitoring dan kontrol otomatis pada sebuah tangki fluida. Sistem menggunakan tiga sensor utama (suhu, level, tekanan) dan beberapa aktuator untuk mengendalikan proses secara real time. Simulasi rangkaian dilakukan menggunakan Tinkercad Circuits, sementara dokumentasi sistem dibuat dalam bentuk Diagram Blok dan P&ID (Piping & Instrumentation Diagram) sesuai standar ISA.

📌 Fitur Utama Sistem

Monitoring suhu, level, dan tekanan secara simultan.

Kontrol level menggunakan metode closed-loop (umpan balik).

Alarm suhu dan tekanan menggunakan metode open-loop.

Pengendalian pompa otomatis berdasarkan batas level.

Sistem keamanan melalui buzzer & LED alarm.

Visualisasi data melalui LCD 16x2 I2C.

Dokumentasi lengkap menggunakan P&ID standar industri.

🧩 Arsitektur Sistem
Input (Sensor)

TT-101 (TMP36) – membaca suhu cairan.

LT-102 (HC-SR04) – membaca level permukaan cairan.

PT-103 (Potensiometer) – simulasi tekanan sistem.

Controller

UC-201 (Arduino Uno) – memproses semua data sensor dan menjalankan logika kontrol.

Output (Actuator)

P-101 (Pompa Motor DC) – mengisi tangki secara otomatis.

CV-101 (Servo / Control Valve) – membuka/menutup untuk mengatur tekanan.

AH-101 (Buzzer + LED) – alarm suhu dan tekanan tinggi.

UI-201 (LCD 16x2 I2C) – menampilkan nilai sensor secara real time.

📡 Diagram Blok Sistem

Aliran kerja sistem secara umum:

[Sensor] → [Arduino Controller] → [Actuator + Display]
TT-101    →                       → Pompa (P-101)
LT-102    →                       → Valve (CV-101)
PT-103    →                       → Alarm (AH-101)
                              → LCD UI-201

🛠️ Daftar Komponen

Arduino Uno

TMP36 Temperature Sensor

Ultrasonic HC-SR04

Potentiometer (tekanan simulasi)

Motor DC + Driver

Servo Motor

Buzzer + LED Merah

LCD 16x2 I2C

Breadboard & Jumper

Sumber daya 5V

🧪 Simulasi di Tinkercad

Rangkaian dibuat di Tinkercad Circuits untuk:

Melakukan uji koneksi sensor.

Menguji respons aktuator.

Menjalankan kode Arduino secara virtual.

Simulasi memudahkan pengujian logika sebelum dibuat versi fisiknya.

💻 Kode Pemrograman (Arduino)

Kode lengkap meliputi:

Pembacaan sensor suhu, level, dan tekanan.

Pengendalian motor pompa.

Pengaturan servo sebagai control valve.

Aktivasi buzzer/LED untuk alarm.

Tampilan LCD untuk monitoring nilai sensor.

Kode dapat dilihat di file: /src/main.ino

📘 Diagram P&ID (Standar ISA)

P&ID menunjukkan:

Letak sensor (TT-101, LT-102, PT-103)

Jalur aliran fluida

Aktuator seperti pompa dan katup

Hubungan sinyal antara perangkat dan Arduino

Dokumen ini mengikuti simbol ISA sehingga dapat digunakan dalam lingkungan industri.

⚠️ Analisis Kestabilan Sistem
Potensi masalah sensor:
Sensor	Error	Dampak	Risiko	Mitigasi
Level	Terbaca rendah	Pompa hidup terus	Tangki meluap	Level switch cadangan
Suhu	Terbaca rendah	Alarm tidak aktif	Overheat	Redundant sensor
Tekanan	Terbaca tinggi	Valve terbuka	Kehilangan fluida	Filter sinyal
📝 Kesimpulan

Sistem berhasil mengintegrasikan tiga sensor dengan aktuator dalam satu kontrol otomatis.

Kontrol level menggunakan closed-loop memberi hasil stabil.

P&ID dan diagram blok membantu visualisasi sistem industri secara profesional.

Sistem dapat dikembangkan dengan HMI dan data logging.

🧭 Saran Pengembangan

Menambah sensor redundan untuk kondisi kritis.

Menggunakan antarmuka HMI grafis.

Menyimpan data monitoring dalam SD card atau database.

Mencoba implementasi hardware nyata setelah simulasi.

📄 Lisensi

Proyek ini bebas digunakan untuk pembelajaran, akademik, maupun pengembangan lebih lanjut.
