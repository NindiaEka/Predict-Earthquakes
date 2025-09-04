# Analisis & Prediksi Gempa Bumi Indonesia 2020–2025


## Repository Outline
```
1. README.md - Penjelasan gambaran umum project
2. P1M2_Nindia-Ekasuci.ipynb - Notebook yang berisi pengolahan data dengan python
3. P1M2_Nindia-Ekasuci_inf.ipynb - Notebook yang berisi uji coba data menggunakan data baru (inference)
4. description.md - Berisi deskripsi singkat mengenai apa yang telah dilakukan
5. model_best_tunning.pkl - berisi file best model yang telah di tunning
6. P1M2_Nindia-Ekasuci_Conceptual_Problem.txt - berisi mengenai penjelasan mengenai dasar - dasar metode atau algoritma yang akan dilakukan
7. Dataset_gempa.csv - Dataset yang akan dilakukan pengolahan lebih lanjut
8. URL.txt - informasi URL dari data set dan deployment
```

## Problem Background
Menurut laporan [Badan Geologi](https://www.cnbcindonesia.com/news/20250122174037-4-605239/gempa-bumi-merusak-hantam-ri-cetak-rekor-di-2024-fakta-aneh-terungkap), kejadian gempa bumi yang telah mengakibatkan terjadinya korban jiwa, kerusakan bangunan, kerusakan lingkungan dan kerugian harta benda. Kejadian gempa bumi merusak tahun 2024 merupakan yang tertinggi dalam kurun waktu 24 tahun terakhir sejak tahun 2000. Memprediksi magnitudo gempa bumi menggunakan parameter lokasi, kedalaman, jumlah stasiun seismik, dan indikator akurasi menggunakan data gempa pada tahun 2020- 2025. Tujuannya adalah mendukung BNPB dalam memperkirakan kekuatan gempa lebih cepat sehingga dapat mengoptimalkan penyaluran sumber daya dan evakuasi.

## Project Output
Output project berupa model machine learning untuk memprediksi magnitudo gempa bumi menggunakan parameter lokasi, kedalaman, jumlah stasiun seismik, dan indikator akurasi. Model ini diintegrasikan ke dalam dashboard interaktif berbasis Streamlit yang menampilkan hasil prediksi, peta lokasi gempa, analisis tren gempa, serta fitur unduh data hasil prediksi dalam format CSV.

## Data
Sumber data berasal dari catalogue gempa dari website [USGS-The U.S. Geological Survey]( https://earthquake.usgs.gov/earthquakes/search/), diambil data bertype earthquakes dengan kekuatan gempa 3 - 7 SR rentang periode 2020 - 2025. Data tersebut di download dalam bentuk CSV dengan informasi sebanyak 6789 rows x 24 columns. Data tersebut terdiri dari 16 kolom numerik dan 8 kolom kategori. Missing value berada pada jumlah stasiun yang merekam gempa sehingga dilakukan handling missing value dengan cara mengelompokkan data berdasarkan lokasinya kemudian dihitung median per masing - masing kelompok data. Outlier tidak di handling karena tujuannya untuk memprediksi semua jenis gempa, termasuk yang besar. Folder deployment yang telah dilakukan lumayan besar karena file .pkl berkisar 30MB sehingga file tersebut di upload pada drive pribadi, berikut link filenya [FIle-Deployment](https://drive.google.com/drive/folders/1pEkzNwObkPcV60bZSLOtgvIZs2rDhfeC?usp=sharing)

## Method
Dilakukan uji coba model menggunakan lima jenis algoritma yaitu KNN (K-Nearest Neighboor), SVM(Super Vector Machine), Decission Tree, Random Forest, dan Gradient Boosting. Dari kelima algoritma tersebut dibandingkan berdasarkan metrik yang digunakan, dalam hal ini adalah MAE (Mean Absolute Error) dan dilakukan juga cross validation untuk melihat mana model yang terbaik. Didapatkan model terbaik adalah algoritma random forest, kemudian dilakukan tunning pada algoritma random forest menggunakan random search

## Stacks
Stacks yang Digunakan

 1. Bahasa Pemrograman
- **Python** → Digunakan untuk pengolahan data, analisis, pemodelan, dan pembangunan aplikasi.

 2. Tools
- **Jupyter Notebook / VS Code / IDE Python** → Pengembangan & eksplorasi data.
- **Streamlit** → Framework untuk membangun aplikasi web interaktif berbasis Python.
- **pip / conda** → Manajemen paket dan lingkungan virtual.

 3. Library Python

| Library / Package | Fungsi Utama |
|-------------------|--------------|
| **pandas** | Manipulasi dan analisis data tabular. |
| **numpy** | Perhitungan numerik dan manipulasi array. |
| **matplotlib** | Visualisasi data dalam bentuk grafik. |
| **seaborn** | Visualisasi statistik yang lebih estetik. |
| **scipy.stats** | Uji statistik (Pearson, Chi-Square, Kruskal-Wallis). |
| **scikit-learn** | Preprocessing (`RobustScaler`, `OneHotEncoder`), pembagian data (`train_test_split`), pencarian parameter (`RandomizedSearchCV`, `GridSearchCV`), pipeline (`make_pipeline`, `ColumnTransformer`), algoritma ML (`KNeighborsRegressor`, `SVR`, `DecisionTreeRegressor`, `RandomForestRegressor`, `GradientBoostingRegressor`, `KMeans`), evaluasi model (MAE, MSE, RMSE, R², MAPE). |
| **streamlit** | Membangun *dashboard* interaktif dan aplikasi web untuk menampilkan hasil analisis dan prediksi model. |
| **re** | Pemrosesan teks dengan *regular expressions*. |

## Reference
[Badan Geologi](https://www.cnbcindonesia.com/news/20250122174037-4-605239/gempa-bumi-merusak-hantam-ri-cetak-rekor-di-2024-fakta-aneh-terungkap)
[USGS-The U.S. Geological Survey]( https://earthquake.usgs.gov/earthquakes/search/)
[File-Deployment](https://drive.google.com/drive/folders/1pEkzNwObkPcV60bZSLOtgvIZs2rDhfeC?usp=sharing)
[Hasil-Deployment](https://predict-earthquakes.streamlit.app/)

---
