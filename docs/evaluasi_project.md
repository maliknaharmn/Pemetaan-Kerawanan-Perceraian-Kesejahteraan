# Evaluasi Project Portfolio

## Status Saat Ini

Project sudah memenuhi mayoritas kebutuhan MVP portfolio:

- Notebook berhasil menjalankan pipeline data science dari load data sampai output cluster.
- K-Means menghasilkan 3 cluster sesuai scope awal.
- Silhouette score sudah dihitung.
- Visualisasi EDA sudah tersedia melalui heatmap dan scatter plot.
- Peta statis dan peta interaktif Folium sudah dibuat.
- Output `cluster_result.csv` sudah tersedia.

## Temuan Utama dari Output Cluster

File `cluster_result.csv` berisi 34 wilayah dan 8 kolom:

| Kolom | Keterangan |
| --- | --- |
| `kode_wilayah` | Kode kabupaten/kota |
| `kabupaten_kota` | Nama wilayah |
| `cluster` | Label numerik hasil K-Means |
| `label_kerawanan` | Interpretasi cluster |
| `ipm` | Indeks Pembangunan Manusia |
| `tpt` | Tingkat Pengangguran Terbuka |
| `kemiskinan` | Persentase kemiskinan |
| `tingkat_cerai` | Rasio perceraian terhadap pernikahan |

Distribusi cluster:

| Label cluster | Jumlah wilayah |
| --- | ---: |
| Kerawanan Tinggi | 4 |
| Kerawanan Sedang | 22 |
| Kerawanan Rendah | 8 |

Profil rata-rata cluster:

| Label cluster | IPM | TPT | Kemiskinan | Tingkat cerai |
| --- | ---: | ---: | ---: | ---: |
| Kerawanan Tinggi | 82.78 | 6.86 | 4.66 | 37.76 |
| Kerawanan Sedang | 72.98 | 4.79 | 9.80 | 30.93 |
| Kerawanan Rendah | 68.40 | 3.03 | 16.73 | 26.39 |

## Interpretasi Sementara

Cluster "Kerawanan Tinggi" didominasi wilayah dengan rata-rata tingkat cerai paling tinggi. Cluster ini juga memiliki rata-rata IPM dan TPT yang lebih tinggi, serta kemiskinan lebih rendah. Ini memberi indikasi bahwa kerawanan perceraian pada data ini tidak sekadar mengikuti tingkat kemiskinan.

Cluster "Kerawanan Sedang" merupakan kelompok terbesar. Wilayah pada cluster ini memiliki tingkat cerai menengah sampai tinggi dengan indikator kesejahteraan yang berada di tengah.

Cluster "Kerawanan Rendah" memiliki rata-rata kemiskinan tertinggi, tetapi rata-rata tingkat cerai paling rendah. Interpretasi ini perlu hati-hati karena bisa dipengaruhi akses pencatatan, perbedaan urban-rural, budaya lokal, dan kualitas data.

## Catatan Teknis Notebook

Poin yang sudah baik:

- Struktur notebook runtut dan mudah diikuti.
- Path Google Drive sudah jelas.
- Fitur `tingkat_cerai` dibuat secara eksplisit.
- Standardisasi fitur sudah benar sebelum K-Means.
- Hasil cluster diberi label interpretatif.
- Folium tooltip sudah mencantumkan indikator penting.

Poin yang perlu dirapikan:

- Jumlah wilayah turun dari 38 menjadi 34 setelah cleaning. Jika ini dipertahankan, jelaskan alasannya di README dan artikel.
- Empat wilayah yang di-drop sebaiknya masuk lampiran atau ditampilkan sebagai "Tidak Ada Data" pada peta.
- Cell load dan merge GeoJSON muncul dua kali. Hapus salah satunya.
- Cell `plt.savefig('scatterplot_cluster.png')` sebaiknya dipindahkan sebelum `plt.show()`.
- Hindari emoji pada output final jika notebook ditujukan untuk artikel ilmiah.
- Gunakan satu bahasa konsisten pada heading: Indonesia penuh atau Inggris penuh.

## Rekomendasi Sebelum Publikasi GitHub

1. Pastikan data final 38 kabupaten/kota atau jelaskan pengecualian 4 wilayah.
2. Tambahkan screenshot peta ke `assets/screenshots/`.
3. Tambahkan link `map_cluster.html` jika sudah di-hosting melalui GitHub Pages.
4. Rapikan notebook agar tidak ada cell duplikat.
5. Tambahkan sumber data pada README: nama publikasi, tahun, dan URL.
6. Tambahkan catatan keterbatasan agar analisis terlihat matang dan jujur.

## Rekomendasi Jika Dikembangkan Menjadi Artikel Jurnal

Untuk versi jurnal, project perlu diperkuat pada bagian:

- dasar teori perceraian dan kesejahteraan sosial,
- justifikasi pemilihan variabel,
- penjelasan data dan tahun pengamatan,
- evaluasi nilai `k` dengan elbow method dan silhouette,
- pembahasan wilayah urban dan rural,
- validasi hasil peta dengan literatur atau data resmi,
- keterbatasan data dan risiko interpretasi kausal.
