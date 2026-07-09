# Data Folder

Folder ini dipakai untuk menyimpan data proyek.

## File utama yang disarankan

Gunakan satu file tabular `.csv` atau `.xlsx` dengan minimal kolom berikut:

| Kolom | Contoh | Keterangan |
| --- | --- | --- |
| `kode_wilayah` | `3501` | Kode kabupaten/kota. Samakan dengan kode di GeoJSON/shapefile. |
| `kabupaten_kota` | `Kabupaten Pacitan` | Nama kabupaten/kota. |
| `ipm` | `70.94` | Indeks Pembangunan Manusia. |
| `tpt` | `2.15` | Tingkat Pengangguran Terbuka. |
| `kemiskinan` | `13.08` | Persentase penduduk miskin. |
| `jumlah_nikah` | `5200` | Jumlah pernikahan. |
| `jumlah_cerai` | `1350` | Jumlah perceraian. |

Notebook akan membuat kolom `tingkat_cerai` otomatis:

```text
tingkat_cerai = jumlah_cerai / jumlah_nikah * 100
```

## Catatan

- `sample_jatim_indicators.csv` adalah data contoh sintetis untuk mengetes alur notebook, bukan data resmi BPS.
- Simpan data resmi mentah di `data/raw/` agar tidak tercampur dengan file contoh.
- Untuk peta, gunakan GeoJSON atau shapefile kabupaten/kota Jawa Timur yang memiliki kolom kode wilayah sepadan dengan `kode_wilayah`.
