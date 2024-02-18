# 🏦 **BANK MARKETING CAMPAIGN**

## **Business Understanding**

### **Context:**
Bank perlu menjaga rasio likuiditasnya untuk memastikan kebutuhan kas terus terpenuhi. Rasio ini menunjukkan kemampuan bank untuk mengatasi kewajiban keuangan jangka pendek, yang mencakup memberikan pinjaman kepada konsumen dan bisnis. Semakin banyak cadangan kas yang dimiliki bank, semakin besar kemampuannya untuk memberikan pinjaman dan menghasilkan keuntungan.

Salah satu cara untuk menjaga rasio ini adalah dengan menawarkan investasi deposito berjangka kepada pelanggan. **Deposito berjangka adalah jenis investasi di mana pelanggan berkomitmen untuk menyetorkan sejumlah uang ke bank atau lembaga keuangan yang tidak dapat ditarik selama jangka waktu tertentu**. Sebagai imbalannya, pelanggan menerima tingkat bunga tetap atas jumlah yang mereka setorkan.

Bank-bank di Portugal melakukan kampanye pemasaran melalui telepon untuk mempromosikan investasi deposito berjangka, menghubungi pelanggan yang diyakini sebagai calon investor potensial. Untuk meningkatkan efektivitas kampanye-kampanye ini, bank-bank bertujuan untuk memprediksi pelanggan mana yang kemungkinan besar akan membuka deposito berjangka. Prediksi yang akurat memungkinkan bank untuk fokus pada pelanggan yang menjanjikan, sehingga mengurangi kerugian keuangan akibat upaya kampanye yang tidak tepat sasaran.

### **Problem Statement:**
Divisi Marketing memainkan peran penting dalam memastikan dana yang dibutuhkan untuk operasi sehari-hari bank dan strategi keuangan yang lebih besar terpenuhi. Salah satu cara yang mereka lakukan adalah melalui deposito berjangka. Ini merupakan sumber dana yang dapat diandalkan, menawarkan risiko rendah dan hasil yang stabil. Namun, terdapat tantangan yaitu deposito berjangka membutuhkan komitmen jangka panjang dan menawarkan pengembalian tetap, yang membuatnya kurang menarik di pasar di mana banyak orang menginginkan investasi dengan pengembalian yang lebih tinggi.

Untuk mengatasi ini, divisi menggunakan kampanye pemasaran telemarketing yang ditargetkan, melibatkan panggilan berulang untuk menilai minat pelanggan. Namun metode ini dapat memakan waktu dan mahal jika tidak dilakukan secara efektif. Jika divisi hanya mengandalkan metode manual untuk mengidentifikasi pelanggan potensial, hal itu bisa mengakibatkan prediksi yang bias dan tidak akurat. Ini berarti mereka bisa saja mengincar orang yang salah, membuang-buang waktu dan uang.

Untuk meningkatkan efektivitas upaya pemasaran mereka, diperlukan pendekatan yang lebih strategis. Dengan menggunakan model klasifikasi yang tepat, divisi dapat fokus pada pelanggan yang lebih mungkin membuka deposito berjangka. Dengan cara ini, mereka dapat menjalankan kampanye yang lebih efisien dan lebih baik memanfaatkan sumber daya mereka.

Dengan menggunakan model klasifikasi yang tidak hanya memprioritaskan prediksi yang akurat tetapi juga memperhitungkan profitabilitas, Divisi Marketing dapat mengincar secara strategis pelanggan yang lebih mungkin membuka deposito berjangka. Pendekatan ini memungkinkan divisi ini untuk mengoptimalkan kampanye dan alokasi sumber daya, yang pada akhirnya meningkatkan profitabilitas mereka.

**`Key Questions:`**
- Faktor atau variabel mana yang sebaiknya difokuskan oleh Divisi Marketing untuk meningkatkan pendaftaran deposito berjangka?
- Bagaimana Divisi Marketing dapat memperkirakan kemungkinan pelanggan untuk berkomitmen pada deposito berjangka?

### **Goals:**

