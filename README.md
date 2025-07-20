# CAPSTONE-2--JCDS-2702----PRADNA-AQMARIL-PARAMITHA
Repository untuk Pradna Aqmaril Paramitha sebagai tempat menyimpan project yang dikerjakan selama menjalani program data science di Purwadhika BSD (JSCD-027).

## Latar belakang dan Rumusan Masalah
Supermarket BrightMart (Brightmart) adalah perusahaan di sektor ritel atau supermarket, yang menjual berbagai macam produk mulai dari kebutuhan pokok hingga kebutuhan tersier.

Sebagai upayanya untuk memahami pelanggan-pelanggannya dengan lebih baik, tim marketing Brightmart mengumpulkan data dari pelanggan-pelanggannya. Informasi yang disimpan antara lain demografi pelanggan, pembelian produk, respons terhadap kampanye, serta kanal-kanal pembelian yang dipakai pelanggan. Data tersebut dikumpulkan dalam suatu file yang bernama 'Supermarket Customers.csv'

Dengan data pelanggan tersebut, tim marketing Brightmart ingin membuat strategi kampanye yang mampu mendatangkan profitabilitas jangka panjang. Mereka berharap mampu meningkatkan pendapatan Supermarket Brightmart melalui strategi marketing yang lebih memahami kebutuhan pelanggan.

## Gambaran Umum Perusahaan Supermarket Brightmart

Supermarket BrightMart (Brightmart) adalah perusahaan di sektor ritel atau supermarket, yang menjual berbagai macam produk mulai dari kebutuhan pokok hingga kebutuhan tersier.

Sebagai upayanya untuk memahami pelanggan-pelanggannya dengan lebih baik, tim marketing Brightmart mengumpulkan data dari pelanggan-pelanggannya. Informasi yang disimpan antara lain demografi pelanggan, pembelian produk, respons terhadap kampanye, serta kanal-kanal pembelian yang dipakai pelanggan. Data tersebut dikumpulkan dalam suatu file yang bernama 'Supermarket Customers.csv'

Dengan data pelanggan tersebut, tim marketing Brightmart ingin membuat strategi kampanye yang mampu mendatangkan profitabilitas jangka panjang. Mereka berharap mampu meningkatkan pendapatan Supermarket Brightmart melalui strategi marketing yang lebih memahami kebutuhan pelanggan.

## Rumusan Masalah

Analisis ini bertujuan untuk mempelajari segmen pelanggan berdasarkan struktur rumah tangga yang paling tepat untuk diberi diskon sesuai kebiasaan belanja mereka.

Pertanyaan yang dapat dianalisis:
1. Bagaimana segmentasi pelanggan berdasarkan struktur rumah tangga (sendiri, berpasangan, dengan anak)?
2. Segmen barang apa yang menimbulkan pengeluaran biaya paling besar untuk tiap jenis struktur rumah tangga?
3. Seperti apa penggunaan diskon bagi segmen-segmen pelanggan tersebut?
4. Berdasarkan analisis kebiasaan belanja (jenis produk), segmen pelanggan mana yang paling responsif terhadap diskon?

Dengan menjawab pertanyaan-pertanyaan di atas, analisis diharapkan bisa memberikan insight yang medalam terhadap segmen berharga dan memberikan rekomendasi yang bermanfaat bagi tim marketing Brightmart untuk meningkatkan efisiensi biaya pemasaran, serta meningkatkan profitabilitas dan menjaga loyalitas dari pelanggan yang paling bernilai.

## Data Understanding and Cleaning

Keterangan Kolom

Data dari Supermarket Customers CSV

People

- ID: ID unik setiap pelanggan
- Year_Birth: Tahun lahir pelanggan
- Education: Tingkat pendidikan pelanggan
- Marital_Status: Status pernikahan pelanggan
- Income: Pendapatan tahunan pelanggan
- Kidhome: Jumlah anak-anak di rumah tangga pelanggan
- Teenhome: Jumlah remaja di rumah tangga pelanggan
- Dt_Customer: Tanggal pelanggan mulai berbelanja di supermarket
- Recency: Hari terakhir pelanggan melakukan pembelian
- Complain: 1 jika pelanggan melayangkan keluhan di dua tahun terakhir, 0 jika tidak

