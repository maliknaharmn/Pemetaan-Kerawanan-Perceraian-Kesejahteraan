# Format Dokumentasi Artikel Jurnal

Judul yang disarankan:

**Analisis Klaster Wilayah Rawan Perceraian Berdasarkan Indikator Sosial Ekonomi di Provinsi Jawa Timur Menggunakan K-Means**

## Abstrak

Tuliskan abstrak 150-250 kata yang memuat:

- latar belakang singkat mengenai perceraian sebagai isu sosial,
- tujuan penelitian,
- data yang digunakan,
- metode K-Means dan evaluasi silhouette score,
- hasil utama jumlah cluster dan profil singkat tiap cluster,
- kontribusi penelitian sebagai pemetaan eksploratif wilayah rawan perceraian.

Contoh narasi:

Penelitian ini bertujuan mengelompokkan kabupaten/kota di Provinsi Jawa Timur berdasarkan indikator kesejahteraan masyarakat dan tingkat perceraian. Data yang digunakan mencakup IPM, TPT, kemiskinan, jumlah pernikahan, jumlah perceraian, dan data spasial batas administrasi kabupaten/kota. Metode yang digunakan adalah K-Means clustering dengan standardisasi fitur sebelum pemodelan. Evaluasi cluster dilakukan menggunakan silhouette score, sedangkan hasil spasial divisualisasikan melalui peta choropleth. Hasil awal menunjukkan tiga kelompok wilayah dengan karakteristik kerawanan berbeda. Penelitian ini bersifat eksploratif dan dapat menjadi dasar awal bagi analisis sosial-ekonomi lanjutan terkait perceraian.

Kata kunci:

K-Means, clustering, perceraian, kesejahteraan masyarakat, Jawa Timur, peta choropleth.

## 1. Pendahuluan

### 1.1 Latar Belakang

Isi bagian ini dengan poin berikut:

- Perceraian merupakan fenomena sosial yang berdampak pada keluarga, anak, ekonomi rumah tangga, dan kesejahteraan masyarakat.
- Jawa Timur memiliki jumlah kabupaten/kota yang besar dan karakter sosial-ekonomi yang beragam.
- Keragaman indikator seperti IPM, pengangguran, kemiskinan, dan tingkat perceraian membuka ruang analisis berbasis wilayah.
- Data publik dari BPS dan lembaga terkait memungkinkan analisis eksploratif menggunakan data science.
- Clustering dapat membantu mengelompokkan wilayah dengan pola yang mirip tanpa harus menentukan label manual sejak awal.

Contoh paragraf:

Perceraian merupakan salah satu isu sosial yang berkaitan dengan stabilitas keluarga dan kesejahteraan masyarakat. Fenomena ini tidak hanya berdampak pada pasangan yang bercerai, tetapi juga dapat memengaruhi kondisi ekonomi rumah tangga, pengasuhan anak, dan dinamika sosial di tingkat wilayah. Di sisi lain, kabupaten/kota di Provinsi Jawa Timur memiliki karakteristik sosial-ekonomi yang beragam, seperti perbedaan IPM, tingkat pengangguran, dan kemiskinan. Keragaman tersebut membuat pendekatan berbasis wilayah menjadi relevan untuk memahami pola kerawanan perceraian secara lebih sistematis.

### 1.2 Rumusan Masalah

Gunakan 2-3 rumusan masalah:

1. Bagaimana mengelompokkan kabupaten/kota di Jawa Timur berdasarkan indikator kesejahteraan masyarakat dan tingkat perceraian?
2. Bagaimana karakteristik tiap cluster wilayah berdasarkan IPM, TPT, kemiskinan, dan tingkat perceraian?
3. Bagaimana pola spasial cluster kerawanan perceraian ketika divisualisasikan dalam peta choropleth?

### 1.3 Tujuan Penelitian

Tujuan penelitian:

1. Menghasilkan cluster kabupaten/kota berdasarkan indikator kesejahteraan dan tingkat perceraian.
2. Mengidentifikasi karakteristik sosial-ekonomi pada tiap cluster.
3. Menyajikan hasil cluster dalam bentuk peta choropleth agar mudah dianalisis secara spasial.

### 1.4 Manfaat Penelitian

Manfaat akademik:

- Menunjukkan penerapan K-Means pada isu sosial berbasis wilayah.
- Menjadi referensi awal untuk penelitian lanjutan tentang perceraian dan kesejahteraan.

Manfaat praktis:

- Membantu pembaca mengenali kelompok wilayah dengan profil kerawanan berbeda.
- Memberi contoh pemanfaatan data publik untuk pemetaan sosial.

### 1.5 Batasan Penelitian

Tuliskan batasan berikut agar artikel lebih kuat:

