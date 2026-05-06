# 🐦 Crawling Data Twitter (X) Menggunakan Tweet Harvest (Google Colab)

## 📌 Deskripsi Proyek

Repository ini berisi implementasi crawling data dari platform Twitter (X) menggunakan **Tweet Harvest** yang dijalankan melalui Google Colab. Proyek ini bertujuan untuk mengumpulkan data tweet berdasarkan kata kunci tertentu tanpa menggunakan API resmi Twitter.

Dataset yang dihasilkan dapat digunakan untuk berbagai kebutuhan seperti:

* Analisis sentimen
* Data mining
* Topic modeling
* Riset sosial media

---

## 🎯 Tujuan

* Mengambil data tweet secara otomatis menggunakan Tweet Harvest
* Menyimpan data hasil crawling dalam format terstruktur
* Mempermudah proses crawling menggunakan Google Colab (tanpa setup lokal)

---

## 🌐 Platform yang Digunakan

* Google Colab (cloud-based notebook)
* Python

---

## 🛠️ Library yang Digunakan

* tweet-harvest
* pandas

---


## 🚀 Cara Menjalankan di Google Colab

### 1. Buka Google Colab

* Upload file `crawling_twitter.ipynb` ke Google Colab
  **atau**
* Buka langsung melalui link notebook (jika tersedia)

---

### 2. Install Dependencies

Jalankan cell berikut di Google Colab:

```python
!pip install tweet-harvest pandas
```

---

### 3. Import Library

```python
from tweet_harvest import TweetHarvest
import pandas as pd
```

---

### 4. Proses Crawling Data

```python
# Inisialisasi Tweet Harvest
harvest = TweetHarvest()

# Crawling data berdasarkan keyword
tweets = harvest.search(
    query="jersey timnas erspo",
    limit=100,
    lang="id"
)

# Konversi ke DataFrame
df = pd.DataFrame(tweets)

# Tampilkan data
df.head()
```

---

### 5. Simpan Data ke CSV

```python
df.to_csv("tweets_erspo.csv", index=False)
```

Jika ingin menyimpan ke Google Drive:

```python
from google.colab import drive
drive.mount('/content/drive')

df.to_csv("/content/drive/MyDrive/tweets_erspo.csv", index=False)
```

---

## 🔍 Parameter Crawling

Beberapa parameter penting yang dapat digunakan:

* `query` → kata kunci pencarian
* `limit` → jumlah tweet yang diambil
* `lang` → bahasa (contoh: `"id"`)
* `since` → tanggal mulai (YYYY-MM-DD)
* `until` → tanggal akhir (YYYY-MM-DD)

### Contoh Penggunaan Lanjutan

```python
tweets = harvest.search(
    query="erspo timnas indonesia",
    limit=200,
    lang="id",
    since="2025-01-01",
    until="2025-01-10"
)
```

---

## 💾 Struktur Data Output

Data hasil crawling umumnya berisi:

* `id` → ID tweet
* `date` → tanggal tweet
* `username` → nama pengguna
* `content` → isi tweet
* `replyCount` → jumlah balasan
* `retweetCount` → jumlah retweet
* `likeCount` → jumlah like

---

## ⚠️ Catatan Penting

* Tweet Harvest menggunakan metode scraping (bukan API resmi)
* Tidak memerlukan API Key / Token Twitter
* Pastikan penggunaan data sesuai dengan kebijakan platform Twitter (X)
* Hindari scraping berlebihan untuk mencegah rate limit atau pemblokiran

---

## 📊 Penggunaan Lanjutan

Dataset yang dihasilkan dapat digunakan untuk:

* Analisis sentimen (Naïve Bayes, SVM, dll)
* Visualisasi data
* Machine Learning / NLP

---

## 🤝 Kontribusi

Kontribusi terbuka untuk siapa saja:

1. Fork repository
2. Buat branch baru
3. Commit perubahan
4. Submit pull request

---

