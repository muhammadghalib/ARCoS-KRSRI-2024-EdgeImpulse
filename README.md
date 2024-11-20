## 📷 Proyek Deteksi Objek dengan Edge Impulse & ESP32-CAM
Proyek ini bertujuan untuk mengembangkan sistem deteksi objek berbasis machine learning yang diterapkan pada perangkat ESP32-CAM menggunakan platform Edge Impulse. Sistem ini akan mampu mengidentifikasi objek dalam gambar secara efisien meskipun dengan perangkat keras berdaya rendah.

## 🚀 Tentang Proyek
Proyek ini bertujuan untuk mengembangkan sistem deteksi objek yang dapat mengenali dua objek utama dalam arena perlombaan KRSRI 2024, yaitu korban dan dummy. Menggunakan platform Edge Impulse untuk melatih model machine learning dan perangkat ESP32-CAM, sistem ini diharapkan dapat memberikan solusi deteksi objek yang cepat dan akurat dalam kondisi lapangan yang dinamis. Tantangan utama dalam proyek ini adalah mengidentifikasi kedua objek tersebut secara efisien, mengingat keterbatasan sumber daya pada perangkat keras yang digunakan, serta variabilitas kondisi pencahayaan dan posisi objek di arena perlombaan.

Apa yang dapat dilakukan?
- ✅ Deteksi Objek Korban dan Dummy.
- ✅ Penggunaan Platform Edge Impulse.

## 🛠️ Fitur Utama
- Deteksi Objek Akurat dengan Machine Learning
- Integrasi dengan ESP32-CAM untuk Deteksi Real-Time
- Optimasi Perangkat Keras Berdaya Rendah

## 📋 Prasyarat
**Perangkat Keras**
1. ESP32-CAM
2. Kabel jumper (Opsional - Sesuai versi ESP32-CAM)
3. Sumber Daya Listrik (baterai atau kabel USB).

**Perangkat Lunak**
1. Akun Edge Impulse – [Daftar di sini](https://www.edgeimpulse.com)
2. Arduino IDE 1.8.19.
3. Board ESP32 2.0.4.

## 📖 Panduan Penggunaan
1️⃣ **Pelatihan Model**
Pelatihan model dilakukan menggunakan platform Edge Impulse. Berikut langkah-langkahnya:
1. Kumpulkan Dataset:
    - Gunakan kamera ESP32-CAM untuk mengumpulkan gambar.
    - Pastikan dataset memiliki variasi kondisi pencahayaan, sudut, dan latar belakang untuk meningkatkan akurasi.
      ![Panduan Pengumpulan Dataset](./Documentation/images/Panduan_pengumpulan_dataset/1.1.jpg "Langkah 1.1 Pengumpulan Dataset")
    - Pastikan dataset memiliki resolusi 320 x 240, karena ESP32-CAM bekerja dengan resolusi tersebut saat pendeteksian objek.
      ![Panduan Pengumpulan Dataset](./Documentation/images/Panduan_pengumpulan_dataset/1.2.jpg "Langkah 1.2 Pengumpulan Dataset")
2. **Dashboard:**
    - Pastikan sudah daftar dan login ke Edge Impulse.
    - Buat proyek baru dan pilih Add existing data di halaman Dashboard.
      ![Panduan Edge Impulse](./Documentation/images/Panduan_edge_impulse/2.3.jpg "Langkah 2.3 Edge Impulse")
    - Pilih Upload Data dan pilih choose file dataset anda.
      ![Panduan Edge Impulse](./Documentation/images/Panduan_edge_impulse/2.4.jpg "Langkah 2.4 Edge Impulse")
3. **Data acquisition:**
    - Pilih Labeling Queue.
      ![Panduan Edge Impulse](./Documentation/images/Panduan_edge_impulse/2.5.jpg "Langkah 2.5 Edge Impulse")
    - Tandai objek pada gambar dan beri label sesuai keinginan, kemudian simpan label tersebut.
5. **Create Impulse:**
    - Jika muncul Configure your target device and application budget, pilih Espressif ESP-EYE (ESP32 240MHZ) lalu save.
      ![Panduan Edge Impulse](./Documentation/images/Panduan_edge_impulse/2.6.jpg "Langkah 2.6 Edge Impulse")
    - Pilih Image pada Add a processing block.
      ![Panduan Edge Impulse](./Documentation/images/Panduan_edge_impulse/2.7.jpg "Langkah 2.7 Edge Impulse")
    - Pilih Object Detection (images) pada Add a learning block dan simpan impulse.
      ![Panduan Edge Impulse](./Documentation/images/Panduan_edge_impulse/2.8.jpg "Langkah 2.8 Edge Impulse")
7. **Image:**
    - Pilih Grayscale untuk color depth dan Save parameters.
      ![Panduan Edge Impulse](./Documentation/images/Panduan_edge_impulse/2.9.jpg "Langkah 2.9 Edge Impulse")
    - Klik Generate Features, dan pastikan statusnya Job completed (success).
      ![Panduan Edge Impulse](./Documentation/images/Panduan_edge_impulse/2.11.jpg "Langkah 2.11 Edge Impulse")
8. **Object Detection:**
    - Atur Number of training cycles ke 60, Atur Learning rate ke 0.005, Pilih model FOMO MobileNetV2 0.35. Kemudian klik Save & Train.
      ![Panduan Edge Impulse](./Documentation/images/Panduan_edge_impulse/2.12.jpg "Langkah 2.12 Edge Impulse")
    - Pastikan statusnya Job completed (success).
9. **Deployment:**
    - Pada Search deployment options pilih Arduino library. Lalu klik Build.
      ![Panduan Edge Impulse](./Documentation/images/Panduan_edge_impulse/2.13.jpg "Langkah 2.13 Edge Impulse")

2️⃣ **Pengunggahan ke ESP32-CAM**

3️⃣ **Uji dan Implementasi**
