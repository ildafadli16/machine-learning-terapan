# Laporan Proyek Machine Learning - Achmad Fadli

## Project Overview

Pada sebuah platform online/aplikasi toko buku berhasil mengumpulkan dataset terkait buku-buku koleksinya. Dengan data yang sudah dikumpulkan tersebut, dapat diolah secara machine learing/AI untuk dijadikan suatu fitur pada aplikasi untuk meningkatkan performa aplikasi tersebut.


## Business Understanding

### Problem Statements

- Bagaimana membuat sistem rekomendasi yang dipersonalisasi dengan teknik content-based filtering?


### Goals

- Menghasilkan sejumlah rekomendasi buku yang dipersonalisasi untuk pengguna dengan teknik contect-based filtering.


## Data Understanding
Dataset berasal dari Kaggle. Dataset : https://www.kaggle.com/datasets/jalota/books-dataset 
Pada berkas yang diunduh yakni Book_Dataset_1.csv berisi 1000 baris dan 11 kolom. Kolom-kolom tersebut terdiri dari 4 buah kolom bertipe object, 4 buah kolom bertipe numerik int64, dan 3 buah kolom bertipe numerik float64. Untuk penjelasan mengenai variabel-variable pada dataset ini dapat dilihat sebagai berikut:

- Title : judul buku
- Category : jenis/kelompok/kategori buku
- Price : harganya buku
- Price_After_Tax : harga buku yang sudah termasuk pajak
- Tax_amount : nominal pajak pada masing-masing buku
- Avilability : Jumlah ketersediaan buku/stock buku
- Number_of_reviews : jumlah user yang sudah memberikan review terhadap tiap buku
- Book_Description : deskripsi buku 
- Image_Link : link yang mana kita bisa melihat gambar dari bukunya
- Stars : rating buku pada rentang 1-5

## Data Preparation

- Pada tahap preparation ini, dilakukan pengecekan missing value menggunakan fungsi isnull().sum(). Dan hasilnya mengeluarkan nilai 0 pada tiap parameternya yang berarti tidak ada missing value pada dataset.
- selanjutnya, dilakukan penghapusan(dropping) komponen yang tidak dibutuhkan. Karena yang dibutuhkan hanya parameter Title dan Category saja, maka kolom selain itu dihapus/di-drop.

## Modeling
Pada tahap modeling ini, menggunakan sistem rekomendasi dengan pendekatan content based filtering. Content-based filtering mempelajari profil minat pengguna baru berdasarkan data dari objek yang telah dinilai pengguna. Algoritma ini bekerja dengan menyarankan item serupa yang pernah disukai di masa lalu atau sedang dilihat di masa kini kepada pengguna. Semakin banyak informasi yang diberikan pengguna, semakin baik akurasi sistem rekomendasi. jadi, di sini algoritma akan menyarankan buku serupa berdasarkan category yang sama dari buku yang pernah disukai di masa lalu. Digunakan TF-IDF Vectorizer untuk menemukan representasi fitur penting dari setiap kategori buku, dan Cosine Similarity untuk menghitung derajat kesamaan (similarity degree) antar buku(judul buku).


## Evaluation
keluaran sistem ini adalah berupa top-N recommendation. Dengan nilai K = 5, yang artinya 5 teratas judul buku yang direkomendasikan. Pada percobaan dilakukan dengan mengecek judul buku apa yang akan direkomendasikan jika dipilih judul 'Life' yang memiliki kategori Music. Dihasilkan 5 judul buku dengan kelima-limanya berkategori Music.


**---Ini adalah bagian akhir laporan---**