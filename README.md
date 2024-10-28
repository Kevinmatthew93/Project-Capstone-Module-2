# 1. Latar Belakang  

TransJakarta diluncurkan pada tahun 2004, merupakan sistem bus rapid transit (BRT) pertama di Asia Tenggara. Sistem ini dirancang untuk mengatasi kemacetan di Jakarta dengan menyediakan jalur khusus bagi bus, memungkinkan transportasi massal yang lebih cepat dan efisien dibandingkan kendaraan pribadi. TransJakarta telah berkembang pesat dengan perluasan rute, peningkatan jumlah armada, dan integrasi dengan moda transportasi lain seperti MRT dan LRT, demi meningkatkan aksesibilitas bagi masyarakat Jakarta. Namun, meskipun telah berhasil mengangkut jutaan penumpang setiap tahunnya, TransJakarta masih menghadapi tantangan seperti keterlambatan bus dan kemacetan di jalur busway. Ke depan, TransJakarta berupaya untuk terus berinovasi dan meningkatkan layanan demi mendukung mobilitas perkotaan yang lebih baik (Jakarta Smart City, 2023).

*Jakarta Smart City. (2023). TransJakarta: Solusi Transportasi Ibu Kota. Diakses dari smartcity.jakarta.go.id.*

# 2. Rumusan Masalah
Dalam rangka mengoptimalkan layanan TransJakarta, diperlukan analisis terhadap perilaku penumpang, durasi perjalanan, dan keterlambatan yang terjadi di setiap koridor. Berdasarkan data yang ada, rumusan masalah ini meliputi:

1. **Penumpang Terbanyak pada Hari Kerja dan Jam Sibuk**  
   Bagaimana pola jumlah penumpang TransJakarta pada hari kerja dan jam sibuk? Apakah ada perbedaan signifikan antara waktu sibuk dan non-sibuk dalam hal volume penumpang?

2. **Rata-rata Durasi Perjalanan untuk Setiap Koridor**  
   Berdasarkan data waktu tap in dan tap out penumpang, berapa rata-rata durasi perjalanan di setiap koridor?

3. **Penghitungan dan Klasifikasi Rata-rata Keterlambatan di Setiap Koridor**  
   Bagaimana cara menghitung rata-rata keterlambatan perjalanan di setiap koridor? Rata-rata keterlambatan tersebut diklasifikasikan dalam tingkatan apa saja?

4. **Analisis Mendalam pada Durasi Keterlambatan Tertinggi**  
   Untuk durasi keterlambatan yang paling tinggi, apa penyebab utamanya? Apakah saja faktor yang berkontribusi terhadap keterlambatan tersebut? Apa langkah-langkah yang dapat diambil untuk mengurangi keterlambatan di koridor tersebut?

# 3. Stakeholder
- **TransJakarta (Perusahaan)**  
  Sebagai operator, TransJakarta bertanggung jawab untuk menyediakan layanan bus yang efisien dan aman. Mereka juga memiliki peran dalam menindaklanjuti hasil analisis untuk meningkatkan kualitas layanan.

- **Dinas Perhubungan DKI Jakarta**  
  Sebagai badan yang mengawasi transportasi umum di wilayah Jakarta, Dinas Perhubungan memiliki pengaruh besar dalam merancang dan mengimplementasikan kebijakan yang berdampak pada transportasi publik.

# 4. Tujuan Analisis

Tujuan analisis dari rumusan masalah yang telah diidentifikasi adalah sebagai berikut:

1. **Mengidentifikasi Pola Jumlah Penumpang pada Hari Kerja dan Jam Sibuk**  
   Menganalisis pola penumpang pada TransJakarta selama hari kerja, khususnya pada jam-jam sibuk, guna memahami distribusi volume penumpang dan perbedaan signifikan antara waktu sibuk dan non-sibuk.

2. **Menghitung Rata-rata Durasi Perjalanan untuk Setiap Koridor**  
   Hasil analisis ini akan menjadi dasar untuk membandingkan durasi aktual perjalanan dengan waktu ideal yang diharapkan. Analisis rata-rata durasi perjalanan diperlukan untuk analisis lebih lanjut terkait keterlambatan.

3. **Menghitung dan Mengklasifikasikan Keterlambatan**  
   Tujuan analisis ini adalah untuk mengetahui keterlambatan setiap koridor dan mengklasifikasikan keterlambatan tersebut menjadi tiga kategori. Dengan pengklasifikasian ini, diharapkan dapat mengidentifikasi pola keterlambatan yang terjadi dan memprioritaskan koridor yang memerlukan perhatian lebih.

4. **Analisis Kategori Keterlambatan Berat**  
   Melakukan analisis mendalam terhadap kategori keterlambatan berat untuk mengidentifikasi penyebab utama keterlambatan. Memahami faktor-faktor yang berkontribusi terhadap keterlambatan di koridor tertentu dan menyusun langkah-langkah strategis yang dapat diambil untuk mengurangi tingkat keterlambatan.

# 5. Pembatasan Masalah  
**1. Batasan Data**  
Analisis ini hanya akan menggunakan data penumpang TransJakarta yang tersedia pada bulan April 2023. Data di luar periode ini tidak akan dianalisis.  
Hanya data yang mencakup waktu tap in dan tap out penumpang yang akan digunakan dalam perhitungan durasi perjalanan.  
Data yang digunakan untuk jarak (`distance`) dan menghitung waktu tempuh ideal (`idealTime`) diambil dari sumber eksternal yang terpercaya.  

**2. Batasan Variabel**  
- `corridorID`: ID Koridor / ID Rute sebagai kunci untuk pengelompokan rute.  
- `corridorName`: Nama koridor yang digunakan untuk mengidentifikasi rute.  
- `tapInStopsName`: Nama Halte Tap In (masuk) di mana pelanggan melakukan tap in.  
- `tapOutStopsName`: Nama Halte Tap Out (keluar) di mana pelanggan melakukan tap out.  
- `stopStartSeq`: Posisi halte awal dalam rute perjalanan pelanggan pada saat melakukan Tap Masuk.  
- `stopEndSeq`: Posisi halte akhir dalam rute perjalanan pelanggan pada saat melakukan Tap Keluar.  
- `tapInTime`: Tanggal dan waktu saat penumpang melakukan tap masuk.  
- `tapOutTime`: Tanggal dan waktu saat penumpang melakukan tap keluar.  
- `payAmount`: Jumlah yang dibayarkan oleh pelanggan. Ada yang gratis. Ada yang tidak.  

**3. Batasan Moda Transportasi**  
Analisis ini akan difokuskan pada moda transportasi TransJakarta. Moda transportasi Royal Trans dan Microtrans tidak akan dianalisis.

**4. Batasan Waktu**  
Analisis ini akan memfokuskan pada hari kerja dan jam sibuk, tanpa mencakup akhir pekan atau hari libur.  

**5. Pendekatan Kuantitatif**  
Analisis ini akan mengedepankan pendekatan kuantitatif, dengan fokus pada penghitungan dan klasifikasi data.  

**6. Pendekatan Kualitatif**  
Analisis kualitatif untuk mengidentifikasi penyebab keterlambatan akan dilakukan secara terbatas pada keterlambatan berat.  

**7. Faktor Lain yang Mempengaruhi Keterlambatan**  
Analisis ini tidak akan mempertimbangkan faktor eksternal seperti kondisi cuaca, kemacetan lalu lintas, atau kejadian tak terduga lainnya yang dapat mempengaruhi durasi perjalanan.
