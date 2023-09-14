# Laporan Proyek Machine Learning - Fajar Zulkautsari Muhammad

## Project Overview

Belakangan ini, industri film telah mengalami pertumbuhan yang luar biasa[[1]](https://journal.untar.ac.id/index.php/koneksi/article/view/21509). Sebagian besar didorong oleh perkembangan teknologi dan perubahan dalam cara kita mengakses hiburan. Dengan semakin banyaknya platform streaming seperti Netflix, Amazon Prime Video, Hulu, Disney+, dan banyak lainnya, pengguna memiliki akses ke ribuan judul film dan acara TV yang dapat di-streaming kapan saja dan di mana saja. Kemajuan dalam teknologi internet telah memungkinkan pengalaman streaming yang mulus dan berkualitas tinggi. Di samping itu, keberagaman konten film yang ditawarkan oleh platform-platform ini, mulai dari film Hollywood terbaru hingga produksi independen dan dokumenter, memberikan pengguna beragam pilihan hiburan.

Dalam konteks ini, sistem rekomendasi film berdasarkan genre memiliki peran yang semakin penting. Kemampuan platform streaming untuk merekomendasikan film-film yang sesuai dengan preferensi pengguna telah menjadi salah satu faktor kunci dalam mempertahankan pelanggan dan mendapatkan pelanggan baru[[2]](https://www.mdpi.com/2227-7390/11/4/895). Personalisasi pengalaman pengguna yang didasarkan pada sejarah penontonan dan pola penontonan, telah menjadi fokus utama untuk meningkatkan retensi pelanggan. Dengan data genre film dan algoritma pembandingan yang cerdas, sistem rekomendasi ini dapat membantu pengguna menavigasi melalui berbagai pilihan film yang ada dan meningkatkan kepuasan mereka dalam menemukan konten hiburan yang sesuai dengan selera mereka. Dengan pertumbuhan pesat konten digital dan pengaruh media sosial dalam berbagi rekomendasi, sistem rekomendasi film berbasis genre menjadi salah satu aspek penting dalam industri film yang berkembang secara signifikan.

## Business Understanding
### Problem Statements
Masalah yang menjadi latar belakang proyek ini antara lain:
- Bagaimana cara meningkatkan kepuasan pengguna dalam platform streaming?
- Bagaimana pengguna platform streaming film bisa mendapatkan rekomendasi film yang sesuai?

### Goals
Tujuan dari proyek ini antara lain:
- Meningkatkan pengalaman pengguna dalam menemukan film-film baru yang mereka mungkin tidak ketahui sebelumnya.
- Memberikan rekomendasi film sesuai dengan genre kesukaan pengguna.

### Solution Statements:
Masalah dan tujuan yang telah diuraikan diatas dapat diselesaikan dengan pendekatan _Machine Learning_ untuk membuat sistem rekomendasi film dengan _Content-Based Filtering_. _Content-Based Filtering_ akan menjadikan konten yang disukai oleh pengguna sebelumnya sebagai acuan. Lalu, sistem rekomendasi akan memberikan konten (dalam konteks ini film) yang mempunyai derajat kemiripan yang tinggi terhadap konten yang disukai oleh pengguna sebelumnya atau berdasarkan histori tontonan pengguna. Dalam proyek ini, perhitungan derajat kemiripan akan dilakukan pada genre dari film. Hal ini berarti suatu film akan memberikan rekomendasi film lainnya dengan genre yang mirip atau bahkan sama persis. Dan hal itu juga bisa memberikan rekomendasi film-film dengan genre yang mirip yang mungkin sebelumnya tidak diketahui pengguna. 

## Data Understanding
Dataset yang digunakan adalah data _Movie System Recommender Datasat_. Dataset tersebut didapatkan dari situs [Kaggle](https://www.kaggle.com/datasets/gargmanas/movierecommenderdataset). Data tersebut terbagi menjadi 2 file yaitu [movies.csv](https://www.kaggle.com/datasets/gargmanas/movierecommenderdataset?select=movies.csv) dan [ratings.csv](https://www.kaggle.com/datasets/gargmanas/movierecommenderdataset?select=ratings.csv).

Variabel-variabel pada dataset movies.csv adalah sebagai berikut:
- movieId   : merupakan indeks film (sebagai id pembeda).
- title     : merupakan judul film.
- genres    : merupakan genre film

Variabel-variabel pada dataset ratings.csv adalah sebagai berikut:
- userId    : merupakan index/id user
- movieId   : merupakan indeks/id film.
- rating    : merupakan rating yang diberikan oleh user (dalam skala 5).
- timestamp : merupakan waktu saat rating diberikan

Dalam proyek ini, untuk sementara dataset yang digunakan hanya movies.csv. Dalam file tersebut terdapat 9742 data. Artinya dalam data tersebut terdapat 9742 film yang berbeda dan masing-masing film dideskripsikan dengan genre yang berbeda-beda. Namun setelah dilakukan eksplorasi, terdapat 5 data yang terindikasi memiliki duplikat pada kolom 'title'. Kelima data tersebut film memiliki judul yang sama dengan data lainnya, tetapi movieId dan genrenya berbeda. Pembersihan dilakukan terhadap data tersebut sehingga menyisakan 9737 data.

Selanjutnya juga ditemukan 34 film yang memiliki keterangan '(no genres listed)' yang menjelaskan bahwa film-film tersebut tidak terdeskripsikan genrenya secara baik. Sehingga tidak ada informasi genre pada 34 film tersebut. Karena pada proyek ini menggunakan genre sebagai fitur, 34 film tersebut dikecualikan dalam proyek ini. Sehingga total data film yang bisa digunakan adalah 9703 film. 

## Data Preparation
Proses data preparation dalam proyek sistem rekomendasi berbasis konten melibatkan persiapan dan pemrosesan data agar dapat digunakan oleh sistem rekomendasi. Langkah-langkah ini mencakup pengumpulan, pembersihan, pengolahan, dan pengaturan data agar dapat digunakan untuk menghasilkan rekomendasi yang akurat. Berikut adalah langkah-langkah utama dalam proses data preparation:

- **Pengumpulan Data:**
Tahap pertama adalah mengumpulkan data yang diperlukan untuk sistem rekomendasi. Data bersumber dari situs Kaggle. 
- **Pembersihan Data:**
Data yang diperoleh seringkali memerlukan pembersihan untuk mengatasi masalah data yang terduplikasi dan data yang tidak konsisten. Pembersihan data juga melibatkan penghapusan dan penanganan data yang tidak relevan, serta koreksi kesalahan data.
- **Ekstraksi Fitur:**
Selanjutnya, adalah mengekstraksi fitur-fitur relevan dari data yang tersedia. Dalam konteks ini, fitur yang tersedia adalah genre film yang akan digunakan untuk mengukur kesamaan antara item. Data film memiliki kolom genre yang berisi daftar genre untuk setiap film. Data tersebut masih berantakan sehingga perlu menggunakan  one-hot encoding untuk mendapatkan data yang bagus. dalam one-hot encoding, setiap genre adalah fitur biner yang menunjukkan keberadaan atau ketiadaan genre tersebut pada setiap film.
- **Transformasi Data:**
Dataframe transformasi kedalam bentuk tabel pivot dengan 'title' sebagai pivot untuk mendapatkan tabel korelasi antar semua film. Tabel pivot ini nantinya akan berisikan data kemiripan antar film.

## Modeling
Model development yang digunakan pada proyek ini adalah _content-based filtering_. Model ini dipilih karena cukup relevan dengan data yang tersedia, yaitu data film dengan fitur berupa macam-macam genrenya. Cara kerja model ini diilustrasikan pada gambar di bawah :

![1 Lr6qL0YjY_WqVK5u-AYHAQ](https://github.com/Loically/Movies_System_Recommender/assets/114181235/3aea8555-7ccb-4be7-b0a6-d83116c792bf)

Ketika seorang pengguna menyukai film A, maka sistem akan merekomendasikan film B dengan genre yang sama dengan film A. Asumsi yang muncul pada konteks ini adalah pengguna akan menyukai film dengan genre yang sama. Sehingga, ada kemungkinan pengguna juga menyukai film B yang memiliki kemiripan dalam genrenya.

**Kelebihan Content-Based Filtering:**

- Personalisasi.
- Kemampuan untuk menangani item baru.
- Interpretabilitas.
- Tidak memerlukan data penggunaan sebelumnya.

**Kekurangan Content-Based Filtering:**
- Keterbatasan dalam diversitas rekomendasi.
- Kesulitan dalam mendeteksi perubahan minat.
- Tidak efektif untuk data yang sangat rinci.
- Tidak efektif untuk item yang jarang terlihat.
- Tidak memperhitungkan interaksi sosial.

## Evaluation
Metrik yang digunakan untuk mengukur derajat kemiripan dalam proyek ini adalah _Cosine Similarity_. _Cosine Similarity_ adalah metrik untuk mengukur kesamaan antara dua vektor dalam ruang multidimensi dengan menghitung cosinus sudut antara mereka. Nilai _Cosine Similarity_ berkisar antara -1 (sangat tidak mirip) hingga 1 (sangat mirip), dengan 0 menunjukkan ketidaksamaan. Dalam konteks ini, _Cosine Similarity_ digunakan untuk membandingkan kesamaan antara item berdasarkan atribut atau fitur mereka. Semakin tinggi nilai Cosine Similarity antara dua item, semakin mirip mereka dalam hal atribut yang dianalisis. Ini digunakan untuk merekomendasikan item yang mirip dengan yang disukai oleh pengguna.

_Cosine Similarity_ dapat diformulakan sebagai berikut:

$$
Cosine Similarity = \frac{{A \cdot B}}{{\|A\| \cdot \|B\|}}
$$

Hasil percobaan dengan menggunakan fungsi 'movie_recommendations' untuk film 'Toy Story (1995)' terlihat pada tabel berikut:

![image](https://github.com/Loically/Movies_System_Recommender/assets/114181235/ce883604-f093-4b9e-bc2c-0b742026210e)

Tabel di atas menunjukkan 15 film yang memiliki genre yang mirip dengan film 'Toy Story (1995)'. Artinya, jika seorang pengguna menonton film 'Toy Story (1995)', maka sistem akan merekomendasikan 15 film tersebut sebagai _TOP 15 recommendations_
