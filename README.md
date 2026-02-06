# Proyek Akhir: Menyelesaikan Permasalahan Perusahaan Edutech

## Business Understanding

Jaya Jaya Maju adalah sebuah perusahaan yang memiliki lebih dari 1000 karyawan. Namun, perusahaan ini sedang menghadapi tantangan besar dalam pengelolaan sumber daya manusia, yaitu tingginya tingkat attrition rate (rasio karyawan yang keluar/resign).

### Permasalahan Bisnis

Tingginya Tingkat Resign

Faktor Penyebab Resign Tidak Diketahui

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
- Berdasarkan analisis Feature Importance yang dihasilkan oleh model Machine Learning, terlihat bahwa keputusan karyawan untuk melakukan resign tidak didorong oleh 1 faktor saja, melainkan kombinasi berbagai faktor. Dimana yang paling signifikan menunjukkan bahwa StockOptionLevel (Tingkat Kepemilikan Saham) merupakan indikator utama dengan bobot pengaruh tertinggi. Hal ini mengindikasikan bahwa karyawan yang tidak memiliki insentif jangka panjang atau rasa kepemilikan terhadap perusahaan cenderung lebih mudah untuk keluar. Faktor krusial berikutnya diikuti oleh aspek psikologis dan lingkungan, yaitu JobSatisfaction dan EnvironmentSatisfaction, yang dampaknya terbukti lebih besar dibandingkan besaran gaji bulanan (MonthlyIncome).

### Rekomendasi Action Items (Optional)

1. **Evaluasi Benefit Saham**: Berikan opsi saham tidak hanya untuk eksekutif, tapi juga karyawan level menengah berprestasi untuk meningkatkan rasa memiliki.

2. **Perbaiki Lingkungan Kerja**: Lakukan survei rutin khusus fasilitas dan kenyamanan kerja. Tindak lanjuti keluhan teknis.

3. **Pelatihan Manajer**: Latih manajer untuk lebih suportif. Hubungan buruk atau stagnan dengan atasan adalah pemicu resign terbesar ke-4
