# Analisis Kualitas Udara Jakarta

## Project Overview
Proyek ini bertujuan menganalisis kualitas udara di Jakarta menggunakan data publik dari tahun 2010-2025. Analisis mencakup distribusi polutan, korelasi antar polutan, distribusi kategori kualitas udara, serta prediksi kategori kualitas udara dengan dukungan Model IBM Granite.

### Data Cleaning / Handling Missing Data
- Kolom PM2.5 (pm25) hanya memiliki 1.516 data valid dari total 5.538 baris (~27%).  
- Missing value pada pm25 mencapai lebih dari 4.000 baris.  
- PM2.5 baru dicatat mulai tahun 2021, sehingga baris sebelum itu memang kosong.  
- Karena PM2.5 merupakan indikator polusi udara paling berbahaya bagi kesehatan manusia (partikel halus dapat masuk ke paru-paru dan aliran darah), kolom ini sangat penting untuk analisis.  

**Solusi:**  
Baris yang tidak memiliki nilai PM2.5 dihapus agar analisis fokus pada periode setelah 2021 dengan data lebih konsisten dan representatif. Dengan begitu, model dan analisis menjadi lebih relevan terhadap kondisi nyata kualitas udara Jakarta berdasarkan polutan kritikal ini.

## Raw Dataset Link
Dataset digunakan untuk analisis dapat diakses di:  
[Air Quality Index in Jakarta 2010-2021](https://www.kaggle.com/datasets/senadu34/air-quality-index-in-jakarta-2010-2021/data)

## Insight & Findings

### Distribusi Polutan
- PM2.5 (pm25) dan PM10 (pm10) memiliki distribusi miring ke kanan (right-skewed), menunjukkan adanya outlier dan variabilitas tinggi.
- SO2, CO, O3, dan NO2 memiliki distribusi lebih simetris, menandakan konsentrasi yang relatif stabil.
- Particulate matter (PM2.5 & PM10) menunjukkan variabilitas lebih tinggi dibanding polutan gas, sehingga menjadi masalah kualitas udara yang serius.

### Rata-Rata Polutan per Stasiun
- Stasiun DKI1 (Bunderan HI) memiliki rata-rata polutan tertinggi, terutama CO dan NO2.
- Data PM2.5 masih terbatas untuk beberapa stasiun karena pengukuran baru dimulai pada 2021.

### Distribusi Kategori Kualitas Udara
- Kategori dominan: "SEDANG" (~65.8%).
- Kategori paling jarang: "SANGAT TIDAK SEHAT" (~0.2%).

### Heatmap Korelasi Polutan
- PM2.5 dan PM10 memiliki korelasi positif kuat (0.79), kemungkinan berasal dari sumber polusi yang sama.
- CO dan SO2 memiliki korelasi positif sedang dengan PM2.5 (0.38 dan 0.36), berasal dari sumber emisi berbasis pembakaran.
- O3 memiliki korelasi lemah dengan polutan lainnya, pembentukan ozon lebih dipengaruhi oleh proses atmosferik.

### Kinerja Model Kualitas Udara
- Accuracy: 0.996  
- Precision: 0.997  
- Recall: 0.996  
- F1-score: 0.996  
- Model XGBoost tersimpan di file `air_quality_classifier.joblib` dan mampu memprediksi kategori kualitas udara dengan sangat akurat.

## AI Support Explanation
AI (IBM Granite) digunakan untuk:  
- Membantu eksplorasi data dan identifikasi pola tersembunyi.  
- Memberikan insight tambahan berdasarkan hasil analisis statistik dan visualisasi.  
- Merumuskan rekomendasi berbasis data secara otomatis dan logis.  

Penggunaan AI mempercepat analisis, memperkaya insight, dan memastikan rekomendasi lebih relevan dan actionable.

## Rekomendasi
- Tingkatkan pengawasan dan penegakan regulasi emisi kendaraan bermotor.  
- Dorong penggunaan transportasi umum dan kendaraan ramah lingkungan.  
- Lakukan penghijauan di area dengan polusi tinggi.  
- Edukasi masyarakat tentang dampak polusi udara dan cara pencegahannya.  
- Monitoring kualitas udara secara real-time dan transparan kepada publik.

## Author
Sadinal Mufti