- Unit analisis adalah kabupaten/kota di Jawa Timur.
- Variabel MVP terbatas pada IPM, TPT, kemiskinan, dan tingkat perceraian.
- Analisis bersifat eksploratif, bukan kausal.
- Hasil cluster dipengaruhi kualitas data, kelengkapan pencatatan, dan pemilihan variabel.
- Jika data final masih 34 wilayah, jelaskan empat wilayah yang tidak masuk analisis.

## 2. Tinjauan Pustaka

### 2.1 Perceraian sebagai Isu Sosial

Bahas perceraian sebagai fenomena sosial yang dapat dikaitkan dengan tekanan ekonomi, pendidikan, urbanisasi, perubahan struktur keluarga, dan akses terhadap lembaga hukum.

### 2.2 Indikator Kesejahteraan Masyarakat

Jelaskan indikator yang dipakai:

- IPM sebagai gambaran kualitas pembangunan manusia.
- TPT sebagai indikator kondisi pasar kerja.
- Kemiskinan sebagai indikator kerentanan ekonomi.
- Tingkat cerai sebagai rasio perceraian terhadap pernikahan.

### 2.3 Clustering dalam Analisis Wilayah

Jelaskan bahwa clustering digunakan untuk menemukan kelompok wilayah yang memiliki kemiripan karakteristik. K-Means cocok untuk MVP karena sederhana, cepat, mudah dijelaskan, dan umum digunakan pada penelitian pemetaan wilayah.

### 2.4 Penelitian Terdahulu

Gunakan artikel referensi K-Means pemetaan kemiskinan sebagai pembanding struktur. Artikel Nugraha (2023) menggunakan K-Means untuk pemetaan tingkat kemiskinan di Jawa Barat, mengevaluasi cluster dengan silhouette coefficient, dan memvisualisasikan hasil dengan peta. Perbedaannya, penelitian ini menerapkan pendekatan serupa pada isu perceraian dan indikator kesejahteraan di Jawa Timur.

## 3. Metode Penelitian

### 3.1 Desain Penelitian

Gunakan pendekatan kuantitatif eksploratif dengan metode data mining. Struktur metode dapat mengikuti CRISP-DM:

1. Business understanding.
2. Data understanding.
3. Data preparation.
4. Modeling.
5. Evaluation.
6. Deployment atau visualisasi hasil.

### 3.2 Lokasi dan Unit Analisis

Unit analisis adalah kabupaten/kota di Provinsi Jawa Timur. Idealnya mencakup 38 wilayah administrasi. Jika data final hanya 34 wilayah, jelaskan alasan eksklusi dan dampaknya terhadap interpretasi.

### 3.3 Sumber Data

Tuliskan sumber data dalam tabel:

| Data | Sumber | Tahun | Keterangan |
| --- | --- | --- | --- |
| IPM | BPS | 2023 | Indikator pembangunan manusia |
| TPT | BPS | 2023 | Tingkat pengangguran terbuka |
| Kemiskinan | BPS | 2023 | Persentase penduduk miskin |
| Jumlah nikah | BPS/Pengadilan Agama | 2023 | Dasar perhitungan rasio |
| Jumlah cerai | BPS/Pengadilan Agama | 2023 | Dasar perhitungan rasio |
| GeoJSON kab/kota | BPS/HDX/sumber geospasial | 2023 | Batas wilayah administrasi |

Sesuaikan tahun dengan data final yang benar-benar dipakai.

### 3.4 Definisi Variabel

Tuliskan definisi operasional:

| Variabel | Definisi | Skala |
| --- | --- | --- |
| IPM | Indeks Pembangunan Manusia kabupaten/kota | Rasio |
| TPT | Persentase angkatan kerja yang menganggur | Rasio |
| Kemiskinan | Persentase penduduk miskin | Rasio |
| Tingkat cerai | Jumlah cerai dibagi jumlah nikah dikali 100 | Rasio |

Rumus:

```text
tingkat_cerai = (jumlah_cerai / jumlah_nikah) * 100
```

### 3.5 Data Preparation

Jelaskan langkah:

- normalisasi nama kolom,
- konversi tipe data numerik,
- pemeriksaan missing value,
- imputasi missing value dengan rata-rata atau eksklusi wilayah bermasalah,
- perhitungan `tingkat_cerai`,
- pengecekan outlier,
- penyamaan kode wilayah antara data tabular dan GeoJSON.

Catatan penting:

Jika ada nilai `tingkat_cerai` sangat ekstrem, seperti lebih dari 100, jelaskan apakah itu kesalahan data, perbedaan definisi periode, atau kasus yang harus dikeluarkan.

### 3.6 Standardisasi Fitur

Jelaskan bahwa K-Means sensitif terhadap skala, sehingga semua fitur distandardisasi menggunakan `StandardScaler`.