Produk
- MntWines: Jumlah yang dibelanjakan untuk wine dalam 2 tahun terakhir
- MntFruits: Jumlah yang dibelanjakan untuk buah-buahan dalam 2 tahun terakhir
- MntMeatProducts: Jumlah yang dibelanjakan untuk daging dalam 2 tahun terakhir
- MntFishProducts: Jumlah yang dibelanjakan untuk ikan dalam 2 tahun terakhir
- MntSweetProducts: Jumlah yang dibelanjakan untuk permen dalam 2 tahun terakhir
- MntGoldProds: Jumlah yang dibelanjakan untuk emas dalam 2 tahun terakhir

Promosi
- NumDealsPurchases: Jumlah pembelian yang dilakukan dengan diskon
- AcceptedCmp1: 1 jika pelanggan menerima penawaran di kampanye pertama, 0 jika tidak
- AcceptedCmp2: 1 jika pelanggan menerima penawaran di kampanye kedua, 0 jika tidak
- AcceptedCmp3: 1 jika pelanggan menerima penawaran di kampanye ketiga, 0 jika tidak
- AcceptedCmp4: 1 jika pelanggan menerima penawaran di kampanye ke-4, 0 jika tidak
- AcceptedCmp5: 1 jika pelanggan menerima penawaran di kampanye ke-5, 0 jika tidak
- Response: 1 jika pelanggan menerima penawaran di kampanye terakhir, 0 jika tidak

Place
- NumWebPurchases: Jumlah pembelian yang dilakukan melalui situs web perusahaan
- NumCatalogPurchases: Jumlah pembelian yang dilakukan menggunakan katalog
- NumStorePurchases: Jumlah pembelian yang dilakukan langsung di toko
- NumWebVisitsMonth: Jumlah kunjungan ke situs web perusahaan selama sebulan terakhir

### Data Cleaning

#### Drop

- Drop missing value dan outlier pada kolom income.
- Drop outlier pada total spending
- Kolom yang tidak terpakai sepeti‘Year_Birth’, ‘Education’, ‘Complain’,‘Dt_Customer’ ‘Z_CostContact’ ‘Z_Revenue’,‘NumWebPurchases’ ‘NumCatalogPurchases’ ‘NumStorePurchases’ ‘NumWebVisitsMonth’
- 
#### Data transformation

1. Mengubah nama nilai di kolom 'Marital_Status' menjadi "Single" dan "Couple" untuk pengelompokkan berdasarkan status pernikahan
2. Mengubah 'Response' menjadi 'AcceptedCmp6'
   
#### Membuat Kolom Baru
Membuat kolom baru:
- Childhome: Jumlah anak-anak dan remaja dalam rumah tangga
- HouseholdType: Klasifikasi tipe struktur rumah tangga berdasarkan jumlah orang dewasa dan anak-anak di rumah
- HouseholdSize: Klasifikasi ukuran rumah tangga berdasarkan jumlah anak-anak
- TotalSpending: total pengeluaran untuk semua produk
- TotalAcceptedCmp: Jumlah total penerimaan campaign dari 1-6

  #### Log Transform
  
  Log transform pada outlier di kolom baru 'TotalSpending'

## Data Analysis

Setelah data bersih, lanjut ke data analisis dengan tiga teknik analisis berbeda. Yaitu:
1. Statistika deskriptif.
2. Statistika inferensial.
3. Statistika deskriptif berupa diagram atau graphical summary.

### Segmentasi Pelanggan

Elemen paling penting dalam analisis ini adalah **segmentasi pelanggan berdasarkan struktur dan ukuran rumah tangga**. Karena itu, kita akan melakukan plotting untuk:
- `HouseholdType` untuk melihat tipe struktur rumah tangga berdasarkan jumlah orang dewasa di rumah serta berapa banyak jumlah anak yang menjadi tanggungan rumah tangga.
- `HouseholdSize` untuk melihat ukuran struktur rumah tangga berdasarkan jumlah anak-anak di rumah.

### Income dan Spending per HouseholdType dan HouseholdSize

Aspek yang sangat relevan dalam menganalisis segmen pelanggan berdasarkan rumah tangga adalah menganalisis kolom `Income` dan `Spending` untuk mempelajari **daya beli** masing-masing segmen. Hal ini memastikan agar segmen pelanggan yang ditarget dengan diskon atau kampanye akan menghasilkan penjualan secara konsisten. 

