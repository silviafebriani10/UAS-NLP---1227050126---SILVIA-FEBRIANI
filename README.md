Nama: Silvia Febriani
NIM: 1227050126
Mata Kuliah: Natural Language Processing
🎯 1. Deskripsi Proyek

Proyek ini merupakan tugas akhir UAS mata kuliah Natural Language Processing (NLP).
Tujuan utama dari proyek ini adalah membangun sistem Analisis Sentimen menggunakan komentar publik terkait pelajaran AI untuk anak sekolah.

Proses yang dilakukan mulai dari:

Mengidentifikasi tujuan NLP

Mengumpulkan dataset

Melakukan text preprocessing

Melatih model Machine Learning (SVM + TF-IDF)

Memprediksi sentimen pada data baru

Menyimpan hasil dan model

Model yang dibangun dapat mengklasifikasikan sentimen menjadi:

0 → Negative

1 → Neutral

2 → Positive

🎯 2. Tujuan NLP (Goals)

Tujuan dari task NLP ini adalah:

✔ Membangun model analisis sentimen pada komentar tentang topik pelajaran AI
✔ Mengklasifikasikan teks ke dalam 3 kelas: negative, neutral, positive
✔ Membersihkan teks menggunakan preprocessing berbahasa Indonesia
✔ Menerapkan teknik NLP modern seperti TF-IDF, stemming, stopwords, dan slang normalization
✔ Melakukan inference pada dataset besar yang tidak memiliki label

Task ini masuk kategori Text Classification / Sentiment Analysis.

📦 3. Dataset

Proyek ini menggunakan dua dataset:

1️⃣ x-data-labeled.csv

Dataset berlabel, digunakan untuk training model.
Kolom:

komentar

label (negative/neutral/positive)

2️⃣ x-data-all.csv

Dataset besar tanpa label.
Digunakan sebagai input untuk prediksi model setelah training.

Dataset output:

x-data-labeled_cleaned.csv — hasil preprocessing

x-data-all_with_predictions.csv — hasil prediksi model

🧹 4. Tahap Preprocessing

Proses preprocessing dilakukan supaya teks menjadi bersih dan siap digunakan model ML.

Jenis preprocessing yang dilakukan:

✔ Case folding

Mengubah seluruh teks menjadi huruf kecil.

✔ Menghapus:

URL

Mention (@username)

Hashtag

Tanda baca

Karakter berulang

✔ Normalisasi slang

Menggunakan kamus slang dictionary, contoh:

“gak” → “tidak”

“anj” → “kasar”

“gue” → “saya”

✔ Mengubah emoji menjadi sentimen

😡 → negatif

😂 → positif

👍 → positif

✔ Tokenisasi
✔ Stopwords removal

Menggunakan NLTK stopwords bahasa Indonesia.

✔ Stemming

Menggunakan library Sastrawi.

✔ Deteksi Sarkasme

Jika terdapat pola seperti:

"hebat banget ya"

"ndasmu"

Maka token sarcasm ditambahkan.

🤖 5. Model Machine Learning

Model yang digunakan:

🔹 TF-IDF Vectorizer

max_features = 5000

Mengubah teks menjadi vektor angka agar bisa diproses model.

🔹 Support Vector Machine (SVM Classifier)

Digunakan karena:

Kinerja sangat baik untuk text classification

Stabil pada ukuran data kecil–sedang

Akurasi tinggi pada dataset sparse seperti TF-IDF

Model disimpan dalam file:

svm_tfidf_model.joblib

tfidf_vectorizer.joblib

🧪 6. Training & Evaluasi

Model dilatih menggunakan:

train_test_split(test_size=0.2, stratify=y)


Evaluasi yang digunakan:

Accuracy Score

Classification Report

Label mapping:

{'negative': 0, 'neutral': 1, 'positive': 2}

📝 7. Prediksi Data Tanpa Label

Dataset x-data-all.csv diproses sebagai berikut:

Preprocess teks

Transform ke TF-IDF

Prediksi sentimen

Simpan hasil ke file:

📁 x-data-all_with_predictions.csv

Kolom output:

komentar

clean_text

predicted_label

label_name

📂 8. Struktur Folder (Dianjurkan)
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

🚀 9. Cara Menjalankan Project

1. Install dependencies

pip install pandas numpy scikit-learn Sastrawi nltk joblib


2. Jalankan notebook utama

UAS_NLP_1227050126_SILVIA_FEBRIANI.ipynb


3. Upload dataset ke folder data/

4. Running semua cell sampai selesai

Hasil prediksi otomatis tersimpan di:

data/x-data-all_with_predictions.csv

🧷 10. Kesimpulan

Proyek ini berhasil:

✔ Membersihkan dan memproses teks berbahasa Indonesia
✔ Menggunakan teknik NLP modern
✔ Melatih model SVM + TF-IDF
✔ Melakukan klasifikasi sentimen pada dataset besar
✔ Menghasilkan model yang siap digunakan kembali
