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
  - Hasil dari ukuran pemusatan yang saya lakukan pada kolom Pendapatan_Tahunan_Miliar_IDR :
    1. Mean : 31.8831846153846
    2. Median : 31.303
    3. Modus : 1.87
  - *Interpretasi:* Jelaskan apa arti dari nilai-nilai tersebut terkait dengan data Anda.
  - Berdasarkan hasil statistik deskriptif pada kolom Pendapatan_Tahunan_Miliar_IDR, diperoleh nilai mean sebesar 31,88 miliar rupiah, yang menunjukkan bahwa rata rata pendapatan tahunan startup SaaS dalam dataset berada pada kisaran tersebut. Nilai median sebesar 31,30 miliar rupiah mengindikasikan bahwa setengah dari startup memiliki pendapatan di bawah nilai tersebut dan setengah lainnya di atasnya, serta menunjukkan bahwa sebaran data relatif cukup seimbang karena nilainya mendekati mean. Namun, nilai modus sebesar 1,87 miliar rupiah menunjukkan bahwa pendapatan yang paling sering muncul justru berada pada tingkat yang relatif rendah, sehingga dapat disimpulkan bahwa meskipun rata-rata pendapatan startup cukup tinggi, sebagian besar startup dalam dataset masih berada pada kategori pendapatan rendah, sementara beberapa startup dengan pendapatan sangat tinggi berkontribusi terhadap peningkatan nilai rata-rata secara keseluruhan.
- **Ukuran Sebaran (Standar Deviasi, Range, Kuartil):**
  - *Tabel atau ringkasan...*
  - Hasil dari ukuran pemusatan yang saya lakukan pada kolom Pendapatan_Tahunan_Miliar_IDR :
    1. Standar Deviasi : 19.7855620465392
    2. Range : 1 - 66.89 = 65.89
    3. Kuartil : Min.= 1.00, Q1= 14.31, Median/Q2= 31.30, Mean= 31.88, Q3= 49.04, Max.= 66.89
  - *Interpretasi:* Jelaskan seberapa menyebar data Anda berdasarkan nilai-nilai ini.
  - Pendapatan tahunan pada kolom Pendapatan_Tahunan_Miliar_IDR memiliki sebaran data yang cukup lebar. Hal ini dapat dilihat dari nilai standar deviasi sebesar 19,79 miliar rupiah, yang menunjukkan bahwa data pendapatan tiap startup cukup bervariasi dan tidak terkumpul di sekitar nilai rata-rata saja. Selain itu, range sebesar 65,89 miliar rupiah (dari 1,00 hingga 66,89 miliar rupiah) menandakan adanya perbedaan yang cukup jauh antara startup dengan pendapatan terendah dan tertinggi. Berdasarkan nilai kuartil, sebagian startup memiliki pendapatan di bawah 14,31 miliar rupiah, sementara sebagian lainnya mencapai lebih dari 49,04 miliar rupiah, sehingga dapat disimpulkan bahwa pendapatan tahunan startup SaaS dalam dataset ini menyebar cukup luas dan tidak merata.
