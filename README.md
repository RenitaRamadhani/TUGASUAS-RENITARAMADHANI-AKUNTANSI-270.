![Screenshot (1)](https://github.com/RenitaRamadhani/TUGASUAS-RENITARAMADHANI-AKUNTANSI-270/assets/153142982/69304c81-a097-46d9-9a0a-9f2dfb92fe7a)# Nama : Renita Ramadhani #
# NIM : 12030122140270 #
# Kelas : Pengkodean dan Pemrograman/D #

# Soal #
Buatlah sistem yang mencatat data penggajian dari setiap pekerja yang lengkap dan jelas, dan intrepetasi dari data tersebut !

# Cara Pengerjaan #
# Import pustaka yang dibutuhkan
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns

# Langkah 1: Memuat Data
data = pd.read_csv('data.csv', sep=';')

# Langkah 2: Eksplorasi Data Awal

# Melihat beberapa baris pertama dari dataset
print("Beberapa baris pertama dari dataset:")
print(data.head())

# Informasi ringkas tentang dataset
print("\nInformasi dataset:")
print(data.info())

# Statistik deskriptif dari dataset
print("\nStatistik deskriptif dataset:")
print(data.describe())

# Mengecek missing values
print("\nMissing values:")
print(data.isnull().sum())

# Langkah 3: Visualisasi Dasar

# Histogram dari semua kolom numerik
print("\nVisualisasi histogram dari kolom numerik:")
data.hist(figsize=(10, 8))
plt.tight_layout()
plt.show()

# Visualisasi korelasi antar kolom numerik
print("\nVisualisasi heatmap korelasi:")
correlation_matrix = data.corr()
plt.figure(figsize=(10, 8))
plt.title('Correlation Matrix')
sns.heatmap(correlation_matrix, annot=True, cmap='coolwarm', linewidths=0.5)
plt.show()

# Plot distribusi dari kolom tertentu (misal kolom 'age')
print("\nVisualisasi distribusi kolom 'age':")
plt.figure(figsize=(8, 6))
sns.histplot(data['age'], kde=True, bins=30)
plt.title('Distribution of Age')
plt.xlabel('Age')
plt.ylabel('Frequency')
plt.show()

# Scatter plot untuk dua kolom tertentu (misal 'age' dan 'salary')
print("\nScatter plot untuk 'age' dan 'salary':")
plt.figure(figsize=(8, 6))
plt.scatter(data['age'], data['salary'], alpha=0.5)
plt.title('Age vs. Salary')
plt.xlabel('Age')
plt.ylabel('Salary')
plt.show()

# Langkah 4: Mengatasi Missing Values (jika ada)

# Mengisi missing values dengan median (contoh)
print("\nMengisi missing values dengan median:")
data_filled = data.fillna(data.median())

print("Missing values setelah pengisian:")
print(data_filled.isnull().sum())

# Simpan dataset yang telah diisi missing values
data_filled.to_csv('data_filled.csv', index=False)

print("\nDataset yang telah diisi missing values disimpan sebagai 'data_filled.csv'")

# Langkah 5: Menyimpan perubahan ke file baru
data.to_csv('data_cleaned.csv', index=False)

print("\nDataset yang telah dibersihkan disimpan sebagai 'data_cleaned.csv'")

# Data #
![image](https://github.com/RenitaRamadhani/TUGASUAS-RENITARAMADHANI-AKUNTANSI-270/assets/153142982/51696293-10ee-479a-8b4b-17976ccfc08c)

# Hasil #
![image](https://github.com/RenitaRamadhani/TUGASUAS-RENITARAMADHANI-AKUNTANSI-270/assets/153142982/d66a191a-52ad-4f43-bc9f-86238317accd)

# Intepretasi #
# Analisis Regresi:

Dalam konteks ini, mari asumsikan kita ingin menganalisis hubungan antara usia (age) seseorang dengan gaji (salary) yang mereka terima. Dengan menggunakan regresi linear sederhana, kita dapat melihat seberapa kuat hubungan antara kedua variabel tersebut.

Dari output regresi:

- Koefisien regresi (slope): Koefisien ini mengindikasikan seberapa banyak perubahan yang diharapkan terjadi dalam gaji jika usia seseorang bertambah satu satuan. Misalnya, jika koefisien adalah 1000, itu berarti setiap tahun usia bertambah, gaji rata-rata diharapkan meningkat sebesar 1000 satuan.
  
- Intercept: Intercept menunjukkan perkiraan gaji saat usia seseorang adalah nol. Ini mungkin memiliki interpretasi yang lebih abstrak tergantung pada konteks data. Misalnya, dalam konteks ini, itu bisa berarti gaji awal yang diharapkan saat seseorang memulai karir mereka.

# Analisis Korelasi:

Korelasi memungkinkan kita untuk memahami seberapa erat hubungan antara variabel-variabel numerik dalam dataset.

Dari heatmap korelasi:

- Jika korelasi antara usia (age) dan gaji (salary) mendekati 1, itu menunjukkan hubungan positif yang kuat. Artinya, semakin tua seseorang, semakin tinggi gaji yang mereka dapatkan (jika korelasi positif).
  
- Jika korelasi mendekati -1, itu menunjukkan hubungan negatif yang kuat. Misalnya, jika korelasi antara usia dan gaji adalah -0.5, itu menunjukkan bahwa semakin tua seseorang, semakin rendah gaji yang mereka terima (jika korelasi negatif).

- Jika korelasi mendekati 0, itu menunjukkan tidak adanya hubungan linear antara kedua variabel tersebut.

Dengan demikian, melalui analisis regresi dan korelasi, kita dapat memahami hubungan antara usia dan gaji