Tujuan utama adalah **membuat model klasifikasi yang efektif**. Model ini diharapkan dapat memprediksi seberapa mungkin klien akan memilih deposito berjangka. Model ini akan memprediksi baik klien yang akan mengatakan setuju maupun mereka yang akan mengatakan tidak untuk deposito berjangka.

Selain itu, kita ingin **mengetahui apa yang membuat pelanggan memutuskan untuk mendaftar deposito berjangka**. Mengetahui faktor-faktor tersebut akan membantu bank menggunakan sumber daya mereka lebih baik, membuat interaksi mereka dengan klien lebih efektif, dan pada akhirnya, mendapatkan lebih banyak klien setuju untuk deposito berjangka melalui pemasaran mereka.


### **Analytical Approach:**
Kita akan menganalisis karakteristik calon pelanggan yang kemungkinan besar akan membuka rekening deposito berjangka, lalu membangun model supervised machine learning, khususnya model klasifikasi, untuk memprediksi yang cenderung membuka rekening deposito berjangka. Dengan cara ini, calon pelanggan ini dapat diprioritaskan dalam kampanye, sehingga membuat prosesnya lebih efisien.

### **Metric Evaluation:**

Analisis ini akan berfokus pada pelanggan yang tertarik untuk berinvestasi dalam deposito berjangka. Target-targetnya didefinisikan sebagai berikut:

- **0:** menandakan pelanggan yang tidak berinvestasi dalam deposito berjangka.
- **1:** menandakan pelanggan yang berinvestasi dalam deposito berjangka.


Memastikan akurasi model kita sangat penting untuk menghindari dampak keuangan dari kesalahan klasifikasi, yang bisa berupa positif palsu atau negatif palsu.

| **Tipe Error**     |**Penjelasan** | **Konsekuensi** | 
|-----------------|------------|----------------|
| **False Positive / Type 1 Error**  |Ini terjadi ketika model secara tidak benar memprediksi bahwa seorang pelanggan akan berinvestasi dalam deposito berjangka padahal sebenarnya tidak. Dengan kata lain, prediksi model positif (1), tetapi nilai sebenarnya negatif (0)| Bank akan mengeluarkan biaya pemasaran yang tidak perlu dengan menargetkan pelanggan yang tidak tertarik untuk berinvestasi dalam deposito berjangka.|
| **False Negative / Type 2 Error**  |Ini terjadi ketika model secara tidak benar memprediksi bahwa seorang pelanggan tidak akan berinvestasi dalam deposito berjangka padahal sebenarnya akan melakukannya. Di sini, prediksi model negatif (0), tetapi nilai sebenarnya positif (1)| Bank akan melewatkan potensi keuntungan dari pelanggan yang kemungkinan besar akan berinvestasi dalam deposito berjangka.| 


# **Data Understanding**

