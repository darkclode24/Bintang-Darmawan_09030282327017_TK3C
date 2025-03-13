### Bintang Darmawan | 0903028327017 | Operating System

## SHELL

Shell adalah Command executive, artinya program yang menunggu instruksi dari pemakai,
memeriksa sintak dari instruksi yang diberikan, kemudian mengeksekusi perintah tersebut.
Shell ditandai dengan prompt. Untuk pemakai menggunakan prompt $ dan untuk superuser
menggunakan prompt #.

## PROFILE

Pada saat login, program akan menjalankan beberapa program yaitu :

1. /etc/profile

Berisi shell script yang berlaku untuk seluruh pengguna Linux.

2. Profil untuk setiap pemakai

Pada home directory, login pertama kali akan memeriksa file .bash_profile. Bila tidak ada, maka
file .bash_login akan dicari. Bila .bash_login tidak ada, maka dicari file bernama .profile.

3. .bashrc

File ini akan dieksekusi untuk perpindahan dari satu shell ke shell yang lain melalui instruksi su.

4. .bash_logout

Pada saat logout, maka bash akan mencari file .bash_logout. Bila ada, file tersebut akan
dieksekusi sebelum logout
PATH merupakan daftar nama direktori. Bila sebuah instruksi diberikan dari prompt shell, maka
instruksi tersebut akan dicari pada daftar tersebut.

## HISTORY

History diadaptasi dari C-Shell, yaitu catatan dari semua instruksi yang sejauh ini telah
dilakukan. Catatan ini dapat dilihat sebagai history, kemudian dapat dipilih kembali, diedit dan
dieksekusi.

## Bash Script

Bash-script adalah file yang berisi koleksi program yang dapat dieksekusi. Untuk eksekusi bash
script gunakan .

## JOB CONTROL

Job adalah sebuah eksekusi program yang diberikan kepada kernel. Sebuah Job dianggap
selesai, bilaeksekusi program tersebut berakhir.

# Percobaan

a. Profile

File .bash_profile dijalankan pada home direktori pemakai yang login.

![image](https://github.com/user-attachments/assets/b5d54fbf-b448-4157-bfee-4efa9b8223ba)

File .bash_logout akan diekseksi sesaat sebelum logout, berfungsi sebagai house clearing
jobs, artinya membersihkan semuanya, misalnya menghapus temporary file atau job lainnya.

![image](https://github.com/user-attachments/assets/d0a9adbd-6fb7-4951-b5c9-4d31616335fe)

