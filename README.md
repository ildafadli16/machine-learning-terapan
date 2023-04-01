# Laporan Proyek Machine Learning - Achmad Fadli

## Domain Proyek
Domain proyek yang dipilih dalam proyek machine learning ini adalah mengenai Pendidikan dengan judul proyek "Prediksi Penempatan". Setelah lulus, mahasiswa tentunya akan terjun ke dunia kerja. Pihak Kampus memiliki tanggung jawab untuk menjamin bahwa lulusan kampusnya memiliki kemampuan yang unggul dilihat dari tingkat daya serap di dunia kerja. Dengan membuat model Machine Learning untuk prediksi keberhasilan ditempatkan atau tidak seorang mahasiswa, bertujuan agar pihak kampus dapat melihat faktor apa yang paling berpengaruh terhadap keberhasilan ditempatkan atau tidaknya sehingga pihal kampus tepat sasaran saat evaluasi dalam upaya peningkatan kompetensi dan mutu. Hasil lain dari proyek ini yaitu sebagai bahan untuk promosi dalam hal pencarian mahasiswa baru, akreditasi, dan lain-lain.

## Business Understanding

Berdasarkan latar belakang yang ada, maka :

### Problem Statements

- Bagaimana cara melakukan pra-pemrosesan pada data kriteria yang akan digunakan untuk perancangan model yang memiliki akurasi tinggi?
- Dari serangkaian kriteria/faktor/fitur yang ada, fitur apa yang berpengaruh terhadap berhasilnya mahasiswa ditempatkan atau tidak?
- Model apa yang memiliki tingkat akurasi tinggi untuk digunakan pada proyek ini?

### Goals

- Melakukan pra-pemrosesan dengan baik agar dapat digunakan dalam pembuatan model.
- Mengetahui fitur yang paling berkorelasi dengan ditempatkan atau tidak. Hal ini bermanfaat untuk pihak kampus dapat mengambil langkah-langkah yang tepat dalam pengembangan kompetensi lebih lanjut sehingga tepat sasaran dan efisiensi.
- Membuat model machine learning yang dapat memprediksi ditempatkan atau tidak seakurat mungkin berdasarkan fitur-fitur yang ada. 


## Data Understanding

Dataset berasal dari Kaggle. merupakan dataset Sebuah Universitas Mengumumkan Catatan Penempatan Di Kampus Untuk Jurusan Teknik. Datanya dari tahun 2013 dan 2014. Dikumpulkan Selama 2 tahun. data ini untuk memprediksi dan menganalisis apakah seorang siswa akan ditempatkan, berdasarkan latar belakangnya. Dataset : https://www.kaggle.com/datasets/tejashvi14/engineering-placements-prediction 

Pada berkas yang diunduh yakni collegePlace.csv berisi 2966 baris dan 8 kolom. Kolom-kolom tersebut terdiri dari 2 buah kolom bertipe objek dan 6 buah kolom bertipe numerik (tipe data int64). Untuk penjelasan mengenai variabel-variable pada dataset ini dapat dilihat sebagai berikut:

### Variabel-variabel collegePlace.csv dataset adalah sebagai berikut:
- Age : usia mahasiswa, parameter usia ini nilainya pada rentang 19-30 tahun
- Gender : jenis kelamin mahasiswa, ada dua nilai yaitu Male dan Female
- Stream : asal jurusan, terdapat 5 jurusan, yaitu Computer Science, Information Technology, Electronics And Communication, Mechanical, Electrical, dan Civil
- internships : berapa kali pengalaman magang
- CGPA : Cumulative Grade Point Average, paramter ini semacam nilai yang dikumpulkan oleh mahasiswa
- Hostel : asrama atau tidak, bernilai 1 jika iya, dan 0 jika tidak asrama
- HistoryOfBacklogs : bisa dikatakan sebuah riwayat akumulasi ketidaklulusan pada suatu task. pada dataset ini ada 2 nilai, 0(artinya lulus semua) dan 1 (ada 1 atau lebih tidak lulus). 
- PlacedOrNot : Ditempatkan atau tidak. Parameter ini adalah parameter tujuan. nilainya 0 dan 1.


## Data Preparation

## Modeling

## Evaluation

**---Ini adalah bagian akhir laporan---**

_Catatan:_
- _Anda dapat menambahkan gambar, kode, atau tabel ke dalam laporan jika diperlukan. Temukan caranya pada contoh dokumen markdown di situs editor [Dillinger](https://dillinger.io/), [Github Guides: Mastering markdown](https://guides.github.com/features/mastering-markdown/), atau sumber lain di internet. Semangat!_
- Jika terdapat penjelasan yang harus menyertakan code snippet, tuliskan dengan sewajarnya. Tidak perlu menuliskan keseluruhan kode project, cukup bagian yang ingin dijelaskan saja.
