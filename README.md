UAS Natural Language Processing

Nama: Silvia Febriani
NIM: 1227050126
Mata Kuliah: Natural Language Processing

1. Deskripsi Proyek

Proyek ini merupakan tugas UAS mata kuliah Natural Language Processing (NLP).
Tujuan utama proyek ini adalah membangun sistem Sentiment Analysis pada komentar publik mengenai pelajaran AI untuk anak sekolah.

Proyek ini mencakup beberapa tahapan utama:

Identifikasi tujuan NLP

Pengumpulan dataset

Text preprocessing

Pelatihan model Machine Learning (SVM + TF-IDF)

Prediksi sentimen pada dataset tanpa label

Penyimpanan model dan hasil prediksi

Model mengklasifikasikan sentimen menjadi tiga kelas:

0 = Negative

1 = Neutral

2 = Positive

2. Tujuan NLP

Tujuan dari task NLP dalam proyek ini adalah:

Membangun model analisis sentimen pada komentar terkait pelajaran AI

Mengklasifikasikan teks ke dalam tiga kelas sentimen

Membersihkan teks menggunakan preprocessing bahasa Indonesia

Menerapkan TF-IDF, stemming, stopwords removal, dan normalisasi kata tidak baku

Melakukan prediksi pada dataset yang tidak memiliki label

Task ini tergolong dalam Text Classification / Sentiment Analysis.

3. Dataset

Proyek ini menggunakan dua dataset utama:

1. x-data-labeled.csv

Dataset berlabel untuk keperluan training.
Kolom:

komentar

label (negative, neutral, positive)

2. x-data-all.csv

Dataset tanpa label, digunakan untuk prediksi setelah training.

Dataset Output:

x-data-labeled_cleaned.csv — hasil preprocessing

x-data-all_with_predictions.csv — hasil prediksi model

4. Preprocessing Teks

Tahap preprocessing dilakukan untuk membersihkan teks sebelum diproses oleh model.

Jenis preprocessing yang dilakukan:

Case folding (mengubah teks menjadi huruf kecil)

Menghapus URL, mention, hashtag, angka, karakter berulang, dan tanda baca

Normalisasi slang menggunakan kamus kata tidak baku

Konversi emoji menjadi sentimen (misal “😂” menjadi positif)

Tokenisasi

Stopwords removal (menggunakan NLTK bahasa Indonesia)

Stemming menggunakan Sastrawi

Deteksi pola sarkasme tertentu (opsional, sesuai coding Anda)

5. Model Machine Learning

Model yang digunakan dalam proyek ini:

TF-IDF Vectorizer

max_features = 5000
Digunakan untuk mengubah teks menjadi vektor numerik.

Support Vector Machine (SVM Classifier)

Dipilih karena:

Performa baik untuk text classification

Stabil pada dataset kecil–menengah

Cocok untuk data sparse seperti TF-IDF

Model yang disimpan:

svm_tfidf_model.joblib

tfidf_vectorizer.joblib

6. Training dan Evaluasi

Model dilatih menggunakan:

train_test_split(test_size=0.2, stratify=y)


Evaluasi yang dilakukan:

Accuracy score

Classification report

Mapping label:

negative = 0
neutral  = 1
positive = 2

7. Prediksi pada Data Tanpa Label

Dataset x-data-all.csv diproses dengan langkah berikut:

Preprocessing teks

Transformasi menggunakan TF-IDF

Prediksi sentimen oleh model

Menyimpan hasil ke file:

x-data-all_with_predictions.csv


Kolom output:

komentar

clean_text

predicted_label

label_name

8. Struktur Folder

Struktur direktori yang disarankan:

UAS-NLP-Silvia/
│
├── data/
│   ├── x-data-labeled.csv
│   ├── x-data-all.csv
│   ├── x-data-labeled_cleaned.csv
│   └── x-data-all_with_predictions.csv
│
├── models/
│   ├── svm_tfidf_model.joblib
│   └── tfidf_vectorizer.joblib
│
├── UAS_NLP_1227050126_SILVIA_FEBRIANI.ipynb
└── README.md

9. Cara Menjalankan Program
1. Install dependencies
pip install pandas numpy scikit-learn Sastrawi nltk joblib

2. Jalankan notebook utama
UAS_NLP_1227050126_SILVIA_FEBRIANI.ipynb

3. Upload dataset ke folder data/
4. Jalankan seluruh cell notebook

Hasil prediksi otomatis tersimpan pada:

data/x-data-all_with_predictions.csv

10. Kesimpulan

Proyek NLP ini berhasil:

Melakukan preprocessing teks berbahasa Indonesia

Menggunakan teknik NLP modern (TF-IDF, stopwords, stemming)

Melatih model SVM untuk sentiment analysis

Mengklasifikasikan sentimen pada dataset besar

Menghasilkan model yang dapat digunakan kembali untuk prediksi
