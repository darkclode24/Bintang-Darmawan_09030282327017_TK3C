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

## a. Profile

File .bash_profile dijalankan pada home direktori pemakai yang login.

![image](https://github.com/user-attachments/assets/b5d54fbf-b448-4157-bfee-4efa9b8223ba)

File .bash_logout akan diekseksi sesaat sebelum logout, berfungsi sebagai house clearing
jobs, artinya membersihkan semuanya, misalnya menghapus temporary file atau job lainnya.

![image](https://github.com/user-attachments/assets/d0a9adbd-6fb7-4951-b5c9-4d31616335fe)

## b. History

Melihat batasan maksimum instruksi yang dapat disimpan

![image](https://github.com/user-attachments/assets/a79d4a28-62f8-4ba3-ba07-fb33007a7390)

Melihat daftar instruksi yang telah dilakukan dengan perintah history. Daftar instruksi
dilengkapi dengan nomor urut.

![image](https://github.com/user-attachments/assets/d1aa548d-ad3d-493a-ab53-984f6317154a)

Selain history, instruksi fc (fix command) juga dapat digunakan

![image](https://github.com/user-attachments/assets/13fbed53-e1a4-4e02-8ca2-22e798250425)

Instruksi fc dapat menampilkan instruksi antara 2 nomor atau dengan menggunakan kata
depan instruksi yang diberikan

![image](https://github.com/user-attachments/assets/d55ad983-5400-4bab-84fa-1e8a3fb74c04)

## c. Create and Run Bash-script

Membuat file `p1.sh` dengan isi dibawah

![image](https://github.com/user-attachments/assets/14c6a9fe-5964-4854-af76-7301202272b4)

Memberi izin `executable` pada file

![image](https://github.com/user-attachments/assets/b6c8186e-271a-4081-b1d9-c1b5be1dadf4)

Menjalankan file, dapat menggunakan `bash`, `sh`, `.` atau yang lain

![image](https://github.com/user-attachments/assets/5183e947-638a-4ea7-bf2f-9cae1be6d22d)

Tambahkan script shell seperti dibawwah pada `p1.sh`

![image](https://github.com/user-attachments/assets/549be1ba-7e0c-464d-ba35-a12939dd7bda)

Buat `p2.sh` dengan isi dibawah

![image](https://github.com/user-attachments/assets/59aaec0d-280e-4d51-bd29-df359fd2ee27)

Menjalankan beberapa program shell dalam satu baris instruksi yang dipisahkan dengan
tanda ;

![image](https://github.com/user-attachments/assets/1e30a2ac-bf91-4bf5-9886-8fb50980e8df)

Menjalankan script sebagai prosees background, sehingga prompt tidak menunggu program
tersebut selesai.

![image](https://github.com/user-attachments/assets/12cb3c95-515d-4755-b7dc-faf10c34ca24)

Menjalankan 2 program atau lebih dalam satu block, kemudian dieksekusi sebagai
proses background

![image](https://github.com/user-attachments/assets/686aedaf-1144-437f-8b96-14a2f8e40a80)

## d. Job Control

Menampilkan proses foreground

![image](https://github.com/user-attachments/assets/1861c563-43d7-4f0d-80f0-c877832ad5b5)

Menampilkan proses background

![image](https://github.com/user-attachments/assets/024de286-b799-4e55-a78b-4f59c33cf0e6)

Melihat jobs yang aktif

![image](https://github.com/user-attachments/assets/d2006c15-82dd-4ff1-9b68-8d85d7d2695c)

Membuat `ploop.sh` dengan isi dibawah, file tidak akan berhenti kecuali diberhentikan (CTRL + C)

![image](https://github.com/user-attachments/assets/25e03b99-60a1-4ff9-b3c8-c4cdc1b76d48)

Memberi izin `executable` dengan `chmod +x ploop.sh` serta menjalankan file

![image](https://github.com/user-attachments/assets/940a2a59-9903-4162-b867-2f91b5026d1a)


