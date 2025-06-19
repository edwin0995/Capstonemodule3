# Capstonemodule3
# 🧳 Travel Insurance Claim Prediction

Proyek ini bertujuan untuk membangun model Machine Learning yang dapat memprediksi apakah seorang pelanggan akan mengajukan klaim asuransi perjalanan. Proyek ini dikembangkan sebagai bagian dari capstone project dalam program pelatihan Data Science.

---

## 🔍 Business Problem

Perusahaan asuransi menghadapi risiko finansial tinggi dari klaim tak terduga. Saat ini, proses underwriting masih banyak dilakukan secara manual, tanpa sistem prediksi risiko berbasis data. Permasalahan utamanya adalah:

- **False Negative (FN)** → Klaim tidak terdeteksi → kerugian besar.
- **False Positive (FP)** → Prediksi salah klaim → premi tinggi, pelanggan kabur.

### 🎯 Tujuan Bisnis

- Mengurangi FN dan meningkatkan **recall** pada nasabah yang benar-benar mengajukan klaim.
- Menyediakan sistem prediksi otomatis untuk mendukung proses underwriting.
- Target recall: **≥ 85%** pada kelas klaim.

---

## 📊 Dataset Description

Dataset berisi data historis pemegang polis asuransi perjalanan, termasuk fitur-fitur seperti:

| Feature | Description |
|--------|-------------|
| `Agency` | Nama agen asuransi |
| `Agency Type` | Tipe agen asuransi |
| `Distribution Channel` | Saluran distribusi |
| `Product Name` | Nama produk asuransi |
| `Gender` | Jenis kelamin tertanggung |
| `Duration` | Lama perjalanan |
| `Destination` | Tujuan perjalanan |
| `Net Sales` | Jumlah penjualan polis |
| `Commission` | Komisi yang diterima agen |
| `Age` | Usia tertanggung |
| `Claim` | Status klaim (1 = klaim, 0 = tidak klaim) |

Jumlah data: ± 50.000 baris  
Distribusi target sangat tidak seimbang: hanya ~8% adalah klaim.

---

## ⚙️ Project Workflow

1. **Business Understanding**  
2. **Data Cleaning & Preprocessing**  
   - Handling missing values & outliers  
   - Encoding kategorikal  
   - Feature scaling  
3. **Exploratory Data Analysis (EDA)**  
4. **Modeling**  
   - Logistic Regression, Random Forest, XGBoost, LightGBM  
   - Penanganan imbalance dengan **RandomUnderSampler**  
5. **Evaluation**  
   - **Recall**, **F2 Score**, dan **ROC AUC**

---

## 📈 Evaluation Metrics

Karena False Negative lebih merugikan bisnis:

- ✅ **Recall (positif)** = metrik utama
- ✅ **F2 Score** = fokus pada recall
- 🔹 **ROC AUC** = pelengkap untuk evaluasi umum

---

## 🧠 Best Model Summary

- **Model:** Logistic Regression
- **Resampling:** RandomUnderSampler
- **Recall (Kelas Klaim):** 88%
- **F2 Score:** 0.79
- **ROC AUC:** 0.86

---

## 💡 Insights

- Lama perjalanan (`Duration`) dan komisi (`Commission`) menjadi prediktor kuat.
- Tanpa penanganan imbalance, recall < 10%.
- Model sederhana (LogReg) dengan resampling bisa mengalahkan model kompleks jika di-tuning dengan benar.

---

## 🚀 Deployment Scenario

Model akan digunakan saat pelanggan mengisi formulir pembelian asuransi:

1. Input: Data nasabah dan detail perjalanan.
2. Output: Probabilitas klaim.
3. Tindakan:
   - Jika risiko tinggi → premi lebih tinggi / proteksi tambahan.
   - Jika risiko rendah → penawaran lebih kompetitif.

---

## ⚠️ Project Limitations

- Tidak ada data riwayat klaim sebelumnya.
- Tujuan perjalanan (bisnis/liburan) tidak tersedia.
- Belum dilakukan interpretabilitas model (SHAP/Explainable AI).
- Waktu terbatas untuk hyperparameter tuning lanjutan.

---

## 🔄 Future Improvements

- Tambahkan fitur baru: riwayat klaim, jenis perjalanan, metode pembayaran.
- Coba algoritma lain seperti CatBoost, AdaBoost, dan stacking ensemble.
- Lakukan hyperparameter tuning dengan Optuna atau Bayesian Optimization.
- Gunakan SHAP untuk interpretasi model.
- Monitoring performa model setelah deployment secara berkala.

---

## 📁 Folder Structure (Optional)

