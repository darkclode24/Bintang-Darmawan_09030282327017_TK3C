### Bintang Darmawan | 09030282327017 | Jaringan Komputer | TK-4C


![image](https://github.com/user-attachments/assets/2f23f4ea-b3f0-4506-a976-31f96bb4d865)

Melakukan konfigurasi switch sederhana pada S1 & S2, yaitu :

1. Mengamankan akses ke Command Line Interface (CLI) dan Console menggunakan password polos dan terenkripsi.

2. Mengkonfigurasi pesan untuk user ketika log in ke switch. Pesan ini juga digunakan untuk memperingatkan user yang tidak berizin.

### 1. Masuk ke Mode Privileged EXEC

![image](https://github.com/user-attachments/assets/c97c3440-0cfc-4bc5-800d-6e5f522f5bc3)

Kita dapat mengakses semua perintah switch dari mode privileged EXEC.

1. Klik Switch S1.
2. Tekan enter untuk memulai.
3. Masukkan `enable` ke dalam CLI untuk memasuki mode privileged EXEC.

### 2. Memasangkan nama pada sebuah switch

![image](https://github.com/user-attachments/assets/7f345474-7d39-43a7-83cc-0a7252e960f6)

1. Memasuki mode konfigurasi global
2. Mengubah nama switch menggunakan `hostname`
3. keluar dari mode konfigurasi global

### 3. Mengamankan akses ke Console Line

![image](https://github.com/user-attachments/assets/c40eab3b-a112-4cb4-b2b8-c33f82437c12)

1. Memasuki mode konfigurasi global
2. Memasuki mode konfigurasi line console dengan `line console 0`
3. Menetapkan password untuk akses konsol, kali ini password adalah `letmein`
4. Mengaktifkan autentikasi password, dengan `login`

### 4. Verifikasi bahwa akses Console Line telah diamankan

![image](https://github.com/user-attachments/assets/aa561721-698b-45a5-aa05-60ef477db972)

Ketika ingin masuk ke Console Line, maka user akan diminta memasukkan password yang telah diatur.

### 5. Mengamankan masuk ke mode privileged

![image](https://github.com/user-attachments/assets/f65e362f-c81c-4bd5-8414-99c4012f9407)

1. Masuk mode privileged EXEC
2. Masuk mode konfigurasi global
3. Mengaktifkan password untuk memasuki mode privileged dengan `enable password [password]`

### 6. Verifikasi bahwa akses mode privileged telah diamankan

![image](https://github.com/user-attachments/assets/3ebc6cf7-260b-4828-ab7f-206d68ee768c)

Sekarang, ketika ingin masuk mode privileged user akan diminta password yang telah diatur

### 7. Mengganti password mode privileged menjadi password terenkripsi

![image](https://github.com/user-attachments/assets/a9b57ff6-9d94-4ba1-a9c1-26c8d340d1c3)

1. Masuk mode privileged.
2. Masuk mode konfigurasi global.
3. Mengaktifkan dan mengganti password dengan password terenkripsi menggunakan `enable secret [password]`

### 8. Verifikasi bahwa password baru terenkripsi

![image](https://github.com/user-attachments/assets/89f240e1-e019-4b61-bcae-3b855cf0b289)

Dapat dilihat, bahwa password yang digunakan untuk mengakses mode privileged sekarang terenkripsi.

Jika `enable password` dan `enable secret` aktif, maka sistem akan menggunakan password `enable secret` karena lebih aman.

