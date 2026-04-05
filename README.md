# 🍫 Klasifikasi Kematangan dan Kesehatan Buah Kakao (Computer Vision)

Proyek ini merupakan implementasi **Pengolahan Citra Digital (Computer Vision)** untuk mengotomatisasi proses penyortiran pascapanen buah kakao secara objektif. Sistem ini menggunakan metode ekstraksi fitur **Warna (HSV)** dan **Tekstur (GLCM)** untuk mengidentifikasi tingkat kematangan serta mendeteksi adanya penyakit busuk buah.

## 🔗 Tautan Penting
- **Google Colab:** [Klik di sini untuk melihat dan menjalankan kode secara langsung](https://colab.research.google.com/drive/1noTarOkAlQtwrhgTXKsF-z1A9f0ZE5cE?usp=sharing)
- **Dataset (Google Drive):** [Lihat atau unduh dataset citra kakao di sini](https://drive.google.com/drive/folders/1CuXs27TuWqO2TGjYVsTJu4kuM5IDWIM6?usp=sharing)

## 🎯 Kategori Klasifikasi
Sistem secara otomatis akan melabeli citra buah kakao ke dalam 4 kelas spesifik:
1. **Sehat (Matang) 🟡:** Permukaan kulit mulus, warna dominan kuning/oranye.
2. **Sehat (Mengkal) 🟢:** Permukaan kulit mulus, warna dominan hijau/kuning kehijauan.
3. **Infeksi Ringan 🟤:** Terdapat indikasi luka atau bercak cokelat dalam skala kecil.
4. **Infeksi Parah ⚫:** Terdapat luka busuk atau bercak hitam penyakit yang luas dan kasar.

## ⚙️ Highlight Teknis & Cara Kerja
- **Preprocessing:** Dimensi seluruh citra dataset diseragamkan menjadi `300x300 piksel` untuk menjaga konsistensi komputasi matriks.
- **Ekstraksi Tekstur (GLCM):** Menggunakan parameter **Contrast** pada citra *grayscale* untuk mendeteksi anomali tekstur dan tingkat kekasaran kulit akibat infeksi.
- **Ekstraksi Warna (HSV):** Menggunakan parameter rata-rata **Hue** dan **Saturation** untuk membedakan tingkat kematangan berdasarkan rentang rona warna.
- **Algoritma Rule-Based:** Logika klasifikasi dibangun secara bertingkat—memprioritaskan evaluasi kerusakan kulit terlebih dahulu sebelum menilai warna. Pendekatan ini terbukti tangguh untuk menangani "kasus bias", seperti buah yang terinfeksi namun masih memiliki tekstur yang relatif halus.

## 🛠️ Teknologi & Library yang Digunakan
- **Python 3.x**
- **OpenCV** `cv2`: Pemrosesan citra dasar dan konversi ruang warna (BGR ke HSV/Grayscale).
- **Scikit-Image** `skimage`: Perhitungan matriks GLCM untuk ekstraksi fitur tekstur.
- **NumPy** `numpy`: Komputasi operasi *array* dan matriks matematika.
- **Pandas** `pandas`: Pengelolaan *dataframe* dan ekspor hasil klasifikasi.
- **Matplotlib** `matplotlib`: Visualisasi galeri dataset citra.

## 📂 Output Program
Skrip akan memproses seluruh gambar di dalam direktori secara berurutan (*looping*), mengekstrak nilai numerik piksel, dan menyimpan hasil akhirnya berupa *dataframe* ke dalam format file Excel (`.xlsx`) lengkap dengan hasil klasifikasinya.
