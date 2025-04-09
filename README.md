# capstone2
# 🗽 NYC TLC Trip Record Analysis

## 📌 Overview
Proyek ini bertujuan untuk menganalisis data perjalanan taksi di Kota New York berdasarkan dataset dari NYC Taxi & Limousine Commission (TLC). Dengan tingginya volume perjalanan harian di kota ini, analisis ini ditujukan untuk menggali insight yang relevan guna meningkatkan kinerja operasional dan pendapatan perusahaan taksi.

---

## 📁 Dataset
Dataset utama yang digunakan: **NYC TLC Trip Record (2023)**  
Sumber: [NYC Open Data / TLC](https://www.nyc.gov/site/tlc/about/about-tlc.page)

Dataset ini mencakup informasi terkait:
- Waktu penjemputan & penurunan (`PUDateTime`, `DODateTime`)
- Lokasi penjemputan & tujuan (`PULocationID`, `DOLocationID`)
- Jumlah penumpang (`passenger_count`)
- Jarak tempuh (`trip_distance`)
- Komponen biaya perjalanan (fare, tip, surcharge, total, dll)

---

## 🔧 Data Preparation
- Konversi kolom waktu ke format datetime
- Feature engineering:
  - `duration` (menit)
  - `day` (hari dalam seminggu)
  - `hour` (jam penjemputan)
- Pembersihan data:
  - Menghapus nilai `trip_distance`, `fare_amount`, atau `duration` yang tidak logis (negatif/ekstrem)
  - Drop lokasi dengan ID 264 & 265 karena tidak memiliki Borough yang valid
  - Filter data hanya untuk tahun 2023

---

## 📊 Exploratory Data Analysis (EDA)
Analisis dilakukan untuk menjawab pertanyaan seperti:
- Kapan waktu tersibuk untuk taksi di NYC?
- Berapa durasi rata-rata dan sebaran waktu perjalanan?
- Lokasi mana yang paling sering digunakan sebagai pickup zone?
- Bagaimana distribusi trip berdasarkan hari dan jam?
- Seperti apa distribusi trip distance dan fare?

Visualisasi yang digunakan:
- Histogram & boxplot untuk mendeteksi outlier
- Heatmap jumlah trip per hari & jam
- Line plot jumlah trip harian
- Pie chart distribusi jarak perjalanan
- Bar plot top 5 pickup zones
- Correlation matrix

---

## 💡 Insights
- Sebagian besar perjalanan berlangsung < 5 miles dan berdurasi < 30 menit.
- Aktivitas trip tertinggi terjadi di jam sibuk (pagi & sore hari kerja).
- Jumlah trip cenderung menurun pada akhir pekan.
- Beberapa zona pickup paling populer adalah area bandara & distrik padat seperti Midtown.
- Outlier ditemukan pada durasi ekstrem (> 2 jam) dan jarak yang tidak masuk akal (> 50 miles).

---

## 🎯 Recommendation
- Optimalkan alokasi driver di jam dan lokasi sibuk berdasarkan pola permintaan.
- Investigasi terhadap outlier untuk mengetahui apakah ada error data atau potensi fraud.
- Perusahaan bisa fokus pada peningkatan layanan di zona populer dan durasi singkat untuk memaksimalkan volume dan efisiensi.

---

## 💻 Tools & Tech
- Python (Pandas, Seaborn, Matplotlib)
- Tableau (untuk visualisasi lanjutan)
- Jupyter Notebook / VSCode

---
