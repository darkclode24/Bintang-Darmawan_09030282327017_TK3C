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
