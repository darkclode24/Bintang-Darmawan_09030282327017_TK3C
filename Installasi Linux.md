## Nama : Bintang Darmawan
## NIM : 09030282327017
## Kelas : TK 4C

## 1. Buatlah laporan proses instalasi di computer mahasiswa dan tampilkan screenshootnya.

![image](https://github.com/user-attachments/assets/1cda13a4-c6b2-4f2b-9dbc-36902eac4897)

Pada **VirtualBox**, pilih **New**, dan masukkan nama untuk Virtual Machine yang akan digunakan.

![image](https://github.com/user-attachments/assets/75ce479a-e0b6-40a9-93d5-bd4a7780447e)
![image](https://github.com/user-attachments/assets/67b46e3c-c8c8-4467-8565-0f83c18d6da6)

Berikan **Memory**,**Processor**, dan juga **Penyimpanan** yang memadai untuk Virtual Machine tersebut.

![image](https://github.com/user-attachments/assets/f12930ed-1d9e-4a13-be08-977525d82f5d)

Pada **Settings** Virtual Machine yang baru dibuat, pada Bagian **Storage** masukkan file .iso Ubuntu yang telah didownload ke dalam **Controller : IDE**.

![image](https://github.com/user-attachments/assets/5ec81f81-430e-422d-a031-4de91a29e983)

Setelah menjalankan Virtual Machine akan tampil opsi installasi, pilih bahasa yang diinginkan dan tekan **Install Ubuntu**

![image](https://github.com/user-attachments/assets/dd24eb04-d053-499a-9edf-8b7c87997fd4)

Akan tampil beberapa kebutuhan opsional yang lebih baik dipenuhi agar penginstallan berjalan dengan baik seperti, menyambungkan laptop ke charger, memiliki penyimpanan setidaknya **7.3 GB**, dan tersambung ke internet. Anda dapat memilih untuk memasang third-party software atau tidak dengan mencentang box pilihan. Setelah memilih preferensi, klik **Continue**

![image](https://github.com/user-attachments/assets/3fe0e955-f962-4270-8fc2-5775463e1160)

Akan ada beberapa opsi tipe penginstallan. Pada installasi ini, kita akan menggunakan opsi **Something else**

![image](https://github.com/user-attachments/assets/e0f5d58c-b88b-4efc-942c-0421f3aec259)

Pilih **New Partition Table** untuk menampilkan partisi /dev/sda yang telah dibuat (_freespace_)

![image](https://github.com/user-attachments/assets/97307419-fa31-4ca0-b0c3-487c759d2d2e)

Membuat partisi **Swap** yang berukuran **1 GB (1024 MB)** yang terletak di akhir penyimpanan / space.

![image](https://github.com/user-attachments/assets/543ff2f7-b9d4-45e0-a102-dfc62f8e8418)

Membuat partisi untuk direktori **/home** yang berukuran **5GB (5291 MB)**, menggunakan format **ext4 journaling file system** pada opsi **use as**, dan mount point partisi diisi sebagai **/home**.

![image](https://github.com/user-attachments/assets/bf82ec80-cef5-46d3-a1fa-b799d6d8be96)

Membuat partisi untuk direktori **root (/)** yang berukuran berapa storage yang tersisa (pada kasus saya yaitu **31,265 MB**) menggunakan format **ext4 journaling file system** pada opsi **use as**, dan mount point partisi diisi sebagai **/**

Setelah itu, pilih **Install Now**

![image](https://github.com/user-attachments/assets/ddf0a795-6dac-4f48-87c8-96086f8ea1b0)

Pilih **zona waktu** yang ingin digunakan, pilih **Continue**

![image](https://github.com/user-attachments/assets/9750d6e2-665e-4fcc-ab2a-8e7bd9d9b814)

Pilih **Keyboard Layout** yang diinginkan, pilih **Continue**

![image](https://github.com/user-attachments/assets/a79f9683-2154-4685-a537-1c9e01ec891c)

Masukkan **Nama, Username, dan Password** yang akan digunakan untuk mengakses Ubuntu, pilih **Continue**

![image](https://github.com/user-attachments/assets/a938a573-f9a7-46e5-b536-f615170dcecd)

Menunggu penginstallan system berlangsung.

![image](https://github.com/user-attachments/assets/7b76b311-cf3b-46ac-8ecc-d1c1869c21af)

Setelah penginstallan, **Restart** Virtual Machine untuk menyelesaikan installasi.

![image](https://github.com/user-attachments/assets/7038390a-ffe1-4a33-aa39-06de23fac681)

Setelah restart, masukkan **Password** yang telah dimasukkan sebelumnya. 

![image](https://github.com/user-attachments/assets/418f5ee6-b12d-4034-ab57-a5b50534ae96)

Penginstallan Ubuntu telah selesai.