Rumus konseptual:

```text
z = (x - mean) / standard_deviation
```

### 3.7 Pemodelan K-Means

Tuliskan konfigurasi:

```text
KMeans(n_clusters=3, random_state=42, n_init=10)
```

Alasan memilih 3 cluster:

- mudah diinterpretasikan sebagai rendah, sedang, dan tinggi,
- sesuai tujuan pemetaan kerawanan,
- cocok untuk MVP portfolio.

Untuk versi jurnal yang lebih kuat, tambahkan uji `k=2` sampai `k=6` menggunakan silhouette score dan elbow method.

### 3.8 Evaluasi Cluster

Gunakan silhouette score.

Jelaskan makna umum:

- nilai mendekati 1 menunjukkan cluster semakin terpisah baik,
- nilai mendekati 0 menunjukkan cluster saling tumpang tindih,
- nilai negatif menunjukkan kemungkinan salah pengelompokan.

Pada hasil sementara, silhouette score adalah `0.354`, sehingga struktur cluster dapat dianggap cukup untuk eksplorasi awal, tetapi belum kuat untuk klaim kategorisasi yang terlalu tegas.

### 3.9 Visualisasi Spasial

Jelaskan proses:

- membaca GeoJSON kabupaten/kota Jawa Timur,
- menyesuaikan kode wilayah,
- merge data spasial dengan hasil cluster,
- membuat peta choropleth berdasarkan label cluster,
- menambahkan tooltip berisi nama wilayah, cluster, IPM, TPT, kemiskinan, dan tingkat cerai.

### 3.10 Tools

Tuliskan:

- Google Colab,
- Python,
- pandas dan numpy,
- scikit-learn,
- seaborn dan matplotlib,
- geopandas,
- folium,
- mapclassify.

## 4. Hasil dan Pembahasan

### 4.1 Deskripsi Data

Isi dengan:

- jumlah wilayah,
- tahun data,
- sumber data,
- statistik deskriptif tiap variabel,
- missing value dan tindakan cleaning.

Untuk hasil saat ini:

- data awal notebook berisi 38 wilayah,
- hasil final cluster berisi 34 wilayah,
- 4 wilayah dikeluarkan karena data perceraian kosong atau tidak normal.

### 4.2 Hasil Feature Engineering Tingkat Cerai

Bahas distribusi `tingkat_cerai`:

- wilayah dengan nilai tertinggi,
- wilayah dengan nilai terendah,
- apakah ada outlier,
- alasan rasio lebih informatif dibanding jumlah cerai absolut.

Contoh interpretasi:

Rasio `tingkat_cerai` digunakan agar wilayah dengan jumlah penduduk besar tidak otomatis terlihat lebih rawan hanya karena memiliki jumlah kasus perceraian absolut yang tinggi.

### 4.3 Korelasi Antarindikator

Bahas hasil heatmap:

- hubungan IPM dengan kemiskinan,
- hubungan TPT dengan tingkat cerai,
- hubungan kemiskinan dengan tingkat cerai,
- korelasi yang lemah tetap perlu dijelaskan sebagai temuan eksploratif.

Jangan memaksakan kesimpulan kausal dari korelasi.

### 4.4 Hasil Clustering K-Means

Masukkan tabel profil cluster:

| Label cluster | Jumlah wilayah | IPM | TPT | Kemiskinan | Tingkat cerai |
| --- | ---: | ---: | ---: | ---: | ---: |
| Kerawanan Tinggi | 4 | 82.78 | 6.86 | 4.66 | 37.76 |
| Kerawanan Sedang | 22 | 72.98 | 4.79 | 9.80 | 30.93 |
| Kerawanan Rendah | 8 | 68.40 | 3.03 | 16.73 | 26.39 |

Bahas bahwa label cluster diberikan berdasarkan rata-rata `tingkat_cerai`, bukan label bawaan dari algoritma.

### 4.5 Pembahasan Cluster Kerawanan Tinggi

Isi:

- Cluster ini memiliki rata-rata tingkat cerai tertinggi.
- Wilayah dalam cluster ini cenderung memiliki IPM tinggi dan kemiskinan rendah.
- Kemungkinan interpretasi: wilayah perkotaan atau wilayah dengan akses layanan pencatatan/peradilan lebih baik dapat menunjukkan angka perceraian tercatat lebih tinggi.
- Jangan menyimpulkan bahwa IPM tinggi menyebabkan perceraian.

Wilayah menonjol pada hasil sementara:

- Kota Malang,
- Kota Surabaya,
- Kota Madiun,
- Kabupaten Sidoarjo.

### 4.6 Pembahasan Cluster Kerawanan Sedang

Isi:

