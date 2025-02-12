### Bintang Darmawan | 09030282327017 | Jaringan Komputer | TK - 4C

Setelah menonton YouTube selama 10 menit, saya mendapatkan statistik dibawah :

![image](https://github.com/user-attachments/assets/752bc36d-e686-4030-9b2e-5bcf5943e795)

### 1. Throughput
Jumlah data yang berhasil dikirim melalui jaringan dalam jangka waktu tertentu disebut 
Throughput. Semakin tinggi throughput, semakin cepat dan efisien jaringan mengirimkan 
data. Kecepatan (rate) transfer data efektif dikenal sebagai throughput, yang diukur dalam bps (bit per second).

![image](https://github.com/user-attachments/assets/55a20bd0-c90c-4fc7-a7f7-38b718410b09)

**Throughput (Byte) = bytes / timespan**

a. 72723753 / 650.711 = **111760.448 bps**

**Throughput (Bit) = Throughput (Byte) * 8**

a. 111760.448 * 8 = **894083.584 Bps**

**Kbps**

a. 894083.584 / 1000 = **894.083584 kbps** 

### 2. Packet Loss
Packet loss terjadi ketika paket data yang dikirim melalui jaringan hilang atau tidak 
sampai ke tujuan. Ini dapat terjadi karena gangguan sinyal atau masalah teknis lainnya, tetapi 
kehilangan paket data dapat mengurangi kualitas layanan, terutama untuk aplikasi seperti 
streaming video dan panggilan suara. 

Untuk mencari Packet Loss, kita menggunakan filter `tcp.analysis.lost_segment` untuk melihat packet data terkirim dan packet data diterima.

![image](https://github.com/user-attachments/assets/b53011a7-8284-41b7-9102-636e08744447)

**Packet Loss**

**((packet data dikirim -  packet data diterima) / packet data dikirim) * 100** 

((73673 - 73610) / 73673) * 100 = **0.085 % / 0.1 %**


Untuk menentukan Delay dan Jitter, kita harus melakukan perhitungan didalam Excel.

![image](https://github.com/user-attachments/assets/0e77a17a-d076-4745-9951-b00b962bf430)

Filter data ke `tcp`, dan export data menjadi bentuk .csv

![image](https://github.com/user-attachments/assets/0293d1f6-334e-4099-8a15-c777ef1b3b29)

Susun data dengan menyetting delimiter sebagai tanda koma (,)

![image](https://github.com/user-attachments/assets/557cf588-a94d-48a6-bb6c-b3e6df4aa701)

Hapus semua Column kecuali `No.` dan `Time`

![image](https://github.com/user-attachments/assets/89aec062-c688-4cf5-bc4a-92cee6f613d6)

Untuk time diatas 1 (ex. 1.xxx.xxx) dibagi 1000000


### 3. Delay / Latensi

Delay adalah lamanya waktu yang dibutuhkan sebuah paket data untuk bergerak dari 
sumber ke tujuan. Latensi tinggi dapat mengganggu komunikasi dan pengalaman pengguna, 
terutama dalam aplikasi real-time seperti video call. 


![image](https://github.com/user-attachments/assets/4559e11b-1fd7-4a1b-aca9-3c45303914b6)

Membuat Column baru `time 1` dan `time 2` 

yang dimana time 1: time dari **No. 1 dst.**

dan time 2 : time dari **No. 2 dst.**

![image](https://github.com/user-attachments/assets/58f60d2b-2535-48fd-820d-4cfe98985598)

Membuat Column `delay` dengan rumus `time2 - time1`

![image](https://github.com/user-attachments/assets/1e9e1844-0219-4a7b-ba68-9d9a2f05cadd)

Total delay adalah `SUM` dari Column `delay`, yaitu **649,995513 s / 650 s**

Rata - Rata Delay adalah `Total delay / total packet diterima`, yaitu **8,836 ms**

### 4. Jitter

Jitter adalah ukuran variasi waktu tunggu antara paket data. Jitter tinggi dapat 
menyebabkan aliran data tidak teratur, yang dapat mengganggu kualitas suara dan video 
selama komunikasi real-time. 

![image](https://github.com/user-attachments/assets/5bcb71bb-5302-4fc8-b3c2-4107ce5d8436)

Membuat column `delay1`, `delay2`dan `jitter` yang dimana :

`delay1`: baris pertama - baris selanjutnya pada Column `delay` (ex. G2-G3, G3-G4, G4-G5, dst..)

`delay2`: nilai baris kedua dst. pada `delay`

`jitter`: nilai `delay2 - delay1`


![image](https://github.com/user-attachments/assets/955e9652-778c-42f5-ae39-a315944825dc)


Total jitter adalah `SUM` dari Column `jitter`, yaitu **650,073 s**

Rata - Rata Delay adalah `Total delay / total packet diterima`, yaitu **8,837 ms**

Setelah pengukuran, Throughput, Packet Loss, Delay, dan Jitter yang didapatkan dapat kategorikan sesuai nilainya

![image](https://github.com/user-attachments/assets/175e195a-b694-43cd-9cde-67fa0e74f4c6)

Setelah mendapatkan hasil perhitungan Throughput, Packet Loss, Delay, dan Jitter. Selanjutnya kita dapat mengisi tabel indeks yang didapatkan dari pengukuran Quality of Service (QoS)

![image](https://github.com/user-attachments/assets/67b9bb68-9aa6-4d4d-9c2f-b7c4d0797e95)
