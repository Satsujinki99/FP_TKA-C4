# FINAL PROJECT TEKNOLOGI KOMPUTASI AWAN

*KELOMPOK C4*
| Nama | NRP |
|---------------------------|------------|
|Muhamad Arrayyan | 5027231014 |
|Naufal Syafi' Hakim | 5027231022 |
|Furqon Aryadana | 5027231024 |
|RM Novian Malcolm B. | 5027231035 |
|Dzaky Faiq Fayyadhi | 5027231047 |

Video Demo: 

## I.) Introduction Permasalahan 
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

## II.) Rancangan Arsitektur 
#### 1. Gambar Rancangan Harga 
![Screenshot 2024-06-28 193653](https://github.com/Satsujinki99/FP_TKA-C4/assets/146155753/d6cbc9b7-2497-40b2-97e3-0a49b46da5cd)
#### 2. Gambar Rancangan Arsiteknya
![Screenshot 2024-06-28 193709](https://github.com/Satsujinki99/FP_TKA-C4/assets/146155753/45bcc125-173e-48c1-86c5-fcd5fd4f0020)

Setelah memikirkan harga dan spesifikasinya, kami akhirnya memutuskan untuk menggunakan Digital Ocean sebagai lingkungan cloud kami. Keputusan ini dibuat karena lingkungan cloud ini paling mudah digunakan dan menawarkan kredit gratis jika Anda memiliki pendidikan github. Dari semua penyedia cloud, kami percaya bahwa Digital Ocean adalah yang paling mudah dipahami. Pada rancangan arsitektur cloud kami, kami menggunakan 3 virtual machine yang berperan sebagai berikut: 1 vmWorker untuk Frontend & Backend, 1 vmWorker untuk Backend dan 1 vm untuk Load Balancer, kami juga menggunakan sebuah Database Server MongoDB sesuai rincian gambar diatas.

#### 3. Gambar tiap Droplets yang digunakan
<img width="1710" alt="image" src=https://github.com/Satsujinki99/FP_TKA-C4/assets/150534107/b5d9cd32-21e0-445e-b3c7-b0a531a66106>

#### 4. Gambar menu Database MongoDb
<img width="1710" alt="image" src=https://github.com/Satsujinki99/FP_TKA-C4/assets/150534107/51e3a475-2843-4d07-b7ad-5bbfe106ac4a>


## III.) Langkah-langkah Implementasi dan Konfigurasi

| No | Langkah-langkah (Backend) |
| --- | --- |
| 1 | `sudo apt update`  |
| 2 | `cd fp-tka/` |
| 3 | `cd Resources/` |
| 4 | `cd BE/` |
| 5 | `python3 -m venv venv` |
| 6 | `sudo apt install python3.12-venv` |
| 7 | `source venv/bin/activate` |
| 8 | `pip install flask flask_cors pymongo textblob` |
| 9 | `pip install flask flask_cors pymongo textblob` |

<details>

<summary>Dokumentasi</summary>

### Terminal

You can add text within a collapsed section. 

You can add an image or a code block, too.

```ruby
   puts "Hello World"
```

</details>

| No | Langkah-langkah (Frontend) |
| --- | --- |
| 1 | `cd fp-tka/`  |
| 2 | `cd Resources/` |
| 3 | `cd FE/` |
| 4 | `sudo apt install nginx` |
| 5 | `cp index.html /var/www/html` |
| 6 | `cp styles.css /var/www/html` |
| 7 | `cd /etc/nginx ` |
| 8 | `cd sites-available/ ` |
| 9 | `sudo nano app ` |
| 10 | `sudo unlink /etc/nginx/sites-enabled/default `  |
| 11 | `sudo ln -s /etc/nginx/sites-available/app /etc/nginx/sites-enabled` |
| 12 | `sudo nginx -t ` |
| 13 | `sudo systemctl restart nginx` |
| 14 | `cd /var/www/html` |
| 15 | `sudo nano index.html ` |
| 16 | `sudo systemctl restart nginx ` |

<details>

<summary>Dokumentasi</summary>

### Implementasi

config app: 

```ruby
   server {
	listen 80;
	listen [::]:80;

	server_name 152.42.237.183;

	root /var/www/html;
	index index.html;

	location / {
		try_files $uri $uri/ =404;
	}
} 
```

</details>

| No | Langkah-langkah buat load balancer dari VM |
| --- | --- |
| 1 | `sudo apt install nginx `  |
| 2 | `sudo nano /etc/nginx/sites-available/default` |
| 3 | `sudo nginx -t` |
| 4 | `sudo systemctl restart nginx ` |
| 5 | `python3 -m venv venv` |
| 6 | `sudo apt install python3.12-venv` |
| 7 | `source venv/bin/activate` |
| 8 | `pip install flask flask_cors pymongo textblob` |
| 9 | `pip install flask flask_cors pymongo textblob` |

<details>

<summary>Dokumentasi</summary>

### Konfigurasi

```ruby
   konfig /etc/nginx/sites-available/default: 
upstream backend {
    server 152.42.237.183:5000;
    server 178.128.122.205:5000;
}
server {
    listen 80;

    location / {
        proxy_pass http://backend;
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header X-Forwarded-Proto $scheme;
    }
}
```

</details>

## IV.) Hasil Pengujian Setiap Endpoint
### Pengujian dengan Hoppscotch
<img width="1710" alt="image" src=https://github.com/Satsujinki99/FP_TKA-C4/assets/150534107/8a2ba3bf-cb7d-490f-862a-8e8f95b5f5ac>

<img width="1710" alt="image" src=https://github.com/Satsujinki99/FP_TKA-C4/assets/150534107/2ecc6752-f328-40c9-acd0-174ff5bbae41>

### Pengujian dari web
<img width="1710" alt="image" src=https://github.com/Satsujinki99/FP_TKA-C4/assets/150534107/0b5a0b12-d861-41b0-b7d6-e1c41c208164>
Disini terlihat setelah ip diuji dari web, website berjalan dengan baik sesuai yang diharapkan 

## V.) Hasil Pengujian dan Analisis Loadtesting Locust
- Peak Concurrency Maksimum (spawn rate 50, load testing 60 detik)
  <img width="1710" alt="image" src=https://github.com/Satsujinki99/FP_TKA-C4/assets/150534107/5ae17505-5d76-411a-818a-f55f1c3c3e92>
   Locust menunjukkan Peak Concurrency sekitar 200 dengan RPS rata-rata 63,4 dengan failure 0%
- Peak Concurrency Maksimum (spawn rate 100, load testing 60 detik)
  <img width="1710" alt="image" src=https://github.com/Satsujinki99/FP_TKA-C4/assets/150534107/ea27f928-152c-4fb7-b89c-b34328653ff2>
   Locust menunjukkan Peak Concurrency sebesar 253,5 dengan RPS rata-rata 71,1 dengan failure 0%
- Peak Concurrency Maksimum (spawn rate 200, load testing 60 detik)
  <img width="1710" alt="image" src=https://github.com/Satsujinki99/FP_TKA-C4/assets/150534107/8e2ad6e5-63cf-4e7b-8506-a97e7cc3eaed>
   Locust menunjukkan Peak Concurrency sebesar 387,25 dengan RPS rata-rata 67,7 dengan failure 0%
- Peak Concurrency Maksimum (spawn rate 500, load testing 60 detik)
  <img width="1710" alt="image" src=https://github.com/Satsujinki99/FP_TKA-C4/assets/150534107/f5d892f0-948b-496d-9c33-89bd7987fe8b>
  Locust menunjukkan Peak Concurrency sebesar 341 dengan RPS rata-rata 72,5 dengan failure 0%
-----
- RPS Tertinggi (spawn rate 500, load testing 60 detik)
  <img width="1710" alt="image" src=https://github.com/Satsujinki99/FP_TKA-C4/assets/150534107/f5d892f0-948b-496d-9c33-89bd7987fe8b>
  RPS tertinggi terjadi pada spawn rate 500 dengan RPS rata-rata 72,5 dan Peak Concurrency sebesar 341  
## VI.) Kesimpulan dan Saran
#### 1. Response Rate tiap detik pada pengujian locust tergantung pula pada jumlah data pada database MongoDb
Ketika melakukan pengujian pastikan Anda menghapus database yang sudah ada, agar hasil pengujian bisa maksimal. Sebelumnya kami menguji locust tanpa melakukan penghapusan database terlebih dahulu dan ketika dicek data yang ada pada database kita sudah terlalu banyak sehingga mengganggu kinerja pada Virtual Machine dan Database yang menyebabkan pengujian pada locust tidak maksimal 
![WhatsApp Image 2024-06-28 at 20 25 50_7c508c80](https://github.com/Satsujinki99/FP_TKA-C4/assets/146155753/c24b1364-9ef8-48c2-9008-60447516e289)

#### 2. Disarankan menggunakan virtual machine dengan spesifikasi yang tinggi
Semakin tinggi spesifikasi virtual machine yang digunakan maka semakin tinggi pula kemampuannya dalam menangani data yang banyak
