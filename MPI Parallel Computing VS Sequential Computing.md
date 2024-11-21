# Bintang Darmawan, 09030282327017, TK3C

Disini saya akan mencoba membandingkan parallel computing menggunakan MPI dengan 1 master dan 2 slave, dengan sequential computing.


# MPI Parallel Computing VS Sequential Computing

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

Test Akses SSH dari Master ke Slave1

<img width="368" alt="image" src="https://github.com/user-attachments/assets/4881a7e3-120f-48d9-8f2c-a74902043dc7">

Test Akses SSH dari Master ke Slave2

## 5. Menyiapkan Direktori Berbagi / Shared Directory

<img width="254" alt="image" src="https://github.com/user-attachments/assets/7c9552c9-2cc9-4aa3-a1b2-af1d92b3dae1">

Membuat folder mpi_shared yang akan dipakai oleh semua VM

![image](https://github.com/user-attachments/assets/e1e8a200-bfdc-433b-b2ff-a6e13056b93c)

![image](https://github.com/user-attachments/assets/310c3ef6-285c-4ef0-8e15-43ca22bb4695)

![image](https://github.com/user-attachments/assets/331cc088-207d-4950-8cd7-1d80cf07bcc0)

Tampilan folder pada masing - masing VM (bisa liat VM pada judul di atas kiri)

## 6. Image Preparing

Pada percobaan kali ini saya akan menggunakan gambar file untuk menunjukkan MPI vs Sequential

<img width="687" alt="image" src="https://github.com/user-attachments/assets/7137aba3-4a11-4a54-b08e-2919f1305f8f">

Disini saya menggunakan gambar 6000x4000

![image](https://github.com/user-attachments/assets/4625db73-ff5b-49ed-b2a9-499d34aef6b0)

Untuk memasukkan gambar dari Windows ke VM Ubuntu, kita menambahkan folder tempat gambar yang kita baru download ke dalam Shared Folders pada bagian setting VM

<img width="449" alt="image" src="https://github.com/user-attachments/assets/9b8de0fa-d725-41fd-bd78-f93811b2327c">

Mounting Shared Folder pada masing - masing VM

## 7. Program

### Kode MPI

Disini saya akan membuat program yang memproses gambar dengan metode MPI Parallel dan juga Sequential.

<img width="284" alt="image" src="https://github.com/user-attachments/assets/71852578-8a98-4638-bf75-bc2e31828a17">

![image](https://github.com/user-attachments/assets/85c2e0ee-fc71-45a3-9feb-b89b682120b2)

Membuat direktori / folder tempat program.

<img width="317" alt="image" src="https://github.com/user-attachments/assets/673aabe6-5d9c-4fd7-bd95-b91faf22e75a">


![image](https://github.com/user-attachments/assets/d23152e6-3bdf-40b7-8757-2b3a66e31caa)

![image](https://github.com/user-attachments/assets/0ad6211c-ed44-4277-8726-8a11117b574f)

Membuat Kode MPI.

Kode membagi proses pengolahan gambar menjadi beberapa proses menggunakan MPI. Proses utama memuat gambar, membaginya menjadi bagian-bagian, dan mengirimkannya ke proses-proses lain untuk diubah menjadi skala abu-abu secara paralel.

<img width="614" alt="image" src="https://github.com/user-attachments/assets/abbe1c85-3f59-4e86-96f2-70fe394eade4">

Compile dan menjalankan kode MPI.

<img width="221" alt="image" src="https://github.com/user-attachments/assets/40252ff8-f1d6-41e3-a3f1-a663d435c7c8">

Hasil output MPI memproses gambar 6000x4000 menjadi Grayscale beserta waktu yang digunakan.


### Kode Sequential

Saya akan membuat Kode Sequential pada direktori yang sama dengan MPI.

<img width="344" alt="image" src="https://github.com/user-attachments/assets/bcbb179c-c9c9-414e-85fc-4849cda1db27">

![image](https://github.com/user-attachments/assets/46c2705b-ade4-4305-b564-a18e0380048b)

![image](https://github.com/user-attachments/assets/8762994b-0e37-4a4a-bed8-408afd2387d6)

Membuat kode sequential.

Kode memuat gambar, mengubahnya menjadi skala abu-abu secara berurutan, dan mencetak waktu prosesnya.

<img width="633" alt="image" src="https://github.com/user-attachments/assets/0cb97259-51ca-4ad5-af59-339aa3fc2116">

Compile dan menjalankan kode sequential.

<img width="240" alt="image" src="https://github.com/user-attachments/assets/ab18fb2d-c5d2-49aa-a182-e5882d11466d">

Hasil output sequential memproses gambar 6000x4000 menjadi Grayscale serta waktu yang digunakan.


# Analisa

Hasil perbandingan menunjukkan bahwa proses menggunakan MPI (64ms) justru lebih lambat dibandingkan proses sequential (15ms) untuk mengubah gambar 6000x4000 menjadi grayscale. Berikut adalah analisa :

## Kenapa MPI Lebih Lambat? 

### 1. Overhead Komunikasi di MPI : 
Dalam pemrosesan paralel dengan MPI, data gambar harus dibagi dan dikirim dari master ke slave. Setelah itu, hasilnya harus dikumpulkan kembali di master. Proses komunikasi ini menambah overhead waktu yang signifikan, terutama untuk tugas sederhana seperti konversi grayscale.

### 2. Tugas yang Kurang Kompleks :
Konversi gambar menjadi grayscale adalah operasi yang cukup ringan secara komputasi. Waktu yang dihemat oleh pemrosesan paralel tidak cukup besar untuk mengimbangi overhead komunikasi MPI.

### 3. Efisiensi MPI :
Pemrograman MPI lebih efektif untuk masalah yang bersifat compute-intensive dengan data besar dan operasi yang kompleks. Untuk tugas yang terlalu sederhana, keunggulan paralelisme tidak dapat dirasakan.

### 4. Resource Sharing :
Jika jumlah core fisik lebih kecil daripada jumlah proses MPI, sistem mengalami bottleneck karena thread bersaing untuk resource.

### 5. Latensi MPI :
MPI menambahkan latensi saat memulai proses paralel, terutama jika hanya ada sedikit node yang digunakan.

### 6. Overhead Sinkronisasi :
Semua node slave harus menunggu hingga seluruh proses selesai sebelum master dapat menggabungkan hasil. Jika satu slave lambat, waktu total akan terpengaruh.

### 7. Input/Output Bottleneck :
Jika proses MPI mengakses disk untuk membaca/membagi/menggabungkan data, ini dapat menjadi bottleneck dibandingkan sequential yang membaca sekali.

## Kenapa Sequential lebih cepat?

### 1. Tanpa Komunikasi :
Proses sequential langsung memproses data tanpa membagi, mengirim, atau menggabungkan hasil.

### 2. Efisiensi Memori Lokal :
Sequential memanfaatkan cache CPU lebih efektif dibandingkan MPI yang mungkin melibatkan akses ke memori antar node.

### 3. Sederhana :
Sequential menghindari overhead seperti koordinasi antar node, latensi jaringan, atau sinkronisasi.

### 4. Minim Overhead :
Tidak ada overhead komunikasi, sinkronisasi, atau pembagian data.

### 5. Operasi Ringan :
Untuk operasi sederhana seperti konversi grayscale, sequential dapat menyelesaikan tugas dengan cepat karena komputasi berjalan langsung di satu thread.

# Kesimpulan

### MPI:
Cocok untuk tugas compute-intensive (simulasi, pemrosesan data besar, deep learning, dll.) yang membutuhkan waktu pemrosesan signifikan.
Tidak efektif untuk tugas ringan dengan overhead komunikasi lebih besar dibandingkan waktu komputasi.

### Sequential:
Optimal untuk tugas kecil, sederhana, atau yang tidak melibatkan banyak kalkulasi.

### Rekomendasi:
Gunakan MPI jika dataset sangat besar atau operasi kompleks.
Untuk dataset kecil dan operasi ringan, proses sequential lebih hemat waktu dan resource.


### Saran untuk MPI pada kasus ini :

Pastikan pembagian data lebih besar per slave untuk mengurangi overhead komunikasi.
Gunakan lebih banyak core fisik untuk menghindari resource sharing.
Hindari menggunakan MPI untuk tugas ringan, atau kombinasikan dengan teknik paralelisme lain (seperti multithreading lokal).
