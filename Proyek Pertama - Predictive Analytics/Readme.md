# Proyek Pertama Flight Price Prediction

Ini merupakan proyek pertama dari kelas _Machine Learning_ Terapan, yaitu Predictive Analytics. Proyek ini menganalisis suatu model _Machine Learning_ untuk memprediksi harga sewa perumahan hingga bangunan apartemen yang berada di Negara India.

## Domain Proyek

Domain proyek yang saya pilih dalam proyek _Machine Learning_ ini adalah mengenai **Transportasi Udara** dengan judul "Prediksi Harga Penerbangan".

### Latar Belakang

Perkembangan di bidang pariwisata menjadi sebuah daya tarik bagi seorang traveller yang ingin berkunjung dan menikmati wisata di seluruh dunia, dan dapat menjadi dampak positif di sektor penerbangan dan sektor pariwisata. Dengan adanya peran teknologi sangat banyak mempengaruhi segala bidang, dan salah satunya pada penjualan tiket pesawat. Hal tersebut menjadi keuntungan bagi penyedia jasa layanan perjalanan dalam memperjualbelikan tiket pesawat dengan tarif yang murah. Dengan banyaknya maskapai yang bersaing satu sama lain, maka maskapai berlomba untuk menjadi pilihan utama konsumen/pasar, namun untuk mencapai hal tersebut, belum ada strategi maskapai yang dapat memprediksi harga tiket pesawat sesuai dengan kebutuhan pasar. Untuk memenuhi kebutuhan maskapai, maka diperlukan suatu cara untuk menetapkan harga tiket pesawat sesuai kebutuhan pasar dengan bantuan pengaruh teknologi dan informasi.

<br>

<div><img src="https://risks.id/wp-content/uploads/2020/05/tiket.jpg" width="1000"/></div>

