# Analisis Klaster Daerah Rawan Perceraian Berdasarkan Indikator Kesejahteraan Masyarakat

Portfolio data science untuk memetakan kerawanan perceraian kabupaten/kota di Jawa Timur menggunakan indikator kesejahteraan masyarakat. Proyek ini menggabungkan EDA, feature engineering, standardisasi fitur, K-Means clustering, silhouette score, dan visualisasi peta choropleth.

## Ringkasan Proyek

Proyek ini bertujuan mengelompokkan wilayah berdasarkan kombinasi indikator sosial-ekonomi dan rasio perceraian. Output utama berupa tabel hasil cluster dan peta interaktif yang dapat dipakai sebagai bahan eksplorasi awal untuk melihat pola kerawanan perceraian antarwilayah.

Analisis bersifat eksploratif. Label seperti "Kerawanan Tinggi", "Kerawanan Sedang", dan "Kerawanan Rendah" tidak dimaksudkan sebagai bukti kausal bahwa indikator kesejahteraan menyebabkan perceraian.

## Metode

Tahapan analisis:

1. Load data indikator kabupaten/kota.
2. Validasi kolom dan tipe data.
3. Feature engineering `tingkat_cerai`.
4. Handling missing value.
5. EDA dengan korelasi dan scatter plot.
6. Standardisasi fitur dengan `StandardScaler`.
7. Clustering menggunakan `KMeans(n_clusters=3, random_state=42)`.
8. Evaluasi cluster menggunakan silhouette score.
9. Merge hasil cluster dengan GeoJSON kabupaten/kota Jawa Timur.
10. Visualisasi peta choropleth interaktif menggunakan Folium.

Fitur yang digunakan pada MVP:

| Fitur | Keterangan |
| --- | --- |
| `ipm` | Indeks Pembangunan Manusia |
| `tpt` | Tingkat Pengangguran Terbuka |
| `kemiskinan` | Persentase penduduk miskin |
| `tingkat_cerai` | `jumlah_cerai / jumlah_nikah * 100` |

## Hasil Sementara

Berdasarkan file `cluster_result.csv` yang diekspor dari notebook:

| Label cluster | Jumlah wilayah | Rata-rata IPM | Rata-rata TPT | Rata-rata kemiskinan | Rata-rata tingkat cerai |
| --- | ---: | ---: | ---: | ---: | ---: |
| Kerawanan Tinggi | 4 | 82.78 | 6.86 | 4.66 | 37.76 |
| Kerawanan Sedang | 22 | 72.98 | 4.79 | 9.80 | 30.93 |
| Kerawanan Rendah | 8 | 68.40 | 3.03 | 16.73 | 26.39 |

Silhouette score pada notebook: `0.354`.

Interpretasi awal:

- Cluster kerawanan tinggi berisi wilayah dengan rata-rata `tingkat_cerai` paling tinggi dan cenderung memiliki IPM serta TPT yang lebih tinggi.
- Cluster kerawanan rendah memiliki rata-rata kemiskinan lebih tinggi, tetapi tingkat cerai lebih rendah.
- Pola ini perlu dibaca hati-hati karena rasio perceraian dapat dipengaruhi kualitas pencatatan, akses lembaga peradilan, struktur urban, migrasi, dan faktor sosial-budaya.

Wilayah dengan `tingkat_cerai` tertinggi pada hasil sementara:

| Wilayah | Cluster | Tingkat cerai |
| --- | --- | ---: |
| Kota Malang | Kerawanan Tinggi | 47.55 |
| Kabupaten Blitar | Kerawanan Sedang | 40.00 |
| Kabupaten Banyuwangi | Kerawanan Sedang | 38.07 |
| Kabupaten Mojokerto | Kerawanan Sedang | 36.57 |
| Kota Surabaya | Kerawanan Tinggi | 35.39 |

## Catatan Evaluasi

Beberapa hal yang perlu diperbaiki sebelum repository dipublikasikan:

- Output `cluster_result.csv` saat ini berisi 34 wilayah, sedangkan Jawa Timur memiliki 38 kabupaten/kota. Empat wilayah dikeluarkan pada proses cleaning karena data perceraian tidak normal atau kosong.
- Merge GeoJSON berhasil pada 34 dari 38 wilayah. Jika ingin klaim "seluruh Jawa Timur", data empat wilayah tersebut perlu diperbaiki atau diberi kategori "Tidak Ada Data" tanpa dikeluarkan dari peta.
- Ada duplikasi cell merge GeoJSON pada notebook. Cukup simpan satu cell.
- `plt.savefig('scatterplot_cluster.png')` sebaiknya dipanggil sebelum `plt.show()` agar gambar tersimpan dengan benar.
- Nilai silhouette `0.354` menunjukkan struktur cluster masih sedang/lemah. Untuk artikel ilmiah, perlu uji tambahan seperti elbow method, silhouette untuk beberapa nilai `k`, dan pembahasan keterbatasan.

## Struktur Repository

```text
.
|-- notebooks/
|   `-- divorce_vulnerability_clustering_jatim.ipynb
|-- data/
|   |-- README.md
|   `-- sample_jatim_indicators.csv
|-- docs/
|   |-- evaluasi_project.md
|   `-- format_jurnal.md
|-- outputs/
|-- assets/
|   `-- screenshots/
|-- requirements.txt
`-- README.md
```

## Cara Menjalankan di Google Colab

1. Upload repository ke GitHub atau Google Drive.
2. Buka notebook di Google Colab.
3. Jalankan cell instalasi library.
4. Mount Google Drive jika data disimpan di Drive.
5. Sesuaikan `BASE_DIR`, `DATA_PATH`, `GEO_PATH`, dan `GEOJSON_KEY`.
6. Jalankan semua cell dari awal sampai akhir.
7. Ambil output dari folder `outputs/`.

## Output

Output utama:

- `cluster_result.csv`: tabel hasil clustering.
- `map_cluster.html`: peta interaktif Folium.
- `peta_choropleth_pysal_jatim_tingkat_cerai.png`: peta statis untuk laporan/jurnal.
- `scatterplot_cluster.png`: scatter plot cluster.

## Tech Stack

- Python
- pandas, numpy
- scikit-learn
- matplotlib, seaborn
- geopandas
- folium
- mapclassify

## Dokumentasi Tambahan

- Evaluasi project tersedia di [docs/evaluasi_project.md](docs/evaluasi_project.md).
- Kerangka artikel jurnal tersedia di [docs/format_jurnal.md](docs/format_jurnal.md).

Referensi gaya penulisan dan struktur metode dapat meniru artikel K-Means pemetaan kemiskinan berbasis CRISP-DM seperti:

Nugraha, I. W. S. A. (2023). Clustering Pemetaan Tingkat Kemiskinan di Provinsi Jawa Barat Menggunakan Algoritma K-Means. Jurnal Ilmiah Wahana Pendidikan, 9(2), 234-244. https://doi.org/10.5281/zenodo.7567622
