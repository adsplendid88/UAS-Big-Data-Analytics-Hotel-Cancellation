# 📘 Analisis Big Data dengan Metode Klasifikasi  
## Prediksi Pembatalan Hotel & Deteksi Potensi Fraud  

**Nama:** Adina Connie  
**NIM:** 825230062  
**Program Studi:** Sistem Informasi  
**Mata Kuliah:** Big Data Analytics  

---

## 📌 Pendahuluan  

Pembatalan pemesanan hotel merupakan permasalahan penting dalam industri perhotelan karena dapat menyebabkan kerugian pendapatan serta ketidakefisienan operasional. Oleh karena itu, diperlukan suatu pendekatan analitik untuk memprediksi kemungkinan pembatalan pemesanan dan mengidentifikasi pola yang berpotensi mengindikasikan kecurangan (fraud).

Pada proyek ini digunakan pendekatan **Machine Learning** dengan metode klasifikasi untuk memprediksi status pembatalan pemesanan hotel. Tiga algoritma yang digunakan adalah **Random Forest**, **Logistic Regression**, dan **XGBoost**. Evaluasi performa model dilakukan menggunakan metrik akurasi, presisi, recall, F1-score, serta AUC-ROC.

---

## 🎯 Tujuan Penelitian  

1. Memprediksi pembatalan pemesanan hotel menggunakan algoritma machine learning.  
2. Membandingkan performa beberapa model klasifikasi.  
3. Mengidentifikasi fitur-fitur yang paling berpengaruh terhadap pembatalan.  
4. Mendeteksi indikator potensi kecurangan berdasarkan pola pembatalan.  
5. Memberikan rekomendasi strategis bagi manajemen hotel.  

---

## 📁 Struktur Repository  

UAS-Big-Data-Analytics-Hotel-Cancellation
├── data/
│ └── dataset.csv
├── images/
│ ├── confusion_matrix_rf.png
│ ├── confusion_matrix_lr.png
│ ├── confusion_matrix_xgb.png
│ ├── roc_curve.png
│ └── feature_importance.png
├── README.md
└── UAS_825230062_Adina.pdf 

---

## 📊 Dataset  

Dataset yang digunakan berisi data pemesanan hotel dengan berbagai atribut, antara lain:

- `lead_time`  
- `arrival_date`  
- `stays_in_weekend_nights`  
- `stays_in_week_nights`  
- `adults`, `children`, `babies`  
- `meal`, `country`  
- `market_segment`, `distribution_channel`  
- `deposit_type`  
- `booking_changes`  
- `adr` (Average Daily Rate)  
- `customer_type`  
- `is_canceled` (target)

Variabel `is_canceled` digunakan sebagai label klasifikasi, di mana:
- `1` = pemesanan dibatalkan  
- `0` = pemesanan tidak dibatalkan  

---

## 🧹 Data Preprocessing  

Tahapan prapemrosesan data meliputi:

- Mengisi nilai kosong pada kolom `agent` dan `company` dengan nilai `0`.  
- Encoding variabel kategorikal menggunakan **Label Encoder**.  
- Normalisasi fitur numerik menggunakan **StandardScaler**.  
- Pembagian data menjadi **80% data latih** dan **20% data uji**.  

---

## 🤖 Model Machine Learning  

Tiga algoritma klasifikasi yang digunakan:

### 1. Random Forest  
Model ensemble berbasis pohon keputusan yang mampu menangkap hubungan non-linear antar fitur.

### 2. Logistic Regression  
Model linear yang digunakan sebagai baseline untuk klasifikasi biner.

### 3. XGBoost  
Model boosting yang menggabungkan beberapa weak learner untuk menghasilkan performa prediksi yang tinggi.

---

## 📈 Evaluasi Model  

Evaluasi dilakukan menggunakan confusion matrix dan metrik klasifikasi berikut:

| Model | Accuracy | Precision | Recall | F1-Score | AUC-ROC |
|------|---------|----------|--------|---------|--------|
| Random Forest | 0.8978 | 0.8917 | 0.8285 | 0.8590 | 0.9624 |
| Logistic Regression | 0.7953 | 0.8133 | 0.5907 | 0.6844 | 0.8685 |
| XGBoost | 0.8851 | 0.8635 | 0.8245 | 0.8435 | 0.9559 |

**Kesimpulan Evaluasi:**  
Random Forest memberikan performa terbaik dibandingkan dua model lainnya, terutama pada nilai AUC-ROC.

---

## 📉 Visualisasi  

Beberapa visualisasi yang digunakan dalam analisis:

- Confusion Matrix untuk setiap model  
- Kurva ROC  
- Feature Importance (Random Forest)  

Contoh penggunaan gambar pada README:

```md
![Confusion Matrix Random Forest](images/confusion_matrix_rf.png)
🔍 Analisis Potensi Kecurangan (Fraud Detection)

Analisis tambahan dilakukan untuk mendeteksi potensi kecurangan berdasarkan pola pembatalan:

Pembatalan tanpa deposit
Pemesanan dengan deposit_type = No Deposit memiliki risiko pembatalan yang lebih tinggi.

Perubahan pemesanan yang tinggi
Pelanggan dengan banyak perubahan pemesanan sebelum pembatalan berpotensi menunjukkan perilaku mencurigakan.

Rasio pembatalan pelanggan tinggi
Analisis ini tidak dapat dilakukan secara optimal karena dataset tidak menyediakan kolom email pelanggan.

🧠 Kesimpulan

Machine Learning efektif digunakan untuk memprediksi pembatalan pemesanan hotel.

Random Forest merupakan model dengan performa terbaik.

Fitur seperti lead_time, adr, dan deposit_type sangat berpengaruh terhadap pembatalan.

Pola pembatalan tertentu dapat dijadikan indikator awal potensi fraud.

Keterbatasan data identitas pelanggan menjadi tantangan dalam analisis lanjutan.

📚 Daftar Pustaka

Referensi yang digunakan mengacu pada jurnal dan penelitian terkait prediksi pembatalan hotel dan machine learning, sebagaimana tercantum pada dokumen laporan UAS.