- Cluster ini merupakan kelompok terbesar.
- Karakteristik sosial-ekonomi berada di tengah.
- Beberapa wilayah memiliki tingkat cerai tinggi tetapi tidak masuk cluster tinggi karena profil indikator lainnya berbeda.

Wilayah menonjol:

- Kabupaten Blitar,
- Kabupaten Banyuwangi,
- Kabupaten Mojokerto,
- Kabupaten Malang,
- Kabupaten Situbondo.

### 4.7 Pembahasan Cluster Kerawanan Rendah

Isi:

- Cluster ini memiliki rata-rata tingkat cerai paling rendah.
- Rata-rata kemiskinan justru paling tinggi.
- Pembahasan penting: angka perceraian tercatat rendah tidak selalu berarti konflik rumah tangga rendah; bisa terkait faktor akses, budaya, struktur sosial, atau pencatatan.

### 4.8 Pola Spasial pada Peta Choropleth

Bahas:

- persebaran cluster pada peta,
- apakah cluster tinggi terkonsentrasi di wilayah perkotaan,
- apakah cluster rendah terkonsentrasi di wilayah tertentu,
- wilayah yang tidak berhasil merge atau tidak memiliki data.

Jika peta masih 34/38 wilayah:

Tuliskan bahwa empat wilayah ditampilkan sebagai "Tidak Ada Data" atau dikeluarkan dari analisis, tergantung keputusan final.

### 4.9 Evaluasi Model

Bahas silhouette score:

Hasil silhouette score sebesar `0.354` menunjukkan bahwa pemisahan cluster cukup terbaca untuk eksplorasi awal, tetapi belum menunjukkan struktur cluster yang sangat kuat. Hal ini wajar karena indikator sosial sering saling tumpang tindih dan tidak selalu membentuk kelompok yang sangat terpisah.

Tambahkan:

- alasan tetap menggunakan K-Means,
- risiko overinterpretation,
- rencana validasi tambahan.

### 4.10 Implikasi

Implikasi akademik:

- clustering dapat membantu eksplorasi isu sosial berbasis wilayah,
- peta membantu mengkomunikasikan hasil kepada pembaca non-teknis.

Implikasi kebijakan:

- wilayah dengan rasio cerai tinggi dapat menjadi prioritas kajian lanjutan,
- indikator kesejahteraan perlu dibaca bersama faktor sosial-budaya dan institusional.

### 4.11 Keterbatasan Penelitian

Tuliskan dengan jujur:

- variabel masih terbatas,
- data hanya satu tahun,
- analisis belum kausal,
- ada potensi outlier dan missing value,
- hasil cluster sensitif terhadap pemilihan fitur dan jumlah cluster,
- data final belum mencakup seluruh 38 wilayah jika masih memakai hasil saat ini.

## 5. Kesimpulan

Isi kesimpulan 3-5 poin:

1. K-Means berhasil membagi wilayah ke dalam tiga cluster kerawanan perceraian.
2. Cluster tinggi memiliki rata-rata tingkat cerai paling besar dan karakteristik IPM/TPT yang lebih tinggi.
3. Cluster rendah tidak identik dengan kesejahteraan tinggi, karena pada hasil sementara justru memiliki rata-rata kemiskinan tertinggi.
4. Peta choropleth membantu menampilkan persebaran cluster secara spasial.
5. Penelitian perlu dikembangkan dengan data lebih lengkap, variabel tambahan, dan evaluasi jumlah cluster.

## 6. Saran

Saran penelitian lanjutan:

- tambahkan PDRB per kapita, rata-rata lama sekolah, urbanisasi, dan kepadatan penduduk,
- gunakan data multi-tahun,
- bandingkan K-Means dengan hierarchical clustering atau DBSCAN,
- lakukan validasi jumlah cluster,
- sertakan pembahasan sosial-budaya lokal.

## Daftar Pustaka Awal

Gunakan format sesuai template jurnal tujuan. Referensi awal:

Nugraha, I. W. S. A. (2023). Clustering Pemetaan Tingkat Kemiskinan di Provinsi Jawa Barat Menggunakan Algoritma K-Means. Jurnal Ilmiah Wahana Pendidikan, 9(2), 234-244. https://doi.org/10.5281/zenodo.7567622

Badan Pusat Statistik. (Tahun data). Indeks Pembangunan Manusia Kabupaten/Kota Provinsi Jawa Timur. BPS.

Badan Pusat Statistik. (Tahun data). Tingkat Pengangguran Terbuka Kabupaten/Kota Provinsi Jawa Timur. BPS.

Badan Pusat Statistik. (Tahun data). Persentase Penduduk Miskin Kabupaten/Kota Provinsi Jawa Timur. BPS.

Pengadilan Agama atau Badan Pusat Statistik. (Tahun data). Jumlah Pernikahan dan Perceraian Kabupaten/Kota Provinsi Jawa Timur.
