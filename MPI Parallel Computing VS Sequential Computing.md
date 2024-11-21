# Bintang Darmawan, 09030282327017, TK3C

Disini saya akan mencoba membandingkan parallel computing menggunakan MPI dengan 1 master dan 2 slave, dengan sequential computing.


# MPI Parallel Computing

## 1 . Membuat Master dan Slave VM Ubuntu pada VirtualBox

<img width="960" alt="image" src="https://github.com/user-attachments/assets/10140c92-87a7-400e-99ef-6417f15fec3f">

Saya membuat 3 VM Ubuntu, yaitu Master, Slave1, dan Slave2.
Untuk konfigurasi masing - masing VM kita menggunakan 4GB Memory, 4 Processor, dan Storage 25GB.
Disini saya menggunakan Bridged Adapter pada masing - masing VM agar setiap VM dapat berkomunikasi satu sama lain melalui jaringan lokal yang sama, memungkinkan proses MPI untuk bertukar pesan dengan efisien. Ini sangat penting untuk komunikasi antara master dan slave dalam pengolahan data paralel.

Saya juga menginstall Guest Additions pada tiap VM Ubuntu untuk mempermudah proses pada tahap selanjutnya 
![image](https://github.com/user-attachments/assets/216ad7e9-d2a0-415d-966b-68d55cc5f433)
![image](https://github.com/user-attachments/assets/0fa2dc66-cdab-4641-8bca-c4288ecd3464)

## 2. Menginstall OpenMPI pada masing-masing VM Ubuntu

<img width="487" alt="image" src="https://github.com/user-attachments/assets/102e012b-54e6-46fc-b486-3547ac913003">

Untuk MPI, saya menggunakan OpenMPI pada setiap VM.

<img width="386" alt="image" src="https://github.com/user-attachments/assets/726fe410-e063-46e7-8809-97c0b22aeb6d">

Memastikan penginstallan berhasil.

## 3. Verifikasi Konfigurasi Network VM

Karena kita menggunakan network Bridged Adapter, ini memungkinkan masing - masing VM untuk dapat berkomunikasi satu sama lain.

Saya menggunakan ping untuk mengecek komunikasi Master dengan Slave1 dan Slave2

<img width="319" alt="image" src="https://github.com/user-attachments/assets/da5b4912-1a63-4a17-97ad-50b79c7c04ee">

Slave1 

<img width="315" alt="image" src="https://github.com/user-attachments/assets/ee04ad9d-8e8e-4aec-9a1a-f46df00a45f2">

Slave2

## 4. Setup SSH

<img width="392" alt="image" src="https://github.com/user-attachments/assets/6be02c7b-6613-4111-a67a-90c2417fcb40">

Menginstall SSH untuk semua VM

<img width="350" alt="image" src="https://github.com/user-attachments/assets/18d20b06-ad7a-4258-8625-4584f9d51772">

Membuat Keygen pada Master VM

<img width="599" alt="image" src="https://github.com/user-attachments/assets/5492b7b2-cd92-46d4-8461-4e0c3ff8499c">

Copy SSH Key kepada Slave1 dan Slave2

<img width="358" alt="image" src="https://github.com/user-attachments/assets/6ab31746-fa66-4b7d-8aa2-f64996166bcb">


<img width="368" alt="image" src="https://github.com/user-attachments/assets/4881a7e3-120f-48d9-8f2c-a74902043dc7">

Test Akses SSH dari Master ke Slave1 dan Slave2 

## 5. Menyiapkan Direktori Berbagi / Shared Directory

<img width="254" alt="image" src="https://github.com/user-attachments/assets/7c9552c9-2cc9-4aa3-a1b2-af1d92b3dae1">

Membuat folder mpi_shared yang akan dipakai oleh semua VM

## 6. Image Processing

Pada percobaan kali ini saya akan menggunakan gambar file untuk menunjukkan MPI vs Sequential

<img width="687" alt="image" src="https://github.com/user-attachments/assets/7137aba3-4a11-4a54-b08e-2919f1305f8f">

Disini saya menggunakan gambar 6000x4000

![image](https://github.com/user-attachments/assets/4625db73-ff5b-49ed-b2a9-499d34aef6b0)

Untuk memasukkan gambar dari Windows ke VM Ubuntu, kita menambahkan folder tempat gambar yang kita baru download ke dalam Shared Folders pada bagian setting VM

![image](https://github.com/user-attachments/assets/f2458a6f-035c-403b-b9de-9c568734ce2d)
