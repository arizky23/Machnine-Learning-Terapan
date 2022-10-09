# Proyek Akhir Book Recommendation Dataset - Ananda Rizky Nurhidayat

## Project Overview

Sistem rekomendasi adalah salah satu fitur pada sebuah perangkat lunak yang sangat bermanfaat untuk memudahkan pengguna. Sistem rekomendasi sendiri sangat diperlukan dikarenakan terlalu banyaknya jenis dan jumlah data yang ada. Dengan adanya sistem rekomendasi, pengguna akan dimanjakan dengan rekomendasi–rekomendasi buku yang sesuai dengan preferensi masing–masing pengguna, sehingga pengguna tidak perlu repot melakukan pencarian buku yang diinginkan. Sistem rekomendasi sendiri harus dapat menganalisis sekian banyak data tentang pengguna dan buku yang tersedia, dapat juga didukung dengan data rating agar hasil yang diberikan lebih akurat.

Teknik untuk sebuah sistem rekomendasi pada buku yang telah ada adalah Content-Based Filtering dan Collaborative Filtering. Content-Based Filtering merupakan teknik untuk mempelajari profil minat pengguna baru berdasarkan data dari objek yang telah dinilai sebelumnya oleh pengguna. Sedangkan, Collaborative Filtering bergantung pada pendapat komunitas pengguna. Ia tidak memerlukan atribut untuk setiap itemnya seperti pada sistem berbasis konten.

