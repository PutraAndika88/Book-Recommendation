# **Proyek Kedua | Aplikasi E-Perpustakaan: Penggunaan *Book Recommendation System* Dengan Metode *Content-Based Filtering* dan *Collaborative Filtering***

###### Oleh : Putra Andika Pradana

Ini adalah proyek kedua, membuat sistem rekomendasi untuk memenuhi submission Dicoding Kelas *machine learning* Terapan. 

Proyek ini membangun model *machine learning* yang dapat memberikan rekomendasi judul buku kepada pengguna.

## 1. *Project Domain*

### Latar Belakang

![E-Book](https://github.com/PutraAndika88/Book-Recommendation/blob/main/img_book/e-book.jpg?raw=true)
[Referensi Gambar](https://eodopen.eu/news/7)

Domain proyek untuk sistem rekomendasi buku ini adalah untuk industri yang bergerak di bidang toko buku yang mana sedang dalam proyek pembuatan perpustakaan *online* untuk membantu pelanggannya agar lebih mudah dalam mengakses koleksi buku elektronik melalui *smartphone*. Di era digital saat ini, masyarakat Indonesia lebih menyukai kegiatan membaca buku secara *online*[[1]](https://www.gramedia.com/best-seller/tren-pembaca-digital-2019-gramedia-digital/). Menurut hasil survei yang dilakukan Gramedia Digital 2019 lalu, sebanyak 85% dari total responden pengguna media digital memilih e-book sebagai media digital yang paling banyak digunakan dibanding media lainnya. Disusul oleh streaming film dengan jumlah presentase 67% dan e-magazine yang berada di urutan ketiga dengan jumlah 65%. Baru kemudian ada streaming musik, e-newspaper dan audiobook. Selain itu, berdasarkan hasil survey Rakuten pada website Katadata bahwa mayoritas atau sebesar 83% responden Indonesia mengaku bahwa lebih menyukai membaca buku melalui smartphone [[2]](https://databoks.katadata.co.id/datapublish/2023/09/21/survei-mayoritas-orang-indonesia-lebih-suka-baca-buku-lewat-smartphone). 

Inovasi perpustakaan digital tentunya menyediakan antarmuka pengguna yang memungkinkan pengguna untuk mencari, menjelajahi, dan mengakses koleksi materi yang tersedia. Pengguna dapat menggunakan kata kunci, kategori, atau fitur pencarian lainnya untuk menemukan sumber daya yang relevan dengan kebutuhan mereka. Keuntungan menggunakan perpustakaan digital adalah aksesibilitas yang lebih luas. Pengguna tidak perlu hadir di lokasi fisik perpustakaan untuk mengakses materi. Mereka dapat mengaksesnya dari mana saja dengan koneksi internet. Ini memudahkan orang untuk mengakses pengetahuan dan informasi yang mereka butuhkan tanpa batasan geografis. Selain itu, perpustakaan digital sering kali menawarkan keunggulan lain, seperti kemampuan untuk meminjam e-buku atau membaca artikel jurnal secara online [[3]](https://vokasi.unair.ac.id/2023/07/01/perpustakaan-digital-memanfaatkan-koleksi-digital-untuk-penelitian-dan-inovasi/).

Dalam domain ini, tantangan yang dihadapi adalah bagaimana menyediakan rekomendasi buku yang relevan dan sesuai dengan minat, tujuan belajar, *rating* buku, dan kebutuhan sesuai pengguna. 

Dalam konteks ini, model *machine learning* dapat memainkan peran penting dalam menganalisis data pengguna, seperti riwayat buku yang pernah dibaca, preferensi buku pengguna, dan ulasan yang telah diberikan.

Model *machine learning* dapat mempelajari pola dan hubungan antara pengguna dan koleksi buku yang ada di sistem rekomendasi ini [[4]](https://www.sciencedirect.com/science/article/pii/S1877050919310944). Dengan menggunakan teknik pengolahan bahasa alami (Natural Language Processing) dan teknik pembelajaran mesin lainnya, model dapat memahami teks deskripsi pada buku, topik, dan keterkaitan antara koleksi buku yang ada. 

Model juga dapat menganalisis data pengguna, seperti preferensi, ulasan oleh pembaca, dan riwayat buku bacaan pengguna, untuk memberikan rekomendasi yang personal dan relevan.

Dengan menggunakan sistem rekomendasi ini, pengguna dapat menemukan rekomendasi buku yang sesuai dengan jenis buku, minat, dan kebutuhan mereka. Hal ini dapat membantu mempermudah pengguna dalam menemukan buku yang sesuai dengan minatnya. 

Sistem rekomendasi ini juga dapat membantu e-perpustakaan dalam meningkatkan pengalaman pengguna dan mempertahankan anggota dengan menyediakan rekomendasi yang akurat dan bermutu.

Dengan membangun model *machine learning* untuk sistem rekomendasi buku pada e-perpustakaan, diharapkan dapat memberikan manfaat bagi pengguna yaitu pembaca *online* dalam mempermudah proses pencarian buku yang sesuai dengan minat dan kebutuhan mereka.

## 2. *Business Understanding*

Dalam konteks proyek ini, pemahaman bisnis adalah memahami tujuan dan manfaat yang ingin dicapai oleh pengembangan sistem rekomendasi buku melalui aplikasi e-perpustakaan. 

Berikut adalah beberapa poin penting dalam pemahaman bisnis proyek ini:

1. Meningkatkan pengalaman pengguna: sistem rekomendasi buku pada aplikasi e-perpustakaan bertujuan untuk meningkatkan pengalaman pengguna dengan menyediakan rekomendasi yang personal, akurat, dan relevan dengan pengguna. Dengan menggunakan model *machine learning*, pengguna akan mendapatkan rekomendasi buku yang sesuai dengan minat, tujuan membaca, dan *rating* buku. Hal ini dapat membantu pengguna dalam menemukan buku yang menarik dan sesuai dengan kebutuhan mereka.

2. Meningkatkan retensi pengguna: dengan menyediakan rekomendasi yang akurat dan bermutu, sistem ini diharapkan dapat membantu e-perpustakaan dalam mempertahankan pengguna yaitu para pembaca. Pengguna yang mendapatkan rekomendasi yang relevan dan memberikan nilai tambah dalam pengalaman mengeksplorasi e-perpustakaan tersebut sehingga mereka cenderung akan tetap aktif dan terlibat dalam *platform* e-perpustakaan tersebut. Meningkatkan retensi pengguna adalah tujuan bisnis yang penting untuk menghasilkan pertumbuhan jangka panjang dan sustainabilitas bisnis.

3. Penyediaan buku yang relevan: sistem rekomendasi ini juga memberikan manfaat kepada e-perpustakaan dalam hal penyediaan rekomendasi buku yang relevan. Dengan menganalisis preferensi pengguna, riwayat buku yang pernah dibaca, dan riwyat *rating* yang telah diberikan pembaca sebelumnya, e-perpustakaan dapat menggunakan hasil rekomendasi untuk meningkatkan pengalaman pengguna dalam mencari buku yang sesuai dengan minat pengguna.

4. Meningkatkan konversi dan pendapatan: sistem rekomendasi yang efektif dapat meningkatkan konversi, yaitu mengubah pengguna yang hanya menjelajahi platform menjadi pembaca buku yang sekaligus berlangganan di e-perpustakaan. Dengan memberikan rekomendasi yang menarik dan relevan, pengguna akan cenderung loyal dan memutuskan untuk bergabung menjadi anggota premium e-perpustakaan. Hal ini dapat meningkatkan pendapatan dan mengoptimalkan model bisnis melalui inovasi e-perpustakaan

5. Analisis data dan pemahaman pengguna: dalam pengembangan sistem rekomendasi, analisis data pengguna menjadi komponen kunci. Dengan memahami pola perilaku pengguna, preferensi, dan riwayat pengguna, e-perpustakaan dapat mendapatkan wawasan berharga tentang minat dan kebutuhan pengguna mereka. Analisis data juga membantu dalam mengukur efektivitas rekomendasi yang diberikan dan melakukan perbaikan yang diperlukan.

Dengan pemahaman bisnis yang kuat, pengembangan sistem rekomendasi buku pada e-perpustakaan dapat fokus pada tujuan dan manfaat yang ingin dicapai. 

Dalam hal ini, meningkatkan pengalaman pengguna, retensi pengguna, penyediaan kursus yang relevan, meningkatkan konversi dan pendapatan, serta analisis data pengguna menjadi fokus utama dalam pengembangan dan evaluasi sistem rekomendasi ini.

## 3. *Problem Statement*

Berdasarkan business understanding di atas, proyek ini akan berusaha menjawab pertanyaan pada masalah-masalah sebagai berikut:

1. Bagaimana mengembangkan sistem rekomendasi yang dapat memberikan pengalaman pengguna yang lebih baik dalam mencari buku yang sesuai di aplikasi e-perpustakaan?

2. Bagaimana meningkatkan retensi pengguna dengan menyediakan rekomendasi buku yang relevan dan menarik bagi pengguna aplikasi e-perpustakaan?

3. Bagaimana mengoptimalkan penyediaan buku yang relevan dengan mengidentifikasi preferensi pengguna, riwayat buku yang pernah dibaca, dan riwayat *rating* buku?

4. Bagaimana meningkatkan konversi pengguna menjadi annggota e-perpustakaan premium dengan menyediakan rekomendasi yang menarik dan memberikan nilai tambah?

5. Bagaimana menganalisis data pengguna dengan efektif untuk memahami perilaku, preferensi, dan kebutuhan pengguna dalam konteks rekomendasi buku?

Dengan memfokuskan diri pada pertanyaan-pertanyaan di atas, tujuan proyek ini akan menjadi lebih jelas dan memungkinkan pengembangan solusi yang efektif untuk memecahkan masalah yang ingin diselesaikan, yaitu meningkatkan pengalaman pengguna, retensi pengguna, penyediaan buku yang relevan, konversi pengguna, dan analisis data pengguna.

## 4. *Goals*

Proyek ini memiliki beberapa tujuan yang ingin dicapai dalam pengembangan sistem rekomendasi buku di aplikasi e-perpustakaan yakni sebagai berikut:

1. Meningkatkan pengalaman pengguna: tujuan utama adalah meningkatkan pengalaman pengguna dengan menyediakan rekomendasi buku yang personal dan relevan. Hal ini akan membantu pengguna dalam menemukan kursus yang sesuai dengan minat, tujuan membaca, dan *rating* buku. Pencapaian tujuan ini akan memberikan manfaat berupa kepuasan pengguna yang lebih tinggi dan peningkatan pengalaman pengguna di aplikasi e-perpustakaan.

- Metrik evaluasi: 
  - Tingkat kepuasan pengguna: dilakukan survei atau pengukuran berdasarkan umpan balik pengguna terkait pengalaman mereka dalam menggunakan sistem rekomendasi. 
  - Tingkat keterlibatan pengguna: meliputi jumlah klik pada rekomendasi, waktu yang dihabiskan di halaman e-perpustakaan yang direkomendasikan, dan tingkat interaksi dengan koleksi buku.

2. Meningkatkan retensi pengguna: tujuan ini bertujuan untuk meningkatkan retensi pengguna dengan memberikan rekomendasi buku yang relevan dan menarik. Dengan rekomendasi yang akurat, pengguna cenderung tetap aktif dan terlibat pada aplikasi e-perpustakaan.

- Metrik evaluasi: 
  - Tingkat retensi pengguna: persentase pengguna yang tetap aktif dalam platform setelah menerima rekomendasi. 
  - Tingkat keterlibatan berkelanjutan: meliputi frekuensi pengguna *online*, kunjungan dalam e-perpustakaan, dan total pengguna aktif.

3. Penyediaan rekomendasi buku yang relevan: tujuan ini melibatkan meningkatkan penyediaan buku yang relevan dengan mengidentifikasi preferensi pengguna, riwayat buku yang pernah dibaca, dan riwayat *rating* buku. Hal ini akan membantu Coursera dalam menyusun kurikulum yang sesuai dengan permintaan pengguna.

- Metrik evaluasi: 
  - Tingkat keberhasilan rekomendasi: persentase kesesuaian antara buku yang direkomendasikan dengan preferensi pengguna.
  - Tingkat penerimaan dan partisipasi dalam kursus: meliputi jumlah pembaca pada buku yang direkomendasikan.

4. Meningkatkan konversi dan pendapatan: tujuan ini berfokus pada meningkatkan konversi pengguna menjadi anggota premium e-perpustakaan  dengan memberikan rekomendasi yang menarik dan memberikan nilai tambah.

- Metrik evaluasi: 
  - Tingkat konversi pengguna: persentase pengguna yang mendaftar untuk menjadi anggota premium e-perpustakaan setelah merasakan fitur rekomendasi.
  - Pendapatan: meningkatnya pendapatan dari penjualan kursus berbayar yang dihasilkan melalui rekomendasi.

5. Analisis data dan pemahaman pengguna: tujuan ini melibatkan analisis data pengguna untuk memahami perilaku, preferensi, dan kebutuhan pengguna dalam konteks rekomendasi kursus.

- Metrik evaluasi: 
  - Akurasi rekomendasi: persentase kesesuaian antara rekomendasi yang diberikan dengan preferensi dan minat pengguna yang terungkap melalui analisis data.
  - Tingkat pemahaman pengguna: menggunakan survei atau pengukuran lainnya untuk mengukur pemahaman pengguna terkait relevansi dan kegunaan rekomendasi yang diberikan.

Dengan menggunakan metrik evaluasi yang tepat, kesuksesan dalam mencapai setiap tujuan dapat diukur dan dinilai secara objektif. 

Hal ini akan membantu dalam mengidentifikasi kekuatan dan kelemahan sistem rekomendasi, serta memberikan wawasan yang berguna dalam pengembangan dan peningkatan selanjutnya.

## 5.  *Solution Approach*

Tahapan untuk menyelesaikan tujuan dari proyek ini adalah sebagai berikut:

1. Tahap EDA (*Exploratory Data Analysis*):
   - Mengumpulkan data: Mengumpulkan data koleksi buku, termasuk informasi kursus seperti judul, Nomor ISBN, deskripsi buku, ulasan pengguna, penulis buku, tahun terbit, penerbit dan jumlah pembaca.
   - Melakukan pembersihan data: Membersihkan dan memformat data agar sesuai dengan kebutuhan analisis.
   - Analisis data: Melakukan analisis eksploratori untuk memahami distribusi data, tren, dan pola yang ada. Ini meliputi pemahaman tentang preferensi kursus yang diambil pengguna, *rating* buku, dan atribut keahlian yang relevan.

2. Pendekatan *Content-Based Filtering*:
   - Pembangunan fitur: Menggunakan teknik pengolahan bahasa alami atau *Natural Language Processing* (NLP) untuk menganalisis penulis buku dan menghasilkan vektor fitur yang merepresentasikan konten kursus.
   - Membangun model: Menggunakan algoritma seperti *TF-IDF Vectorizer* atau *Word Embeddings* dan *Cosine Similarity* untuk membangun model yang dapat mengukur kesamaan antara buku berdasarkan fitur-fitur kontennya.
   - Rekomendasi kursus: Menghitung kesamaan antara buku yang ada dengan kursus yang diminati oleh pengguna berdasarkan kursus yang telah diambil dan atribut keahlian.

3. Pendekatan *Collaborative Filtering*:
   - Membangun model: Menggunakan algoritma melalui *TensorFlow Framework* yaitu *RecommenderNet* untuk membangun model yang dapat menemukan pola kolaboratif di antara kursus dan keahlian.
   - Rekomendasi kursus: Membuat rekomendasi kursus berdasarkan peringkat prediksi yang diberikan oleh model.

4. Evaluasi Model:
   - Evaluasi *Content-Based Filtering*: Menggunakan metrik *Precission*, *Recall*, dan *F1-Score* untuk mengukur sejauh mana rekomendasi kursus yang diberikan relevan dengan preferensi pengguna.
   - Evaluasi *Collaborative Filtering*: Menggunakan metrik *Root Mean Square Error* (RMSE) untuk mengukur sejauh mana peringkat prediksi model mendekati peringkat yang sebenarnya.

5. Perbaikan dan Penyesuaian Model:
   - Menganalisis hasil evaluasi model dan melakukan perbaikan atau penyesuaian yang diperlukan untuk meningkatkan performa dan akurasi rekomendasi.

Dengan pendekatan ini, fitur-fitur konten kursus (*Content-Based Filtering*) akan dimanfaatkan serta pola kolaboratif antara pengguna, *rating* dan buku (*Collaborative Filtering*) untuk memberikan rekomendasi kursus yang relevan kepada pengguna. 

Evaluasi menggunakan metrik *Precission*, *Recall*, *F1-Score* dan *RMSE* akan memberikan wawasan tentang sejauh mana performa model dalam memberikan rekomendasi yang tepat.

## 6. *Data Understanding*

Sumber Data: [Book Recommendation](https://www.kaggle.com/datasets/arashnic/book-recommendation-dataset)

+ Dataset tersebut terdiri dari tiga *dataframe* dengan format *Comma Separated Value* (CSV) yaitu *book.cvs*, *users.csv*, dan *ratings.csv*
+ Dataset tersebut berjumlah 271.360 ribu baris *unique value*

### Sampel Data

1. Data *books.csv*

Tabel 6.1 Contoh Data Buku Pada Dataset *books.csv* 

|  ISBN 	|   *Title* 	|   *Author*	|   *Year_Of_Publication*	|  *Publisher* 	|   *Image_URL_M*	|
|---	|---	|---	|---	|---	|---	|
|  0195153448 	|  Classical Mythology  	|  Mark P. O. Morford  	|   2002	|  Oxford University Press  	|  http://images.amazon.com/images/P/0195153448.01.MZZZZZZZ.jpg 	|
|  0002005018 	|  Clara Callan 	|  Richard Bruce Wright 	|   2001	|  HarperFlamingo Canada 	|   http://images.amazon.com/images/P/0002005018.01.MZZZZZZZ.jpg	|
|  0060973129 	|  Decision in Normandy 	|   Carlo D'Este	|  1991 	|   HarperPerennial	|   http://images.amazon.com/images/P/0060973129.01.MZZZZZZZ.jpg	|
|  0374157065 	|  Flu: The Story of the Great Influenza Pandemic of 1918 and the Search for the Virus That Caused It 	|  Gina Bari Kolata 	|  1999 	|  Farrar Straus Giroux 	|  http://images.amazon.com/images/P/0374157065.01.MZZZZZZZ.jpg 	|
|   0393045218	|  The Mummies of Urumchi 	|  E. J. W. Barber 	|   1999	|  W. W. Norton &amp; Company 	|  http://images.amazon.com/images/P/0393045218.01.MZZZZZZZ.jpg 	|

2. Data *users.csv*

Tabel 6.2 Contoh Data *User* Pada Dataset *Users.csv* 

|  *UserID* 	|   *Age*	|  *City*	|  *state* 	|  *Country* 	|   	
|---	|---	|---	|---	|---	|
|  1 	|  24 	|   Nyc	|  new york	 	|   usa	|
|   2	|   18	|  Stockton 	|   california	|   usa	|
|   3	|   24	|   Moscow	|  yukon territory	 	|   russia	|
|   4	|   17	|   Porto	|   v.n.gaia		|   portugal	|
|   5	|   24	|   Farnborough	|  hants 	|  united kingdom |

3. Data *Ratings.csv*

Tabel 6.3 Contoh Data *Rating* Pada Dataset *Ratings.csv* 

|  *UserID* 	|  ISBN 	|  *Rating* 	|
|---	|---	|---	|
|  276725 	|  034545104X 	|  0 	|
|   276726	|  0155061224 	|   5	|
|  276727 	|   0446520802	|  0 	|
|  276729 	|   052165615X	|   3	|
|   276729	|   0521795028	|   6	|

4. *Dataframe* Sebagai Input Sistem Rekomendasi Untuk Metode *Content-Based Filtering*

Tabel 6.4 Sampel *Dataframe* Input Pada Model Rekomendasi Sistem *Content-Based Filtering* 

|  ISBN 	|  *Book_Title* 	|  *Book_Author* 	|  *Year_Of_Publication* 	|  *Publisher* 	|
|---	|---	|---	|---	|---	|
|  0000913154 	|  The Way Things Work: An Illustrated Encycloped... 	|  Judith Kerr 	|   1967	|   Simon &amp; Schuster	|
|  0001010565 	|   Mog's Christmas	|  C. van Amerongen (translator) 	|   1992 	|  Collins 	|
|   0001046438	|   Liar	|  Judith Kerr 	|  1992 	|  Harpercollins Uk 	|
|   0001046713	|  Twopence to Cross the Mersey 	|  Stephen Fry 	|   1992	|  HarperCollins Publishers 	|
|  000104687X 	|  T.S. Eliot Reading \The Wasteland\" and Other ... 	|   Helen Forrester	|  1993 	|   HarperCollins Publishers	|

5. *Dataframe* Sebagai Input Sistem Rekomendasi Untuk Metode *Collaborative Filtering*

Tabel 6.5 Sampel *Dataframe* Input Pada Model Rekomendasi Sistem *Collaborative Filtering* 

|  *User-ID*	 	|  ISBN 	|  *Book-Rating*	 	|   *Reader*	|  book_title 	|
|---	|---	|---	|---	|---	|
|  446 	|   0061000280		|  10.0 	|  1005 	|   9861	|
|   277478	|   0340565276	|   8.0	|   273	|  1978 	|
|  278418 	|   1569751544	|  3.0 	|  678 	|   8223	|
|   277195	|   0394726413	|  0.0	 	|   173	|  1098 	|
|  1928 	|   0373196903	|   0.0		|   1511		|  12430 	|

### Variabel-variabel pada dataset Coursera Courses 2021 adalah sebagai berikut:

- UserID: ID pengguna di perpustakaan.
- ISBN: Nomor buku standar internasional
- *Age*: Umur pengguna.
- *City* Rating: Domisili pengguna.
- *State* & *Country*: Negara asal pengguna
- *Rating*: Nilai buku yang diberikan oleh pembaca terdahulu
- *Book Title*: Judul buku
- *Book Author*: Penulis buku
- *Year of Publication*: Tahun terbit
- *Publisher*: Penerbit
- *Reader*: Jumlah pembaca

### *Top* Sepuluh Penerbit Teratas

Gambar 6.1 Visualisasi *Top* Sepuluh Penerbit Teratas dengan *Pie Chart*

![Top_10](https://github.com/PutraAndika88/Book-Recommendation/blob/main/img_book/10%20penerbit%20teratas%20dengan%20jumlah%20buku%20terbanyak.png?raw=true)

Berdasarkan Gambar 6.1 tersebut diketahui bahwa penerbit teratas dengan jumlah terbitan buku terbanyak pada perpustakaan tersebut adalah sebagai berikut. Posisi pertama diduduki oleh penerbit *Harlequin* yang mana merupakan penyumbang 20% dari koleksi buku di perpustakaan tersebut. 

### Pengguna Dengan Kontribusi Ulasan atau *Rating* Terbanyak

Gambar 6.2 Visualisasi Pengguna dengan *Rating* Terbanyak dengan *Pie Chart*

![Rating terbanyak](https://github.com/PutraAndika88/Book-Recommendation/blob/main/img_book/UserIDs%20dengan%20rating%20tertinggi.png?raw=true)

Berdasarkan Gambar 6.2 tersebut diketahui bahwa pengguna dengan nomor ID 153662 merupakan pembaca buku paling loyal karena telah mencatatkan penilaian buku terbanyak yaitu sebesar 69% dari total penilaian dari seluruh koleksi buku di perpustakaan. 

### Histogram Umur Pengguna

Gambar 6.3 Visualisasi Umur Pengguna Dengan Histogram

![hist](https://github.com/PutraAndika88/Book-Recommendation/blob/main/img_book/histogram%20umur%20pengguna.png?raw=true)

Bagian-bagian Grafik:

+ Sumbu X: Menunjukkan usia pengguna dalam rentang 0-100 tahun.
+ Sumbu Y: Menunjukkan kepadatan probabilitas, yang mewakili proporsi pengguna dalam setiap rentang usia.
+ Batang: Tinggi setiap batang menunjukkan proporsi pengguna yang berada dalam rentang usia yang sesuai.

Informasi yang Dapat Diperoleh:

+ Distribusi Usia Pengguna: Grafik menunjukkan bahwa mayoritas pengguna berusia di bawah 40 tahun.
+ Konsentrasi Usia: Terdapat konsentrasi pengguna yang signifikan di rentang usia 20-30 tahun.
+ Pengguna Usia Lanjut: Jumlah pengguna yang berusia di atas 60 tahun relatif kecil.

Kesimpulan:

+ Grafik menunjukkan bahwa platform ini didominasi oleh pengguna muda.
+ Distribusi usia pengguna tidak merata, dengan konsentrasi tinggi pada kelompok usia tertentu.

## 7. *Data Preparation*

Berikut adalah tahapan-tahapan yang dilakukan:

1. Mengatasi *missing value*: Melakukan penanganan terhadap nilai yang hilang pada dataset, seperti menghapus baris atau mengisi nilai yang hilang dengan metode tertentu, seperti *mean* atau median.
2. Mengambil kolom yang diperlukan dan merubah nama kolom: Memilih kolom-kolom yang relevan untuk analisis dan memberikan nama baru jika diperlukan.
3. *Exclude* data *rating* yang ingin dihapus dari dataset: Menghapus data dengan rating tertentu yang ingin dikecualikan dari analisis.
4. *Reset* indeks *dataframe* untuk menghindari *error*: Mereset indeks *dataframe* setelah melakukan operasi penghapusan atau pemrosesan data agar indeks kembali terurut secara berurutan.
5. Konversi kolom "rating" ke *int64 data type*: Mengubah tipe data kolom "rating" menjadi tipe data int64 untuk mempermudah analisis numerik.
6. Melakukan *merge* dari *dataframe* berdasarkan kolom 'ISBN'

## 8. *Modelling*

Pada proyek ini diterapkan 2 tipe model, yaitu *Content-Based Filtering* dan *Collaborative-Based Filtering*.

### *Content-Based Filtering*

*Content-Based Filtering* adalah pendekatan dalam sistem rekomendasi yang mengandalkan analisis konten dari item yang direkomendasikan. 

Dalam konteks sistem rekomendasi buku pada aplikasi e-perpustakaan, pendekatan ini akan menganalisis fitur-fitur konten dari buku, seperti judul buku, penulis buku, dan *rating* untuk memberikan rekomendasi yang relevan kepada pengguna.

Kelebihan *Content-Based Filtering*:
1. Personalisasi: Pendekatan *Content-Based Filtering* memungkinkan personalisasi yang tinggi, karena rekomendasi didasarkan pada preferensi pengguna yang diungkapkan melalui analisis konten buku.
2. Tidak tergantung pada data pengguna lain: Pendekatan ini tidak memerlukan informasi tentang preferensi pengguna lain, sehingga tidak bergantung pada data kolaboratif atau historis dari pengguna lainnya.
3. Memperhitungkan kepentingan unik pengguna: Pendekatan ini memperhitungkan preferensi pengguna yang spesifik dan tidak terpengaruh oleh tren atau preferensi umum.

Kekurangan *Content-Based Filtering*:
1. Terbatas pada fitur yang diamati: Pendekatan ini terbatas pada fitur-fitur yang diamati dan dianalisis dalam konten buku. Rekomendasi mungkin kurang beragam jika tidak ada fitur yang signifikan dalam analisis konten yang dapat membedakan kursus secara signifikan.
2. Tidak memperhitungkan preferensi baru: Pendekatan ini tidak secara otomatis menyesuaikan dengan perubahan preferensi pengguna. Jika preferensi pengguna berubah atau berkembang, rekomendasi mungkin tetap berfokus pada preferensi yang lebih lama.

Teknik Perhitungan Similarity:
1. *Cosine Similarity*: *Cosine Similarity* mengukur kesamaan antara dua vektor dengan menghitung kosinus sudut antara vektor-vektor tersebut. Dalam konteks *Content-Based Filtering*, *Cosine Similarity* digunakan untuk mengukur kesamaan antara vektor representasi fitur buku berdasarkan deskripsi, topik, atau keterampilan. Nilai *Cosine Similarity* berkisar antara -1 hingga 1, di mana nilai 1 menunjukkan kesamaan yang sempurna dan nilai -1 menunjukkan perbedaan yang sempurna.

2. **Euclidean Distance**: **Euclidean Distance** mengukur jarak antara dua titik dalam ruang Euclidean. Dalam konteks *Content-Based Filtering*, **Euclidean Distance** digunakan untuk mengukur jarak antara vektor representasi fitur buku. Semakin kecil nilai **Euclidean Distance**, semakin mirip kedua buku dalam hal fitur-fitur yang diamati.

Kedua teknik perhitungan *similarity* tersebut digunakan untuk membandingkan kesamaan antara buku dalam sistem rekomendasi. 

### Tahapan yang dilakukan dengan pendekatan *Content-Based Filtering*
Selama pendekatan ini, proses modeling dilakukan berdasar urutan sebagai berikut ini:

1. *TF-IDF Vectorizer*: Tahap ini melibatkan penggunaan TF-IDF (Term Frequency-Inverse Document Frequency) Vectorizer untuk mengubah teks pada deskripsi kursus menjadi representasi numerik. TF-IDF mengukur pentingnya suatu kata dalam dokumen berdasarkan frekuensi kemunculan kata tersebut dalam dokumen dan inversi frekuensi kemunculan kata tersebut dalam seluruh koleksi dokumen. *TF-IDF Vectorizer* menghasilkan vektor fitur yang merepresentasikan konten buku.

2. *Cosine Similarity*: Setelah mendapatkan vektor fitur menggunakan *TF-IDF Vectorizer*, tahap selanjutnya adalah menghitung kesamaan antara kursus menggunakan metode *Cosine Similarity*. *Cosine Similarity* mengukur kesamaan arah antara dua vektor dalam ruang vektor. Pada konteks *Content-Based Filtering*, *Cosine Similarity* digunakan untuk mengukur kesamaan antara vektor fitur buku berdasarkan deskripsi, topik, atau keterampilan yang terkait. Semakin tinggi nilai *Cosine Similarity*, semakin mirip kedua buku dalam hal fitur-fitur yang diamati.

Tabel 3. Hasil Perhitungan Cosine Similarity pada Matrix TF-IDF

```sh
array([[1., 0., 0., ..., 0., 0., 0.],
       [0., 1., 0., ..., 0., 0., 0.],
       [0., 0., 1., ..., 0., 0., 0.],
       ...,
       [0., 0., 0., ..., 1., 0., 0.],
       [0., 0., 0., ..., 0., 1., 0.],
       [0., 0., 0., ..., 0., 0., 1.]])
```

Tabel 8.1 Sampel Hasil *Similarity Matrix* Dengan *Cosine-Similarity* pada Setiap Buku

|  Book_Title 	|  The Circle of Simplicity: Return to the Good Life	 	| The Heart of a Goof	  	|   The Log from the Sea of Cortez (Penguin Great Books of the 20th Century)		|  Criminals 	|   Hawaii (Frommer's City Guides)	|
|---	|---	|---	|---	|---	|---	|
|  McAuslan in the Rough	 	|  0.0 	|   0.0	|  0.0 	|   0.0	|   0.0	|
|   How a Seed Grows (Let's-Read-and-Find-Out Science)		|  0.0 	|   0.0	|  0.0 	|  0.0 	|  0.0 	|
|   The Shape of Things to Come		|   0.0	|  0.0 	|   0.0	|  0.0 	|  0.0 	|
|  Art Since 1940 (2nd Edition)	 	|  0.0 	|  0.0 	| 0.0  	|   0.0	|  0.0 	|
|  The Horse's Mouth	 	|   0.0	|  0.0 	|   0.0	|   0.0	| 0.0  	|

### *Collaborative Filtering*

*Collaborative Filtering* adalah pendekatan dalam sistem rekomendasi yang mengandalkan kumpulan informasi dari pengguna lain dalam menghasilkan rekomendasi. 

Pendekatan ini mencoba untuk menemukan pola kolaboratif antara pengguna dan item yang direkomendasikan berdasarkan interaksi atau preferensi mereka.

Ada dua jenis utama dalam *Collaborative Filtering*:
1. *User-Based Collaborative Filtering*: Pendekatan ini mencari kesamaan antara pengguna berdasarkan riwayat preferensi atau interaksi mereka dengan item. Jika dua pengguna memiliki pola preferensi yang serupa, kemungkinan besar mereka akan memiliki preferensi yang sama pada item yang belum mereka eksplorasi. Rekomendasi diberikan berdasarkan preferensi pengguna yang serupa.

2. *Item-Based Collaborative Filtering*: Pendekatan ini mencari kesamaan antara item berdasarkan riwayat preferensi atau interaksi pengguna dengan item tersebut. Jika dua item memiliki pola preferensi yang serupa dari pengguna yang sama, kemungkinan besar pengguna yang memiliki preferensi pada item pertama juga akan memiliki preferensi pada item kedua. Rekomendasi diberikan berdasarkan kesamaan antara item yang ada dengan item yang diminati oleh pengguna.

Kelebihan *Collaborative Filtering*:
1. *Discovery of Serendipity*: *Collaborative Filtering* dapat menghasilkan rekomendasi yang tidak terduga atau serendipitous. Pendekatan ini memungkinkan pengguna menemukan item baru yang mungkin tidak mereka eksplorasi sebelumnya.
2. Tidak tergantung pada fitur konten: Pendekatan ini tidak memerlukan informasi tentang fitur konten dari item yang direkomendasikan. Ini membuatnya berguna dalam situasi di mana informasi fitur tidak tersedia atau sulit untuk dianalisis.

Kekurangan *Collaborative Filtering*:
1. *Cold Start Problem*: *Collaborative Filtering* memiliki tantangan saat menghadapi pengguna baru atau item baru. Jika tidak ada riwayat preferensi atau interaksi yang tersedia, sulit untuk memberikan rekomendasi yang relevan.
2. *Scalability*: Pendekatan ini dapat mengalami kesulitan dalam skala yang besar. Semakin banyak pengguna dan item yang ada, semakin sulit untuk menghasilkan rekomendasi yang akurat secara efisien.

Pendekatan *Collaborative Filtering* memanfaatkan informasi dari pengguna-pengguna lain untuk memberikan rekomendasi. 

Dalam praktiknya, seringkali pendekatan ini dikombinasikan dengan *Content-Based Filtering* untuk meningkatkan performa dan relevansi rekomendasi yang dihasilkan.

### *Training Model*

Pada tahapan training model, proses yang dilakukan adalah sebagai berikut: 

1. Splitting Data: Bagi data menjadi set pelatihan (*train set*) dan set pengujian (*test set*). Set pelatihan akan digunakan untuk melatih model, sedangkan set pengujian akan digunakan untuk menguji performa model secara independen. Perbandingan umum adalah sekitar 80% data untuk set pelatihan dan 20% untuk set pengujian.

2. Arsitektur Model: Tentukan arsitektur model *RecommenderNet* yang mana merupakan *framework* dari *TensorFlow* yang akan digunakan. *RecommenderNet* adalah model yang dirancang khusus untuk tugas rekomendasi dan memanfaatkan teknik deep learning untuk menghasilkan rekomendasi yang personal dan akurat. Arsitektur model *RecommenderNet* harus disesuaikan dengan masalah spesifik dan karakteristik data.

3. *Data Preparation* untuk *Training*: Melakukan pra-pemrosesan pada data pelatihan. Ini melibatkan konversi variabel kategori menjadi representasi numerik yang sesuai, normalisasi data jika diperlukan, dan pembuatan data dalam bentuk yang cocok untuk pelatihan model *RecommenderNet*.

4. *Training Model*: Melatih model *RecommenderNet* menggunakan set pelatihan. Selama proses pelatihan, model akan mempelajari pola-pola dan relasi antara pengguna dan kursus untuk menghasilkan rekomendasi yang tepat. Proses ini melibatkan optimisasi parameter melalui iterasi berulang untuk mengurangi kesalahan dan meningkatkan kinerja model.

5. Evaluasi Model: Evaluasi performa model menggunakan set pengujian yang telah dipisahkan sebelumnya. Hitung metrik evaluasi yang sesuai, seperti akurasi, presisi, *recall*, dan *Root Mean Square Error (RMSE)* untuk mengukur sejauh mana model mampu memberikan rekomendasi yang relevan dan sesuai dengan preferensi pengguna.
   
+ Presisi adalah fraksi positif yang benar di antara semua prediksi positif. Dengan kata lain, ini memberi tahu terkait banyak item yang diklasifikasikan sebagai positif oleh model yang sebenarnya positif.
  
+ *Recall* adalah fraksi positif yang benar di antara semua positif yang sebenarnya. Dengan kata lain, ini memberi tahu terkait jumlah proporsi item positif aktual yang diidentifikasi dengan benar oleh model.
  
+ *F1-Score* adalah rata-rata harmonis dari presisi dan *recall*, yang merupakan cara untuk menyeimbangkan dua metrik ke dalam satu skor. Skor F1 yang lebih tinggi menunjukkan kinerja keseluruhan yang lebih baik.

F1-Score = $2 * (Precision * Recall) / (Precision + Recall)$

Dimana:

+ *Precision*: fraksi positif yang benar di antara semua prediksi positif. Dengan kata lain, ini memberi tahu terkait banyak item yang diklasifikasikan sebagai positif oleh model yang sebenarnya positif

+ *Recall*: fraksi positif yang benar di antara semua positif yang sebenarnya. Dengan kata lain, ini memberi tahu terkait jumlah proporsi item positif aktual yang diidentifikasi dengan benar oleh model
  
+  RMSE adalah metrik umum yang digunakan untuk mengukur tingkat kesalahan suatu model dalam meramalkan nilai kontinu. Sederhananya, ini menunjukkan seberapa dekat prediksi model dengan nilai aktual. Semakin kecil nilai RMSE, semakin baik kinerja model
  
RMSE = $`\sqrt( 1/n * sum((y_true - y_pred)^2) )$

 
Dimana:

+ n: Jumlah *data points*
+ *y_true*: nilai y sebenarnya
+ *y_pred*: nilai y *predicted*


Dalam tahapan ini, data dipisahkan menjadi set pelatihan dan set pengujian untuk memastikan evaluasi yang objektif terhadap performa model. 

Set pelatihan digunakan untuk melatih model, sedangkan set pengujian digunakan untuk menguji performa model secara independen dan mengukur sejauh mana model dapat menggeneralisasi dengan baik ke data yang belum pernah dilihat sebelumnya.

Tabel 8.1 Hasil Top 5 Rekomendasi dengan *Cosine Similarity* Metode *Content-Based Filtering* Dengan Judul Buku "Johnny Panic and the Bible of Dreams: Short Stories, Prose, and Diary Excerpts" 

|   Book_Title	|  Book_Author 	|
|---	|---	|
|  Letters home: Correspondence, 1950-1963		|   Sylvia Plath	|
|  Johnny Panic and the Bible of Dreams : Short S...	 	|  Sylvia Plath 	|
|   Collected Poems Reissue		|   Sylvia Plath	|
|   The Bell Jar (Perennial Classics)		|  Sylvia Plath 	|
|   Letters Home: Correspondence, 1950-1963		|   Sylvia Plath	|

Tabel 8.2 Hasil Top 5 Rekomendasi dengan *Recommender Net* Metode *Collaborative Filtering* Dengan Buku Rating 5

|  Book Title	 	|   Book Author|
|---	|---	|
|  Politically Correct Bedtime Stories: Modern Ta...|   James Finn Garner|
|   The Lives of Christopher Chant		|   Diana Wynne Jones|
| Little Altars Everywhere|  Rebecca Wells|
|   The Holiday Present		|   Johanna Lindsey|
|The Perfect Storm : A True Story of Men Agains...|   Sebastian Junger|

## 9. Evaluation

Dalam proyek ini, dua metrik evaluasi yang berbeda akan digunakan berdasarkan pada metode pendekatan yang digunakan, yaitu *Precision* untuk pendekatan *Content-Based Filtering* dan *Root Mean Square Error* (RMSE) untuk pendekatan *Collaborative-Based Filtering*.

### 1. *Precision* (Presisi)

*Precision* adalah metrik evaluasi yang digunakan untuk mengukur keakuratan rekomendasi dalam pendekatan *Content-Based Filtering*. 

Presisi menghitung persentase rekomendasi yang relevan dari total rekomendasi yang diberikan kepada pengguna.

Presisi dihitung dengan membagi jumlah rekomendasi yang relevan dengan jumlah total rekomendasi yang diberikan. 

Semakin tinggi nilai presisi, semakin akurat sistem dalam memberikan rekomendasi yang relevan kepada pengguna.

### *Precision*, *Recall*, *F1-Score*

Berikut adalah tabel hasil evaluasi dari *Content-Based Filtering*

Tabel 8. Metrik Evaluasi dengan Pendekatan *Content-Based Filtering* (*Cosine Similarity*)


| *Precision*	| *Recall*  	|  *F1-Score* 	|
|---	|---	|---	|
|  1.0 	|   1.0	|   1.0	|

Interpretasi:

+ Nilai *Precision* 1.0 menunjukkan bahwa semua yang diklasifikasikan model sebagai positif memang benar-benar positif. Tidak ada positif palsu (*false positive*).
+ Nilai *Recall* 1.0 menunjukkan bahwa semua data positif telah teridentifikasi oleh model. Tidak ada positif yang terlewatkan (*false negative*).
+ Nilai *F1-Score* 1.0 merupakan kombinasi sempurna dari precision dan recall, menunjukkan bahwa model sangat akurat dalam membedakan positif dan negatif.

### *Root Mean Square Error (RMSE)*

RMSE adalah metrik evaluasi yang digunakan untuk mengukur sejauh mana model *Collaborative-Based Filtering* dapat memprediksi preferensi pengguna dengan akurat. 

*RMSE* mengukur selisih antara nilai rating yang diprediksi oleh model dan nilai rating sebenarnya dalam dataset.

RMSE dihitung dengan mengambil akar kuadrat dari rata-rata dari selisih kuadrat antara nilai rating yang diprediksi dan nilai rating sebenarnya. 

Semakin rendah nilai *RMSE*, semakin baik model dalam memprediksi preferensi pengguna dengan akurat.

Penggunaan metrik evaluasi yang sesuai untuk masing-masing pendekatan memungkinkan untuk mengukur kualitas dan performa dari sistem rekomendasi yang dikembangkan. 

*Precision* memberikan gambaran tentang sejauh mana rekomendasi yang diberikan sesuai dengan preferensi dan minat pengguna dalam pendekatan *Content-Based Filtering*. 

Sedangkan *RMSE* memberikan indikasi tentang tingkat akurasi prediksi preferensi pengguna dalam pendekatan *Collaborative-Based Filtering*.

Dengan menggunakan kedua metrik evaluasi ini, akan dapat dipahami sejauh mana sistem rekomendasi dapat memenuhi tujuan yang telah ditetapkan dan mengidentifikasi area perbaikan yang diperlukan untuk meningkatkan kualitas rekomendasi yang diberikan.

Gambar 8.1 Grafik Evaluasi *Collaborative Filtering* Dengan Metrik RMSE

![RMSE](https://github.com/PutraAndika88/Book-Recommendation/blob/main/img_book/evaluasi%20cf.png?raw=true)

Interpretasi:

+ Nilai RMSE *train* dan *test* berfluktuasi selama pelatihan.
+ Nilai RMSE *train* umumnya lebih rendah daripada nilai RMSE *test*. Hal ini menunjukkan bahwa model beradaptasi dengan data *training*, tetapi belum generalisasi dengan baik ke data *test*.
+ Nilai RMSE *train* menurun selama pelatihan, menunjukkan bahwa model belajar dan meningkatkan akurasinya.
+ Nilai RMSE *test* menurun pada awalnya, tetapi kemudian meningkat setelah epoch 30

## 10. Kesimpulan 

Proyek ini berhasil mengembangkan sebuah sistem rekomendasi yang dapat memberikan pengalaman pengguna yang lebih baik dalam mencari buku di e-perpustakaan. 

Dengan menerapkan pendekatan *Content-Based Filtering* dan *Collaborative Filtering*, sistem dapat memberikan rekomendasi buku yang relevan berdasarkan preferensi pengguna.

Melalui penggunaan metrik evaluasi yang relevan seperti *Precission*, *Recall*, *F1-Score*, dan *Root Mean Square Error* (RMSE), keberhasilan sistem akan dapat diukur dalam mencapai tujuan yang telah ditetapkan. 

Evaluasi terhadap pendekatan *Content-Based Filtering* menggunakan metrik *Precission*, *Recall*, *F1-Score*, sedangkan pendekatan *Collaborative Filtering* dievaluasi menggunakan metrik *RMSE*.

Dengan memberikan rekomendasi kursus yang relevan dan menarik, proyek ini berpotensi meningkatkan retensi pengguna pada e-perpustakaan. 

Rekomendasi yang disesuaikan dengan preferensi pengguna akan membantu pengguna dalam menemukan buku yang paling sesuai dengan kebutuhan dan minat mereka.

Selain itu, sistem rekomendasi ini juga dapat memberikan manfaat bagi e-perpustakaan dalam mengoptimalkan penyediaan buku yang relevan. 

Dalam hal meningkatkan konversi pengguna menjadi anggota e-perpustakaan premium, sistem rekomendasi dapat memainkan peran penting dengan menyediakan rekomendasi yang menarik dan memberikan nilai tambah kepada pengguna. 

Dengan memperhitungkan preferensi pengguna, sistem dapat memberikan rekomendasi buku yang relevan dengan minat dan kebutuhan mereka.

Selain itu, proyek ini juga berhasil melakukan analisis data pengguna untuk memahami perilaku, preferensi, dan kebutuhan pengguna dalam konteks rekomendasi kursus. 

Dengan menganalisis data secara efektif, akan didapatkan pelajaran berharga tentang pengguna dan menggunakan informasi ini untuk meningkatkan kualitas rekomendasi buku yang diberikan.

Secara keseluruhan, proyek ini berhasil mengimplementasikan sistem rekomendasi yang dapat meningkatkan pengalaman pengguna, retensi pengguna, konversi pengguna, dan pemahaman tentang pengguna dalam konteks rekomendasi buku di e-perpustakaan. 

Dengan menggunakan metrik evaluasi yang relevan, keberhasilan mencapai tujuan yang telah ditetapkan dan memberikan manfaat yang signifikan bagi pengguna dan e-perpustakaan dapat diukur.

## References

[1] 	A. Rifda, "Gramedia Blog," Kompas Gramedia, 2020. [Online]. Available: https://www.gramedia.com/best-seller/tren-pembaca-digital-2019-gramedia-digital/. [Accessed 10 Februari 2024].

[2] 	N. Muhammad, "Databoks Katadata," Katadata, 21 09 2023. [Online]. Available: https://databoks.katadata.co.id/datapublish/2023/09/21/survei-mayoritas-orang-indonesia-lebih-suka-baca-buku-lewat-smartphone. [Accessed 2024 02 10].

[3] 	N. a. L. K. a. N. Kurmashov, "Online Book Recommendation System," in 2015 Twelve International Conference on Electronics Computer and Computation (ICECCO), Kazakhstan, 2015. 

[4] 	Universitas Airlangga, "Perpustakaan Digital: Memanfaatkan Koleksi Digital Untuk Penelitian dan Inovasi," Universitas Airlangga, 01 Juli 2023. [Online]. Available: https://vokasi.unair.ac.id/2023/07/01/perpustakaan-digital-memanfaatkan-koleksi-digital-untuk-penelitian-dan-inovasi/. [Accessed 10 02 2024].

[5] 	I. S. M. K. S. S. W. Noor Ifada, "Enhancing The Performance of Library Book Recommendation System by Employing The Probabilistic-Keyword Model on a Collaborative Filtering Approach," Procedia Computer Science, vol. 157, pp. 345-352, 2019. 
