### Bintang Darmawan | 09030282327017 | Jaringan Komputer | TK - 4C

Setelah menonton YouTube selama 10 menit, saya mendapatkan statistik dibawah :

![image](https://github.com/user-attachments/assets/752bc36d-e686-4030-9b2e-5bcf5943e795)

### 1. Throughput
Jumlah data yang berhasil dikirim melalui jaringan dalam jangka waktu tertentu disebut 
Throughput. Semakin tinggi throughput, semakin cepat dan efisien jaringan mengirimkan 
data. Kecepatan (rate) transfer data efektif dikenal sebagai throughput, yang diukur dalam bps (bit per second).

![image](https://github.com/user-attachments/assets/55a20bd0-c90c-4fc7-a7f7-38b718410b09)

**Throughput (Byte) = bytes / timespan**

a. 72723753 / 650.711 = **111760.448 Bps**

**Throughput (Bit) = Throughput (Byte) * 8**

a. 111760.448 * 8 = **894083.584 bps**

**Kbps**

a. 894083.584 / 1000 = **894.083584 kbps** 

### 2. Packet Loss

Untuk mencari Packet Loss, kita menggunakan filter `tcp.analysis.lost_segment` untuk melihat packet data terkirim dan packet data diterima.

![image](https://github.com/user-attachments/assets/b53011a7-8284-41b7-9102-636e08744447)

**Packet Loss**

**((packet data dikirim -  packet data diterima) / packet data dikirim) * 100** 

((73673 - 73610) / 73673) * 100 = **0.085 % / 0.1 %**
