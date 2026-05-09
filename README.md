# 🛍️ NLP Pipeline: N-Gram & Syntactic Parsing pada Ulasan Tokopedia

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1BW8KiBGM6Xf-pL9MKKJ7-O8rQrD7gdQL?authuser=1#scrollTo=w3NeCa1nP1RS)
[![Python Version](https://img.shields.io/badge/Python-3.8%2B-blue.svg)](https://www.python.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

Proyek ini merupakan implementasi komprehensif dari *Natural Language Processing* (NLP) untuk menganalisis data tidak terstruktur berupa ulasan pelanggan e-commerce (Tokopedia). Proyek ini berfokus pada penggabungan pendekatan statistik (**N-Gram**) dan pemodelan linguistik komputasional (**Constituency & Dependency Parsing**) untuk mengekstrak wawasan konsumen (*customer insights*) yang presisi.

---

## 🎯 Tujuan Proyek
1. **Mengekstrak Pola Opini (N-Gram):** Mengidentifikasi tren sentimen dan kata kunci yang paling sering dibicarakan konsumen menggunakan analisis Unigram, Bigram, dan Trigram.
2. **Menganalisis Hierarki Kalimat (Constituency Parsing):** Membedah struktur teks ulasan informal menjadi blok penyusun kalimat dasar seperti Frasa Benda (NP) dan Frasa Kerja (VP).
3. **Memetakan Relasi Kata (Dependency Parsing):** Mengidentifikasi hubungan logis antar kata (menentukan subjek pelaku, akar aksi, dan objek sasaran) menggunakan pemodelan linguistik.
4. **Membuktikan Kekuatan Integrasi NLP:** Menunjukkan bahwa ekstraksi N-Gram yang dipertajam dengan *Parsing* sintaksis menghasilkan pemahaman konteks bisnis yang jauh lebih akurat.

---

## 📊 Dataset
Dataset yang digunakan dalam proyek ini adalah **Tokopedia Product Reviews 2019**.
Data ini berisi ribuan ulasan teks asli dari pembeli beserta *rating* bintang (1-5) yang merepresentasikan polaritas sentimen.
- **Sumber:** [Kaggle - Tokopedia Product Reviews](https://www.kaggle.com/datasets/dimasikno/tokopedia-product-reviews-2019) *(Sesuaikan link jika menggunakan dataset Kaggle lain)*
- **Format:** `.csv`

---

## 🛠️ Teknologi & *Library*
Proyek ini dibangun menggunakan bahasa pemrograman **Python** dengan dukungan *library* Data Science dan NLP terkemuka:
- `pandas` & `numpy` (Manipulasi Data)
- `scikit-learn` (Ekstraksi Fitur / CountVectorizer)
- `NLTK` (RegexpParser, Chunking, Tree Visualization)
- `Stanza` (Stanford NLP Pipeline untuk Bahasa Indonesia)
- `spaCy` & `displacy` (Dependency Visualization)
- `matplotlib` (Visualisasi Data Sentimen)
- `PyTorch` (Backend *Deep Learning* untuk Stanza)

---

## 🚀 Alur Kerja (*Pipeline*)

1. **Data Preprocessing:** Pembersihan teks (Regex), *case folding*, dan eliminasi kata hubung menggunakan *Custom Indonesian Stopwords*.
2. **Ekstraksi N-Gram:** Menghitung frekuensi kemunculan frasa menggunakan `CountVectorizer`, memisahkan N-Gram (1-3 kata), dan mengkorelasikannya dengan nilai sentimen pelanggan.
3. **Constituency Parsing:** Melakukan POS Tagging dan menerapkan aturan *Context-Free Grammar* (CFG) untuk mengekstrak Frasa Benda (NP) dan Frasa Kerja (VP) ke dalam bentuk struktur *Bracket* dan Pohon ASCII.
4. **Dependency Parsing:** Menelusuri relasi logis Induk-Anak (*Head-Child*) secara rekursif dari setiap kata. Hasil direpresentasikan melalui Tabulasi Pandas, Pohon Dependensi ASCII, dan Graf Interaktif.

---

## 💻 Cara Menjalankan Proyek

Kamu dapat menjalankan kode ini secara langsung tanpa perlu melakukan instalasi lokal melalui Google Colab:
1. Klik *badge* **Open in Colab** di bagian paling atas *readme* ini.
2. Pastikan file dataset `tokopedia-product-reviews-2019.csv` sudah terunggah di Google Drive Anda.
3. Sesuaikan *path* direktori pada *cell* konfigurasi *Google Drive Mount*.
4. Jalankan *cell* secara berurutan (*Run All*).

Jika ingin menjalankan secara lokal (Jupyter Notebook):
```bash
# 1. Clone repositori ini
git clone [https://github.com/username-kamu/nama-repo-kamu.git](https://github.com/username-kamu/nama-repo-kamu.git)

# 2. Masuk ke direktori proyek
cd nama-repo-kamu

# 3. Install requirement/library yang dibutuhkan
pip install spacy spacy-stanza stanza nltk pandas numpy scikit-learn matplotlib torch
