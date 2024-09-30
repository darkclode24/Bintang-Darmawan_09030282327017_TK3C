## Kelas : TK III C

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

## 2. Analisislah pada gambar kenapa saat instalasi perlu dipilih “/” pada opsi Mount Point ? :

Karena pada **Ubuntu**, **"/"** adalah direktori root, direktori ini adalah direktori utama dalam hierarki sistem file. Semua **file, aplikasi, konfigurasi sistem,** dan **direktori lain** seperti **/home, /boot, /var,** dan **/etc** berada di bawah root directory ini.)

Ketika memilih "/" sebagai **mount point**, kita menetapkan partisi tersebut sebagai lokasi utama di mana seluruh sistem akan diinstal dan beroperasi.
Setiap **OS Linux** membutuhkan direktori “/” agar bisa berfungsi dengan baik. Tanpa partisi yang di-mount di “/”, sistem tidak akan tahu di mana harus menyimpan atau menemukan file-file penting seperti kernel, libraries, dan program-program inti.

**Mount point** adalah lokasi dalam sistem file di mana partisi atau perangkat penyimpanan di-mount (_dipasang_). Pada penginstallan ini, " / " adalah **mount point utama** yang menjadi pusat dari seluruh struktur sistem file. Dengan memilih “/”, kita memastikan bahwa partisi yang kita gunakan menjadi tempat penyimpanan semua file penting sistem operasi, dan ini memungkinkan sistem berjalan dengan benar.

## 3. Berikan penjelasan tentang **ext4, ext3, swap, ntfs, fat32,btrfs** !

**a. ext4 (Fourth Extended Filesystem):**
ext4 adalah sistem file yang umum digunakan di Ubuntu. Dibandingkan dengan ext3, ext4 mendukung file hingga 16 TB, meningkatkan kinerja dengan delayed allocation, dan memiliki fitur journaling untuk keamanan data.

**b. ext3 (Third Extended Filesystem):**
ext3 adalah pendahulu ext4 yang juga mendukung journaling untuk mencegah kerusakan data. Namun, ext3 lebih lambat dan mendukung ukuran file yang lebih kecil dibandingkan ext4.

**c. Swap:**
Swap adalah partisi khusus untuk memori virtual yang digunakan ketika RAM penuh. Ini membantu menjaga kinerja sistem agar tetap stabil, terutama saat memori fisik habis.

**d. NTFS (New Technology File System):**
NTFS adalah sistem file Windows yang bisa diakses di Ubuntu menggunakan driver NTFS-3G. Meski dapat digunakan, NTFS kurang optimal dibandingkan sistem file Linux seperti ext4.

**e. FAT32 (File Allocation Table 32):**
FAT32 adalah sistem file lama yang sering digunakan untuk perangkat penyimpanan portabel. Keterbatasannya adalah tidak mendukung file lebih dari 4 GB, sehingga tidak cocok untuk partisi sistem utama.

**f. btrfs (B-tree Filesystem):**
btrfs adalah sistem file modern dengan fitur seperti snapshot dan self-healing. Meskipun lebih canggih, btrfs belum sepopuler ext4 karena masalah stabilitas yang sedang diperbaiki.
