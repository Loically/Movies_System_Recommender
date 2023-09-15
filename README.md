# Movies System Recommender - Fajar Zulkautsari Muhammad

## Project Overview

Belakangan ini, industri film telah mengalami pertumbuhan yang luar biasa[[1]](https://journal.untar.ac.id/index.php/koneksi/article/view/21509). Sebagian besar didorong oleh perkembangan teknologi dan perubahan dalam cara mengakses hiburan. Dengan semakin banyaknya platform streaming seperti Netflix, Amazon Prime Video, Hulu, Disney+, dan banyak lainnya, pengguna memiliki akses ke ribuan judul film dan acara TV yang dapat di-streaming kapan saja dan di mana saja. Kemajuan dalam teknologi internet telah memungkinkan pengalaman streaming yang mulus dan berkualitas tinggi. Di samping itu, keberagaman konten film yang ditawarkan oleh platform-platform ini, mulai dari film Hollywood terbaru hingga produksi independen dan dokumenter, memberikan pengguna beragam pilihan hiburan.

Pertumbuhan pesat dalam industri film telah mengubah lanskap konsumsi konten hiburan secara signifikan. Dengan ratusan bahkan ribuan film yang dirilis setiap tahun, pengguna dihadapkan pada pilihan yang semakin besar. Dalam situasi seperti ini, sistem rekomendasi genre film menjadi sangat penting. Industri film yang berkembang juga membawa diversifikasi genre yang lebih besar, termasuk genre yang lebih spesifik dan eksperimental. Oleh karena itu, sistem rekomendasi harus mampu mengakomodasi beragam preferensi pengguna dan mengidentifikasi film yang sesuai dengan genre yang mungkin kurang populer. Personalisasi juga menjadi kunci dalam memenuhi kebutuhan pengguna yang semakin beragam[[2]](https://www.inderscienceonline.com/doi/abs/10.1504/IJHPCN.2017.083199). Dalam persaingan sengit antara platform streaming dan layanan hiburan online lainnya, sistem rekomendasi yang efektif dapat menjadi faktor yang membedakan, membantu pengguna menemukan konten yang mereka sukai. Terlebih lagi sistem rekomendasi dapat dimanfaatkan untuk meningkatkan akurasi dan relevansi rekomendasi genre film, memberikan pengalaman yang lebih baik bagi pengguna dalam menavigasi kekayaan film yang tersedia saat ini.

Dalam konteks ini, sistem rekomendasi film berdasarkan genre memiliki peran yang semakin penting. Kemampuan platform streaming untuk merekomendasikan film-film yang sesuai dengan preferensi pengguna telah menjadi salah satu faktor kunci dalam mempertahankan pelanggan dan mendapatkan pelanggan baru[[3]](https://www.mdpi.com/2227-7390/11/4/895). Personalisasi pengalaman pengguna yang didasarkan pada sejarah penontonan dan pola penontonan, telah menjadi fokus utama untuk meningkatkan retensi pelanggan. Dengan data genre film dan algoritma pembandingan yang cerdas, sistem rekomendasi ini dapat membantu pengguna menavigasi melalui berbagai pilihan film yang ada dan meningkatkan kepuasan mereka dalam menemukan konten hiburan yang sesuai dengan selera mereka. Dengan pertumbuhan pesat konten digital dan pengaruh media sosial dalam berbagi rekomendasi, sistem rekomendasi film berbasis genre menjadi salah satu aspek penting dalam industri film yang berkembang secara signifikan. Dengan kata lain, sistem rekomendasi dapat memberikan keuntungan untuk kedua belah pihak, kepada pengguna dan platform penyedia. Pengguna akan mendapatkan kepuasan dalam menonton film yang akan menyebabkan keuntungan untuk platform penyedia[[4]](https://ddd.uab.cat/record/232276).



## Business Understanding
### Problem Statements
Dalam konteks pembuatan sistem rekomendasi film, proyek ini bertujuan untuk mengatasi beberapa masalah berikut:
- Bagaimana cara meningkatkan kepuasan pengguna dalam platform streaming?
- Bagaimana cara memberikan rekomendasi film yang sesuai dengan preferensi pengguna dengan tingkat presisi yang tinggi?

Fokus utama proyek ini adalah menghasilkan rekomendasi film yang presisi dan relevan berdasarkan preferensi pengguna.
### Goals
Tujuan utama dari proyek ini adalah:
- Meningkatkan pengalaman pengguna dalam menemukan film-film baru yang sesuai dengan preferensi mereka.
- Mengembangkan sistem rekomendasi film yang dapat memberikan rekomendasi film yang sesuai dengan preferensi pengguna dengan tingkat presisi yang tinggi.

Dalam konteks pembuatan sistem rekomendasi film, tujuan utama adalah memberikan rekomendasi yang presisi dan relevan kepada pengguna sesuai dengan preferensi mereka. Presisi mengukur sejauh mana film-film yang direkomendasikan benar-benar relevan dan sesuai dengan preferensi pengguna.

### Solution Statements:
Untuk mengatasi masalah dan mencapai tujuan yang telah diuraikan, proyek ini akan menggunakan pendekatan Machine Learning dengan metode Content-Based Filtering. Content-Based Filtering akan menggunakan konten yang telah disukai oleh pengguna sebelumnya sebagai referensi. Sistem rekomendasi akan memberikan konten (dalam konteks ini, film) yang memiliki tingkat presisi yang tinggi dengan konten yang telah disukai oleh pengguna sebelumnya atau berdasarkan riwayat tontonan pengguna. Dalam proyek ini, perhitungan tingkat kemiripan akan dilakukan berdasarkan genre dari film. Hal ini berarti bahwa sistem akan memberikan rekomendasi film lain dengan genre yang mirip atau bahkan sama dengan genre yang telah digemari oleh pengguna. Dengan pendekatan ini, diharapkan pengguna akan mendapatkan rekomendasi film-film dengan genre yang sesuai dengan preferensi mereka, bahkan mungkin film-film yang sebelumnya tidak mereka ketahui.

Rekomendasi genre film yang tepat akan membantu pengguna dengan cara berikut:
- Pengguna akan lebih cenderung menikmati film-film yang sesuai dengan selera mereka, sehingga meningkatkan kepuasan mereka.
- Pengguna akan lebih terlibat dalam platform streaming karena mereka mendapatkan rekomendasi yang relevan dan menarik.
- Pengguna akan menemukan film-film baru yang sesuai dengan genre favorit mereka, mengembangkan preferensi tontonan mereka, dan membuat pengalaman menonton lebih beragam.

Dengan pendekatan ini, dapat dipahami bahwa sistem rekomendasi genre film yang tepat akan memberikan dampak positif pada kepuasan dan keterlibatan pengguna dalam platform streaming.

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

Selanjutnya, ditemukan sebanyak 34 film yang tidak memiliki keterangan genre yang dapat digunakan untuk analisis rekomendasi. Dalam konteks sistem rekomendasi berbasis konten yang menggunakan genre sebagai salah satu fitur utama, ketiadaan informasi genre ini menjadi tantangan. Oleh karena itu, ke-34 film tersebut dikecualikan dari proyek ini, sehingga total data film yang dapat digunakan adalah sebanyak 9703 film. Keputusan ini diambil agar analisis dan rekomendasi genre film dapat lebih akurat dan relevan, mengingat genre adalah salah satu aspek penting dalam menentukan kesukaan dan preferensi pengguna. Meskipun 34 film ini tidak termasuk dalam analisis, data sebanyak 9703 film yang tersedia tetap mencerminkan keragaman dan kompleksitas industri film yang berkembang pesat saat ini, dan sistem rekomendasi genre film akan berfokus pada memberikan rekomendasi yang sesuai berdasarkan genre-genre yang terdefinisi dengan baik.

## Data Preparation
Proses data preparation dalam proyek sistem rekomendasi berbasis konten melibatkan persiapan dan pemrosesan data agar dapat digunakan oleh sistem rekomendasi. Langkah-langkah ini mencakup pengumpulan, pembersihan, pengolahan, dan pengaturan data agar dapat digunakan untuk menghasilkan rekomendasi yang akurat. Berikut adalah langkah-langkah utama dalam proses data preparation:

- **Pengumpulan Data:**

Dalam tahap awal proyek, langkah pertama yang diambil adalah mengumpulkan data yang diperlukan untuk sistem rekomendasi genre film. Data ini bersumber dari situs Kaggle, sebuah platform yang menyediakan beragam dataset untuk analisis. Proses ini dimulai dengan mengunggah token API Kaggle, yaitu kunci otentikasi yang diperlukan untuk mengakses data dari Kaggle. Setelah token API berhasil diunggah, data yang diperlukan diunduh dari Kaggle langsung ke lingkungan proyek menggunakan fungsi Kaggle datasets download. Dengan pendekatan ini, data yang digunakan dalam proyek ini selalu diperbaharui sesuai dengan sumbernya, memastikan kualitas dan keakuratan data yang digunakan dalam pengembangan sistem rekomendasi film berdasarkan genre film.
- **Pembersihan Data:**

Dalam proses pembersihan data, teridentifikasi beberapa duplikasi dalam kolom 'title' pada dataset film. Untuk mengatasi masalah ini, dilakukan penyaringan data dengan mempertahankan satu entri film dengan judul yang sama, tetapi hanya menjaga data film yang memiliki deskripsi genre yang lebih lengkap. Ini berarti bahwa entri yang memiliki deskripsi genre yang lebih sedikit dihapus dari dataset. Tindakan ini bertujuan untuk menyederhanakan dataset dan memastikan bahwa data yang digunakan untuk analisis dan rekomendasi genre film adalah yang paling informatif. Dengan demikian, langkah ini diambil untuk meningkatkan akurasi rekomendasi dan memastikan bahwa dataset yang digunakan dalam proyek ini memiliki kualitas yang lebih baik.
- **Ekstraksi Fitur:**

Pada tahap ekstraksi fitur, kolom genre dalam dataset diubah menjadi representasi numerik yang dapat digunakan dalam analisis lebih lanjut. Salah satu pendekatan yang digunakan dalam proyek ini adalah teknik one-hot encoding. Dalam konteks ini, setiap genre yang ada dalam kolom genre diterjemahkan menjadi kolom-kolom biner terpisah. Setiap kolom ini menggambarkan satu genre khusus, dan jika film memiliki genre tersebut, nilai dalam kolom tersebut akan menjadi 1, sedangkan jika tidak, akan menjadi 0. Sebagai contoh, one-hot encoding akan mengubah tabel seperti berikut:

| ...  | genres  |                  
|---|---|
|   |  Comedy, Romance   |
|   |  Comedy, Drama, Romance  |
|   |   |

Menjadi tabel seperti di bawah ini 

| ...  | Comedy  | Romance  | Drama  |
|---|---|---|---|
|   | 1  | 1  | 0  |
|   | 1  | 1  | 1  |

Hasil dari ekstraksi fitur ini adalah transformasi dataset menjadi representasi biner yang memungkinkan algoritma untuk memahami dan memproses genre sebagai fitur yang dapat digunakan dalam perhitungan kesamaan dan rekomendasi film. Ini adalah langkah penting dalam mempersiapkan data sebelum menerapkan berbagai metode rekomendasi berbasis konten.

- **Transformasi Data:**

Dalam konteks pemahaman tingkat korelasi atau kemiripan antar film berdasarkan genre, telah dibentuk sebuah tabel pivot yang menggunakan metrik Cosine Similarity yang sudah dihitung sebelumnya. Tabel pivot ini berperan sebagai alat visual yang sangat berguna untuk mengilustrasikan sejauh mana setiap film dalam dataset memiliki keterkaitan satu sama lain dalam hal genre-genre yang ada. Setiap baris dan kolom dalam tabel ini merepresentasikan satu film, dan nilai yang terletak di setiap sel menggambarkan sejauh mana dua film tersebut serupa berdasarkan genre-genre yang mereka miliki. Nilai Cosine Similarity yang tinggi menandakan bahwa kedua film tersebut memiliki kemiripan yang kuat dalam genre-genre tertentu, sementara nilai yang lebih rendah menunjukkan tingkat kesamaan yang lebih rendah.

Tabel pivot ini dapat mempermudah untuk melakukan ekplorasi hubungan antara berbagai film dalam dataset dan identifikasi film-film yang memiliki tingkat kemiripan tinggi berdasarkan genre. Hal ini menjadi landasan dalam menghasilkan rekomendasi film yang lebih akurat, karena dapat secara visual menampilkan film-film yang memiliki genre yang serupa. Tabel pivot ini adalah alat yang sangat penting dalam pemahaman dan visualisasi tingkat kemiripan antar film dalam konteks genre, yang menjadi inti dari metode rekomendasi berbasis konten yang diterapkan dalam proyek ini. Berikut merupakan ilustrasi tabel pivot yang berhasil dibuat.

| 'title'  | Toy Story (1995)  | Jumanji (1995)  | Grumpier Old Men (1995)  |  ...  |
|---|---|---|---|---|
| Toy Story (1995)  | 1.000  | 0.774597  | 0.316228  |
|  Jumanji (1995) | 0.774597  | 1.000  | 0.000000  |
|  Grumpier Old Men (1995) | 0.316228  | 1.000  | 0.000000  |
|  ... | ...  | ...  | ...  |

Sebagai contoh cara membaca tabel di atas, film Toy Story (1995) dan Jumanji (1995) memiliki derajat kemiripan sebesar 0.774597. Dengan nilai maksimal yaitu 1.000, kedua film tersebut bisa dikatakan 77.46% mirip berdasarkan genrenya.

## Modeling and Result
Model pengembangan yang digunakan dalam proyek ini adalah Content-Based Filtering, sebuah metode rekomendasi yang mengandalkan fitur-fitur intrinsik dari item yang akan direkomendasikan, dalam hal ini, film. Model ini dipilih karena sangat relevan dengan dataset yang tersedia, yang mencakup data film beserta berbagai genre yang terkait dengan setiap film.

![1 Lr6qL0YjY_WqVK5u-AYHAQ](https://github.com/Loically/Movies_System_Recommender/assets/114181235/3aea8555-7ccb-4be7-b0a6-d83116c792bf)

Cara kerja dari model Content-Based Filtering dalam proyek ini dimulai dengan ekstraksi fitur dari dataset film. Fitur utama yang digunakan adalah genre-genre yang terkait dengan masing-masing film. Pertama, setiap genre diubah menjadi representasi biner menggunakan pendekatan one-hot encoding. Artinya, setiap film diwakili oleh vektor biner di mana setiap elemen vektor mengindikasikan keberadaan atau ketiadaan suatu genre dalam film tersebut. Ini menciptakan representasi numerik yang dapat digunakan dalam perhitungan kemiripan.

Selanjutnya, untuk merekomendasikan film kepada pengguna, model Content-Based Filtering membandingkan film yang sudah disukai oleh pengguna dengan film-film lainnya dalam dataset berdasarkan kemiripan genre. Hal ini dilakukan dengan menghitung skor kemiripan antara vektor genre dari film yang disukai pengguna dengan vektor genre dari semua film dalam dataset. Skor kemiripan ini dihitung menggunakan metrik Cosine Similarity, yang mengukur sudut antara vektor-vektor genre dalam ruang berdimensi tinggi. Semakin kecil sudut antara dua vektor, semakin mirip dua film dalam hal genre.

$$
Cosine Similarity = \frac{{A \cdot B}}{{\|A\| \cdot \|B\|}}
$$

Cosine Similarity adalah metrik yang berguna dalam mengukur kemiripan antara vektor-vektor dalam konteks ini karena mengabaikan skala vektor dan hanya memperhatikan arahnya. Dalam hal ini, arah vektor genre mencerminkan sejauh mana dua film memiliki genre-genre yang serupa. Hasil dari perhitungan Cosine Similarity ini digunakan untuk mengurutkan dan merekomendasikan film-film dengan skor kemiripan tertinggi kepada pengguna.

Dengan demikian, model Content-Based Filtering pada proyek ini menggabungkan ekstraksi fitur, perhitungan kemiripan genre menggunakan Cosine Similarity, dan rekomendasi berdasarkan genre-genre yang paling mirip. Ini memungkinkan sistem untuk memberikan rekomendasi yang lebih personal dan sesuai dengan preferensi pengguna berdasarkan analisis genre film yang telah diberikan. Juga, pada fungsi movie_recommendations() pada notebook, setelah merekomendasikan film, informasi genre dari film-film yang direkomendasikan ditampilkan dalam satu kolom untuk memberikan pemahaman lebih lanjut kepada pengguna tentang alasan di balik rekomendasi tersebut.

Model di test untuk mencari film yang mirip dengan film 'Toy Story (1995). Hasil test model terlampir seperti pada tabel di bawah yang menampilkan **TOP 10 Movie Recommendations**.

| title  | similarity_score  | genres  |
|---|---|---|
|  Tale of Despereaux, The (2008) |  1.0000 |  Adventure, Animation, Children, Comedy, Fantasy |
|  Moana (2016) |  1.0000 |  Adventure, Animation, Children, Comedy, Fantasy |
|  Shrek the Third (2007) |  1.0000 |  Adventure, Animation, Children, Comedy, Fantasy |
| Antz (1998)  |  1.0000 |  Adventure, Animation, Children, Comedy, Fantasy |
| Wild, The (2006)  |  1.0000 |  Adventure, Animation, Children, Comedy, Fantasy |
|  Monsters, Inc. (2001) |  1.0000 |  Adventure, Animation, Children, Comedy, Fantasy |
| Toy Story 2 (1999)  |  1.0000 |  Adventure, Animation, Children, Comedy, Fantasy |
| Turbo (2013)  |  1.0000 |  Adventure, Animation, Children, Comedy, Fantasy |
| Phantom Tollbooth, The (1970) |  0.894427 |  Adventure, Animation, Children, Fantasy |
|  We're Back! A Dinosaur's Story (1993) |  0.894427 |  Adventure, Animation, Children, Fantasy |

## Evaluation
Dalam sistem rekomendasi ini, penggunaan metrik presisi sangat relevan dan penting dalam mengevaluasi kualitas rekomendasi yang diberikan. Presisi adalah metrik yang mengukur sejauh mana film-film yang direkomendasikan oleh sistem benar-benar relevan dan sesuai dengan preferensi pengguna.

Formula untuk menghitung presisi secara sederhana adalah sebagi berikut:

$$
Presisi = \frac{\text{Jumlah Film yang Relevan}}{\text{Jumlah N Rekomendasi}}
$$

Metrik presisi digunakan untuk memastikan bahwa rekomendasi yang diberikan tidak hanya berjumlah banyak, tetapi juga memiliki tingkat relevansi yang tinggi. Dalam kata lain, untuk menghindari memberikan rekomendasi yang sebagian besar tidak sesuai dengan preferensi pengguna.

Dari hasil test yang telah dilakukan, dari 10 film yang direkomendasikan, terdapat 8 film yang memiliki genre yang sama persis (similarity_score = 1.0000). Dengan menggunakan rumus presisi sederhana, maka nilai presisi dari model ini adalah 80.0%
