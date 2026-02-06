# Proyek Akhir: Menyelesaikan Permasalahan Perusahaan Edutech

## Business Understanding

Jaya Jaya Maju merupakan sebuah perusahaan yang mempunyai jumlah tenaga kerja lebih dari 1.000 karyawan. Sebagai organisasi berskala besar, aset terbesar perusahaan bukanlah infrastruktur fisik, melainkan sumber daya manusia yang dimilikinya.

Namun, saat ini perusahaan menghadapi ancaman serius terhadap keberlanjutan operasional, yaitu tingginya tingkat attrition rate (rasio karyawan yang keluar/resign). Tingginya perputaran karyawan ini menjadi tantangan strategis karena tidak hanya berdampak pada stabilitas tim, tetapi juga membebani efisiensi biaya perusahaan. Manajemen menyadari bahwa untuk tetap kompetitif, mereka harus mengubah pendekatan pengelolaan SDM dari reaktif menjadi proaktif berbasis data.

### Permasalahan Bisnis

Tingginya Tingkat Resign:
Perusahaan mengalami lonjakan rasio karyawan yang mengundurkan diri melebihi batas toleransi wajar industri. Kondisi ini menyebabkan dampak terhadap perusahaan berupa:

- Peningkatan Biaya Operasional: Membengkaknya biaya untuk proses rekrutmen, onboarding, dan pelatihan karyawan baru.
- Penurunan Produktivitas: Terhambatnya alur kerja tim akibat kekosongan posisi dan hilangnya pengetahuan akan perusahaan yang dibawa oleh karyawan senior yang keluar.

Faktor Penyebab Resign Tidak Diketahui:
Perusahaan memiliki data karyawan yang lengkap, namun belum dimanfaatkan untuk menganalisis alasan di balik keputusan resign. Akibatnya, manajemen tidak memiliki landasan yang kuat untuk merancang kebijakan yang tepat sasaran, sehingga upaya pencegahan karyawan keluar menjadi tidak optimal.

### Cakupan Proyek

Data Understanding & Preprocessing: Membersihkan data dari missing values, duplikasi, dan anomali, serta menyiapkan data untuk analisis.

Exploratory Data Analysis (EDA): Menganalisis distribusi dan mencari korelasi antar variabel terhadap keputusan resign.

Machine Learning Modeling: Membangun model prediksi (Random Forest Classifier) untuk memprediksi potensi resign dan mengidentifikasi faktor terpenting.

Business Dashboard: Membuat visualisasi menggunakan Tableau untuk memantau performa karyawan dan faktor risiko secara real-time.

### Persiapan

Dataset yang digunakan adalah data internal HR perusahaan yang mempunyai berbagai informasi.
Nama file dataset: employee_data.csv

Setup environment:

```
# Membuat virtual environment (Opsional)
python -m venv venv
source venv/bin/activate  # Untuk Mac/Linux
venv\Scripts\activate     # Untuk Windows

# Menginstall library yang dibutuhkan
pip install -r requirements.txt
```

## Business Dashboard

Dashboard ini terdiri dari 4 komponen visual utama:

Total Karyawan: Menampilkan total tenaga kerja saat ini.

Chart Faktor Penyebab Resign: Grafik batang horizontal yang mengurutkan fitur berdasarkan Feature Importance. Grafik ini memvalidasi bahwa Stock Option Level dan Job Satisfaction adalah dua faktor terkuat keputusan resign.

Analisis Pengaruh Saham (Stock Option): Grafik stacked bar yang menunjukkan korelasi negatif antara kepemilikan saham dan tingkat resign. Terlihat jelas bahwa karyawan di Level 0 (Tanpa Saham) memiliki proporsi resign (warna oranye) terbesar dibandingkan level lainnya.

Analisis Pengaruh Kepuasan Kerja: Grafik stacked bar ini menunjukkan distribusi karyawan berdasarkan tingkat kepuasan kerja (skala 1-4). Terlihat adanya korelasi negatif yang kuat, di mana karyawan pada tingkat kepuasan terendah (Level 1) memiliki proporsi resign yang paling tinggi.

https://public.tableau.com/views/M891D5Y1083-Dashboard/Dashboard1?:language=en-US&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link

## Conclusion

- Performa Model: Model mencapai akurasi sebesar 83.49%. Artinya, secara umum model sudah cukup baik membedakan antara karyawan yang bertahan dan yang akan keluar. Namun kemampuan mendeteksi yang resign masih terbatas karena hanya mendapatkan Recall 33%.

- Faktor Utama Pemicu Attrition Berdasarkan analisis Feature Importance, keputusan karyawan untuk resign tidak didorong oleh satu faktor tunggal, melainkan kombinasi faktor finansial dan psikologis.
  **Stock Option Level (Kepemilikan Saham)** teridentifikasi sebagai indikator paling dominan. Karyawan yang tidak memiliki rasa kepemilikan (Level 0) memiliki kecenderungan keluar yang jauh lebih tinggi.
  **Job Satisfaction & Environment Satisfaction** menjadi faktor krusial berikutnya, di mana pengaruhnya terbukti lebih signifikan dibandingkan besaran gaji bulanan (MonthlyIncome). Ini mengindikasikan bahwa karyawan Jaya Jaya Maju lebih dipengaruhi oleh lingkungan dan kenyamanan kerja daripada sekadar gaji pokok.

### Rekomendasi Action Items (Optional)

1. **Evaluasi Benefit Saham**: Berikan opsi saham tidak hanya untuk eksekutif, tapi juga karyawan level menengah berprestasi untuk meningkatkan rasa memiliki.

2. **Perbaiki Lingkungan Kerja**: Lakukan survei rutin khusus fasilitas dan kenyamanan kerja. Tindak lanjuti keluhan teknis.

3. **Pelatihan Manajer**: Latih manajer untuk lebih suportif. Hubungan buruk atau stagnan dengan atasan adalah pemicu resign terbesar ke-4
