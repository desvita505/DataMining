# DataMining
Judul Laporan: Implementasi Decision Tree untuk Klasifikasi Kanker Payudara

1. Deskripsi Umum
File ini merupakan skrip Python yang dibuat secara otomatis dari Google Colab. Skrip ini menggunakan dataset kanker payudara dari Scikit-learn (`datasets.load_breast_cancer()`) untuk melatih dan mengevaluasi model klasifikasi berbasis Decision Tree. Visualisasi dari decision tree juga ditampilkan di akhir.

2. Library yang Digunakan
 `sklearn.datasets`: Untuk memuat dataset kanker payudara.
 `sklearn.model_selection.train_test_split`: Untuk membagi data menjadi data latih dan data uji.
 `sklearn.tree`: Untuk menggunakan model `DecisionTreeClassifier` dan fungsi visualisasi `plot_tree`.
 `matplotlib.pyplot`: Untuk menampilkan visualisasi decision tree.

3. Dataset
Dataset yang digunakan adalah Breast Cancer Wisconsin Dataset, yang disediakan secara built-in oleh Scikit-learn:
 Jumlah fitur: 30
 Jenis fitur: Numerik (contoh: mean radius, mean texture, mean perimeter, dll)
 Jumlah sampel: 569
 Kelas target: 2 (0 = malignant, 1 = benign)
```python
data = datasets.load_breast_cancer()
x = data.data        Fitur
y = data.target      Label
```

 4. Pemrosesan Data
Data dibagi menjadi dua bagian:
 80% untuk pelatihan (training)
 20% untuk pengujian (testing)
```python
x_train, x_test, y_train, y_test = train_test_split(x, y, test_size=0.2)
```

 5. Model Machine Learning
Model yang digunakan adalah Decision Tree Classifier dari Scikit-learn dengan parameter berikut:
 `max_depth=3`: Membatasi kedalaman pohon maksimum hingga 3 level untuk menghindari overfitting.
```python
dtree = DecisionTreeClassifier(max_depth=3)
dtree.fit(x_train, y_train)
```

 6. Evaluasi Model
Akurasi model dihitung berdasarkan data uji yang telah dipisahkan sebelumnya. Nilai akurasi dikalikan 100 untuk ditampilkan dalam format persentase dua desimal:
```python
accuracy = dtree.score(x_test, y_test)
print(f"Akurasi model: {accuracy100:.2f}%")
```
Output dari kode ini akan mencetak akurasi model klasifikasi, contohnya:
```
Akurasi model: 91.23%
```
(Nilai akurasi aktual bisa berbeda-beda tergantung hasil split random)

 7. Visualisasi Pohon Keputusan
Model decision tree divisualisasikan menggunakan `plot_tree` dari `sklearn.tree` dengan ukuran figure yang cukup besar:
```python
plt.figure(figsize=(50, 30))
plot_tree(dtree, filled=True)
plt.show()
```
 Warna pada setiap node menggambarkan kelas dominan (malignant atau benign).
 Informasi fitur, threshold, dan impurity ditampilkan secara visual pada setiap node.

 8. Kesimpulan
 Kode ini membangun dan mengevaluasi model klasifikasi berbasis pohon keputusan dengan dataset kanker payudara.
 Model sederhana dengan kedalaman pohon terbatas (`max_depth=3`) mampu memberikan akurasi yang cukup tinggi di atas 90% pada data uji.
 Visualisasi pohon memudahkan interpretasi logika pengambilan keputusan oleh model.

