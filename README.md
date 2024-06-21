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

## Rancangan Arsitektur
![image](https://github.com/Satsujinki99/FP_TKA-C4/assets/122516105/2ac40946-80a8-4065-b5b2-0e06cc6ef89d)

![image](https://github.com/Satsujinki99/FP_TKA-C4/assets/122516105/f71ae97e-f4f0-4a93-b97d-2e9502622e60)

Pada rancangan arsitektur cloud kami, kami menggunakan 2 vm worker, 1 load balancer dan 1 database Server MongoDB sesuai gambar diatas.  

## Endpoints:
![uji endpoint](https://github.com/Satsujinki99/FP_TKA-C4/assets/151041878/443e26a7-efea-4448-8628-b4cd676c3ccc)

<img width="1710" alt="image" src=https://github.com/Satsujinki99/FP_TKA-C4/assets/150534107/d0dfde10-b3a6-4ff0-b0d6-108c1fd783d2>

## Rancangan Arsitektur
![image](https://github.com/Satsujinki99/FP_TKA-C4/assets/122516105/2ac40946-80a8-4065-b5b2-0e06cc6ef89d)

![image](https://github.com/Satsujinki99/FP_TKA-C4/assets/122516105/f71ae97e-f4f0-4a93-b97d-2e9502622e60)

Pada rancangan arsitektur cloud kami, kami menggunakan 2 vm worker, 1 load balancer dan 1 database Server MongoDB sesuai gambar diatas.  



## Hasil Pengujian dan Analisis Loadtesting Locust
- RPS Maksimum (load testing 60 detik)
  ![IMG-20240621-WA0026](https://github.com/Satsujinki99/FP_TKA-C4/assets/151041878/d832470c-b28d-4560-9161-09ebe22086ca)
- Peak Concurrency Maksimum (spawn rate 25, load testing 60 detik)
- Peak Concurrency Maksimum (spawn rate 50, load testing 60 detik)
- Peak Concurrency Maksimum (spawn rate 100, load testing 60 detik)
## Kesimpulan dan Saran
