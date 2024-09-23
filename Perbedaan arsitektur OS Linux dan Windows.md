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


Windows Menggunakan **hybrid kernel**, yang menggabungkan elemen dari **monolithic** dan **microkernel**. Beberapa layanan berjalan di kernel mode, sementara yang lainnya diisolasi untuk efisiensi.

![image](https://github.com/user-attachments/assets/89dc727e-e77e-4759-a0cc-41857c3bdd4b)