- **Visualisasi (Histogram/Boxplot):**
  - *Sematkan gambar plot dari folder /results...*
    ![alt text](https://github.com/triadanyana-lgtm/staprob-project/blob/main/results/histogram_Pendapatan_Tahunan_Miliar_IDR.png)
  - *Interpretasi:* Jelaskan wawasan apa yang Anda dapatkan dari bentuk distribusi data.
  - Berdasarkan histogram Pendapatan_Tahunan_Miliar_IDR, dapat dilihat bahwa data tersebar cukup luas dari nilai rendah hingga tinggi, dengan sebagian besar pendapatan berada di kisaran menengah. Garis putus-putus merah yang menunjukkan nilai mean sekitar 31,88 miliar rupiah berada di tengah distribusi, yang menandakan bahwa rata-rata pendapatan cukup mewakili pusat data. Namun, masih terlihat adanya nilai pendapatan yang relatif rendah dan cukup tinggi, sehingga distribusi data tidak sepenuhnya terkonsentrasi pada satu titik. Bentuk distribusi ini menunjukkan bahwa dalam dataset terdapat perbedaan skala pendapatan antar startup, di mana beberapa startup memiliki pendapatan jauh lebih tinggi dibandingkan yang lain, sementara sebagian besar berada di sekitar nilai rata-rata.

### 5.2. Uji Normalitas
- **Hasil Uji Shapiro-Wilk:**
  - *Nilai p-value...*
    p-value = 1.497e-14
  - *Interpretasi:* Apakah data Anda terdistribusi normal berdasarkan hasil uji? Apa implikasinya?
  - Berdasarkan hasil uji normalitas Shapiro–Wilk pada variabel Pendapatan_Tahunan_Miliar_IDR, diperoleh nilai p-value sebesar 1,497 × 10⁻¹⁴, yang jauh lebih kecil dari tingkat signifikansi 0,05. Hal ini menunjukkan bahwa data tidak terdistribusi normal, sehingga hipotesis nol yang menyatakan data berdistribusi normal dapat ditolak. Implikasinya, analisis lanjutan yang mengasumsikan normalitas data, seperti uji parametrik tertentu, perlu dilakukan dengan hati-hati atau digantikan dengan metode alternatif, misalnya transformasi data atau penggunaan metode non-parametrik agar hasil analisis lebih valid.
- **Plot Q-Q:**
  - *Sematkan gambar plot dari folder /results...*
    ![alt text](https://github.com/triadanyana-lgtm/staprob-project/blob/main/results/qqplot_Pendapatan_Tahunan_Miliar_IDR.png)
  - *Interpretasi:* Apakah titik-titik data mengikuti garis lurus? Apa artinya?
  - Berdasarkan Q–Q plot Pendapatan_Tahunan_Miliar_IDR, titik-titik data tidak sepenuhnya mengikuti garis lurus, terutama pada bagian awal dan akhir grafik, di mana terlihat penyimpangan yang cukup jelas dari garis diagonal. Hal ini menunjukkan bahwa distribusi data tidak mengikuti distribusi normal, dengan adanya perbedaan pada ekor distribusi (tail) yang menandakan ketidaksimetrisan atau kemungkinan adanya nilai ekstrem. Artinya, asumsi normalitas pada data pendapatan tahunan tidak terpenuhi, sehingga hasil ini memperkuat temuan dari uji Shapiro–Wilk bahwa data tidak berdistribusi normal.

### 5.3. Analisis Korelasi
- **Nilai Koefisien Korelasi:**
  - *Nilai r...* nilai r = 0.996
  - *Interpretasi:* Seberapa kuat dan apa arah hubungan antara dua variabel yang Anda uji? (misalnya, korelasi positif kuat, negatif lemah, atau tidak ada korelasi).
  - Berdasarkan hasil uji korelasi yang dilakukan, diperoleh bahwa terdapat hubungan linear positif yang kuat dan signifikan secara statistik antara Pendapatan Tahunan (Miliar IDR) dan Biaya Akuisisi Pelanggan (Juta IDR) dengan nilai p-value < 0,05 dan korelasi 0,996. Hal ini menunjukkan bahwa peningkatan pendapatan tahunan perusahaan cenderung diikuti oleh peningkatan biaya yang dikeluarkan untuk mengakuisisi pelanggan.
- **Visualisasi (Scatter Plot):**
  - *Sematkan gambar plot dari folder /results...*
    ![alt text](https://github.com/triadanyana-lgtm/staprob-project/blob/main/results/scatterplot_Pendapatan_Tahunan_Miliar_IDR_vs_Biaya_Akuisisi_Pelanggan_Juta_IDR.png)
  - *Interpretasi:* Apakah pola pada scatter plot mendukung hasil koefisien korelasi?
  - Ya, pola pada scatter plot mendukung hasil koefisien korelasi. Titik-titik data membentuk pola naik dari kiri ke kanan dan mengikuti garis tren linear yang ditunjukkan oleh garis merah, sehingga menunjukkan adanya hubungan positif antara Pendapatan_Tahunan_Miliar_IDR dan Biaya_Akuisisi_Pelanggan_Juta_IDR. Artinya, semakin tinggi pendapatan tahunan startup, cenderung semakin tinggi pula biaya akuisisi pelanggan yang dikeluarkan. Pola yang relatif rapat di sekitar garis tren juga mengindikasikan bahwa hubungan antar kedua variabel tersebut cukup kuat dan konsisten, sehingga hasil visual ini sejalan dengan nilai koefisien korelasi yang menunjukkan hubungan positif.

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