Dengan melakukan analisis daya beli. Kita dapat menjawab pertanyaan sebagai berikut:
- Segmen mana yang memiliki pendapatan paling tinggi dan segmen mana yang memiliki pendapatan paling rendah? Apakah segmen dengan pendapatan tertinggi otomatis mendorong pemebelanjaan tertinggi di supermarket?
- Kampanye apa yang cocok terhadap segmen pelanggan berdasarkan daya beli mereka?

 ### 3. Penggunaan Diskon tiap Segmen Pelanggan

 Setelah kita melihat kebiasaan belanja pada setiap segmen, selanjutnya kita melihat kebiasaan masing-masing segmen pelanggan dalam penggunaan diskon.

Kita akan menggunakan **rata-rata jumlah pembelian dengan diskon** agar kita dapat membandingkan perilaku individu dalam memanfaatkan diskon antar segmen rumah tangga. Penggunaan rata-rata memungkinkan kita melihat seberapa sering pelanggan dalam tiap segmen biasanya membeli produk dengan diskon, tanpa dipengaruhi oleh ukuran atau jumlah anggota dalam segmen tersebut, sehingga hasilnya lebih representatif untuk memahami kecenderungan penggunaan diskon.

### 4. Perilaku Penerimaan Penawaran pada Setiap Segmen Pelanggan

Berikutnya, kita dapat melihat perilaku setiap segmen pelanggan berdasarkan struktur dan ukuran rumah tangganya terhadap penerimaan tawaran saat dilakukan campaign. Hal ini bermanfaat apabila kita berniat menargetkan kampanye pada segmen tertentu yang memiliki kemungkinan paling banyak untuk menerima tawaran saat ada campaign.

### 5. Perilaku Konsumsi Produk berdasarkan Segmen Pelanggan

Kita telah menganalisis segmen-segmen pelanggan supermarket berdasarkan daya beli serta penerimaan terhadap kampanye dan diskon. Selanjutnya, kita perlu menganalisis produk mana saja yang dibeli oleh segmen-segmen ini untuk mempelajari jenis-jenis produk mana yang paling efektif untuk dimasukkan dalam kampanye atau diberi diskon. 

Dengan menganalisis kebiasaan belanja tiap produk, kita dapat membuktikan atau menolak beberapa asumsi seperti:
- Pada ukuran rumah tangga lebih besar, jumlah biaya yang akan dikeluarkan untuk bahan pokok untuk memasak seperti `MntMeatProducts` dan `MntFishProducts` akan lebih besar.
- Pada struktur rumah tangga dengan anak, akan ada pengalokasian biaya lebih banyak untuk `MntSweetProducts`
- Pada struktur rumah tangga tanpa anak, akan ada pengalokasian biaya lebih besar untuk `MntWines` atau `MntGoldProds`. 

## Kesimpulan dan Rekomendasi

### Kesimpulan 

#### Komposisi Segmen Pelanggan

Melalui visualisasi di atas, kita dapat menyimpulkan bahwa segmen pelanggan di supermarket XYZ berdasarkan rumah tangganya adalah sebagai berikut:
- Segmen pelanggan dibagi berdasarkan jumlah orang dewasa dan jumlah anak termasuk remaja dan anak-anak. Hasilnya, segmen pelanggan di supermarket XYZ berdasarkan tipe struktur rumah tangga terdiri dari:
    - **Single_NoChild** atau lajang tanpa anak dengan presentase 11.4% dengan jumlah 252 orang pelanggan. Segmen ini merupakan **segmen pelanggan paling sedikit**
    - **Couple_NoChild** atau pasangan tanpa anak dengan presentase 17.2% dengan jumlah 381 orang pelanggan. Merupakan segmen paling sedikit kedua.
    - **Single_WithChild** atau lajang dengan anak dengan dengan presentase 24.1% dengan jumlah 533 orang pelanggan dan merepresentasikan segmen paling terbanyak kedua.
    - **Couple_WithChild** atau pasangan dengan anak dengan presentase 7.4% dengan jumlah 1049 orang pelanggan. Segmen ini mendominasi pelanggan Supermarket XYZ, sehingga layak untuk dipertimbangkan dalam analisis atau pengambilan keputusan yang berkaitan dengan segmentasi pelanggan.
  
  Sebagai analisis tambahan, disertakan juga analisis segmentasi pelanggan berdasarkan ukuran rumah tangga dengan hasil sebagai berikut:
    - **No Children** atau rumah tangga dengan jumlah anak 0 yaitu 28.6% dengan jumlah 633 pelanggan. Sebagai segmen pelanggan kedua terbesar, segmen ini sangat mungkin untuk dipertimbangkan dalam pengambilan keputusan atau analisis.
    - **Small Family** atau keluarga dengan satu atau dua anak mencapai 69.2% dengan jumlah 1532 pelanggan. Sebagai segmen pelanggan terbesar berdasarkan ukuran rumah tangga, segmen dengan karakteristik ini penting untuk dipertimbangkan dalam pengambilan keputusan atau analisis yang berkaitan dengan ukuran struktur rumah tangga. 
    - **(Large Family)**, keluarga dengan lebih dari dua anak merupakan segmen terkecil, yaitu 2.3% dengan 50 pelanggan.
  
  Analisis ini akan berfokus pada tipe struktur rumah tangga atau **`HouseholdType`** karena memberikan segmentasi yang lebih tajam dan relevan untuk tujuan campaign targeting. Kolom `HouseholdType` sangat tepat untuk campaign targeting karena dengan jelas membedakan persona pelanggan berdasarkan ada tidaknya anak di rumah dan status hubungan (lajang atau berpasangan), yang sangat berkaitan dengan gaya hidup.

