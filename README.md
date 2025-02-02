# AI-FRAUD-Detection-System BY @shrl.py

Sistem Machine Learning ini dirancang khusus untuk membantu pekerjaan audit

# Tutorial Penggunaan AI Deteksi Fraud Transaksi Keuangan

Kode ini digunakan untuk mendeteksi transaksi keuangan yang bersifat fraud (penipuan) menggunakan algoritma *Random Forest*. Berikut tutorial penggunaannya:

**1. Persiapan Lingkungan:**

* Pastikan Anda telah menginstal library yang dibutuhkan. Jalankan sel kode pertama yang memuat perintah `!pip install prettytable`. Jika library lain belum terinstal, tambahkan perintah instalasi di sel yang sama. 
* Siapkan dua file CSV: `financial_transactions.csv` (data training) dan `new_transactions.csv` (data baru yang akan diprediksi). Pastikan kedua file tersebut berada di direktori yang sama dengan notebook ini atau tentukan path yang benar.


**2.  Data Training (`financial_transactions.csv`):**

File ini berisi data historis transaksi keuangan yang telah diberi label `is_fraud` (1 untuk transaksi fraud dan 0 untuk non-fraud). Kolom yang diperlukan minimal meliputi:

* `amount`: Jumlah transaksi.
* `transaction_type`: Jenis transaksi.
* `customer_id`: ID pelanggan.
* `transaction_time`: Waktu transaksi dalam format yang dikenali pandas (misal: YYYY-MM-DD HH:MM:SS).
* `is_fraud`: Label untuk menunjukkan apakah transaksi merupakan fraud atau tidak (0 atau 1).

Kolom lain yang relevan dapat ditambahkan sesuai dengan kebutuhan. 

**3. Data Baru (`new_transactions.csv`):**

File ini berisi data transaksi baru yang akan diprediksi sebagai fraud atau bukan. Format kolom harus sama dengan data training, kecuali kolom `is_fraud` yang akan diprediksi oleh model.


**4. Eksekusi Kode:**

Jalankan seluruh sel kode secara berurutan. Kode akan melakukan langkah-langkah berikut:

* **Membaca Data:** Membaca data training dan data baru dari file CSV.
* **Prapemrosesan Data:**
    * Mengisi nilai yang hilang (missing values) dengan metode *forward fill*.
    * Mengubah variabel kategorikal (misalnya, `transaction_type`) menjadi numerik menggunakan *Label Encoding*.
    * Ekstrak fitur tanggal dan waktu dari kolom `transaction_time`.
* **Membagi Data:** Membagi data training menjadi data latih dan data uji.
* **Melatih Model:** Melatih model *Random Forest* menggunakan data latih.
* **Evaluasi Model:** Mengevaluasi performa model menggunakan berbagai metrik (akurasi, presisi, recall, F1-score, ROC AUC) dan matriks konfusi. Hasil evaluasi akan ditampilkan dalam bentuk tabel.
* **Prediksi Transaksi Baru:** Menerapkan model pada data transaksi baru dan memprediksi label `is_fraud` serta probabilitas terjadinya fraud. Hasil prediksi ditampilkan dan disimpan dalam file `predicted_fraud_transactions.csv`.

**5. Output:**

* Hasil evaluasi model (akurasi, presisi, recall, F1-score, ROC AUC, dan matriks konfusi) akan dicetak ke konsol.
* Data transaksi baru beserta prediksi `is_fraud` dan probabilitasnya akan dicetak ke konsol dan disimpan dalam file `predicted_fraud_transactions.csv`.


**Catatan:**

* Anda dapat menyesuaikan parameter model *Random Forest* (misalnya, `n_estimators`) untuk meningkatkan kinerja model.
* Pastikan file CSV Anda memiliki format yang sesuai dengan yang diharapkan kode.
* Ganti nama file jika diperlukan.


**Contoh Penggunaan:**

Anda dapat mengganti `financial_transactions.csv` dan `new_transactions.csv` dengan nama file CSV Anda yang sebenarnya.  Setelah menjalankan kode, hasil prediksi akan disimpan di file `predicted_fraud_transactions.csv`.  Anda dapat membuka file tersebut untuk melihat transaksi baru beserta prediksi fraudnya.
