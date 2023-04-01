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
### Visualisasi data dan EDA
- Pada dataset tidak ada missing value sehingga data bisa digunakan semua.
- Pada pengecekan menggunakan boxplot, ada outlier pada parameter age. Namun, jika ditangani dengan IQR dan mengedropnya maka data akan sangat banyak berkurang serta mengakibatkan nilai pada parameter HistoryOfBacklogs hanya tersisa yang bernilai 0 saja. Jadi, pada penanganan kasus ini dibiarkan apa adanya dataset dengan tetap tidak adanya missing value(bernilai 0 atau kosong).
![alt text](https://github.com/ildafadli16/machine-learning-terapan/blob/main/boxplotage.png?raw=true)
![alt text](https://github.com/ildafadli16/machine-learning-terapan/blob/main/boxplotcgpa.png?raw=true)
![alt text](https://github.com/ildafadli16/machine-learning-terapan/blob/main/boxplotintern.png?raw=true)
- melakukan univariate Analysis pada categorial features. Yaitu pada Gender dan Stream. ini untuk melihat perbandingan jumlah sampel yang ada pada tiap-tiap fiturnya. 
![alt text](https://github.com/ildafadli16/machine-learning-terapan/blob/main/uni-gender.png?raw=true)
![alt text](https://github.com/ildafadli16/machine-learning-terapan/blob/main/uni-stream.png?raw=true)
![alt text](?raw=true)
- melakukan univariate Analysis pada numerical features. Yaitu pada Age, Internships, CGPA, Hostel, HistoryOfBackLogs, dan PlaceOrNot . ini untuk melihat perbandingan jumlah sampel yang ada pada tiap-tiap fiturnya.
![alt text](https://github.com/ildafadli16/machine-learning-terapan/blob/main/uni-num.png?raw=true) 
- Melakukan Multivariate Analysis pada pada categorial features. Yaitu pada Gender dan Stream. ini untuk melihat pengaruh tiap fitur categorial terhadap fitur PlaceOrNot. Terlihat bahwa gender berpengaruh rendah karena baik Male atau Female besarnya sama. Pada Stream juga demikian memiliki pengaruh rendah karena tiap komponen besarnya hampir sama.
![alt text](https://github.com/ildafadli16/machine-learning-terapan/blob/main/multi-categorial.png?raw=true)
- melakukan multivariate Analysis pada numerical features. Yaitu pada Age, Internships, CGPA, Hostel, HistoryOfBackLogs, dan PlaceOrNot . ini untuk melihat pengaruh tiap fitur categorial terhadap fitur PlaceOrNot. Fokus pada baris PlacedOrNot terletak di baris 6 (dari atas). bahwa yang paling berpengaruh adalah terlihat fitur CGPA yang mana memperlihatkan jika semakin tinggi nilai CGPA semakin banyak pula yang nilai PlacedOrNot adalah 1.
![alt text](https://github.com/ildafadli16/machine-learning-terapan/blob/main/multi-num.png?raw=true)

- Membuat correlation matrix untuk fitur numerik, terlihat bahwa korelasi antara CGPA dengan PlaceOrNot memiliki nilai 0.59 yang artinya mendekati 1 (berkorelasi positif).
![alt text](https://github.com/ildafadli16/machine-learning-terapan/blob/main/corellation.png?raw=true)

## Data Preparation

- pada tahap ini, menggunakan teknik label encoder. Diterapkan pada fitur Gender dan Stream karena keduanya merupakan categorial features. Data bertipe object tidak dapat diproses dalam machine learning, maka dari itu dalam harus diubah dalam bentuk numerik. AAda beberapa cara melakukan encoding categorical data dengan melakukan label encoding dan one hot encoding. Label encoding mengubah setiap nilai dalam kolom menjadi angka yang berurutan.
- Melakukan pembagian dataset menjadi dengan 80% untuk data latih dan 20% untuk data uji. Pembagian dataset ini menggunakan modul train_test_split dari scikit-learn.
- Melakukan standardisasi data pada semua fitur data. Tahap terakhir yaitu melakukan standarisasi data. Hal ini dilakukan untuk membuat semua fitur berada dalam skala data yang sama yaitu dengan range 0-1. Strandadisasi data ini menggunakan fungsi StandardScaler.


## Modeling
Setelah dilakukan pra-pemrosesan pada dataset, langkah selanjutnya adalah modeling terhadap data. Pada tahap ini menggunakan 2 algoritma yaitu Random Forest dan K-Nearest Neighbor karena lebih mudah diaplikasikan untuk jenis dataset ini. Algoritma dengan tanpa parameter tambahan. Pertama-tama kedua model ini dilatih menggunakan data latih. Setelah itu kedua model akan diuji dengan data uji.
-KNN
 Proses klasifikasi dilakukan dengan mencari titik c terdekat dari c-baru (nearest neighbor). Teknik pencarian tetangga terdekat yang umum dilakukan dengan menggunakan formula jarak euclidean. Berikut beberapa formula yang digunakan dalam algoritma knn.
![alt text](https://github.com/ildafadli16/machine-learning-terapan/blob/main/matrixknn.png?raw=true)

-RF
Pengklasifikasi random forest membuat satu set tree keputusan dari subset set pelatihan yang dipilih secara acak. Kemudian mengumpulkan suara dari tree keputusan yang berbeda untuk memutuskan kelas akhir dari objek uji.
![alt text](https://github.com/ildafadli16/machine-learning-terapan/blob/main/matrixrf.png?raw=true)

## Evaluation
Pada proyek ini, model yang dikembangkan adalah kasus klasifikasi sehingga menggunakan metriks akurasi, f1-score, recall dan precision. Hasil pengukuran model yang mana hasilnya akurasi RF lebih besar daripada KNN. Pada model dengan algoritma Random Forest memiliki nilai akurasi, f1-score, recall dan precision lebih tinggi dibanding dengan algoritma K-Nearest Neighbor, yaitu pada RF mendapat accuracy 0.878788 sedangan KNN mendapatkan accuracy  0.875421. Untuk membuktikannya, kedua model tersebut diuji pada data uji dan divisualisasikan pada confussion matrix. Dengan hasil diatas, maka model dengan algoritma Random Forest merupakan model yang dipilih untuk digunakan.


**---Ini adalah bagian akhir laporan---**

_Catatan:_
- _Anda dapat menambahkan gambar, kode, atau tabel ke dalam laporan jika diperlukan. Temukan caranya pada contoh dokumen markdown di situs editor [Dillinger](https://dillinger.io/), [Github Guides: Mastering markdown](https://guides.github.com/features/mastering-markdown/), atau sumber lain di internet. Semangat!_
- Jika terdapat penjelasan yang harus menyertakan code snippet, tuliskan dengan sewajarnya. Tidak perlu menuliskan keseluruhan kode project, cukup bagian yang ingin dijelaskan saja.
