# Laporan Proyek Machine Learning - Firda Sa'baniyah

## Domain Proyek

Domain proyek yang dipilih dalam proyek machine learning ini mengenai kesehatan dengan judul "Prediksi Harga Asuransi Kesehatan".

* #####  Latar Belakang 

Asuransi kesehatan merupakan suatu instrumen sosial untuk menjamin bahwa seseorang dapat memenuhi kebutuhan pemeliharaan kesehatan tanpa mempertimbangkan keadaan ekonomi orang tersebut pada waktu terjadinya kebutuhan pelayanan kesehatan. Indonesia termasuk negara berkembang yang tidak menyediakan pemenuhan seluruh kebutuhan pelayanan kesehatan, akan tetapi juga tidak sama sekali menyerahkan kepada masyarakat. Pembangunan Puskesmas dan rumah sakit di seluruh Indonesia dimaksudkan untuk menjamin bahwa penduduk tidak mampu dapat memenuhi kebutuhan kesehatannya. 

Sebab dewasa ini, kesehatan adalah hal terpenting dan paling berharga. Namun ketahuilah bahwasanya, biaya medis akan terus mengalami kenaikan seiring dengan berjalannya waktu. Oleh karenanya, setiap orang perlu antisipasi hal tersebut dengan mengetahui prediksi harga asuransi kesehatan. Untuk itu penggunaan machine learning dalam melakukan prediksi serta dengan menggunakan model regresi linear sangat dibutuhkan untuk dijadikan sebagai solusidalam pemecahan masalah. Projek ini mengimplementasikan prediksi biaya asuransi kesehatan dengan dipengaruhi dari berbagai faktor seperti umur, jenis kelamin, bmi (kategori berat badan), banyaknya anak, apakah seorang perokok atau bukan serta wilayah.

