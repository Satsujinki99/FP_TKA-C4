# FINAL PROJECT TEKNOLOGI KOMPUTASI AWAN

*KELOMPOK C4*
| Nama | NRP |
|---------------------------|------------|
|Muhamad Arrayyan | 5027231014 |
|Naufal Syafi'i Hakim | 5027231022 |
|Furqon Aryadana | 5027231024 |
|RM Novian Malcolm B. | 5027231035 |
|Dzaky Faiq Fayyadhi | 5027231047 |

## Permasalahan 
Anda adalah seorang lulusan Teknologi Informasi, sebagai ahli IT, salah satu kemampuan yang harus dimiliki adalah Keampuan merancang, membangun, mengelola aplikasi berbasis komputer menggunakan layanan awan untuk memenuhi kebutuhan organisasi.

Pada suatu saat anda mendapatkan project untuk mendeploy sebuah aplikasi Sentiment Analysis dengan komponen Backend menggunakan python: sentiment-analysis.py dengan spesifikasi sebagai berikut

## Endpoints:

#### 1. Analyze Text
  - Endpoint: `POST /analyze`
  - Description: This endpoint accepts a text input and returns the sentiment score of the text.
  - Request:
    <img width="1710" alt="image" src=https://github.com/Satsujinki99/FP_TKA-C4/assets/150534107/ff0cc87c-c389-4845-8a67-0260fde9f7b3>
  - Request:
    <img width="1710" alt="image" src=https://github.com/Satsujinki99/FP_TKA-C4/assets/150534107/1dc14f3e-4b26-4d31-8527-3c675e2df980>

#### 2. Retrieve History
  - Endpoint: `GET /history`
  - Description: This endpoint retrieves the history of previously analyzed texts along with their sentiment scores.
  - Request:
    <img width="1710" alt="image" src=https://github.com/Satsujinki99/FP_TKA-C4/assets/150534107/3483d9c4-e835-4433-a89b-e3e36341bf67>
----
Kemudian juga disediakan sebuah Frontend sederhana menggunakan index.html dan styles.css dengan tampilan antarmuka sebagai berikut

<img width="1710" alt="image" src=https://github.com/Satsujinki99/FP_TKA-C4/assets/150534107/9f51dc0a-41a7-4142-89ed-0c43663fb430>
Kemudian anda diminta untuk mendesain arsitektur cloud yang sesuai dengan kebutuhan aplikasi tersebut. Apabila dana maksimal yang diberikan adalah 1 juta rupiah per bulan (65 US$) konfigurasi cloud terbaik seperti apa yang bisa dibuat?

-----

## Rancangan Arsitektur
<img width="1710" alt="image" src=https://github.com/Satsujinki99/FP_TKA-C4/assets/122516105/2ac40946-80a8-4065-b5b2-0e06cc6ef89d>

<img width="1710" alt="image" src=https://github.com/Satsujinki99/FP_TKA-C4/assets/122516105/f71ae97e-f4f0-4a93-b97d-2e9502622e60>

## INI DIPERBAIKI KALIMAT NYA KARENA ADA PERUBAHAN DI ARISTEKTURNYA
Setelah memikirkan harga dan spesifikasinya, kami akhirnya memutuskan untuk menggunakan Digital Ocean sebagai lingkungan cloud kami. Keputusan ini dibuat karena lingkungan cloud ini paling mudah digunakan dan menawarkan kredit gratis jika Anda memiliki pendidikan github. Dari semua penyedia cloud, kami percaya bahwa Digital Ocean adalah yang paling mudah dipahami. Pada rancangan arsitektur cloud kami, kami menggunakan 3 vm worker, 1 Frontend & Database, 1 Load Balancer dan 1 Database Server MongoDB sesuai gambar diatas.

<img width="1710" alt="image" src=https://github.com/Satsujinki99/FP_TKA-C4/assets/150534107/b5d9cd32-21e0-445e-b3c7-b0a531a66106>

<img width="1710" alt="image" src=https://github.com/Satsujinki99/FP_TKA-C4/assets/150534107/f1110b82-6b2c-4dd2-bc40-80b870013653>


## Hasil Pengujian Setiap Endpoint
### Pengujian dengan Hoppscotch
<img width="1710" alt="image" src=https://github.com/Satsujinki99/FP_TKA-C4/assets/150534107/8a2ba3bf-cb7d-490f-862a-8e8f95b5f5ac>

### Pengujian dari web
<img width="1710" alt="image" src=https://github.com/Satsujinki99/FP_TKA-C4/assets/150534107/0b5a0b12-d861-41b0-b7d6-e1c41c208164>

## Hasil Pengujian dan Analisis Loadtesting Locust
- Peak Concurrency Maksimum (spawn rate 50, load testing 60 detik)
  <img width="1710" alt="image" src=https://github.com/Satsujinki99/FP_TKA-C4/assets/150534107/5ae17505-5d76-411a-818a-f55f1c3c3e92>
- Peak Concurrency Maksimum (spawn rate 100, load testing 60 detik)
  <img width="1710" alt="image" src=https://github.com/Satsujinki99/FP_TKA-C4/assets/150534107/ea27f928-152c-4fb7-b89c-b34328653ff2>
- Peak Concurrency Maksimum (spawn rate 200, load testing 60 detik)
  <img width="1710" alt="image" src=https://github.com/Satsujinki99/FP_TKA-C4/assets/150534107/8e2ad6e5-63cf-4e7b-8506-a97e7cc3eaed>
- Peak Concurrency Maksimum (spawn rate 500, load testing 60 detik)
  <img width="1710" alt="image" src=https://github.com/Satsujinki99/FP_TKA-C4/assets/150534107/f5d892f0-948b-496d-9c33-89bd7987fe8b>
  
## Kesimpulan dan Saran

