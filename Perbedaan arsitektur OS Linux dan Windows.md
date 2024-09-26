# Perbedaan Arsitektur OS Linux (Ubuntu) dan Windows

### Nama : Bintang Darmawan (09030282327017)
### Kelas : TK III C
### Mata Kuliah : Arsitektur dan Organisasi Komputer

Pada kesempatan ini, saya akan membahas perbedaan antara arsitektur sistem operasi Linux yaitu Ubuntu dengan Windows. Setelah berhasil mengunduh dan menginstal Ubuntu melalui VirtualBox, saya dapat mengakses dan menggunakan Ubuntu melalui **VM** (*Virtual Machine*) yang disediakan oleh VirtualBox.
Setelah mencoba menggunakan berbagai fitur Ubuntu, saya mengamati beberapa perbedaan dibandingkan dengan arsitektur OS Windows.

![image](https://github.com/user-attachments/assets/5512bda1-d0ff-494c-bde1-1df7ce67751b)



Beberapa diantaranya adalah :

## 1. Tipe Kernel :

Linux (Ubuntu) menggunakan **kernel monolitik** (_Monolithic Kernel_), yang di mana sebagian besar layanan inti OS seperti **manajemen file, driver perangkat,** dan **jaringan** ditangani di **kernel space** (Area memori yang dikhususkan untuk kernel sistem operasi). Kernel ini modular, yang artinya modul kernel bisa ditambahkan/dicopot secara dinamis.

![image](https://github.com/user-attachments/assets/59a4c503-22a1-47b8-905f-353ca4beebf2)


Windows Menggunakan **hybrid kernel**, yang menggabungkan elemen dari **monolithic** dan **microkernel**. Beberapa layanan berjalan di **kernel mode**, sementara yang lainnya berjalan di bagian yang lebih aman dan terpisah dari kernel (**user mode**).

![image](https://github.com/user-attachments/assets/c0bb0b75-8f77-4866-8c34-1e3b1857116a)
_note : p adalah nama user_


## 2. Manajemen Proses

Linux (Ubuntu) dikelola oleh **systemd** atau sistem init lainnya dengan struktur proses berbentuk hierarki, di mana setiap proses memiliki "_parent_" dan diinisialisasi oleh proses init (**PID 1**).

![image](https://github.com/user-attachments/assets/ef75b38d-9e4b-40ae-a047-fdc37959865b)

Windows Menggunakan **NT process manager** di mana kernel Windows mengelola penjadwalan proses. Proses seperti **svchost.exe** menjalankan banyak layanan.

![image](https://github.com/user-attachments/assets/a147957b-4ebc-49e4-ba3b-eb4d5ee66d30)


## 3. Arsitektur Sistem File

Linux (Ubuntu) Menggunakan **EXT4** sebagai sistem file utama dengan struktur direktori yang dimulai dari direktori root (_/_). Semua file sistem dimount ke dalam direktori di bawah /.

![image](https://github.com/user-attachments/assets/eef66e91-b2d8-48d4-9a95-36335bdbf6e6)

Windows Menggunakan **NTFS** sebagai sistem file utama, dengan sistem direktori berbasis huruf drive (seperti C:\). NTFS mendukung enkripsi, izin akses, dan journaling.

![image](https://github.com/user-attachments/assets/47adf7f7-52b3-4469-93d2-8ed351c8a2bb)


## 4. Manajemen Memori

Linux (Ubuntu) Menggunakan manajemen memori virtual dengan sistem paging yang sangat dapat dikustomisasi. Linux juga menggunakan **slab allocation** untuk efisiensi penggunaan memori di kernel.

![image](https://github.com/user-attachments/assets/a9ee98b1-17ab-46fe-a2a3-c6732e75b471)

Windows juga menggunakan memori virtual, terintegrasi dengan file paging (_pagefile.sys_). Windows menggunakan **demand paging**, di mana halaman memori hanya dimuat ketika diperlukan.

![image](https://github.com/user-attachments/assets/8c5a2832-372f-4f5c-aa81-be043fd4ecc9)


## 5. Arsitektur Driver Perangkat

Linux (Ubuntu) memperlakukan sebagian besar perangkat sebagai file, dan driver perangkat dimuat sebagai **modul kernel**. Modul-modul ini dapat ditambahkan atau dihapus secara dinamis menggunakan perintah **modprobe**.

<img width="960" alt="370599978-32793048-814e-4cb7-9ff9-05eac2263e3c" src="https://github.com/user-attachments/assets/e47ff9fd-e71b-49c8-8efd-1fafede9e1e5">

Windows Menggunakan **Windows Driver Model (WDM)**, di mana driver berjalan di user mode atau kernel mode. Driver biasanya harus ditandatangani oleh Microsoft untuk kompatibilitas perangkat keras.

![image](https://github.com/user-attachments/assets/27b55018-c49d-4400-ae5b-85f8668f7a04)


## 6. Instalasi Software dan Manajemen Paket

Linux (Ubuntu) menggunakan **manajer paket (misalnya, APT)** untuk menginstal software dari repositori pusat. Pengguna dapat menginstal, memperbarui, atau menghapus software dengan satu perintah.

![image](https://github.com/user-attachments/assets/1a30f6a0-35f2-4ae7-90f3-bd16a59de7e5)

Windows mengandalkan file **executable (.exe, .msi)** untuk instalasi software. Tidak ada manajer paket terpusat (meskipun winget dan Windows Store mulai diperkenalkan).

![image](https://github.com/user-attachments/assets/f7548596-c858-4ee6-9c0d-eccabd0db9e0)


## 7. Izin dan Hak Akses Pengguna

Ubuntu mengikuti model izin yang ketat, di mana tugas administratif memerlukan akses root melalui perintah **sudo**.

![image](https://github.com/user-attachments/assets/8e676508-2739-4e81-b068-3a720bd97e88)
_Tanpa menggunakan **Sudo**_

![image](https://github.com/user-attachments/assets/f83dd38d-0c6c-433f-898f-f97b2f760abd)
_Dengan menggunakan **Sudo**_

Windows menggunakan **User Account Control (_UAC_)** untuk mengelola hak istimewa administratif. Sebagian besar pengguna menjalankan sistem sebagai Administrator, yang membuat sistem lebih rentan terhadap perubahan yang tidak disengaja atau malware.

![image](https://github.com/user-attachments/assets/6aa961fe-4bf2-44b7-aa18-e17a9652f0c2)


## 8. Kustomisasi dan Sifat Open Source

Ubuntu karena bersifat **open-source**, Ubuntu sangat dapat disesuaikan, dari level kernel hingga lingkungan desktop. Pengguna dapat memodifikasi dan membangun ulang sistem operasi sesuai kebutuhan.

![image](https://github.com/user-attachments/assets/53deea09-9e02-4535-a99c-48017375f574)
_Mengedit bootloader yang digunakan untuk memuat sistem operasi **(GRUB)**_

Windows merupakan software **proprietary**, yang membatasi seberapa banyak sistem inti dapat disesuaikan. Modifikasi biasanya memerlukan alat pihak ketiga, dan pengguna tidak dapat mengakses atau memodifikasi kode sumber.

![image](https://github.com/user-attachments/assets/0f7f47e3-c3cd-4ec6-abf3-f287efb631f8)
_Modifikasi langsung di bootloader **Windows** sangat terbatas._