Dataset [Bank Marketing Campaign](https://drive.google.com/drive/folders/13lrEDlKfnTPNREfGLBaYGYf8dSjHBzfW) terkait dengan kampanye pemasaran langsung (telepon) sebuah lembaga perbankan di Portugal. Dataset ini diadaptasi dari [UC Irvine Machine Learning Repository](https://archive.ics.uci.edu/dataset/222/bank+marketing) dan diambil pada tahun 2014. 

Dataset Bank Marketing Campaign terdiri dari 7.813 baris dan 17 kolom. Ini mencakup informasi tentang profil pelanggan serta data terkait keuangan pelanggan dan upaya pemasaran bank.

| Variabel      | Penjelasan | 
|------------|-----------|
| age  | Variabel numerik yang mewakili usia klien, berkisar dari 18 hingga 95 tahun    | 
|job| Kategorisasi pekerjaan klien|
| balance| Variabel numerik yang mewakili jumlah saldo tahunan rata-rata klien   |
|housing| Nilai biner yang menunjukkan apakah klien memiliki pinjaman rumah atau tidak   |
|loan| Nilai biner yang menunjukkan keberadaan atau ketiadaan pinjaman pribadi klien |
|contact  | Jenis komunikasi kontak | 
|month| Bulan terakhir kontak dalam setahun|
|campaign|Jumlah kontak yang dilakukan selama kampanye ini dan untuk klien ini |
|pdays| Jumlah hari setelah klien dihubungi dari kampanye sebelumnya |
|poutcome| Hasil kampanye pemasaran sebelumnya|
|deposit| Apakah pelanggan melakukan deposit atau tidak|
| marital* | Status pernikahan |
| education* | Tingkat pendidikan | 
| default* | Apakah memiliki kredit bermasalah? |
| day* | Hari terakhir kontak |
| duration* | Durasi kontak terakhir, dalam detik |
| previous* | Jumlah kontak yang dilakukan sebelum kampanye ini dan untuk klien ini |

### **Benchmark Model**

Tahap pemodelan pertama adalah mencari model benchmark untuk digunakan sebagai dasar kinerja untuk pemodelan pada tahap selanjutnya. Membandingkan model regresi atau klasifikasi untuk mendapatkan benchmark model antara Light Gradient Boosting Machine (lightgbm), Gradient Boosting Classifier (gbc), Random Forest Classifier (rf), Logistic Regression (lr), Decision Tree Classifier (dt), K Neighbors Classifier (kn)

Setelah melalui kuantifikasi dan tunning hyperparameters, maka kita akan mendapatkan bahwa model **Light Gradient Boosting Machine (lightgbm)** memiliki nilai `f1-score` yang lebih tinggi dibandingkan model yang lain. Sehingga, kita menetapkan akan menggunakan model tersebut.

**Insight** : 
- Kita mendapatkan bahwa fitur paling **importance** dalam membangun model machine learning ini adalah **duration**
- Pada fitur **duration** juga menampilkan bahwa semakin lama durasi bank menghubungi nasabah, akan banyak mempengaruhi nasabah untuk terprediksi membuka rekening deposito.
- Pada fitur **contact** menunjukkan bahwa nasabah yang dihubungi dengan phone/telepon cenderung lebih berpengaruh untuk teprediksi membuka rekening deposito
- Fitur paling **importance** selanjutnya yaitu **month**, di mana nasabah yang dihubungi pada bulan-bulan di akhir tahun dan awal tahun juga akan banyak mempengaruhi nasabah untuk teprediksi membuka rekening deposito, namun kebanyakan nasabah jika ditinjau dari fitur month akan cenderung terprediksi tidak membuka rekening deposito
- Pada fitur **poutcome** menginterpretasikan bahwa nasabah yang pada campaign sebelumnya berhasil untuk didapatkan oleh bank juga cenderung lebih berpotensi untuk terprediksi membuka rekening deposito 
- Pada fitur **housing** orang yang tidak memiliki kredit perumahan lebih cenderung lebih berpotensi untuk terprediksi membuka rekening deposito
- Dari lima fitur dengan kontribusi terbesar, yang paling berpengaruh untuk klasifikasi adalah fitur yang terkait dengan kampanye. Hal ini menunjukkan bahwa upaya marketing sangat berperan dalam meningkatkan jumlah pengguna yang berinvestasi dalam deposito berjangka.

Dari sini dapat dilihat bahwa penggunaan model biaya pemasaran jauh lebih kecil dibandingkan dengan biaya yang harus ditanggung bank sebelumnya. Penghematan biaya pemasaran yang dapat dilakukan bank adalah:
**Marketing Savings** = ((initial_cost_marketing - final_cost_marketing) / initial_cost_marketing) * 100 = **47%**
Sementara itu, kerugian yang dapat dikurangi dengan menggunakan model adalah
**Loss Reduction** = ((initial_loss - final_loss) / initial_loss) * 100  = **82.1%**
Kenaikan keuntungan dari sebelum menggunakan model adalah **6.44%.**

### **Conclusion**

Pilihan Model:
- Model Light Gradient Boosting Machine dipilih sebagai model utama berdasarkan pertimbangan f1-score

Evaluasi Model:
- Model menunjukkan kemampuan yang baik dalam mengidentifikasi kasus positif.
- Performa model cenderung konsisten antara data uji dan data holdout, menunjukkan tingkat generalisasi yang baik dan model terbukti robust

Limitasi dan Rekomendasi Model:
- Rekomendasi untuk memperbaiki recall kelas 0 atau mengevaluasi strategi bisnis yang dapat mengatasi potensi kesalahan prediksi pada kasus negatif.

Keandalan Model:
Model telah dianggap cukup umum dan robust untuk menangani data baru atau data yang belum pernah dilihat sebelumnya.
Keseluruhan, model dapat diandalkan dalam konteks prediksi deposit berjangka pada dataset yang telah disediakan.

Pertimbangan Tambahan:
- Evaluasi tambahan perlu dipertimbangkan berdasarkan kebutuhan bisnis spesifik.
- Model dapat terus diperbaiki atau disesuaikan dengan perubahan karakteristik data atau kebijakan bisnis yang mungkin timbul di masa mendatang.

Feature Importance:
duration merupakan fitur yang paling berkontribusi dalam memprekdisikan model karena mencerminkan lama durasi bank menghubungi nasabah

Dengan demikian, model Light Gradient Boosting Machine yang telah disesuaikan parameter terbukti cukup baik untuk memenuhi kebutuhan dan tujuan prediksi deposit berjangka pada dataset yang telah diberikan. Namun, evaluasi terus-menerus dan penyesuaian model dapat menjadi langkah berkelanjutan untuk memastikan kinerja optimal seiring berjalannya waktu.

### **Recommendation**

Rekomendasi Untuk Bank:
- Bank dapat menggunakan model Machine Learning untuk mengidentifikasi nasabah yang memiliki potensi untuk menaruh deposit berjangka, tetapi belum pernah menerima penawaran dari bank. Dengan mengidentifikasi nasabah potensial ini, bank dapat menargetkan mereka dengan konten pemasaran yang lebih relevan dan meningkatkan peluang untuk menabung.
- Bank dapat menargetkan kampanye kepada nasabah yang memiliki saldo yang tinggi dan sudah lama tidak dihubungi atau diberikan kampanye
- Bank dapat menggunakan model Machine Learning untuk mengembangkan konten pemasaran yang dipersonalisasi untuk setiap nasabah, berdasarkan profil dan minat mereka. Konten yang dipersonalisasi lebih cenderung menarik perhatian nasabah dan mendorong mereka untuk mengambil tindakan.
- Bank dapat menggunakan model Machine Learning untuk mengukur efektivitas kampanye pemasaran, seperti jumlah nasabah yang mendaftar untuk deposit berjangka dan jumlah deposit yang berhasil ditarik. Dengan mengukur efektivitas kampanye, bank dapat memahami apa yang berhasil dan apa yang perlu ditingkatkan.

Rekomendasi Implementasi di Kehidupan Nyata:
Perbaikan dan saran untuk future use:
- Threshold Adjustment:
Eksplorasi penyesuaian ambang batas prediksi untuk mencapai keseimbangan antara precision dan recall berdasarkan kebijakan bisnis dan dampak relatif dari false positives dan false negatives.

- Model Ensemble:
Pertimbangkan untuk mengimplementasikan model ensemble, seperti gabungan Logistic Regression dengan Random Forest, untuk meningkatkan kinerja dan mengatasi kelemahan masing-masing model.

Perbaikan Kondisi Data:
- Feature Engineering:
Perhatikan potensi feature engineering yang lebih baik untuk mendapatkan wawasan tambahan dari data. Misalnya, transformasi fitur atau penggabungan fitur untuk menciptakan variabel baru yang dapat memberikan informasi lebih banyak.

- Penanganan Outliers:
Jika ditemukan outliers pada fitur numerik tertentu, pertimbangkan untuk menangani atau menghilangkan outliers tersebut.

Rekomendasi Umum:
- Pelibatan Pihak Bisnis: Melibatkan tim pemasaran dan tim bisnis dalam interpretasi hasil model serta mendapatkan masukan dan pengetahuan domain.
- Edukasi Stakeholder: Memberikan pemahaman kepada pemangku kepentingan mengenai kekuatan dan keterbatasan model, sehingga keputusan dapat diambil dengan pemahaman yang lebih baik.
- Monitoring: Implementasikan sistem pemantauan yang terus-menerus untuk mendeteksi perubahan dalam performa model atau data.

Dengan mengikuti rekomendasi ini, implementasi model dapat menjadi alat yang berharga dalam mendukung keputusan strategis dan operasional dalam kampanye pemasaran deposit berjangka.
