# 🚗 Dampak Resesi pada Penjualan DasAutomobile

![Python](https://img.shields.io/badge/Python-3.x-3776AB?logo=python&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?logo=jupyter&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-150458?logo=pandas&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-Visualization-11557C)
![Seaborn](https://img.shields.io/badge/Seaborn-Visualization-4C72B0)
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/USERNAME/NAMA-REPO/blob/main/DasAutomobile_Data_Visualization.ipynb)

> Analisis dan visualisasi data penjualan mobil DasAutomobile selama 1980–2023 untuk memahami **seberapa besar resesi memengaruhi penjualan**, jenis kendaraan mana yang paling terdampak, dan bagaimana alokasi iklan saat resesi.

<img width="1720" height="1475" alt="dashboard" src="https://github.com/user-attachments/assets/ac058e83-c13c-4ba8-b617-398a26dafc58" />


---

## 📌 Ringkasan Proyek

Proyek ini menganalisis **528 baris data penjualan bulanan (1980–2023)** menggunakan **Python, Pandas, Matplotlib, dan Seaborn**. Notebook berisi **9 visualisasi** (grafik garis, batang, sebar, gelembung, pai, dan subplot), ringkasan angka, dan sebuah **dashboard** yang dibuat langsung dari hasil analisis tersebut.

**Pertanyaan yang dijawab:**

1. Bagaimana fluktuasi penjualan dari tahun ke tahun, dan kapan resesi terjadi?
2. Seberapa besar penjualan turun saat resesi dibanding periode non-resesi?
3. Jenis kendaraan mana yang paling terpukul (dan paling tahan) saat resesi?
4. Apakah pengeluaran iklan berkaitan dengan penjualan, dan bagaimana alokasinya saat resesi?
5. Apakah ada pengaruh musiman, harga, GDP, dan tingkat pengangguran?

---

## ✨ Sorotan Hasil

| Indikator | Hasil |
|---|---|
| Jumlah baris data | 528 (Januari 1980 – Desember 2023) |
| Proporsi periode | 21,4% resesi (113 bulan) · 78,6% non-resesi (415 bulan) |
| Rata-rata penjualan bulanan, non-resesi | **2.817** |
| Rata-rata penjualan bulanan, resesi | **649** |
| Perubahan penjualan saat resesi | **−77,0%** |
| Tahun penjualan tertinggi / terendah | 1995 (4.300,2) / 1982 (631,1) |
| Bulan terkuat / terlemah | Desember (2.514) / Agustus (2.214), selisih 13,5% |
| Jenis kendaraan paling terdampak / paling tahan | Sports (−94,15%) / Supperminicar (−73,58%) |
| Porsi iklan terbesar saat resesi | Mediumfamilycar (38,4%) |
| Korelasi iklan vs penjualan (non-resesi) | r = −0,124 (lemah, negatif) |
| Korelasi harga vs penjualan (resesi) | r = −0,147 (lemah, negatif) |

---

## 🧮 Definisi Metrik

Beberapa angka dihitung dengan definisi yang berbeda, sehingga perlu dibaca dengan konteksnya:

- **Tahun resesi** adalah tahun yang memuat minimal satu bulan resesi, jadi sebagian tahun resesi (mis. 1983 dan 2020) hanya sebagian bulannya yang resesi.
- **Rata-rata penjualan 2.817 vs 649** dihitung dari seluruh baris data bulanan non-resesi dan resesi (gabungan semua jenis kendaraan). Angka per jenis kendaraan pada bagian 3 dihitung terpisah per jenis, lalu dibandingkan.
- **Perubahan (%)** = (rata-rata resesi − rata-rata non-resesi) ÷ rata-rata non-resesi.
- **Korelasi iklan vs penjualan** dihitung dari rata-rata tahunan pada periode non-resesi, sedangkan **korelasi harga vs penjualan** dihitung dari setiap baris data (bulan) pada periode resesi.
- **Porsi iklan** dihitung dari total pengeluaran iklan.

---

## 📂 Dataset

- **File:** `historical_automobile_sales.csv` (dimuat langsung dari URL di dalam notebook, jadi tidak perlu diunduh manual)
- **Sumber:** dataset proyek akhir kursus *IBM Data Visualization with Python* (IBM Developer Skills Network)
- **Ukuran:** 528 baris × 15 kolom, Januari 1980 – Desember 2023
- **Kualitas data:** tidak ada nilai kosong (*missing values*) pada seluruh kolom

| Kolom | Keterangan |
|---|---|
| `Year`, `Month`, `Date` | Waktu pengamatan |
| `Recession` | 1 = periode resesi, 0 = non-resesi |
| `Automobile_Sales` | Rata-rata penjualan mobil bulanan |
| `Advertising_Expenditure` | Pengeluaran iklan DasAutomobile |
| `Vehicle_Type` | Jenis kendaraan (`Supperminicar`, `Smallfamiliycar`, `Mediumfamilycar`, `Executivecar`, `Sports`) |
| `Price` | Harga rata-rata kendaraan |
| `GDP` | Produk Domestik Bruto |
| `unemployment_rate` | Tingkat pengangguran |
| `Seasonality_Weight` | Bobot musiman |
| `Consumer_Confidence` | Indeks kepercayaan konsumen |

> Penulisan nama jenis kendaraan (mis. `Supperminicar`, `Smallfamiliycar`) dipertahankan sesuai dataset asli.

---

## 🛠️ Tools & Library

- **Python** (Pandas, NumPy)
- **Matplotlib** untuk grafik dasar, subplot, dan dashboard
- **Seaborn** untuk grafik statistik (barplot, scatterplot, regplot, lineplot)
- **Jupyter Notebook / Google Colab**

---

## 📊 Visualisasi & Temuan di Notebook

### 1.1 Fluktuasi penjualan dari tahun ke tahun
<img width="1384" height="584" alt="01_sales_trend_yearly" src="https://github.com/user-attachments/assets/2151f53a-51fd-44dc-93a9-5aeaa15fdd7b" />


- Rata-rata penjualan **tertinggi pada 1995 (4.300,2)** dan **terendah pada 1982 (631,1)**.
- Terdapat lima periode resesi dalam data (1980–1983, 1990–1992, 2000–2002, 2008–2009, dan 2020). Pada sebagian besar periode tersebut penjualan **jatuh tajam**, lalu **pulih relatif cepat** setelah resesi berakhir.
- Rata-rata tahunan pada tahun yang memuat bulan resesi adalah **1.238**, dibanding **2.820** pada tahun lainnya. Resesi 2020 menunjukkan penurunan yang lebih ringan dibanding resesi sebelumnya.

### 1.2 Pengeluaran iklan vs penjualan (non-resesi)
<img width="1384" height="584" alt="02_advertising_vs_sales" src="https://github.com/user-attachments/assets/87c55925-1458-4c11-8ce9-00496f1a56e0" />


- Korelasi antara rata-rata pengeluaran iklan dan penjualan tahunan pada periode non-resesi adalah **−0,124**, yaitu hubungan **lemah** dan secara praktis hampir tidak ada hubungan linear yang berarti.
- Pada data ini, tahun dengan iklan lebih besar tidak otomatis diikuti penjualan yang lebih tinggi. Ini korelasi pada rata-rata tahunan, bukan bukti sebab-akibat.

### 1.3 Penjualan per jenis kendaraan: resesi vs non-resesi
<img width="1184" height="584" alt="03_sales_by_vehicle_type" src="https://github.com/user-attachments/assets/97785857-940c-4e5b-b872-aa57038e1dea" />


| Jenis kendaraan | Non-resesi | Resesi | Perubahan | Jumlah bulan resesi (n) |
|---|---:|---:|---:|---:|
| Supperminicar | 2.495,24 | 659,27 | **−73,58%** | 31 |
| Smallfamiliycar | 2.752,66 | 650,73 | −76,36% | 36 |
| Mediumfamilycar | 2.981,50 | 674,85 | −77,37% | 42 |
| Executivecar | 2.686,44 | 564,00 | −79,01% | 1 |
| Sports | 2.910,64 | 170,33 | **−94,15%** | 3 |

- **Semua** jenis kendaraan turun drastis saat resesi (74% hingga 94%).
- Tiga segmen dengan data terbanyak (Supperminicar, Smallfamiliycar, Mediumfamilycar) turun dengan angka yang berdekatan, yaitu **−74% hingga −77%**.
- ⚠️ **Sports hanya memiliki 3 bulan resesi dan Executivecar hanya 1 bulan.** Penurunan Sports (−94%) tampak paling dalam, tetapi angkanya sangat bergantung pada sedikit observasi, jadi sebaiknya dibaca sebagai indikasi, bukan kesimpulan yang kuat.

### 1.4 Variasi GDP pada periode resesi dan non-resesi
<img width="1584" height="590" alt="04_gdp_recession_vs_non" src="https://github.com/user-attachments/assets/49f299fc-155a-4af9-8e6b-7456f0a24571" />


- Rata-rata GDP saat resesi berada pada kisaran sekitar 22–41, dengan titik terendah pada awal 1980-an.
- Pada periode non-resesi, GDP lebih tinggi dan lebih fluktuatif (kisaran sekitar 31–63, dengan puncak sekitar tahun 1990 dan 2000).

### 1.5 Dampak musiman terhadap penjualan
<img width="1191" height="584" alt="05_seasonality_bubble" src="https://github.com/user-attachments/assets/e6bb430b-6821-4532-9ad9-3d2770fca36d" />


- Rata-rata penjualan tertinggi terjadi pada **Desember (2.514)**, disusul **April (2.477)** dan **Maret (2.425)**. Penjualan terendah terjadi pada **Agustus (2.214)**.
- Bobot musiman tertinggi ada di Maret dan Mei (1,23), tetapi bobot tinggi tidak selalu sejalan dengan penjualan tinggi (Desember justru berbobot rendah, 0,32).
- Selisih bulan tertinggi dan terendah sebesar **13,5%**, sehingga **efek musiman tergolong moderat** dibanding efek resesi.

### 1.6 Harga kendaraan vs volume penjualan saat resesi
<img width="1082" height="584" alt="06_price_vs_sales_scatter" src="https://github.com/user-attachments/assets/4bddb06c-db1d-4a79-9b2a-05cf06d48482" />


- Korelasi harga dan penjualan selama resesi adalah **−0,147**, yaitu hubungan negatif yang **lemah**. Harga bukan penjelas utama turunnya penjualan pada data ini.
- Grafik ini juga memperlihatkan bahwa data resesi didominasi tiga segmen (Supperminicar, Mediumfamilycar, Smallfamiliycar), sedangkan Sports hanya muncul 3 kali dan Executivecar 1 kali.

### 1.7 Porsi pengeluaran iklan: resesi vs non-resesi
<img width="640" height="684" alt="07_ad_share_pie" src="https://github.com/user-attachments/assets/0cab19bd-9f76-49ba-a23d-8c104319cd36" />


- Total iklan saat resesi sebesar 339.910 (**21,0%**) dan non-resesi sebesar 1.279.707 (**79,0%**).
- Porsi 21% ini hampir sama dengan porsi bulan resesi dalam data (113 dari 528 bulan, 21,4%). Rata-rata iklan per bulan juga nyaris sama (≈3.008 saat resesi vs ≈3.084 saat non-resesi), sehingga **anggaran iklan tampaknya tidak dipangkas saat resesi**, padahal penjualan anjlok.

### 1.8 Pengeluaran iklan per jenis kendaraan saat resesi
<img width="783" height="683" alt="08_ad_by_vehicle_recession" src="https://github.com/user-attachments/assets/90a80449-bf4d-46c8-8e4d-16767b42b1f3" />


- Tiga segmen (**Mediumfamilycar 38,4%**, **Smallfamiliycar 30,2%**, **Supperminicar 26,7%**) menyerap sekitar **95%** total iklan saat resesi.
- Porsi kecil **Sports (3,7%)** dan **Executivecar (1,0%)** mencerminkan jumlah bulannya yang sedikit, bukan anggaran yang sengaja dikecilkan. Rata-rata iklan per bulan resesi relatif sebanding antarjenis (≈2.854 hingga ≈4.189 per bulan).

### 1.9 Tingkat pengangguran vs penjualan saat resesi
<img width="1183" height="584" alt="09_unemployment_vs_sales" src="https://github.com/user-attachments/assets/94ba2eae-f761-4eb7-bda0-e12f98b43b2e" />


- Garis rata-rata per jenis kendaraan cukup bergelombang dan **tidak menunjukkan pola menurun yang konsisten** terhadap kenaikan tingkat pengangguran.
- Sports dan Executivecar hanya muncul sebagai garis pendek atau titik tunggal karena datanya sangat sedikit, sehingga tidak cukup untuk disimpulkan.

---

## 🖥️ Dashboard Ringkasan

Dashboard di bagian atas dibuat pada **bagian 3 notebook** dan disimpan otomatis sebagai `images/dashboard.png`. Seluruh angkanya berasal dari hasil bagian 1 dan ringkasan pada bagian 2:

| Panel dashboard | Sumber di notebook |
|---|---|
| Penjualan per Bulan (dan bobot musiman) | 1.5 |
| Penjualan Rata-rata per Tahun | 1.1 |
| Alokasi Iklan saat Resesi | 1.8 |
| Perubahan Penjualan per jenis kendaraan | 1.3 |
| Harga vs Penjualan saat Resesi | 1.6 |
| Porsi Iklan resesi vs non-resesi | 1.7 |
| Korelasi iklan vs penjualan (pada ringkasan) | 1.2 |

---

## 💡 Kesimpulan & Implikasi Bisnis

1. **Resesi menekan penjualan secara drastis dan merata.** Rata-rata penjualan bulanan turun **77%** (2.817 menjadi 649), dan seluruh jenis kendaraan turun 74% hingga 94%. Perencanaan stok dan target perlu memperhitungkan skenario resesi.
2. **Tiga segmen utama turun dengan pola yang seragam, sedangkan Sports perlu data tambahan.** Supperminicar, Smallfamiliycar, dan Mediumfamilycar turun **−74% hingga −77%**. Sports (−94%) tampak paling rentan, tetapi hanya didasarkan pada 3 bulan data.
3. **Efektivitas iklan perlu dievaluasi.** Korelasi iklan dan penjualan lemah (r = −0,124), dan anggaran iklan per bulan hampir tidak berubah saat resesi (≈3.008 vs ≈3.084). Analisis ROI per segmen layak dilakukan sebelum menambah anggaran.
4. **Musiman dan harga bukan faktor dominan.** Selisih antarbulan hanya 13,5% dan korelasi harga lemah (r = −0,147), jauh lebih kecil dibanding efek resesi.

---

## ⚠️ Keterbatasan

- Analisis bersifat **deskriptif dan eksploratif**. Korelasi yang ditemukan tidak membuktikan sebab-akibat.
- Sebagian grafik memakai **rata-rata tahunan**, yang dapat menyembunyikan variasi bulanan, terutama pada tahun yang hanya sebagian bulannya resesi.
- Observasi saat resesi untuk **Sports (3 bulan)** dan **Executivecar (1 bulan)** sangat sedikit, jadi hasil kedua segmen ini tidak dapat digeneralisasi.
- Pengaruh tingkat pengangguran dan GDP hanya dilihat secara visual (bagian 1.9 dan 1.4), belum diukur dengan korelasi atau model.
- Variabel lain dalam dataset (mis. `Competition`, `Growth_Rate`, `City`, `Consumer_Confidence`) belum dieksplorasi pada notebook ini.

---

## 📁 Struktur Repositori

```
.
├── DasAutomobile_Data_Visualization.ipynb   # Notebook analisis, ringkasan, dan dashboard
├── images/                                  # Dashboard dan hasil grafik untuk README
│   ├── dashboard.png
│   └── 01_… sampai 09_….png
└── README.md
```

## ▶️ Cara Menjalankan

**Opsi terbaik: Google Colab**
Klik badge **Open In Colab** di bagian atas.

Data diambil otomatis dari URL, jadi dibutuhkan koneksi internet saat menjalankan sel pertama. Pilih **Kernel → Restart & Run All** untuk mereproduksi seluruh grafik, angka ringkasan, dan dashboard. Dashboard akan tersimpan ke `images/dashboard.png`.

---

## 👤 Tentang Penulis

**M. Maulana Aryo M.**
Data Analyst · Python · Pandas · Matplotlib · Seaborn

https://www.linkedin.com/in/mmaulanaaryo9b9174253/ · mmaulanaryo@gmail.com

Jika proyek ini bermanfaat, jangan lupa beri ⭐ pada repositori ini.

---

## 📚 Sumber Data

Dataset `historical_automobile_sales.csv` merupakan dataset proyek akhir Coursera **IBM Data Visualization with Python**, disediakan oleh **IBM Developer Skills Network**.