[Referensi gambar](https://risks.id/penjualan-tiket-pesawat-dibatasi-hanya-50-dari-kapasitas-kursi/)

<br>

Berdasarkan latar belakang permasalahan yang telah diuraikan sebelumnya, maka penulis membuat sebuah model _Machine Learning_ dengan menggunakan algoritma K-Neighbor, Random Forest dan AdaBoost sehingga pihak maskapai dapat memprediksi penetapan harga tiket pesawat tepat berdasarkan kebutuhan konsumen atau pasar. Parameter yang digunakan dalam membuat sebuah model yaitu maskapai penerbangan, kode penerbangan, waktu keberangkatan, waktu tiba, destinasi penerbangan, kelas, durasi penerbangan dan pemberhentian tujuan pesawat tiap maskapai penerbangan. Dari model tersebut diambil algoritma dengan akurasi tertinggi yang akan digunakan untuk memprediksi penetapan tarif tiket pesawat yang akan dikonfigurasikan dengan _Machine Learning_.

Pada proyek ini, data yang saya pakai adalah data prediksi harga penerbangan dengan 12 atribut sebagai parameter prediksi. Dalam Pelaksanaan penelitian ini dilakukan dengan menggunakan media bantu Google Colaboratory untuk membuat sebuah model data dengan algoritma K-Neighbor, RandomForest dan AdaBoost.

Referensi: [PREDIKSI PENETAPAN TARIF PENERBANGAN MENGGUNAKAN AUTO-ML DENGAN ALGORITMA RANDOM FOREST](http://jurnal.murnisadar.ac.id/index.php/Tekinkom/article/download/508/315)

## Business Understanding

Proyek ini dibangun untuk perusahaan dengan karakteristik bisnis sebagai berikut:

- Pihak maskapai dapat memprediksi penetapan harga tiket pesawat tepat berdasarkan kebutuhan konsumen atau pasar.

### Problem Statements

Dengan banyaknya maskapai yang bersaing satu sama lain, maka maskapai berlomba untuk menjadi pilihan utama konsumen/pasar. Namun untuk mencapai hal tersebut, belum ada strategi maskapai yang dapat memprediksi harga tiket pesawat sesuai dengan kebutuhan pasar.

- Bagaimana cara untuk memenuhi kebutuhan maskapai dalam penetapan harga tiket pesawat menggunakan _Machine Learning_?

### Goals

Tujuan dari proyek ini adalah mendapatkan akurasi tertinggi yang akan digunakan untuk memprediksi penetapan tarif tiket pesawat yang akan dikonfigurasikan dengan _Machine Learning_

### Solution statements

Untuk menyelesaikan masalah ini, saya akan mengajukan 3 solusi model _Machine Learning_ yang digunakan dalam model predictive analytics ini. berikut penjelasan dari model-model yang akan saya gunakan dalam proyek ini:

- K-Neighbors
  <br> K-nearest neighbor adalah salah satu algoritma Machine Learning yang bersifat supervised yang digunakan untuk mengklasifikasikan suatu data. Prinsip di balik metode nearest neighbor adalah menemukan sejumlah data training yang sudah ditentukan dan menghitung jarak yang paling dekat dengan jarak ke titik baru, serta memprediksi label dari data yang baru. Jumlah sampel dapat berupa konstanta yang ditentukan pengguna (k-nearest neighbor learning).

- Random Forest
  <br> Random forest (RF) adalah suatu algoritma yang digunakan pada klasifikasi data dalam jumlah yang besar. Klasifikasi random forest dilakukan melalui penggabungan pohon (tree) dengan melakukan training pada sampel data yang dimiliki. Penggunaan pohon (tree) yang semakin banyak akan mempengaruhi akurasi yang akan didapatkan menjadi lebih baik. Penentuan klasifikasi dengan random forest diambil berdasarkan hasil voting dari tree yang terbentuk. Pemenang dari tree yang terbentuk ditentukan dengan vote terbanyak. Pembangunan pohon (tree) pada random forest sampai dengan mencapai ukuran maksimum dari pohon data.
  ![Random_forest](https://miro.medium.com/max/724/0*f_qQPFpdofWGLQqc.png)

## Data Understanding

Data understanding adalah sebuah tahapan di dalam metodologi sains data dan pengembangan AI yang bertujuan untuk mendapatkan pemahaman awal mengenai data yang dibutuhkan untuk memecahkan permasalahan bisnis yang diberikan.

Himpunan data berisi informasi tentang opsi pemesanan penerbangan dari situs Web Easemytrip untuk perjalanan penerbangan antara 6 kota metro teratas di India. Ada 300000 baris data dan 12 fitur dalam himpunan data yang dibersihkan. Dataset ini dapat diunduh di: [Kaggle : Flight Price Prediction](https://www.kaggle.com/datasets/shubhambathwal/flight-price-prediction?select=Clean_Dataset.csv).

Berikut informasi pada dataset:

- Dataset memiliki format CSV (Comma-Seperated Values). Terdapat 3 CSV di dalamnya, yaitu Clean_Dataset, business, dan economy.
- Dari ketiga dataset tersebut, saya menggunakan Clean_Dataset untuk melakukan penelitian. Dataset tersebut memiliki 300.000 sample dengan 12 fitur di dalamnya.
- Dataset memiliki 8 fitur bertipe object, 2 fitur bertipe int64, dan 1 fitur bertipe float64.
- Tidak ada missing value dalam dataset.

### Variabel-variabel pada Flight Price Prediction adalah sebagai berikut:

1. Airline: Nama perusahaan penerbangan disimpan di kolom maskapai penerbangan, ini adalah fitur kategori yang memiliki 6 maskapai berbeda.
2. Flight: Penerbangan menyimpan informasi mengenai kode penerbangan pesawat, ini adalah fitur kategori.
3. Source City: Kota tempat penerbangan lepas landas, ini adalah fitur kategori yang memiliki 6 kota unik.
4. Departure Time: Ini adalah fitur kategori turunan yang diperoleh yang diperoleh dengan mengelompokkan periode waktu ke dalam tempat sampah, ini menyimpan informasi tentang waktu keberangkatan dan memiliki 6 label waktu unik.
5. Stops: Fitur kategori dengan 3 nilai berbeda yang menyimpan jumlah perhentian antara kota sumber dan tujuan.
6. Arrival Time: Ini adalah fitur kategori turunan yang dibuat dengan mengelompokkan interval waktu ke dalam tempat sampah, ini memiliki enam label waktu yang berbeda dan menyimpan informasi tentang waktu kedatangan.
7. Destination City: Kota tempat penerbangan akan mendarat, ini adalah fitur kategoris yang memiliki 6 kota unik.
8. Class: Fitur kategori yang berisi informasi tentang kelas kursi; ia memiliki dua nilai yang berbeda: Bisnis dan Ekonomi.
9. Duration: Fitur berkelanjutan yang menampilkan jumlah keseluruhan waktu yang diperlukan untuk melakukan perjalanan antar kota dalam hitungan jam.
10. Days Left: Ini adalah karakteristik turunan yang dihitung dengan mengurangi tanggal perjalanan berdasarkan tanggal pemesanan.
11. Price: Target variabel menyimpan informasi harga tiket.

## Data Preparation

### Univariate Analysis

Univariate Analysis adalah menganalisis setiap fitur secara terpisah.

#### Analisis jumlah nilai pada setiap fitur kategorik

Disini saya menghitung masing-masing kolom serta melihat berapa banyak isi dalam kolom tersebut.

- Airline
  <div><img src="https://user-images.githubusercontent.com/86810501/193819954-50c2c79c-1dfc-4db3-8903-0f2479c3b6cc.jpg" width="220"/></div>

- Flight
  <div><img src="https://user-images.githubusercontent.com/86810501/193819991-8ec625ff-b594-44dd-a85d-9b28f960c408.jpg" width="220"/></div>
  Fitur Flight memiliki banyak sekali nilai unique. Untuk menghindari high dimensional data, maka fitur ini akan dihapus.

- Source City
  <div><img src="https://user-images.githubusercontent.com/86810501/193820003-81372d6c-4f1d-41b9-b3c8-e37c9b1ddccf.jpg" width="220"/></div>

- Departure Time
  <div><img src="https://user-images.githubusercontent.com/86810501/193820014-211a381e-608d-4890-af1c-2758f884f62b.jpg" width="220"/></div>

- Arrival Time
  <div><img src="https://user-images.githubusercontent.com/86810501/193820032-2299c486-f85e-482c-b7f0-97d28530efcf.jpg" width="220"/></div>

- Destination City
  <div><img src="https://user-images.githubusercontent.com/86810501/193820040-89afd424-4061-4154-b00c-81350ddf48a9.jpg" width="220"/></div>

- Class
  <div><img src="https://user-images.githubusercontent.com/86810501/193820026-05e13223-4554-42e2-a9b5-af0715f33f5a.jpg" width="220"/></div>

Terlihat bahwa semua fitur kategorik diatas memiliki sebaran sample yang cukup merata. Kecuali fitur flight yang dimana ia memiliki banyak sekali nilai unique, jadi saya drop fitur tersebut.

#### Analisis sebaran pada setiap fitur numerik

<div><img src="https://user-images.githubusercontent.com/86810501/193820053-78a0d221-7bcb-4b3f-b44e-eda2eb58644d.jpg" width="450"/></div><br />
Berikut analisis dari grafik di atas:

- Peningkatan harga tiket penerbangan sebanding dengan penurunan jumlah sampel. Hal ini dapat kita lihat jelas dari histogram "price" yang grafiknya mengalami penurunan seiring dengan semakin banyaknya jumlah sampel.
- Rentang harga tiket penerbangan cukup tinggi, yaitu dari skala ratusan hingga 90000.
- Rata-rata harga tiket penerbangan berada di 30000. Distribusi harga yang kurang bagus sehingga dapat berimplikasi pada model.

### Multivariate Analysis

Multivariate Analysis menunjukkan hubungan antara dua atau lebih fitur dalam data.

#### Analisis fitur kategorik

Pada tahap ini kita akan melihat korelasi antara fitur kategorik dengan fitur target yaitu price

- Rata-rata "Price" relatif terhadap Airline
  <div><img src="https://user-images.githubusercontent.com/86810501/193828251-bcba4065-5cd6-47a9-bdb2-dfb1c09ea76e.jpg" width="450"/></div>
  Pada fitur 'airline', rata-rata harga cenderung tak beraturan. Grade tertinggi yaitu grade Vistara memiliki harga 30000 lebih tinggi diantara grade lainnya. Sehingga, fitur airline memiliki pengaruh atau dampak yang kecil terhadap rata-rata harga.

- Rata-rata "Price" relatif terhadap Source City
  <div><img src="https://user-images.githubusercontent.com/86810501/193828259-3221cd3b-b9f7-4335-a973-fa78df378438.jpg" width="450"/></div>
  Pada fitur 'source_city', rata-rata harga cenderung mirip. Rentangnya berada antara 18000 hingga 30000. Dari sini dapat disimpulkan bahwa kota tempat penerbangan lepas landas memiliki pengaruh yang rendah terhadap harga.

- Rata-rata "Price" relatif terhadap Departure Time
  <div><img src="https://user-images.githubusercontent.com/86810501/193828303-31fa4f72-f0a0-4217-90ed-951e68cea7c3.jpg" width="450"/></div>
  Pada fitur 'departure time', waktu keberangkatan sedikit berpengaruh terhadapt harga.

- Rata-rata "Price" relatif terhadap Arrival Time
  <div><img src="https://user-images.githubusercontent.com/86810501/193828275-2d31db02-b225-4e00-a615-5a55501e52b4.jpg" width="450"/></div>
  Pada fitur 'arrival time', waktu kedatangan cenderung lebih berpengeruh terhadap harga.

- Rata-rata "Price" relatif terhadap Destination City
  <div><img src="https://user-images.githubusercontent.com/86810501/193828286-e3ee9fc1-d8b0-4454-89fa-4a9938663caf.jpg" width="450"/></div>
  Pada fitur 'destination city', rata-rata harganya cenderung mirip. Rentangnya berada di antara 18000 hingga 25000.

- Rata-rata "Price" relatif terhadap Class
  <div><img src="https://user-images.githubusercontent.com/86810501/193828313-0f3135b3-a5ad-4abc-bf49-37abf1e7d354.jpg" width="450"/></div>
  Pada fitur 'class', dapat kita lihat bahwa class yang ada pada business lebih tinggi harganya dibanding dengan economy. Ini sangat berpengaruh terhadap harga, sebab dari kedua kategori tersebut memiliki fasilitas yang berbeda.

Kesimpulan akhir, fitur kategori ini memiliki pengaruh yang signifikan terhadap harga.

#### Analisis fitur numerik

- Mengamati hubungan antar fitur numerik
  <div><img src="https://user-images.githubusercontent.com/86810501/193828333-6b23dd6d-8161-4d6e-83d0-128506bc388d.jpg" width="450"/></div>

- Melihat kolerasi antara semua fitur numerik
  <div><img src="https://user-images.githubusercontent.com/86810501/193828358-b90344cf-b789-407b-a0e7-ee5086c543d5.jpg" width="350"/></div>
  Jika kita amati, fitur 'duration' memiliki skor korelasi yang besar berada di 0.22 dengan fitur target 'price'. Sementara itu, fitur 'days_left' memiliki korelasi yang sangat kecil yaitu -0.09. Sehingga, fitur tersebut dapat di-drop.

## Check Outliers

Menurut Kuhn dan Johnson dalam Applied Predictive Modeling, Outliers adalah sampel yang nilainya sangat jauh dari cakupan umum data utama. Ia adalah hasil pengamatan yang kemunculannya sangat jarang dan berbeda dari data hasil pengamatan lainnya.

#### Menjabarkan outliers

- Duration
  <div><img src="https://user-images.githubusercontent.com/86810501/193832815-a8ac50fd-15d2-44d1-8ff0-3d6a5522bba5.jpg" width="450"/></div>

- Price
  <div><img src="https://user-images.githubusercontent.com/86810501/193832822-39d54582-b1a8-4999-95ab-09f2f05e8c03.jpg" width="450"/></div>

Jika kita perhatikan kembali, pada beberapa fitur numerik di atas terdapat outliers. Kita akan mengatasi outliers tersebut dengan menggunakan metode IQR. Menggunakan metode IQR ini tujuannya untuk mengidentifikasi outlier yang berada di luar Q1 dan Q3. Nilai apa pun yang berada di luar batas ini akan dianggap sebagai outlier.

### Menangani outliers menggunakan metode IQR

- Berikut adalah ilustrasi dan penjelasan nilai statistik pada boxplot
  <div><img src="https://user-images.githubusercontent.com/86810501/193832839-79f393aa-3039-4aa2-8ff4-63ff5cb0dc2f.jpg" width="450"/></div>

Hal pertama yang perlu Kita perhatikan adalah membuat batas bawah dan batas atas. Untuk membuat batas bawah, kurangi Q1 dengan 1.5 _ IQR. Kemudian, untuk membuat batas atas, tambahkan 1.5 _ IQR dengan Q3.

- Berikut persamaannya:
  Batas bawah = Q1 - 1.5 _ IQR
  Batas atas = Q3 + 1.5 _ IQR

## Data Preparation

- One Hot Encoding
  <br> One hot encoding adalah teknik mengubah data kategorik menjadi data numerik dimana setiap kategori menjadi kolom baru dengan nilai 0 atau 1. Fitur yang akan diubah menjadi numerik pada proyek ini adalah 'airline', 'source_city', 'departure_time', 'arrival_time', 'destination_city', dan 'class'.

- Train Test Split
  <br> Train test split aja proses membagi data menjadi data latih dan data uji. Data latih akan digunakan untuk membangun model, sedangkan data uji akan digunakan untuk menguji performa model. Pada proyek ini dataset sebesar 297920 dibagi sebesar 70:30 sehingga dapat jumlahnya menjadi 208544 untuk data latih dan 89376 untuk data uji.

- Standarisasi
  <br> Standardisasi adalah teknik transformasi yang paling umum digunakan dalam tahap persiapan pemodelan. Untuk fitur numerik, kita tidak akan melakukan transformasi dengan one-hot-encoding seperti pada fitur kategori. Kita akan menggunakan teknik StandarScaler dengan sklearn.preprocessing.StandardScaler.

## Modeling

Pada tahap ini kita akan membuat tiga buah model _Machine Learning_ dengan algoritma berikut:

- K-Nearest Neighbor (KNN)
  <br> K-Nearest Neighbour bekerja dengan membandingkan jarak satu sampel ke sampel pelatihan lain dengan memilih sejumlah k tetangga terdekat. Proyek ini menggunakan [sklearn.neighbors.KNeighborsRegressor](https://scikit-learn.org/stable/modules/generated/sklearn.neighbors.KNeighborsRegressor.html) dengan memasukkan X_train dan y_train dalam membangun model. Parameter yang digunakan pada proyek ini adalah:

  - `n_neighbors` = Jumlah k tetangga tedekat.

  Disini saya memasukkan n_neighbors atau k sebanyak 10 tetangga.

- Random Forest
  <br> Algoritma random forest adalah teknik dalam _Machine Learning_ dengan metode ensemble. Teknik ini beroperasi dengan membangun banyak decision tree pada waktu pelatihan. Proyek ini menggunakan [sklearn.ensemble.RandomForestRegressor](https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.RandomForestRegressor.html) dengan memasukkan X_train dan y_train dalam membangun model. Parameter yang digunakan pada proyek ini adalah :

  - `n_estimators` = Jumlah maksimum estimator di mana boosting dihentikan.

  Untuk n_estimators saya masukkan angka sebesar 50 estimator.

  - `max_depth` = Kedalaman maksimum setiap tree.

  Untuk max_depth saya masukkan angka sebesar 16.

  - `random_state` = Mengontrol seed acak yang diberikan pada setiap base_estimator pada setiap iterasi boosting.

  Untuk random_state saya masukkan angka sebesar 55.

  - `n_jobs` = Jumlah job yang digunakan secara paralel. Ia merupakan komponen untuk mengontrol thread atau proses yang berjalan secara paralel.

  Untuk n_jobs diberikan nilai -1 yang artinya semua proses berjalan secara paralel.

- AdaBoost
  <br> AdaBoost juga disebut Adaptive Boosting adalah teknik dalam _Machine Learning_ dengan metode ensemble. Algoritma yang paling umum digunakan dengan AdaBoost adalah pohon keputusan (decision trees) satu tingkat yang berarti memiliki pohon Keputusan dengan hanya 1 split. Pohon-pohon ini juga disebut Decision Stumps. Algoritma ini bertujuan untuk meningkatkan performa atau akurasi prediksi dengan cara menggabungkan beberapa model sederhana dan dianggap lemah (weak learners) secara berurutan sehingga membentuk suatu model yang kuat (strong ensemble learner). Proyek ini menggunakan [sklearn.ensemble.AdaBoostRegressor](https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.AdaBoostRegressor.html) dengan memasukkan X_train dan y_train dalam membangun model. Parameter yang digunakan pada proyek ini adalah:

  - `learning_rate` = Bobot yang diterapkan pada setiap regressor di masing-masing proses iterasi boosting.

  Untuk learning_rate yang diterapkan adalah 0.05

  - `random_state` = Digunakan untuk mengontrol random number generator yang digunakan.

  Untuk random_state saya masukkan angka sebesar 55.

## Evaluation

Metrik evaluasi yang akan kita gunakan pada prediksi ini adalah MSE atau Mean Squared Error yang menghitung jumlah selisih kuadrat rata-rata nilai sebenarnya dengan nilai prediksi. MSE didefinisikan sebagai persamaan berikut:

<div><img src="https://user-images.githubusercontent.com/86810501/193994956-4cb2df0a-2379-44fd-9f04-cec67983cbc3.jpg" width="300"/></div>

Berikut hasil evaluasi pada proyek ini :

- Hasil evaluasi pada proyek ini:

|  model   |    train     |     test     |
| :------: | :----------: | :----------: |
|   KNN    | 13684.968264 | 15261.179694 |
|    RF    | 13311.047334 | 14410.958053 |
| Boosting | 36444.675468 | 36242.291304 |

## Conclusion

Model prediksi harga tiket penerbangan telah selesai dibuat dan model ini dapat digunakan untuk memprediksi data yang sebenarnya. Berdasarkan model tersebut dapat diketahui bahwa algoritma terbaik dalam model ini adalah _Random Forest_ & _K-Neighbor_ karena memiliki akurasi yang stabil baik itu pada data training maupun data testing (Good fits)

![MSE](https://user-images.githubusercontent.com/86810501/193842490-04277b31-4278-4a8d-82af-79cb66cc9f9b.jpg)

Hasil prediksi dari pengujian terhadap MSE

![Prediksi terhadap MSE](https://user-images.githubusercontent.com/86810501/193847377-093fd692-dd48-4ff5-8c32-7575ee87b3cc.jpg)

Dari model prediksi diatas dapat dilihat bahwa, model dengan algoritma _Random Forest_ memiliki akurasi lebih tinggi dan tingkat error lebih kecil. Sedangkan _K-Neighbor_ hampir mendekati tetapi memiliki tingkat eror yang lebih naik sedikit dari _Random Forest_. Namun dalam prediksi dengan model algoritma _Random Forest_ ini memberikan hasil yang paling mendekati dibandingkan algoritma lainnya.