![CF CBF](https://user-images.githubusercontent.com/86810501/194766309-cb8efe3e-c260-4d3c-a28a-87d6479357ee.jpg)

Pada proyek ini, data yang saya pakai adalah data rekomendasi buku yang dimana ini penting untuk diselesaikan. Karena dapat memudahkan pelanggan untuk melihat rekomendasi buku lain ketika berbelanja di toko buku secara online. Dengan membaca pola data, mudah bagi kita merekomendasikan buku kepada seorang pelanggan. Selain dapat membantu pengguna dalam memberikan referensi buku, kita juga mendapatkan keuntungan dalam meningkatkan minat berbelanja dan keingin-tahuan pelanggan terhadap buku yang direkomendasikan sehingga tingkat penjualan pun akan meningkat.

## Business Understanding

Dengan menggunakan dataset tersebut kita dapat mengolah terkait informasi buku, penilaian yang diberikan terhadap buku tersebut, serta mengolah data pengguna yang ada. Kita akan menggunakan sistem rekomendasi ini untuk memprediksi rating atau preferensi pengguna terhadap buku tertentu. Sistem ini tidak merekomendasikan secara spesifik, namun ia merekomendasikan sejumlah item yang mungkin cocok dengan preferensi si pengguna. Oleh karena itu pada sistem rekomendasi ini kita akan memperoleh keluaran berupa "top-N" recommendation. Dengan menggunakan sistem ini, diharapkan penjual akan mengalami peningkatan karena pengguna akan mendapatkan rekomendasi terkait buku yang telah ia beli ataupun yang telah ia beri penilaian.

### Problem Statements

Tentunya tidak mudah bagi kita membuat sebuah sistem yang dapat merekomendasikan buku dengan tujuan memperoleh keluaran berupa top-N recommendation.

- Bagaimana sebuah toko online dapat merekomendasikan buku-buku lain yang mungkin pengguna akan suka terhadap tersebut dan belum pernah dibaca oleh si pengguna?
- Bagaimana cara untuk mempelajari profil minat pengguna baru berdasarkan data dari objek yang telah dinilai sebelumnya oleh pengguna?

### Goals

Tujuan dari proyek ini adalah:

- Kita dapat membuat sistem rekomendasi mengenai buku-buku lain yang mungkin pengguna akan suka terhadap tersebut dan belum pernah dibaca oleh si pengguna menggunakan teknik Collaborative Filtering.
- Kita dapat membuat sistem rekomendasi menggunakan teknik Content-Based Filtering untuk mempelajari profil minat pengguna baru berdasarkan data dari objek yang telah dinilai sebelumnya oleh pengguna

### Solution statements

Dalam proyek ini kita akan menggunakan dua teknik sistem rekomendasi untuk menyelesaikan permasalahan tersebut. Dua teknik tersebut adalah Content-Based Filtering dan Collaborative Filtering.

- **Content-Based Filtering** adalah merekomendasikan item yang mirip dengan item yang disukai pengguna di masa lalu. teknik ini mempelajari profil minat pengguna baru berdasarkan data dari objek yang telah dinilai pengguna. teknik ini bekerja dengan menyarankan item serupa yang pernah disukai di masa lalu atau sedang dilihat di masa kini kepada pengguna. Semakin banyak informasi yang diberikan pengguna, semakin baik akurasi sistem rekomendasi tersebut.

![CBF](https://user-images.githubusercontent.com/86810501/194766480-230f6174-d62b-4cc6-b6e6-e5f55d36f09b.jpg)

- **Collaborative Filtering** adalah salah satu teknik rekomendasi yang popular yang prediksi dan rekomendasinya berbasis pada nilai _rating_ atau tingkah laku dari pengguna lain dalam sistem tersebut. Kelebihan dari teknik ini adalah memungkinkan pengguna aktif untuk mendapatkan rekomendasi berdasarkan produk yang pengguna telah beli dan diberi _rating_ positif. Dan dengan menggunakan _rating_, pengguna aktif dan riwayat transaksi untuk membangun model yang menyediakan satu set baru produk serupa. Namun kekurangan pada teknik ini adalah penggunanya tidak bisa memilih pengguna mana yang ingin dijadikan acuan agar mendapatkan rekomendasi produk yang diinginkan.

![CF](https://user-images.githubusercontent.com/86810501/194766482-8d2b0154-daf5-4129-9985-3f940597534f.jpg)

## Data Understanding

Dataset yang saya gunakan adalah Book Recommendation Dataset. Dataset ini dapat diunduh di: [Kaggle : Book Recommendation Dataset](https://www.kaggle.com/datasets/arashnic/book-recommendation-dataset?select=Books.csv). Dataset memiliki 3 file berformat CSV (Comma-Seperated Values) di dalamnya yaitu Books, Ratings, dan Users.

#### Variabel-variabel pada Book Recommendation Dataste adalah sebagai berikut:

Dataset pertama yaitu 'Books'. Dataset ini memiliki 8 buah kolom, yakni:

1. 'ISBN', merupakan identifikasi dari masing-masing buku.
2. 'Book-Title', merupakan judul buku.
3. 'Book-Author', merupakan penulis buku.
4. 'Year-Of-Publication', merupakan tahun dipublikasikannya buku.
5. 'Publisher', merupakan penerbit buku.
6. 'Image-URL-S', merupakan URL gambar cover buku dalam ukuran S(Small).
7. 'Image-URL-M', merupakan URL gambar cover buku dalam ukuran M(Medium).
8. 'Image-URL-L', merupakan URL gambar cover buku dalam ukuran L(Large).

Dataset kedua yaitu 'Users'. Dataset ini memiliki 3 buah kolom, yakni:

1. 'User-ID', berisi ID pengguna dari toko buku online.
2. 'Location', berisi lokasi pengguna.
3. 'Age', berisi usia pengguna.

Dataset ketiga yaitu 'Ratings'. Dataset ini memiliki 3 buah kolom, yakni:

1. 'User-ID', yang berisi ID dari user yang memberikan rating terhadap buku.
2. 'ISBN', merupakan identifikasi buku atau nomor buku yang diberi rating oleh user.
3. 'Book-Rating', berisi nilai Rating dari buku, skala yang ada dalam rating ini yakni dari 0-10.

Dalam tahap ini saya menggunakan proses _Univariate EDA(Exploratory Data Analysis)_ dengan menjabarkan masing-masing variabel yang sudah dijelaskan sebelumnya. Karena masing-masing dataset memiliki jumlah sangat banyak yakni lebih dari 250.000, maka saya hanya mengambil sebanyak 4500 data dari setiap variabel yang nantinya akan kita gunakan dalam proses pembuatan sistem rekomendasi ini.

## Data Preparation

Tahapan yang saya gunakan pada Data Preparation ini adalah:

- **Mengatasi _Missing Value_**.
  <br> Tahap ini diperlukan karena dengan tidak adanya _Missing Value_ atau nilai yang hilang, kita dapat membuat performa pada saat pemodelan itu menjadi lebih baik. Langkah pertama yang saya gunakan untuk mengecek apakah terdapat _Missing Value_ atau tidak yaitu dengan menggunakan fungsi .isnull().sum(). Apabila terdapat sebuah nilai yang hilang atau null, maka kita akan melakukan drop fitur terhadap kolom yang terdapat _Missing Value_ tersebut dengan menggunakan fungsi .dropna().

- **Membuang Data Duplikat**.
  <br> Tahap selanjutnya ialah membuang data yang terduplikat. Dalam hal ini kita hanya menggunakan data unik untuk dimasukkan ke dalam proses pemodelan sehingga kita perlu menghapusnya agar tidak memiliki data yang bertumpuk dengan format atau nama yang sama. Langkah untuk menghapus data duplikat tersebut yaitu dengan menggunakan fungsi .drop_duplicates() dan kita definisikan variabel mana yang akan kita hindari terhadap duplikasi data tersebut. Disini saya menggunakan variabel dari 'ISBN'.

- **Konversi Data Series menjadi List**
  <br> Tahap berikutnya kita akan membuat sebuah dictionary yang di dalamnya terdapat informasi diantaranya yaitu book_id, book_title, dan book_author. Sebelum kita membuat sebuah dictionary, kita akan mengubah terlebih dahulu informasi yang disebutkan sebelumnya ke dalam sebuah list. Untuk mengonversi data series tersebut menjadi ke dalam bentuk list, kita perlu menerapkan fungsi .tolist() dari library numpy.

- **Membuat _Dictionary_**
  <br> Dalam tahap ini kita akan membuat dictionary untuk menentukan pasangan key-value pada data book_id, book_title, dan book_author yang telah kita siapkan sebelumnya. Tahapan ini penting dikarenakan kita akan melihat informasi dari data terkait 3 variabel tersebut sebelum dimasukkan ke dalam tahap pemodelan.

## Modeling

Pada tahap ini saya akan mengembangkan sistem rekomendasi dengan menggunakan dua teknik untuk menyajikan 'top-N' recommendation sebagai solusi dalam permasalahan sebelumnya, yakni dengan menggunakan teknik _Content-Based Filtering_ dan _Collaborative Filtering_.

Berikut langkah yang digunakan dalam penerapan model dengan _Content-Based Filtering_:

1. TF-IDF Vectorizer.
   <br> Pada tahap ini, kita akan membangun sistem rekomendasi menggunakan teknik TF-IDF Vectorizer yang dimana teknik tersebut digunakan untuk menemukan representasi fitur penting dari setiap kategori buku. untuk menggunakannya kita gunakan fungsi tfidfvectorizer() dari library sklearn.
2. Fit & Transform.
   <br> Disini saya melakukan fit pada 'book_title' kemudian ditransformasikan ke dalam bentuk matriks.
3. Menampilkan vektor TF-IDF ke dalam bentuk matriks dengan menggunakan fungsi todense().
4. Membuat dataframe untuk melihat tf-idf matriks, kemudian kolom diisi dengan judul buku dan baris diisi dengan author buku.
5. _Cosine Similarity_.
   <br> Tahap ini adalah menghitung derajat kesamaan (similarity degree) antar buku dengan teknik cosine similarity. Di sini, saya menggunakan fungsi cosine_similarity dari library sklearn.
6. Membuat dataframe dari variabel cosine_sim dengan baris dan kolom berupa author buku.
7. Mendapatkan Rekomendasi.
   <br> Disini saya membuat fungsi dengan nama book_recommendations untuk mendapatkan rekomendasi dengan memasukan parameter berupa nama penulis buku, penulis yang saya masukkan ke dalam parameter tersebut ialah Andre Dubus III. Berikut adalah hasil rekomendasi yang saya dapatkan dari proses tersebut.

   |     |     book_author     |               book_title                |
   | :-: | :-----------------: | :-------------------------------------: |
   |  0  | Mark Z. Danielewski |             House of Leaves             |
   |  1  |   William Sleator   |             House of Stairs             |
   |  2  |   James Patterson   |               The Jester                |
   |  3  |   James Patterson   |               2nd Chance                |
   |  4  |   James Patterson   |             The Beach House             |
   |  5  |   James Patterson   | Along Came a Spider (Alex Cross Novels) |
   |  6  |   James Patterson   |   Jack &amp; Jill (Alex Cross Novels)   |
   |  7  |   James Patterson   |    Roses Are Red (Alex Cross Novels)    |
   |  8  |   James Patterson   |            The Midnight Club            |
   |  9  |   James Patterson   |              Black Friday               |

   Dari hasil rekomendasi di atas, kita telah mampu menampilkan 10 buku dengan kategori yang mirip dengan buku yang ditulis oleh Andre Dubus III tersebut.

Untuk solusi permasalahan kedua yaitu kita akan menggunakan teknik _Collaborative Filtering_, untuk langkah-langkahnya yaitu sebagai berikut:

1. Melakukan Encode(penyandian) pada fitur 'User-ID' dan 'ISBN' ke dalam indeks integer. Kemudian lakukan hal yang sama pada fitur 'ISBN'.
2. Lakukan Mapping dari 'User-ID' ke dataframe user, dan 'ISBN' ke dataframe buku.
3. Membagi data train dengan data validation dengan komposisi 80:20.
4. Membuat kelas RecommenderNet dengan proses menghitung skor kecocokan antara user dan buku didalamnya dan menggunakan teknik embedding terhadap data user dan book.
5. Menginisialisasi model dengan memanggil class RecommenderNet yang telah dibuat, kemudian melakukan compile model menggunakan Binary Crossentropy untuk menghitung loss function, Adam(Adaptive Moment Estimation) sebagai optimizernya, dan root mean squared error(RMSE) sebagai metrics evalutaion.
6. Melakukan proses training dengan menggunakan fungsi .fit() dan parameternya yaitu batch_size = 8 serta epochsnya sebanyak 100. Berikut adalah hasil dari metrik evaluasi menggunakan library matplotlib.
7. Mendapatkan Rekomendasi.
   <br> Mendapatkan Rekomendasi Buku dengan cara definisikan variabel book_not_visited, dimana variabel ini merupakan daftar buku yang belum pernah dikunjungi oleh pengguna. Berikut adalah hasil rekomendasi yang saya dapatkan menggunakan teknik Collaborative Filtering.

   | Showing book by author recommendations for users: 277962                                     |
   | -------------------------------------------------------------------------------------------- |
   | ------------------------------------                                                         |
   | Top 10 Book Author Recommendation                                                            |
   | ------------------------------------                                                         |
   | James Finn Garner : Politically Correct Bedtime Stories: Modern Tales for Our Life and Times |
   | Sylvia Plath : The Bell Jar : A Novel (Perennial Classics)                                   |
   | David Sedaris : Me Talk Pretty One Day                                                       |
   | Andre Dubus III : House of Sand and Fog                                                      |
   | OSCAR WILDE : The Picture of Dorian Gray (Modern Library (Paperback))                        |
   | Sheri S. Tepper : The Family Tree                                                            |
   | Maeve Binchy : This Year It Will Be Different: And Other Stories                             |
   | K. A. Applegate : The Encounter (Animorphs , No 3)                                           |
   | Jack Canfield : Chicken Soup for the Woman's Soul (Chicken Soup for the Soul Series (Paper)) |
   | Carlos Ruiz Zafon : La Sombra del Viento                                                     |

   Hasil di atas adalah rekomendasi untuk user dengan id 277962. Dari output tersebut, kita telah memberikan rekomendasi buku berdasarkan pengarangnya.

## Evaluation

**Content-Based Filtering**
Di tahap ini saya menggunakan metrik evaluasi yang bernama _Presicion_. Precision adalah jumlah item rekomendasi yang relevan. Kita tidak bisa menghitung dengan memanggil library scikit learn karena tidak ada data target/label seperti pada supervised learning.

![precision](https://user-images.githubusercontent.com/86810501/194769741-822c7221-ba85-44f8-8828-b3c163a277c4.jpg)

Dari proses ini, kita berhasil memberikan rekomendasi berupa 10 judul buku dengan kategori book_authornya adalah Mark Z. Danielwski, William Sleator, dan James Patterson.

**Collaborative Filtering**

Di tahap ini saya menggunakan metrik evaluasi yang bernama _RMSE(root mean squarred error)_. RMSE ini merupakan besarnya tingkat kesalahan hasil prediksi, dimana semakin kecil (mendekati 0) nilai RMSE maka hasil prediksi akan semakin akurat. Berikut adalah hasil evaluasi menggunakan metode RMSE.

![metrik evaluasi](https://user-images.githubusercontent.com/86810501/194756059-f04633ad-7d36-4f1e-9547-ebcbc8263688.jpg)

Dari proses ini, kita memperoleh nilai error akhir pada data latih sebesar sekitar 0.13 dan error pada data validasi sebesar 0.38. Nilai tersebut cukup bagus untuk sebuah sistem rekomendasi.
