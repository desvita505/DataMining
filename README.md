# DataMining


Program ini dimulai dengan proses instalasi dan import berbagai library yang dibutuhkan dalam analisis data, khususnya untuk visualisasi, pemrosesan data, reduksi dimensi, dan klasterisasi. Library yellowbrick digunakan untuk membantu visualisasi proses machine learning, sementara pandas, numpy, matplotlib, dan seaborn digunakan untuk manipulasi data serta visualisasi statistik. Library dari sklearn seperti LabelEncoder, StandardScaler, PCA, dan KMeans digunakan untuk preprocessing, reduksi dimensi, dan klasterisasi. Selain itu, modul warnings digunakan untuk menyembunyikan peringatan agar output lebih bersih.

Selanjutnya, dataset dibaca menggunakan pandas.read_csv() dengan pemisah tab (\t) karena file CSV tersebut menggunakan tab sebagai delimiter. Data kemudian diproses dengan menambahkan beberapa fitur baru. Kolom Dt_Customer dikonversi ke format datetime dan digunakan untuk menghitung lamanya seseorang telah menjadi pelanggan melalui kolom baru Customer_For. Selain itu, kolom Age dihitung berdasarkan tahun lahir, dan kolom Spent dihitung sebagai total belanja pelanggan dari beberapa kategori produk.

Dalam tahap berikutnya, beberapa fitur baru ditambahkan, seperti Children yang merupakan penjumlahan dari Kidhome dan Teenhome, serta Family_Size yang menghitung ukuran keluarga berdasarkan jumlah anak dan status pernikahan. Nilai pada Marital_Status disesuaikan agar dapat dikonversi ke bentuk numerik dengan makna logis, misalnya "Married" atau "Together" dianggap 2, sedangkan lainnya dianggap 1.

Untuk persiapan analisis lebih lanjut, fitur-fitur yang dianggap tidak relevan seperti ID, Year_Birth, Dt_Customer, Z_CostContact, dan Z_Revenue dihapus dari dataset. Selanjutnya, nilai-nilai pada kolom Education disederhanakan ke dalam tiga kategori utama: Undergraduate, Graduate, dan Postgraduate, untuk memudahkan analisis.

Setelah itu, semua kolom bertipe kategori (object) diubah menjadi bentuk numerik menggunakan LabelEncoder agar dapat digunakan dalam model machine learning. Dataset kemudian dinormalisasi menggunakan StandardScaler agar seluruh fitur berada dalam skala yang sama dan tidak mendominasi satu sama lain saat dilakukan analisis atau klasterisasi.

Sebelum proses analisis utama dilakukan, baris data yang memiliki nilai kosong (missing values) dihapus untuk menjaga kualitas data. Dataset kemudian dinormalisasi kembali setelah pembersihan data agar hasilnya konsisten. Proses selanjutnya adalah melakukan PCA (Principal Component Analysis), yaitu teknik reduksi dimensi untuk menyederhanakan dataset menjadi tiga komponen utama (PC1, PC2, PC3) yang tetap mempertahankan sebagian besar informasi dari data asli.

Akhirnya, hasil dari proses PCA disimpan ke dalam pca_df, yaitu dataframe baru yang berisi tiga komponen utama. Data ini nantinya bisa digunakan untuk visualisasi 3D atau proses klasterisasi lebih lanjut seperti menggunakan KMeans atau Hierarchical Clustering.


