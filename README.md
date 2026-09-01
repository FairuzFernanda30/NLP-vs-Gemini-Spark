# 📊 Benchmark: Traditional ML vs. Zero-Shot Gemini Spark (Indonesian Sentiment Analysis)
Sebuah studi kasus empiris yang membandingkan performa model **Traditional Machine Learning (TF-IDF + Logistic Regression)** dengan **Zero-Shot LLM (Gemini 3.5 Flash-Lite / Spark)** menggunakan dataset tolok ukur resmi bahasa Indonesia **IndoNLU (SmSA)**.
---
## 🎯 Ringkasan Hasil Eksperimen
| Metrik Evaluasi | 🤖 Traditional ML (TF-IDF + Logistic Regression) | ⚡ Gemini Spark (Gemini 3.5 Flash-Lite) |
| :--- | :--- | :--- |
| **Kebutuhan Data Latih** | Dilatih pada **11.000 data** berlabel | **0 data latih (Zero-Shot)** |
| **Akurasi Riil (Data Nyata)** | **74.00%** | **98.00%** 🏆 |
| **Throughput / Latensi** | ~10 ms (Lokal CPU) | ~35 ms / item (via JSON Batching) |
| **Ketahanan Sarkasme & Slang** | Rendah (Rentan bias leksikal) | Sangat Tinggi (Memahami semantik konteks) |
---
## 🔬 Metodologi Penelitian
1. **Dataset:** Menggunakan subset uji acak dari dataset standar akademik **IndoNLU SmSA** (kumpulan ulasan informal masyarakat Indonesia dari Twitter dan e-commerce).
2. **Model 1 (Baseline):** TF-IDF Vectorizer (2.500 fitur) + Logistic Regression classifier yang dilatih pada 11.000 data latih.
3. **Model 2 (Challenger):** Gemini 3.5 Flash-Lite menggunakan teknik **Single-Batch JSON Prompting** untuk memproses 50 ulasan secara simultan tanpa terkena *rate-limit*.
4. **Evaluasi:** Mengukur akurasi *ground truth*, matriks konfusi (*Confusion Matrix*), dan analisis kesalahan baris-per-baris.
---
## 📁 Berkas yang Disertakan
* `notebook.ipynb` : Seluruh kode alur kerja eksperimen di Google Colab.
* `Hasil_Benchmark_IndoNLU_ML_vs_GeminiSpark.xlsx` : Berkas spreadsheet berisi detail 50 ulasan uji, kunci jawaban, dan status prediksi kedua model.
---
## 💡 Kesimpulan
Model LLM mikro/ringan modern (seperti Gemini Spark/Flash-Lite) membuktikan keunggulan pemahaman semantik yang jauh lebih tinggi dibanding pendekatan NLP tradisional, mengeliminasi kebutuhan rekayasa fitur (*feature engineering*) manual dan proses pelabelan data yang mahal.