**Rubrik/Kriteria Tambahan**:
- Salah satu masalah yang sering dihadapi oleh penduduk dalam mengakses layanan kesehatan adalah hambatan finansial. Untuk itu dibutuhkan sistem pembiayaan kesehatan yang mampu menghilangkan hambatan tersebut dan menjangkau seluruh penduduk. Karenaya prediksi harga asuransi memiliki manfaat dengan memberikan solusi finansial ketika tertanggung mengalami risiko medis. Asuransi kesehatan penting karena risiko sakit bisa menimpa siapa saja, baik usia muda dan tua.
- Secara keseluruhan penduduk yang tidak memiliki jaminan kesehatan mempunyai probabilitas mengalami gangguan kesehatan (selama sebulan terakhir) lebih tinggi dibandingkan dengan penduduk yang memiliki jaminan kesehatan. Hal itu terlihat baik untuk tahun 1995 maupun 1998. Pada penduduk yang memiliki jaminan kesehatan, 272
dari 1.000 orang (tahun 1998) mengalami gangguan kesehatan, sementara pada penduduk yang tidak mempunyai jaminan kesehatan jumlah tersebut lebih besar yaitu 281 per 1.000 orang. 
  
   Referensi: [Tinjauan Akademis Asuransi Kesehatan Nasional](https://staff.ui.ac.id/system/files/users/hasbulah/material/tinjauanakademisasuransikesehatannasional.pdf) 

## Business Understanding

#### Problem Statements

berdasarkan latar belakang diatas, berikut ini rumusan masalah yang dapat diselesaikan pada proyek ini:
* Bagaimana cara melakukan pra-pemrosesan pada data Issurance yang akan digunakan untuk membuat model yang baik?
* Bagaimana cara membuat model untuk memprediksi harga asuransi kesehatan dengan menggunakan _machine learning_?
* Berapa nilai yang akan muncul mengenai akurasi terbaik yang didapatkan dengan menggunakan _machine learning_?

### Goals

* Melakukan pra-pemrosesan dengan sangat baik supaya dapat digunakan dalam pembuatan model.
* Mengetahui cara membuat model machine learning untuk memprediksi harga asuransi kesehatan.
* Membuat model _machine learning_ dengan nilai akurasi yang mencapai 90%.

#### Solution Statements
Solusi yang dapat dilakukan untuk memenuhi tujuan dari proyek ini diantaranya :
* Untuk pra-pemrosesan data dapat dilakukan beberapa teknik, diantaranya :
    * Mengecek terlebih dahulu terhadap data yang kosong.
    * Melakukan Encoding terhadap kolom yang bertipe _object_.
    * Mengatasi masalah data tidak seimbang dengan _resample_.
    * Melakukan pembagian dataset menjadi dua bagian dengan rasio 80% untuk data latih dan 20% untuk data uji.
    * Melakukan _Standard Scaler_.


* Untuk membuat maka model dipilih penggunaan dengan algoritma Random Forest dan K-Nearest Neighbor. Algoritma tersebut dipilih karena mudah digunakan dan juga cocok untuk kasus ini. Berikut cara kerja, kelebihan dan kekurangan algoritma Random Forest dan K-Nearest Neighbor:
    * Cara kerja Algoritma Random Forest [[1]](https://repository.usd.ac.id/35513/):
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

Sumber | [Kaggle Dataset : Medical Cost Personal Datasets](kaggle datasets download -d mirichoi0218/insurance)
Lisensi | http://opendatacommons.org/licenses/dbcl/1.0/
Kategori | Kesehatan
Jenis dan Ukuran Berkas | CSV (16 kB)

### Variabel-variabel pada dataset Issurance adalah sebagai berikut:
- Age: usia penerima manfaat utama.
- Sex: jenis kelamin kontraktor asuransi, perempuan, laki-laki.
- bmi: Indeks massa tubuh, memberikan pemahaman tentang tubuh, berat badan yang relatif tinggi atau rendah relatif terhadap tinggi badan,
indeks objektif berat badan (kg/m^2) menggunakan rasio tinggi terhadap berat badan, idealnya 18,5 hingga 24,9.
- children: Jumlah anak yang ditanggung oleh asuransi kesehatan / Jumlah tanggungan
- smoker: Merokok
- region: daerah perumahan penerima di AS, timur laut, tenggara, barat daya, barat laut.
- charges: Biaya medis individu ditagih oleh asuransi kesehatan


## Data Preparation
* Melakukan Encoding terhadap kolom yang bertipe object
* Data bertipe object tidak dapat diproses dalam machine learning, maka dari harus diubah dalam bentuk numerik. Ada beberapa cara melakukan encoding categorical data dengan melakukan _label encoding_ dan _one hot encoding_. _Label encoding_ mengubah setiap nilai dalam kolom menjadi angka yang berurutan.
* _One hot encoding_ adalah teknik yang merubah setiap nilai di dalam kolom menjadi kolom baru dan mengisinya dengan nilai biner yaitu 0 dan 1. Contoh pada kolom _gender_ yang memiliki 2 nilai yaitu "Female" atau "Male".
* Melakukan pembagian dataset dengan 80% untuk data latih dan 20% untuk data uji. Setelah melakukan pra-pemrosesan ke dataset, selanjutnya adalah membagi dataset untuk data latih dan data uji dengan rasio 80:20. Data latih adalah data yang hanya untuk melatih model, sedangkan data uji adalah data yang hanya sebagai uji coba model. Pembagian dataset ini menggunakan modul train_test_split dari scikit-learn.
* Melakukan standardisasi data pada semua fitur data. Tahapp terakhir yaitu melakukan standarisasi data. Hal ini dilakukan untuk membuat semua fitur berada dalam skala data yang sama yaitu dengan range 0-1.


## Modeling
- Setelah dilakukan pra-pemrosesan pada dataset, langkah selanjutnya adalah _modeling_ terhadap data. Pada tahap ini menggunakan 2 algoritma yaitu Random Forest dan K-Nearest Neighbor dengan adanya tambahan parameter. Pertama-tama kedua model ini dilatih menggunakan data latih. Setelah itu kedua model akan diuji dengan data uji. Terakhir kedua model akan diukur nilai akurasinya.
- Pada model dengan algoritma Random Forest memiliki nilai akurasi, _f1-score_, _recall_ dan _precision_ lebih tinggi dibanding dengan algoritma K-Nearest Neighbor. Untuk membuktikannya, kedua model tersebut diuji pada data uji dan di visualisasikan pada confussion matrix seperti berikut. 
- Dengan hasil diatas, maka model dengan algoritma Random Forest merupakan model yang dipilih untuk digunakan.



## Evaluation
Pada proyek ini, model yang dikembangkan adalah kasus klasifikasi dan menggunakan metriks akurasi, _f1-score_, _recall_ dan _precision_. 

**Referensi**

 [[1]](https://repository.usd.ac.id/35513/)
 [[2]](https://eprints.umm.ac.id/39299/)
 [[3]](https://publikasi.dinus.ac.id/index.php/jais/article/view/1189/)
 [[4]](https://simdos.unud.ac.id/uploads/file_penelitian_1_dir/721bdb509a6f0bb9ccca6d7374b86759.pdf)
