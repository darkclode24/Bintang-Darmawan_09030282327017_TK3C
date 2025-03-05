### Bintang Darmawan | 09030282327017 | Jaringan Komputer | TK-4C 

Prerequisites : Ubuntu Desktop, Ubuntu Server
→
### 1. Install Versi OpenSSH yang benar pada masing - masing Ubuntu

Sebelum installasi, ada baiknya menggunakan `sudo apt update` untuk memperbarui package list Ubuntu

a. Untuk Ubuntu Desktop, kita menginstall openssh-client

<img src="https://github.com/user-attachments/assets/e37501f3-b42b-4032-9b2f-6f71c4169af3" width="700" height="300">

b. Untuk Ubuntu Server, kita menginstall openssh-server

![image](https://github.com/user-attachments/assets/d447657a-2534-4285-8c2b-d41d5ef32b58)

### 2. Konfigurasi SSH

a. Pada Ubuntu Server

pastikan `ssh` berjalan dengan `sudo systemctl start ssh` dan `sudo systemctl enable ssh`. 


![image](https://github.com/user-attachments/assets/2bc81795-99f9-4ab6-ab8a-8949b88f2a94)

Konfigurasi firewall menggunakan UFW untuk mengizinkan koneksi SSH dengan `sudo ufw allow ssh`

![image](https://github.com/user-attachments/assets/de2a9342-2acc-4f4a-8876-25fb23f8d1ef)

Tampilkan IP Address server untuk digunakan pada SSH

![image](https://github.com/user-attachments/assets/b73e451a-540c-4119-ad87-620ceddd0946)

b. Pada Ubuntu Desktop

Sambungkan Desktop ke Server menggunakan `ssh [username-server]@[ip-server]`

![image](https://github.com/user-attachments/assets/661edadb-ff7b-4782-9c92-7d0bf3e7c595)

### 3. Test Konektivitas

Untuk menguji koneksi SSH, kita akan membuat file pada Server dan menampilkannya dari Desktop.

a. Pada Ubuntu Server

Buat file dan isinya menggunakan `nano` dengan tipe file .sh

![image](https://github.com/user-attachments/assets/5b237c99-0331-4951-894e-6898c7909e34)

Jadikan file tersebut **Executable** menggunakan `chmod +x [nama-file]`

![image](https://github.com/user-attachments/assets/408e64c2-71cb-4688-8be7-9f2d04ce7137)

b. Pada Ubuntu Desktop

Pada terminal, jalankan script file yang telah dibuat

![image](https://github.com/user-attachments/assets/dd2507d8-7395-4593-b7fe-76bed838127d)
