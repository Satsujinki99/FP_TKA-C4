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


## Rancangan Arsitektur
## Langkah Implementasi dan Konfigurasi Teknologi
1. Buat database dan copy connection stringn
   ![IMG-20240621-WA0027](https://github.com/Satsujinki99/FP_TKA-C4/assets/151041878/2f0762c0-bd56-43ee-938e-19c96a63a113)
2.Create new connection dengan string database yan
g sudah di-copy sebelumnya
4. Buat database sesuai dengan variabel yang sudah dibuat di dalam app.py
5. Create database baru dengan collection order, add data (import json file)lalu pilih file orders.json yang berisi data-data yang akan dimasukan ke database
6. Run app.py hingga muncul url-nya
7. Untuk mengecek database-nya bisa menggunakan postman, request ke url/orders. Jika statusnya sudah 200 ok, maka database sudah bisa berjalan dengan normal
8. Deploy VM untuk worker dengan installasi requirement yang diperlukan di worker
9. Buat Load Balancer dan pilih droplet worker yang sudah dibuat sebelumnya
10. Jika tidak ada error, maka selanjutnya bisa dilakukan load tetsting locust
   
## Hasil Pengujian Setiap Endpoint
1. Get All Orders
2. Get a Specific Orders by ID
3. Create a New Order
4. Update an Order by ID
5. Delete an Order by ID

## Hasil Pengujian dan Analisis Loadtesting Locust
- RPS Maksimum (load testing 60 detik)
- Peak Concurrency Maksimum (spawn rate 25, load testing 60 detik)
- Peak Concurrency Maksimum (spawn rate 50, load testing 60 detik)
- Peak Concurrency Maksimum (spawn rate 100, load testing 60 detik)
## Kesimpulan dan Saran
