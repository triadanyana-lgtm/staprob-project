# Tugas Analisis Statistik: Deskriptif, Korelasi, dan Regresi

## 1. Informasi Penyusun

- **Nama:** I KOMANG TRI ADNYANA
- **NIM:** 2515091039
- **Program Studi:** SISTEM INFORMASI
- **Mata Kuliah:** Statistika dan Probabilitas

---

## 2. Deskripsi Proyek

Pada bagian ini, jelaskan secara singkat dataset yang Anda gunakan. Apa saja variabel di dalamnya? Apa tujuan dari analisis yang Anda lakukan?

> Dataset yang digunakan adalah data data_startup_saas.csv yang berisi informasi tentang startup SaaS dan digunakan untuk analisis bisnis, seperti membandingkan pendapatan tahunan, biaya langganan, nilai pelanggan, serta tingkat churn berdasarkan kategori layanan. Variabel kunci dalam dataset ini meliputi Pendapatan_Tahunan_Miliar_IDR, Biaya_Langganan_Juta_IDR.Jadi disini saya hanya menggunakan 2 varaiable untuk melakukan proyek ini.
Tujuan dari proyek ini adalah untuk memahami karakteristik data melalui statistik deskriptif, menguji hubungan antara Pendapatan_Tahunan_Miliar_IDR dan Biaya_Langganan_Juta_IDR melalui analisis korelasi, serta memprediksi Biaya_Langganan_Juta_IDR sebagai variabel target menggunakan Pendapatan_Tahunan_Miliar_IDR sebagai variabel prediktor melalui analisis regresi.

---

## 3. Struktur Proyek

Proyek ini diorganisir ke dalam beberapa folder:
- `/data`: Berisi dataset mentah yang digunakan untuk analisis.
- `/scripts`: Berisi semua skrip R yang digunakan dalam analisis, diurutkan berdasarkan alur kerja.
- `/results`: Berisi output dari analisis, seperti plot, gambar, atau tabel ringkasan.

---

## 4. Cara Menjalankan Analisis

Untuk mereproduksi hasil analisis ini, ikuti langkah-langkah berikut:
1. Pastikan Anda memiliki R dan RStudio terinstal.
2. Buka proyek R ini di RStudio.
3. Instal paket yang diperlukan dengan menjalankan perintah berikut di konsol R:
   ```R
   # install.packages(c("tidyverse", "corrplot", "knitr"))
   ```
4. Jalankan skrip di dalam folder `/scripts` secara berurutan, mulai dari `01_data_preparation.R` hingga `05_analisis_regresi.R`.

---

## 5. Hasil dan Interpretasi

Di bagian ini, mahasiswa diharapkan untuk menyajikan dan menginterpretasikan hasil dari setiap tahap analisis.

### 5.1. Statistik Deskriptif
- **Ukuran Pemusatan (Mean, Median, Modus):**
  - *Tabel atau ringkasan...*
    Hasil dari ukuran pemusatan yang saya lakukan pada kolom Pendapatan_Tahunan_Miliar_IDR :
    Mean : 31.8831846153846
    Median : 31.303
    Modus : 1.87
  - *Interpretasi:* Jelaskan apa arti dari nilai-nilai tersebut terkait dengan data Anda.
    Berdasarkan hasil statistik deskriptif pada kolom Pendapatan_Tahunan_Miliar_IDR, diperoleh nilai mean sebesar 31,88 miliar rupiah, yang menunjukkan bahwa rata rata pendapatan tahunan startup SaaS dalam dataset berada pada kisaran tersebut. Nilai median sebesar 31,30 miliar rupiah mengindikasikan bahwa setengah dari startup memiliki pendapatan di bawah nilai tersebut dan setengah lainnya di atasnya, serta menunjukkan bahwa sebaran data relatif cukup seimbang karena nilainya mendekati mean. Namun, nilai modus sebesar 1,87 miliar rupiah menunjukkan bahwa pendapatan yang paling sering muncul justru berada pada tingkat yang relatif rendah, sehingga dapat disimpulkan bahwa meskipun rata-rata pendapatan startup cukup tinggi, sebagian besar startup dalam dataset masih berada pada kategori pendapatan rendah, sementara beberapa startup dengan pendapatan sangat tinggi berkontribusi terhadap peningkatan nilai rata-rata secara keseluruhan.
- **Ukuran Sebaran (Standar Deviasi, Range, Kuartil):**
  - *Tabel atau ringkasan...*
  - Hasil dari ukuran pemusatan yang saya lakukan pada kolom Pendapatan_Tahunan_Miliar_IDR :
  - Standar Deviasi : 
  - *Interpretasi:* Jelaskan seberapa menyebar data Anda berdasarkan nilai-nilai ini.
- **Visualisasi (Histogram/Boxplot):**
  - *Sematkan gambar plot dari folder /results...*
  - *Interpretasi:* Jelaskan wawasan apa yang Anda dapatkan dari bentuk distribusi data.

### 5.2. Uji Normalitas
- **Hasil Uji Shapiro-Wilk:**
  - *Nilai p-value...*
  - *Interpretasi:* Apakah data Anda terdistribusi normal berdasarkan hasil uji? Apa implikasinya?
- **Plot Q-Q:**
  - *Sematkan gambar plot dari folder /results...*
  - *Interpretasi:* Apakah titik-titik data mengikuti garis lurus? Apa artinya?

### 5.3. Analisis Korelasi
- **Nilai Koefisien Korelasi:**
  - *Nilai r...*
  - *Interpretasi:* Seberapa kuat dan apa arah hubungan antara dua variabel yang Anda uji? (misalnya, korelasi positif kuat, negatif lemah, atau tidak ada korelasi).
- **Visualisasi (Scatter Plot):**
  - *Sematkan gambar plot dari folder /results...*
  - *Interpretasi:* Apakah pola pada scatter plot mendukung hasil koefisien korelasi?

### 5.4. Analisis Regresi
- **Model Regresi:**
  - *Persamaan regresi: Y = b0 + b1*X*
  - *Interpretasi:* Jelaskan arti dari koefisien intercept (b0) dan slope (b1) dalam konteks data Anda.
- **Evaluasi Model (R-squared):**
  - *Nilai R-squared...*
  - *Interpretasi:* Berapa persen variasi dari variabel dependen yang dapat dijelaskan oleh model regresi Anda?
- **Visualisasi (Garis Regresi pada Scatter Plot):**
  - *Sematkan gambar plot dari folder /results...*
  - *Interpretasi:* Jelaskan bagaimana garis regresi merepresentasikan hubungan antara variabel.

---

## 6. Kesimpulan

Rangkum temuan utama dari analisis Anda dalam beberapa kalimat. Apa wawasan paling penting yang Anda peroleh?