#### Pendapatan per Segmen

- Segmen Single_NoChild dan Couple_NoChild memiliki rata-rata pendapatan tertinggi, masing-masing sekitar $65.000. Segmen ini juga menunjukkan daya beli lebih tinggi, dengan rata-rata pengeluaran mendekati $1.100.
- Sebaliknya, Couple_WithChild dan Single_WithChild memiliki pendapatan lebih rendah, sekitar $45.000, serta pengeluaran rata-rata yang lebih rendah, yaitu sekitar $400.
- Sebagian besar pelanggan dari segmen dengan anak memperlihatkan pengeluaran yang cenderung rendah dan terdistribusi di kisaran yang lebih kecil.

#### Pendapatan per Segmen

- Segmen Single_NoChild dan Couple_NoChild memiliki rata-rata pendapatan tertinggi, masing-masing sekitar $65.000. Segmen ini juga menunjukkan daya beli lebih tinggi, dengan rata-rata pengeluaran mendekati $1.100.
- Sebaliknya, Couple_WithChild dan Single_WithChild memiliki pendapatan lebih rendah, sekitar $45.000, serta pengeluaran rata-rata yang lebih rendah, yaitu sekitar $400.
- Sebagian besar pelanggan dari segmen dengan anak memperlihatkan pengeluaran yang cenderung rendah dan terdistribusi di kisaran yang lebih kecil.

#### Penggunaan Diskon

- Segmen Couple_WithChild dan Single_WithChild memiliki rata-rata penggunaan diskon tertinggi (sekitar 2.8), sedangkan Couple_NoChild dan Single_NoChild memiliki angka penggunaan diskon yang lebih rendah (sekitar 1).
- Tingginya penggunaan diskon pada segmen dengan anak selaras dengan rata-rata pendapatan mereka yang lebih rendah.

#### Respons terhadap Kampanye

- Segmen Single_NoChild menunjukkan tingkat penerimaan kampanye tertinggi, diikuti oleh Couple_NoChild.
- Segmen dengan anak (Single_WithChild dan Couple_WithChild) merupakan yang paling rendah dalam penerimaan kampanye.
- Segmen dengan penerimaan kampanye yang tinggi juga merupakan segmen dengan daya beli dan pendapatan yang tinggi.

#### Preferensi Produk per HouseholdType

- Produk dengan pengeluaran rata-rata tertinggi adalah Wine dan Meat, khususnya oleh segmen Couple_NoChild dan Single_NoChild.
- Segmen dengan anak menunjukkan pengeluaran yang lebih rendah di seluruh kategori produk.
- Segmen tanpa anak mengalokasikan lebih banyak pengeluaran untuk produk premium seperti Wines dan Gold, sedangkan segmen dengan anak menunjukkan pengeluaran yang lebih rendah dan merata di semua kategori produk.

#### Temuan Tambahan dari Preferensi Produk

- Pengeluaran untuk MntMeatProducts dan MntFishProducts tidak lebih tinggi pada segmen dengan anak, melainkan lebih tinggi pada segmen tanpa anak.
- Tidak terdapat bukti bahwa segmen dengan anak mengalokasikan lebih banyak untuk MntSweetProducts.
- Pengeluaran untuk MntWines dan MntGoldProds terbukti lebih tinggi pada segmen tanpa anak.

