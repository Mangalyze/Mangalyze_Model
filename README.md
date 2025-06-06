# Mangalyze – Mango Leaf Analyze
**Mangalyze** adalah sistem deteksi kondisi daun mangga berbasis pengenalan citra dan logika rekomendasi sederhana.

## Tentang Proyek
Proyek ini bertujuan untuk mengembangkan Mango Leaf Analyze (MANGALYZE), sebuah sistem deteksi kondisi daun mangga berbasis teknologi pengenalan citra dan logika rekomendasi sederhana. Latar belakang permasalahan muncul dari kesulitan yang dihadapi petani dalam mendeteksi dini penyakit atau gangguan pada daun mangga, yang sering kali berdampak pada penurunan hasil panen dan peningkatan biaya produksi. Sistem ini dirancang untuk mengklasifikasikan kondisi daun berdasarkan foto yang diunggah oleh pengguna, ke dalam beberapa kategori, seperti daun sehat, terserang penyakit (misalnya antraknosa atau bercak daun), serta gejala kekurangan nutrisi seperti klorosis. Proses klasifikasi dilakukan menggunakan teknik Convolutional Neural Network (CNN), yang telah terbukti efektif dalam pengenalan pola visual. Hasil klasifikasi kemudian diikuti oleh pemberian rekomendasi penanganan berbasis logika aturan (rule-based logic) yang sederhana dan mudah dipahami. Dengan pendekatan ini, MANGALYZE diharapkan mampu memberikan solusi praktis, cepat, dan akurat dalam pemantauan kesehatan daun mangga, serta mendukung implementasi pertanian musiman yang lebih efisien dan berkelanjutan. Sistem ini juga berpotensi menjadi kontribusi nyata dalam penerapan pertanian presisi dan pengelolaan sumber daya di sektor hortikultura lokal Indonesia.

## Anggota 
1. A296YBF008 – Achmad Fauzihan Bagus Sajiwo – Universitas Pembangunan Nasional Veteran Jawa Timur
2. A673XBF392 – Permata Ayu Rahmawati – Universitas Bhayangkara Surabaya
3. A308YBF407 – Rahmad Ramadhan Laska – Universitas Riau
4. A312XBF453 – Sevyra Nanda Octavianti – Universitas Sebelas Maret

## Repositori Pendukung
| Team               | Link Repository                                                         |
|--------------------|-------------------------------------------------------------------------|
| Web Development    | [Mangalyze-Website](https://github.com/Mangalyze/Website_Mangalyze.git) |               
| Machine Learning   | **(Repositori ini)**                                                    |

## Tentang Dataset

Dataset yang digunakan adalah **[Mango Leaf Disease Dataset](https://www.kaggle.com/datasets/aryashah2k/mango-leaf-disease-dataset/data)** dari Kaggle, yang berisi gambar daun mangga dengan berbagai kondisi kesehatan dan penyakit.

### Rangkuman Dataset

- **Jumlah gambar:** 4000 gambar  
  - Sekitar **1800 gambar unik** berasal dari daun yang berbeda  
  - Sisanya dihasilkan melalui **augmentasi** (zoom dan rotasi)
- **Jumlah kelas:** 8 kelas
  - 7 jenis penyakit (Anthracnose, Bacterial Canker, Cutting Weevil, Die Back, Gall Midge, Powdery Mildew, dan Sooty Mould)
  - 1 kelas daun sehat (healthy)
 
## Model Development

Proses pembangunan model dilakukan dalam beberapa tahap berikut:

1. **Eksplorasi dan Persiapan Data**
   - Mengecek struktur folder dan distribusi kelas
   - Mengecek resolusi gambar
   - Mengecek gambar apakah ada yang rusak

2. **Pembagian Dataset dan Preprocessing**
   - Split data menjadi train, validation, dan test
   - Menggunakan `ImageDataGenerator` dari TensorFlow/Keras
   - Melakukan augmentasi
   - Normalisasi dan resize citra

4. **Arsitektur Model**
   - Melakukan pendekatan transfer learning menggunakan model DenseNet201 
   - Penambahan custom layers di atas model pre-trained

5. **Pelatihan Model**
   - Optimizer: Adam
   - Loss: Categorical Crossentropy
   - Evaluasi selama pelatihan dengan metrik akurasi

6. **Evaluasi Model**
   - Confusion matrix
   - Classification report
   - Visualisasi prediksi dan kurva akurasi/loss

7. **Penyimpanan Model**
   - Model terbaik disimpan dalam format `.keras` di folder `/models`
