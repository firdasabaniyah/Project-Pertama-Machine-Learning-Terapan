# Laporan Proyek Machine Learning - Firda Sa'baniyah

## Domain Proyek

Domain proyek yang dipilih dalam proyek machine learning ini mengenai kesehatan dengan judul "Prediksi Harga Asuransi Kesehatan".

##### Latar Belakang 

![menentukan-plan-asuransi-kesehatan](https://user-images.githubusercontent.com/111235408/193184803-c674ebd8-ddd1-4760-ba38-799fbddf27fc.jpeg)


Asuransi kesehatan merupakan suatu instrumen sosial untuk menjamin bahwa seseorang dapat memenuhi kebutuhan pemeliharaan kesehatan tanpa mempertimbangkan keadaan ekonomi orang tersebut pada waktu terjadinya kebutuhan pelayanan kesehatan. Indonesia termasuk negara berkembang yang tidak menyediakan pemenuhan seluruh kebutuhan pelayanan kesehatan, akan tetapi juga tidak sama sekali menyerahkan kepada masyarakat. Pembangunan Puskesmas dan rumah sakit di seluruh Indonesia dimaksudkan untuk menjamin bahwa penduduk tidak mampu dapat memenuhi kebutuhan kesehatannya. 

Sebab dewasa ini, kesehatan adalah hal terpenting dan paling berharga. Namun ketahuilah bahwasanya, biaya medis akan terus mengalami kenaikan seiring dengan berjalannya waktu. Oleh karenanya, setiap orang perlu antisipasi hal tersebut dengan mengetahui prediksi harga asuransi kesehatan. Untuk itu penggunaan machine learning dalam melakukan prediksi serta dengan menggunakan model regresi linear sangat dibutuhkan untuk dijadikan sebagai solusi dalam pemecahan masalah. Projek ini mengimplementasikan prediksi biaya asuransi kesehatan dengan dipengaruhi dari berbagai faktor seperti umur, jenis kelamin, bmi (kategori berat badan), banyaknya anak, apakah seorang perokok atau bukan serta wilayah dan yang paling utama yaitu harga/biaya.

##### **Rubrik/Kriteria Tambahan:**
- Salah satu masalah yang sering dihadapi oleh penduduk dalam mengakses layanan kesehatan adalah hambatan finansial. Untuk itu dibutuhkan sistem pembiayaan kesehatan yang mampu menghilangkan hambatan tersebut dan menjangkau seluruh penduduk. Karenaya prediksi harga asuransi memiliki manfaat dengan memberikan solusi finansial ketika tertanggung mengalami risiko medis. Asuransi kesehatan penting karena risiko sakit bisa menimpa siapa saja, baik usia muda ataupun tua.
- Menurut data dari jurnal menyatakan bahwa secara keseluruhan penduduk yang tidak memiliki jaminan kesehatan mempunyai probabilitas mengalami gangguan kesehatan (selama sebulan terakhir) lebih tinggi dibandingkan dengan penduduk yang memiliki jaminan kesehatan. Hal itu terlihat dari tahun 1995 maupun 1998. Pada penduduk yang memiliki jaminan kesehatan, 272 dari 1.000 orang (tahun 1998) mengalami gangguan kesehatan, sementara pada penduduk yang tidak mempunyai jaminan kesehatan jumlah tersebut lebih besar yaitu 281 per 1.000 orang. 
  
   Referensi: [Tinjauan Akademis Asuransi Kesehatan Nasional](https://staff.ui.ac.id/system/files/users/hasbulah/material/tinjauanakademisasuransikesehatannasional.pdf) 

## Business Understanding

##### Problem Statements

Berdasarkan latar belakang yang telah dijelaskan diatas, berikut ini rumusan masalah yang dapat diselesaikan :
* Bagaimana cara melakukan pra-pemrosesan pada data Issurance yang akan digunakan untuk membuat model yang baik?
* Apa saja tahapan yang dapat dilakukan untuk menyelesaikan kasus prediksi Harga Asuransi Kesehatan dalam proyek ini?
* Bagaimana cara membuat model untuk memprediksi Harga Asuransi Kesehatan dengan menggunakan _machine learning_?
* Apa model yang tepat untuk digunakan dalam menyelesaikan kasus memprediksi Harga Asuransi Kesehatan?
* Berapa nilai yang akan muncul mengenai akurasi terbaik yang didapatkan dengan menggunakan _machine learning_?

##### Goals

* Melakukan pra-pemrosesan dengan sangat baik supaya dapat digunakan dalam pembuatan model.
* Mengetahui tahapan yang dapat dilakukan untuk menyelesaikan kasus prediksi Harga Asuransi Kesehatan.
* Mengetahui cara membuat model machine learning untuk memprediksi harga asuransi kesehatan.
* Menentukan model yang tepat untuk digunakan dalam menyelesaikan kasus prediksi Harga Asuransi Kesehatan.
* Membuat model _machine learning_ dengan nilai akurasi yang mencapai 90%.

##### **Rubrik/Kriteria Tambahan**:

#### Solution Statements
Solusi yang dapat dilakukan untuk memenuhi tujuan dari proyek ini diantaranya :
* Untuk pra-pemrosesan data dapat dilakukan beberapa teknik, diantaranya :
    * Mengecek terlebih dahulu terhadap data yang kosong.
    * Melakukan Encoding terhadap kolom yang bertipe _object_.
    * Mengatasi masalah data tidak seimbang dengan _resample_.
    * Melakukan pembagian dataset menjadi dua bagian dengan rasio 80% untuk data latih dan 20% untuk data uji.
    * Melakukan _Standard Scaler_.
 
* Untuk membuat model Machine Learning maka model dipilih penggunaan dengan algoritma Random Forest dan K-Nearest Neighbor. Algoritma tersebut dipilih karena mudah  digunakan dan juga cocok untuk kasus ini. Berikut cara kerja, kelebihan dan kekurangan algoritma Random Forest dan K-Nearest Neighbor:
    * Cara kerja Algoritma Random Forest [[1]](https://repository.usd.ac.id/35513/):
      Random Forest bekerja dengan membangun beberapa decision tree dan menggabungkannya demi mendapatkan prediksi yang lebih stabil dan akurat.
        * Tahap awal yaitu dengan pemilihan k pada sampel dataset yang diambil secara acak dengan pengembalian
        * Gunakan dataset untuk membangun _decision tree_ ke-i
        * Ulangi langkah kedua langkah diatas sebanyak k.
    * Kelebihan dan kekurangan Algoritma Random Forest [[2]](https://eprints.umm.ac.id/39299/):
        * Kelebihannya yaitu dapat mengatasi _noise_ dan _missing value_ serta dapat mengatasi data dalam jumlah yang besar.
        * Kekurangan pada algoritma Random Forest yaitu interpretasi yang sulit dan membutuhkan tuning model yang tepat untuk data. 
    * Cara kerja Algoritma K-Nearest Neighbor [[3]](https://publikasi.dinus.ac.id/index.php/jais/article/view/1189/):
        * Menentukan jumlah tetangga terdekat K
        * Menghitung jarak dokumen _testing_ ke dokumen _training_
        * Urutkan data berdasarkan data yang mempunyai jarak Euclidean terkecil
        * Tentukan kelompok testing berdasarkan label pada K.
    * Kelebihan dan kekurangan Algoritma K-Nearest Neighbor [[4]](https://simdos.unud.ac.id/uploads/file_penelitian_1_dir/721bdb509a6f0bb9ccca6d7374b86759.pdf):
        * KNN memiliki beberapa kelebihan yaitu bahwa algoritmanya tangguh terhadap _training_ data yang _noisy_ dan efektif apabila data latihnya besar.
        * Kekurangan pada algoritma KKN yaitu perlu menentukan nilai dari parameter K (jumlah dari tetangga terdekat), Pembelajaran berdasarkan jarak tidak jelas mengenai jenis jarak apa yang harus digunakan dan atribut mana yang harus digunakan untuk mendapatkan hasil yang terbaik dan Biaya komputasi cukup tinggi karena diperlukan perhitungan dari jarak tiap sample uji pada keseluruhan sample latih.

## Data Understanding

| Sumber | [Kaggle Dataset : Medical Cost Personal Datasets](https://www.kaggle.com/datasets/mirichoi0218/insurance)|
| ------------ |---------------| 
| Lisensi | http://opendatacommons.org/licenses/dbcl/1.0/ |
| Kategori | Kesehatan |
| Jenis dan Ukuran Berkas | CSV (16 kB) |

### Variabel-variabel pada dataset Issurance adalah sebagai berikut:
- Age: usia penerima manfaat utama.
- Sex: jenis kelamin kontraktor asuransi, perempuan, laki-laki.
- bmi: Indeks massa tubuh, memberikan pemahaman tentang tubuh, berat badan yang relatif tinggi atau rendah relatif terhadap tinggi badan,
indeks objektif berat badan (kg/m^2) menggunakan rasio tinggi terhadap berat badan, idealnya 18,5 hingga 24,9.
- children: Jumlah anak yang ditanggung oleh asuransi kesehatan / Jumlah tanggungan
- smoker: Merokok
- region: daerah perumahan penerima di AS, timur laut, tenggara, barat daya, barat laut.
- charges: Biaya medis individu ditagih oleh asuransi kesehatan.

##### **Rubrik/Kriteria Tambahan**:

- Exploratory data analysis
Exploratory data analysis atau sering disingkat EDA merupakan proses investigasi awal pada data untuk menganalisis karakteristik, menemukan pola, anomali, dan memeriksa asumsi pada data. Teknik ini biasanya menggunakan bantuan statistik dan representasi grafis atau visualisasi. [[5]](https://www.dicoding.com/academies/319/tutorials/17008)

| # | Column | Non-Null | Count | Dtype |
| ------------ |---------------| ---------------| ---------------| ---------------| 
| 0 | age | 1338 | non-null | int64 |
| 1 | sex | 1338 | non-null | object |
| 3 | bmi | 1338 | non-null | float64 |
| 4 | children | 1338 | non-null | int64 |
| 5 | smoker | 1338 | non-null | object |
| 6 | region | 1338 | non-null | object |
| 7 | charges | 1338 | non-null | float64 |

Dari output terlihat bahwa bahwasanya data insurance:

- Terdapat 3 kolom dengan tipe object, yaitu: sex, smoker, dan region. Kolom ini merupakan categorical features (fitur non-numerik).
- Terdapat 2 kolom numerik dengan tipe data float64 yaitu: bmi dan charges. Ini merupakan fitur numerik yang merupakan hasil pengukuran secara fisik.
- Terdapat 2 kolom numerik dengan tipe data int64, yaitu: age dan children. Kolom ini merupakan target fitur kita.

Uraian tersebut menunjukkan bahwa setiap kolom telah memiliki tipe data yang sesuai. Selanjutnya, cek deskripsi statistik data dengan fitur describe().
 
| | age | bmi | children | charges | 
| ------------ |---------------| ---------------| ---------------| ---------------|
| count | 1338.000000 | 1338.000000 | 1338.000000 | 1338.000000 |
| mean | 39.207... | 30.66... | 1.094... | 13270.422... |
| std | 14.049... | 6.098... | 1.205... | 12110.0112... |
| min | 18.000000 | 15.96... | 0.000... | 1121.873... |
| 25% | 27.000000 | 26.29... | 0.000... | 4740.287... |
| 50% | 39.000000 | 30.40... | 1.000... | 9382.033... |
| 75% | 51.000000 | 34.69... | 2.000... | 16639.912... |
| max | 64.000000 | 53.13... | 5.000... | 63770.428... |

Fungsi describe() memberikan informasi statistik pada masing-masing kolom, antara lain:

- Count  adalah jumlah sampel pada data.
- Mean adalah nilai rata-rata.
- Std adalah standar deviasi.
- Min yaitu nilai minimum setiap kolom. 
- 25% adalah kuartil pertama. Kuartil adalah nilai yang menandai batas interval dalam empat bagian sebaran yang sama. 
- 50% adalah kuartil kedua, atau biasa juga disebut median (nilai tengah).
- 75% adalah kuartil ketiga.
- Max adalah nilai maksimum.

- Missing Value
Dari analisis yang dilakukukan dalam data ini tidak terdapat missing value. Maka dari itu, tidak perlu dilakukannya tahap menemukan missing value ini.

- Menangani Pencilan (Outliers)
Outliers adalah titik data yang berbeda secara signifikan dari pengamatan lainnya sehingga dapat berakibat buruk pada model prediksi. Pada proyek ini menggunakan IQR (InterQuartile Range) untuk mendeteksi outliers. IQR dapat menentukan data outliers yang kondisinya di luar batas bawah atau batas atas dari dataset. IQR dapat divisualkan menggunakan boxplot.

- Univariate Analysis
Selanjutnya, kita akan melakukan proses analisis data dengan teknik Univariate EDA. Pertama, bagi fitur pada dataset menjadi dua bagian, yaitu numerical features dan categorical features. Data yang termasuk numerical_features adalah age, bmi, children, charges. Sedangkan untuk categorical_features adalah sex, smoker, region.

Sementara itu, pada bagian metrik dapat di simpulkan bahwa Koefisien korelasi berkisar antara -1 dan +1. Ia mengukur kekuatan hubungan antara dua variabel serta arahnya (positif atau negatif). Mengenai kekuatan hubungan antar variabel, semakin dekat nilainya ke 1 atau -1, korelasinya semakin kuat. Sedangkan, semakin dekat nilainya ke 0, korelasinya semakin lemah.  

Berikut beberapa tahapan visualisasi data pada data preparation:

- Pertama membagi dataset kedalam 2 bentuk variable, yaitu variable untuk kolom tipe numerik dan variable kolom untuk tipe object.
- Kemudian melakukan visualisasi distribusi categorial  dengan jumlah sampel  persentase male 676 dan female 662.
- lalu melakukan visualisasi distribusi numerik dengan tampilan terlihat dalam file ipynb.
- Selanjutnya visualisasi dilakukan untuk mengetahui korelasi antar fitur yg terdapat pada dataset. Terlihat pada tabel korelasi yang ditampilkan di file ipynb.


## Data Preparation
* Melakukan Encoding terhadap kolom yang bertipe objek.
* Data bertipe object tidak dapat diproses dalam machine learning, maka dari itu harus diubah dalam bentuk numerik. Ada beberapa cara melakukan encoding categorical data dengan melakukan _label encoding_ dan _one hot encoding_. _Label encoding_ mengubah setiap nilai dalam kolom menjadi angka yang berurutan.
* Proses Reduksi Dimensi dengan PCA dapat dilakukan dengan teknik reduksi (pengurangan) dimensi atau prosedur yang mengurangi jumlah fitur dengan tetap mempertahankan informasi pada data. Dengan menggunakan Principal Component Analysis atau PCA. PCA bekerja menggunakan metode aljabar linier. Ia mengasumsikan bahwa sekumpulan data pada arah dengan varians terbesar merupakan yang paling penting (utama). 
Dalam kode memanggil class PCA() dari library sciikit-learn. Paremeter yang dimasukkan ke dalam class adalah n_components dan random_state. Parameter n_components merupakan jumlah komponen atau dimensi, dalam kasus kita jumlahnya ada 3, yaitu children, age, dan bmi. Sedangkan, parameter random_state berfungsi untuk mengontrol random number generator yang digunakan. Menentukan parameter random_state bertujuan untuk dapat memastikan bahwa hasil pembagian dataset konsisten dan memberikan data yang sama setiap kali model dijalankan. [[6]](https://www.dicoding.com/academies/319/tutorials/18575)
* _One hot encoding_ adalah teknik yang merubah setiap nilai di dalam kolom menjadi kolom baru dan mengisinya dengan nilai biner yaitu 0 dan 1. Contoh pada kolom _gender_ yang memiliki 2 nilai yaitu "Female" atau "Male". Dengan melakukan mapping terhadap kolom diagnosis dari type object ke numerik agar bisa dibaca mesin. 
* Melakukan perhitungan jumlah baris terhadap kolom target.
* Melakukan pembagian dataset dengan 80% untuk data latih dan 20% untuk data uji. Setelah melakukan pra-pemrosesan ke dataset, selanjutnya adalah membagi dataset untuk data latih dan data uji dengan rasio 80:20. Data latih adalah data yang hanya untuk melatih model, sedangkan data uji adalah data yang hanya sebagai uji coba model. Pembagian dataset ini menggunakan modul train_test_split dari scikit-learn.
* Train-Test-Split 
Melakukan standardisasi data pada semua fitur data. Tahapp terakhir yaitu melakukan standarisasi data. Hal ini dilakukan untuk membuat semua fitur berada dalam skala data yang sama yaitu dengan range 0-1. Standardisasi adalah teknik transformasi yang paling umum digunakan dalam tahap persiapan pemodelan. Untuk fitur numerik, tidak akan melakukan transformasi dengan one-hot-encoding seperti pada fitur kategori. Saya akan menggunakan teknik StandarScaler dari library Scikitlearn, StandardScaler melakukan proses standarisasi fitur dengan mengurangkan mean (nilai rata-rata) kemudian membaginya dengan standar deviasi untuk menggeser distribusi.  StandardScaler menghasilkan distribusi dengan standar deviasi sama dengan 1 dan mean sama dengan 0. Sekitar 68% dari nilai akan berada di antara -1 dan 1.[[7]](https://www.dicoding.com/academies/319/tutorials/18575)


## Modeling
- Setelah dilakukan pra-pemrosesan pada dataset, langkah selanjutnya adalah _modeling_ terhadap data. Pada tahap ini menggunakan 2 algoritma yaitu Random Forest dan K-Nearest Neighbor dengan adanya tambahan parameter. Pertama-tama kedua model ini dilatih menggunakan data latih. Setelah itu kedua model akan diuji dengan data uji. Terakhir kedua model akan diukur nilai akurasinya.
- Pada model dengan algoritma Random Forest memiliki nilai akurasi, _f1-score_, _recall_ dan _precision_ lebih tinggi dibanding dengan algoritma K-Nearest Neighbor. Untuk membuktikannya, kedua model tersebut diuji pada data uji dan di visualisasikan pada confussion matrix.
Pada kasus ini, Saya membuat prediksi dengan nilai k = 10 tetangga dan metric Euclidean untuk mengukur jarak antara titik. Pada tahap ini saya hanya melatih data training. Dengan memilih nilai k yang lebih besar dapat membantu menghindari overfit, meskipun kadang bisa menyebabkan kehilangan kemampuan prediksi. Pada prediksi dengan nilai k = 1 (hanya mengecek satu tetangga terdekat), maka hasilnya akan sangat rigid atau kaku. Sedangkan jika kita set nilai k lebih besar, misalnya pada kasus ini k = 10, maka hasil prediksi akan lebih smooth (halus).
- Confussion Matrix algoritma Random Forest: pada algoritma tersebut menjelaskan bahwa bagian atas kiri merepresentasikan TN (True negatif) yaitu data negatif yg diprediksi benar, dan bagian bawah kanan merupakan data positif yg di prediksi benar, selain itu merupakan data false negatif (atas kanan) dan false positif (bawah kiri), dimana hasil itu merupakan data negatif namun diprediksi positif maupun sebaliknya.

- Confussion Matrix algoritma K-Nearest Neighbor: pada penjelasan algoritma K-NN tidak jauh berbeda dengan algoritma random forest dimana bagian atas kiri merepresentasikan TN (True Negatif) yaitu data negatif yg diprediksi benar, dan bagian bawah kanan merupakan data positif yg di prediksi benar, selain itu merupakan data false negatif (atas kanan) dan false positif (bawah kiri), dimana hasil itu merupakan data negatif namun diprediksi positif maupun sebaliknya.

Pada kasus ini saya mengimport RandomForestRegressor dari library scikit-learn. saya juga mengimpor mean_squared_error sebagai metrik untuk mengevaluasi performa model. Berikutnya, Saya membuat variabel RF dan memanggil RandomForestRegressor dengan beberapa nilai parameter. Berikut adalah parameter-parameter yang digunakan:

* n_estimator: jumlah trees (pohon) di forest. Di sini kita set n_estimator=50.
* max_depth: kedalaman atau panjang pohon. Ia merupakan ukuran seberapa banyak pohon dapat membelah (splitting) untuk membagi setiap node ke dalam jumlah * pengamatan yang diinginkan.
* random_state: digunakan untuk mengontrol random number generator yang digunakan. 
* n_jobs: jumlah job (pekerjaan) yang digunakan secara paralel. Ia merupakan komponen untuk mengontrol thread atau proses yang berjalan secara paralel. * n_jobs=-1 artinya semua proses berjalan secara paralel.

- Selain ke-2 model yang telah saya sebutkan diatas saya juga menggunakan algoritma boosting yaitu bekerja dengan membangun model dari data latih. 
Berikut merupakan parameter-parameter yang digunakan pada potongan kode di atas.

* learning_rate: bobot yang diterapkan pada setiap regressor di masing-masing proses iterasi boosting.
* random_state: digunakan untuk mengontrol random number generator yang digunakan.

- Dengan hasil tersebut, maka model dengan algoritma Random Forest merupakan model yang dipilih untuk digunakan.



## Evaluation
Pada proyek ini, metrik yang akan Saya gunakan pada prediksi ini adalah MSE atau Mean Squared Error yang menghitung jumlah selisih kuadrat rata-rata nilai sebenarnya dengan nilai prediksi. 

Dengan rumus penyelesaian :
![gambar 2](https://user-images.githubusercontent.com/111235408/193244772-a218c80c-ba86-4bfb-b5e9-3d3e5d4d44da.png)

Keterangan :

N = jumlah dataset

yi = nilai sebenarnya

y_pred = nilai prediksi

Namun, sebelum menghitung nilai MSE dalam model, Saya melakukan proses scaling fitur numerik pada data uji terlebih dulu. Selanjutnya, Saya dapat mengevaluasi ketiga model dengan metrik MSE. Saat menghitung nilai Mean Squared Error pada data train dan test, Saya membaginya dengan nilai 1e3. Hal ini bertujuan agar nilai mse berada dalam skala yang tidak terlalu besar.

Dengan hasil perhitungan sebagai berikut :
|  | train | test | 
| ------------ |---------------| ---------------| 
| KNN | 47179.514392 | 50241.517842 |
| RF | 10232.997408 | 43768.417466 | 
| Boosting | 48200.12633 | 46166.39224 | 

![gambar 3](https://user-images.githubusercontent.com/111235408/193245819-5f56e140-e386-44d0-b9c1-23fda2c7d3a5.png)

Dari gambar di atas, terlihat bahwa, model Random Forest (RF) memberikan nilai eror yang paling kecil. Sedangkan model dengan KNN memiliki eror yang paling besar (berdasarkan grafik, angkanya di atas 800). Model inilah yang akan Saya pilih sebagai model terbaik untuk melakukan prediksi Harga Asuransi Kesehatan.

**Referensi**

 [[1]](https://repository.usd.ac.id/35513/)
 [[2]](https://eprints.umm.ac.id/39299/)
 [[3]](https://publikasi.dinus.ac.id/index.php/jais/article/view/1189/)
 [[4]](https://simdos.unud.ac.id/uploads/file_penelitian_1_dir/721bdb509a6f0bb9ccca6d7374b86759.pdf)
 [[5]](https://www.dicoding.com/academies/319/tutorials/17008)
 [[6]](https://www.dicoding.com/academies/319/tutorials/18575)
 [[7]](https://www.dicoding.com/academies/319/tutorials/18575)
 
 