#### Kesimpulan Akhir

- Segmen tanpa anak (Single_NoChild dan Couple_NoChild) memiliki karakteristik daya beli dan respons kampanye yang tinggi, serta kecenderungan membli dalam volume banyak di semua aktegori termasuk Meat Products dan pengeluaran pada produk premium, seperti Wine.

- Segmen dengan anak (Single_WithChild dan Couple_WithChild) menunjukkan sensitivitas terhadap diskon, pengeluaran lebih rendah, dan preferensi belanja yang lebih hemat.

- Dari segi Return of Investment (ROI) kampanye jangka panjang berdasarkan konsistensi dan jumlah pendapatan dari perilaku berbelanja tiap segmentasi, segmen tanpa anak (Single_NoChild dan Couple_NoChild) merupakan segmen paling kuat.

### Rekomendasi 

#### Rekomendasi Targeted Campaign

Adapun targeted campaign yang bisa dirancang dari hasil analisis adalah sebagai berikut:
1. Karena marketing Supermarket XYZ diharapkan efisien secara biaya promosi namun tetap menghasilkan value yang tinggi dan stabil secara jangka panjang, maka disarankan menyasar ke segmen tanpa anak yaitu **Single_NoChild** & **Couple_NoChild** karena kedua segmen tersebut tidak hanya menghasilkan penjualan yang tinggi namun karena kebiasaan belanja mereka yang cenderung konsisten serta penerimaan yang sangat tinggi terhadap kampanye. Hal ini mendandakan kedua segmen tersebut sebagai **high-value customer**.
2. Marketing campaign sebaiknya difokuskan pada kategori-kategori produk yang sudah terbukti menjadi favorit segmen ini, seperti **Wine** dan **Meat**. Terlebih lagi, kedua kategori produk tersebut telah terbukti menyumbang porsi penjualan yang lebih besar dan signifikan dibanding produk-produk lainnya.
3. Campaign perlu dijalankan secara berkala dan konsisten dan memanfaatkan berbagai macam channel yang mungkin dipakai oleh segmen-segmen ini misalnya seperti website, social media, dan lain-lain untuk mendorong brand association dan pembelian berulang. 
4. Meski masih bisa dilakukan dalam jumlah yang dibatasi, hindari pendekatan berbasis diskon untuk segmen ini, karena analisis menunjukkan bahwa mereka memiliki penggunaan diskon paling rendah

Dengan mempersempit sasaran targeted campaign ke segmen pelanggan yang memiliki potensi pembelanjaan tinggi, diharapkan kampanye yang dihasilkan dapat membantu perusahaan meningkatkan efisiensi biaya pemasaran, serta meningkatkan profitabilitas dan menjaga loyalitas dari pelanggan yang paling bernilai.

#### Contoh Targeted Campaign: Strategi Pemasaran All Year Round Wine & Meat 

Contoh targeted campaign yang bisa disarankan berdasarkan produk favorit segmen high-value Single_NoChild & Couple_NoChild, yaitu untuk kategori Wine dan Meat. Untuk memaksimalkan penjualan keduanya sekaligus, supermarket dapat melakukan beberapa strategi:
1. Strategi bundling, misalnya membuat paket khusus charcuterie board yang umumnya berisi daging-dagingan dengan keju atau cemilan lain sebagai teman minum wine. Charcuterie board ini dapat dipromosikan all-year round atau bahkan pada hari-hari raya tertentu, seperti Natal dan Tahun Baru. Di sisi lain, strategi marketing juga dapat menarget segmen pelanggan terhadap persona mereka, misalnya Charcuterie Board for Couples di Hari Valentine.
2. Soft-selling melalui konten informatif atau edukasional dengan memanfaatkan berbagai kanal marketing luring atau daring. Misalnya, membuat konten di sosial media tentang jenis-jenis daging yang paling cocok dipadukan dengan white wine, red wine, atau rose wine. Supermarket juga dapat menggelar event luring seperti Wine Pairing dan Steak Tasting Event dengan mendatangkan bintang tamu yang ahli di bidang wine atau chef terkenal.

## Link Visualisasi Tableu

Link visualisasi tableu dapat ditemukan pada link berikut ini:

Link alternatif

https://public.tableau.com/views/Book1_17529175713450/SegmentasiPelangganSupermarketXYZ?:language=en-US&publish=yes&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link




