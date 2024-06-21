# FINAL PROJECT TKA

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
![uji endpoint](https://github.com/Satsujinki99/FP_TKA-C4/assets/151041878/443e26a7-efea-4448-8628-b4cd676c3ccc)

Kemudian juga disediakan sebuah Frontend sederhana menggunakan `index.html` dan `styles.css` dengan tampilan antarmuka sebagai berikut

<img width="1710" alt="image" src=https://github.com/Satsujinki99/FP_TKA-C4/assets/150534107/d0dfde10-b3a6-4ff0-b0d6-108c1fd783d2>
Kemudian anda diminta untuk mendesain arsitektur cloud yang sesuai dengan kebutuhan aplikasi tersebut. Apabila dana maksimal yang diberikan adalah 1 juta rupiah per bulan (65 US$) konfigurasi cloud terbaik seperti apa yang bisa dibuat?

## Rancangan Arsitektur
![image](https://github.com/Satsujinki99/FP_TKA-C4/assets/122516105/2ac40946-80a8-4065-b5b2-0e06cc6ef89d)

Pada rancangan arsitektur cloud kami, kami menggunakan 2 vm worker, 1 load balancer dan 1 database Server MongoDB sesuai gambar diatas.  
## Langkah Implementasi dan Konfigurasi Teknologi
1. Buat database dan copy connection stringn
   ![IMG-20240621-WA0027](https://github.com/Satsujinki99/FP_TKA-C4/assets/151041878/2f0762c0-bd56-43ee-938e-19c96a63a113)
3. Buat database sesuai dengan variabel yang sudah dibuat di dalam app.py
4. Create database baru dengan collection order, add data (import json file)lalu pilih file orders.json yang berisi data-data yang akan dimasukan ke database
5. Run app.py hingga muncul url-nya
6. Untuk mengecek database-nya bisa menggunakan postman, request ke url/orders. Jika statusnya sudah 200 ok, maka database sudah bisa berjalan dengan normal
7. Deploy VM untuk worker dengan installasi requirement yang diperlukan di worker
8. Buat Load Balancer dan pilih droplet worker yang sudah dibuat sebelumnya
9. Jika tidak ada error, maka selanjutnya bisa dilakukan load tetsting locust
   
## Hasil Pengujian Setiap Endpoint
1. Get All Orders
2. Get a Specific Orders by ID
3. Create a New Order
4. Update an Order by ID
5. Delete an Order by ID

## Hasil Pengujian dan Analisis Loadtesting Locust
- RPS Maksimum (load testing 60 detik)
  ![IMG-20240621-WA0026](https://github.com/Satsujinki99/FP_TKA-C4/assets/151041878/d832470c-b28d-4560-9161-09ebe22086ca)
- Peak Concurrency Maksimum (spawn rate 25, load testing 60 detik)
- Peak Concurrency Maksimum (spawn rate 50, load testing 60 detik)
- Peak Concurrency Maksimum (spawn rate 100, load testing 60 detik)
## Kesimpulan dan Saran
