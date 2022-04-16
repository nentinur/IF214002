# Implementasi Data Science dalam Bisnis
- 15 April 2022
- Pemateri: Nanda Harsana Octavya

### Apa perbedaan Data Science, Data Analyst, dan Data Engineer?
Data science = berhubugan dengan machine learning, gabungan matematika, bisnis, dan ilmu komputasi
Data analyst = menganalisis data
data engineer = mengurusi penyimpanan data, sebelum data diolah oleh data analyst dan data science diolah dulu oleh data engineer

Tipe Machine Learning: 
- Supervised Learning
  Pembelajaran yang dilakukan menggunakan data fitur (idependent variable) dan data target (dependent variable). cocok untuk sudah punya label (keterangan)
  Dibagi menjadi 2:
  1. Regression:
    - Linear Regression
    - Support Vector Machine (Regression)
    - Decision Tree (Regression)
    - K-Nearest Neighbor (Regression)
  2. Classification:
    - Logistik Regression
    - Support Vector Machine (Classifier)
    - Multi-Layer Perceptron (Classifier)
    - Decision Tree (Classifier)
    - Rabdom Forest (Classifier)
    - K-Nearest Neighbor (Classifier)

- Unsupervised Learning
  Pembelajaran yang dilakukan menggunakan data fitur (independent variable) saja. cocok untuk data yang tidak punya label.
  Dibagi menjadi 2:
  1. Clustering: mengelompokkan data berdasarkan pola pada fitur
    - K-Means
    - DBSCAN
    - Gaussian Mixture Model (GMM)
  3. Dimensionality Reduction: mengurangi ukuran dimensi data dengan cara mencari fitur yang terbaik.
    - Principal Component Analyst (CPA)
    - Singular Value Decomposition (SVD)
    - Linear Discriminant Analyst (LDA)

### Data Science dapat membantu perusahaan membuat keputusan yang lebih cepat dan lebih baik
Contoh:
- Prediksi: Memprediksi perilaku konsumen berdasarkan histori penjualan
- Pengambilan Keputusan: menentukan nilai akreditasi berdasarkan data terkait performa instansi
- Rekomendasi: Rekomendasi produk dari toko online berdasarkan halaman produk yang dikunjungi calon pembeli.
- Deteksi: Mendeteksi celah kemanan website berdasarkan data yang diperoleh dari plugin keamanan.
- Klasifikasi: Membedakan produk berkualitas tinggi an produk berkualitas rendah.

### Skill yang harus dimiliki data scientist
- Statistik
- Bahasa Pemrograman
- Machine Learning
- Analytics dan Modeling
- Visualsasi data
- Wawasan bisnis

### Tahapan deployment :
- import data
- membersihkan data (data duplikast, data kosong)
- pre prosessing (tek harus dibersihkan lagi, menghapus karakter2 yg tidak dibutuhkan)
ektraksi fitur
- modelling menggunakan machine learning
- evaluasi model
- deployment misalnya mengunakan flask
