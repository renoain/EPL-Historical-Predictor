
# README.md

```markdown
# EPL Historical Predictor - UAS Data Mining

## Informasi Proyek

| Atribut | Keterangan |
|---------|-------------|
| Judul Proyek | EPL Historical Predictor: Sistem Prediksi Premier League Berbasis Data 32 Musim (1993-2025/2026) |
| Mata Kuliah | UAS Data Mining |
| Semester | Genap 2025/2026 |
| Metodologi | CRISP-DM |

### Tim Pengembang

| Peran | Nama |
|-------|------|
| Data Scientist | [Nama Anggota 1] |
| Machine Learning Engineer | [Nama Anggota 2] |
| Web Developer | [Nama Anggota 3] |

---

## 1. Deskripsi Proyek

EPL Historical Predictor adalah sistem prediksi hasil pertandingan English Premier League (EPL) yang dikembangkan untuk memenuhi tugas UAS Data Mining. Sistem ini memanfaatkan data historis 32 musim (1993-2025/2026) untuk melatih model machine learning.

### Masalah yang Diselesaikan

Prediksi hasil pertandingan sepak bola selama ini seringkali didasarkan pada intuisi, bukan analisis data terukur. Proyek ini bertujuan untuk:

1. Mengidentifikasi faktor-faktor kunci yang mempengaruhi hasil pertandingan
2. Membuat prediksi hasil pertandingan berdasarkan data historis
3. Mengelompokkan tim berdasarkan karakteristik performa

### Tujuan Proyek

1. Melakukan preprocessing dan feature engineering dari dataset EPL 32 musim
2. Mengimplementasikan XGBoost untuk klasifikasi hasil pertandingan (H/D/A)
3. Mengimplementasikan K-Means untuk segmentasi tim
4. Membangun web app interaktif dengan Streamlit

---

## 2. Dataset

### Sumber Data

| Atribut | Detail |
|---------|---------|
| Nama Dataset | English Premier League (football) |
| Sumber | DataHub.io |
| Link | https://datahub.io/core/english-premier-league |
| Cakupan | 1993/94 hingga 2025/26 (musim berjalan) |
| Jumlah Record | 42,046+ pertandingan |
| Jumlah Fitur | 20+ variabel per pertandingan |
| Status Update | Daily update (harian) |
| Data Mentah | Football-Data.co.uk |

### Kolom yang Tersedia

| Kategori | Kolom |
|----------|-------|
| Informasi Dasar | Date, HomeTeam, AwayTeam, Referee |
| Skor & Hasil | FTHG, FTAG, FTR (H/D/A), HTHG, HTAG, HTR |
| Statistik Serangan | HS, AS, HST, AST |
| Statistik Lain | HC, AC, HF, AF, HY, AY, HR, AR |

### Alur Pengolahan Data (CRISP-DM)

1. Business Understanding - Prediksi hasil pertandingan EPL
2. Data Understanding - Eksplorasi dataset 32 musim
3. Data Preparation - Preprocessing, feature engineering
4. Modeling - XGBoost classification + K-Means clustering
5. Evaluation - Accuracy, F1-score, Elbow method
6. Deployment - Streamlit web app

---

## 3. Metode Data Mining

### Metode 1: Classification - XGBoost

**Target Variable (3 kelas):**
- H (Home Win) - tim tuan rumah menang
- D (Draw) - hasil imbang
- A (Away Win) - tim tamu menang

**Alasan memilih XGBoost:**
- Performa tinggi pada dataset tabular
- Menangani missing values otomatis
- Feature importance terinterpretasi
- Regularization mencegah overfitting

### Metode 2: Clustering - K-Means

**Fitur yang digunakan:**
- Points (total poin)
- Goal Difference (selisih gol)
- Wins (jumlah kemenangan)

**Penentuan jumlah cluster:** Elbow method → 4 cluster

**Karakteristik 4 cluster:**
| Cluster | Karakteristik |
|---------|---------------|
| 0 | Tim elite, perebutan gelar |
| 1 | Tim kompetitif, perebutan Champions League |
| 2 | Mid-table, stabil |
| 3 | Tim bawah, battle degradasi |

### Feature Engineering

| Fitur | Deskripsi |
|-------|-----------|
| Recent Form (5 matches) | Performa 5 pertandingan terakhir |
| Home Advantage | Keuntungan bermain di kandang |
| Rolling Goals Avg (3,5,10) | Rata-rata gol n pertandingan terakhir |
| Team Strength | Rating kekuatan tim musiman |
| Head to Head History | Hasil pertemuan 5 terakhir |

---

## 4. Struktur Folder Proyek

```
UAS_DataMining_TimEPL/
│
├── README.md
│
├── dataset/
│   ├── raw/                         # Dataset mentah
│   └── processed/                   # master_dataset.csv
│
├── notebooks/
│   └── analysis.ipynb               # Kode preprocessing & training
│
├── models/
│   ├── xgboost_model.pkl
│   ├── kmeans_model.pkl
│   ├── scaler.pkl
│   └── label_encoder.pkl
│
├── app/
│   ├── app.py                       # Main entry point
│   ├── assets/
│   │   ├── base.css                 # Style dasar
│   │   ├── theme_light.css          # Tema terang
│   │   └── theme_dark.css           # Tema gelap
│   ├── components/
│   │   ├── header.py
│   │   ├── sidebar.py
│   │   └── footer.py
│   ├── pages/
│   │   ├── 1_home.py
│   │   ├── 2_dataset_overview.py
│   │   ├── 3_prediction.py
│   │   ├── 4_visualization.py
│   │   └── 5_about.py
│   └── utils/
│       ├── data_loader.py
│       ├── predictor.py
│       └── visualizations.py
│
├── docs/
│   └── design_system.md             # Dokumentasi design system
│
├── laporan/
│   └── laporan_UAS_datamining.pdf
│
└── requirements.txt
```

---

## 5. Aplikasi Web (Streamlit)

### 5 Halaman Web

| Halaman | Fitur |
|---------|-------|
| Home | Judul proyek, deskripsi, identitas anggota |
| Dataset Overview | Informasi dataset, jumlah data, statistik, visualisasi |
| Prediction | Form input tim, tombol proses, hasil prediksi |
| Visualization | Grafik feature importance, clustering, confusion matrix |
| About | Penjelasan metode, dataset, informasi proyek |

### Tema

Aplikasi mendukung 2 tema:
- Tema Terang (Light Mode)
- Tema Gelap (Dark Mode)

Pengguna dapat mengganti tema melalui toggle di sidebar.

---

## 6. Teknologi yang Digunakan

### Data Mining (Google Colab)

| Tools | Kegunaan |
|-------|----------|
| Python 3.10 | Bahasa pemrograman |
| Pandas, NumPy | Manipulasi data |
| Scikit-learn | Preprocessing, evaluasi, clustering |
| XGBoost | Klasifikasi |
| Matplotlib, Seaborn | Visualisasi |
| SHAP | Explainable AI |
| Joblib | Serialisasi model |

### Web App (Streamlit)

| Tools | Kegunaan |
|-------|----------|
| Streamlit | Framework web |
| Plotly | Grafik interaktif |
| Pandas | Data handling |
| Joblib | Load model |

---

## 7. Hasil yang Ditargetkan

### Metrik Evaluasi XGBoost

| Metrik | Target |
|--------|--------|
| Accuracy | 58-60% |
| Precision (Home Win) | >60% |
| Recall (Home Win) | >55% |
| F1-Score | >55% |

### Perbandingan Model

| Model | Target Accuracy |
|-------|-----------------|
| XGBoost | 58-60% |
| Random Forest | 55-58% |
| Logistic Regression | 53-55% |

---

## 8. Cara Menjalankan Proyek

### Prasyarat

- Python 3.10 atau lebih baru
- Koneksi internet (untuk akses dataset)

### Langkah-langkah

1. Clone repository
```bash
git clone https://github.com/[username]/UAS_DataMining_TimEPL.git
cd UAS_DataMining_TimEPL
```

2. Buat virtual environment
```bash
python -m venv venv
source venv/bin/activate  # Linux/Mac
venv\Scripts\activate     # Windows
```

3. Install dependencies
```bash
pip install -r requirements.txt
```

4. Download model dan dataset dari Google Drive ke folder yang sesuai

5. Jalankan web app
```bash
streamlit run app/app.py
```

6. Buka browser di http://localhost:8501

### Menjalankan Training Ulang di Google Colab

1. Buka `notebooks/analysis.ipynb` di Google Colab
2. Jalankan semua cell secara berurutan
3. Dataset otomatis diambil dari DataHub.io
4. Model dan dataset tersimpan ke Google Drive
5. Download file ke folder proyek lokal

---

## 9. Deliverables

| Berkas | Format | Lokasi |
|--------|--------|--------|
| Source code | .ipynb, .py | notebooks/, app/ |
| Dataset | .csv | dataset/raw/, dataset/processed/ |
| Model | .pkl | models/ |
| Laporan | .pdf (min 15 halaman) | laporan/ |
| Video presentasi | .mp4 (7-15 menit) | - |
| Repository | GitHub | - |

---

## 10. Bonus yang Dikejar

| Bonus | Poin | Status |
|-------|------|--------|
| Deployment online | +2 | Rencana |
| UI/UX menarik (2 tema) | +2 | Akan dikerjakan |
| Explainable AI (SHAP) | +2 | Akan dikerjakan |
| Dashboard interaktif | +2 | Rencana |
| Model advanced (XGBoost) | +2 | Terpenuhi |

---

## 11. Referensi

### Dataset
- DataHub.io (2025). English Premier League (football). https://datahub.io/core/english-premier-league
- Football-Data.co.uk (2025). English Premier League Results.

### Jurnal dan Thesis
- Collins, J. (2024). Identification of Inefficiencies in Football Betting Markets. NCI Dublin.
- Fedorik, T. (2024). Utilization of Machine Learning for Predicting Football Match Outcomes. University of Economics, Prague.
- Ibrahim, Y. (2022). K-Means Clustering dan XGBoost untuk Prediksi Poin di Fantasy Premier League. UPI.

### Dokumentasi
- Streamlit - https://docs.streamlit.io
- XGBoost - https://xgboost.readthedocs.io
- Scikit-learn - https://scikit-learn.org
- SHAP - https://shap.readthedocs.io

---

## 12. Persetujuan

| Peran | Nama | Tanggal |
|-------|------|---------|
| Data Scientist | [Nama Anggota 1] | 25/05/2026 |
| Machine Learning Engineer | [Nama Anggota 2] | 25/05/2026 |
| Web Developer | [Nama Anggota 3] | 25/05/2026 |

---

## 13. Riwayat Revisi

| Versi | Tanggal | Perubahan |
|-------|---------|-----------|
| 1.0 | 20/05/2026 | Draft awal |
| 2.0 | 25/05/2026 | Perubahan ke 1 dataset (IvanRamos) |
| 3.0 | 25/05/2026 | Perubahan ke DataHub.io (32 musim, daily update) |
| 4.0 | 25/05/2026 | Penambahan design system (2 tema), struktur folder final |
```

