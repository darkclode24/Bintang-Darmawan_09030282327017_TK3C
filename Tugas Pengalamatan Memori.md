# Pengalamatan Memori

### Nama: Bintang Darmawan  
### NIM: 09030282327017  
### Kelas: TK III C  

---

## A. Pengalamatan Langsung (Direct Addressing)

Pada mode pengalamatan langsung, alamat operand (data yang akan diproses) langsung disediakan di dalam instruksi. Artinya, instruksi memuat alamat memori spesifik tempat operand berada.

Kelebihan pengelamatan ini adalah pengalamatan berlangsung cepat dan sederhana karena tidak perlu perhitungan tambahan, sementara kekurangannya adalah pengelamatan ini hanya dapat digunakan ketika alamat operand langsung diketahui, sehingga kurang fleksibel bila dibandingkan dengan mode lain yang lebih dinamis.


## Soal
Hitung alamat yang diakses untuk instruksi `LOAD A, 2000`.

Pada Pengalamatan Langsung, alamat operand disediakan secara langsung dalam instruksi, sehingga tidak perlu perhitungan tambahan. CPU cukup langsung mengakses alamat memori yang diberikan, yaitu 2000. Mode ini tidak memerlukan perhitungan tambahan karena alamat operand sudah diketahui di instruksi.

**Jawaban : Alamat yang diakses adalah 2000.**

---

## B. Pengalamatan Tidak Langsung (Indirect Addressing)

Pada mode pengalamatan tidak langsung, instruksi tidak memuat alamat operand secara langsung, melainkan menggunakan register atau alamat memori sebagai perantara untuk menunjukkan lokasi operand sebenarnya.

Kelebihann pengalamatan ini adalah lebih fleksibel karena dapat digunakan untuk mengakses data di alamat memori yang dapat berubah-ubah. Namun, kekurangannya adalah membutuhkan dua tahap pengaksesan memori, sehingga lebih lambat dibandingkan pengalamatan langsung.

## Soal
Jika register R1 berisi 1500, berapa alamat yang diakses untuk instruksi `LOAD A, (R1)`?

Pada Pengalamatan Tidak Langsung, alamat yang diberikan bukanlah lokasi data langsung, tetapi alamat yang mengarah ke alamat operand. Di sini, isi dari register R1 (1500) menunjukkan lokasi memori yang berisi alamat operand sebenarnya. Jadi, CPU akan mengakses memori di alamat 1500 untuk menemukan alamat operand yang sebenarnya.

Pengalamatan ini menambah satu langkah ekstra. CPU pertama-tama mengakses alamat yang disebutkan dalam R1, lalu menggunakan alamat yang ditemukan sebagai target instruksi LOAD.

**Jawaban : Alamat yang diakses adalah alamat yang tersimpan di lokasi memori 1500.**

---

## C. Pengalamatan Indeks (Indexed Addressing)

Pada mode pengalamatan indeks, alamat operand dihitung dengan menambahkan nilai dari register indeks ke alamat dasar yang diberikan dalam instruksi. Mode ini sering digunakan dalam operasi berbasis array. Mode pengalamatan ini sangat efisien untuk mengakses elemen dalam array atau tabel, karena bisa dengan mudah melakukan iterasi melalui elemen-elemen tersebut. Namun sedikit lebih lambat karena memerlukan tambahan operasi penjumlahan.

## Soal
Hitung alamat yang diakses untuk instruksi `LOAD A, 500(R2)` jika `R2 = 100`.

Dalam Pengalamatan Indeks, isi dari register indeks (misalnya R2) ditambahkan ke alamat dasar (500) yang disediakan dalam instruksi untuk menentukan alamat final. Mode ini umum dipakai untuk mengakses elemen-elemen dalam array atau data berurutan.

Ini memungkinkan pengalamatan dinamis, yang berguna untuk mengakses data secara berurutan. Alamat yang diakses berubah tergantung isi dari R2.

**Jawaban : Alamat yang diakses adalah 500 + R2, yang hasilnya adalah 500 + 100 = 600.**

---

## D. Pengalamatan Relatif (Relative Addressing)

Dalam mode pengalamatan relatif, alamat operand ditentukan berdasarkan posisi instruksi saat ini, ditambah dengan offset yang diberikan dalam instruksi. Mode ini sering digunakan dalam program yang menggunakan instruksi percabangan atau looping.

Kelebihan, Sangat berguna dalam struktur program yang dinamis, terutama ketika melakukan pengulangan atau percabangan.
Kekurangan, Alamat operand bergantung pada posisi instruksi saat ini, yang bisa membuatnya sulit untuk dipahami dalam debugging.

## Soal 
Hitung alamat yang diakses untuk instruksi `LOAD A, 40` jika alamat instruksi saat ini adalah 1200.

Pada Pengalamatan Relatif, alamat operand ditentukan dengan menambahkan offset relatif (40) ke alamat instruksi saat ini (1200). Mode ini mempermudah pengoperasian dalam kode dengan menggunakan percabangan, loop, atau kondisi.

Ini membuat alamat operand relatif terhadap alamat instruksi saat ini, sehingga mendukung posisi yang dinamis dalam kode.

**Jawaban : Alamat yang diakses adalah 1200 + 40 = 1240.**

---

## E. Pengalamatan Segmen (Segment Addressing)

Mode pengalamatan segmen melibatkan dua komponen: segment base dan offset. Segment base menunjukkan awal segmen memori, sedangkan offset menunjukkan jarak atau pergeseran dari base tersebut untuk menemukan alamat operand. Pengalamatan ini memungkinkan pengaturan memori yang lebih fleksibel dan terorganisir, seperti membagi memori menjadi segmen-segmen berbeda untuk kode, data, dan stack. Tetapi, penggunaan segment base dan offset bisa mempersulit pengaturan dan penghitungan alamat jika struktur memori yang lebih rumit dibutuhkan.

## Soal
Berapa alamat yang diakses jika Segment Base = 4000 dan Offset = 300?

Pada Pengalamatan Segmen, alamat operand dihitung dengan menambahkan offset (300) ke base segment (4000). Ini biasanya digunakan pada sistem yang membagi memori menjadi beberapa segmen (misalnya, untuk kode, data, atau stack) dengan setiap segmen memiliki base address tertentu.

Ini memungkinkan akses ke segmen-segmen memori yang terpisah, berguna untuk pengaturan memori yang lebih rapi dan efisien.

**Jawaban : Alamat yang diakses adalah 4000 + 300 = 4300.**

---

## F. Pengalamatan Indeks dengan Offset (Indexed Addressing with Offset)

Mode ini adalah variasi dari pengalamatan indeks, di mana alamat dasar juga ditambahkan ke register tertentu untuk memperoleh alamat operand yang tepat. Kombinasi ini sangat bermanfaat untuk mengakses data dalam struktur kompleks seperti array dengan offset tertentu. Tetapi membutuhkan dua kali operasi penjumlahan, sehingga sedikit lebih lambat dari pengalamatan indeks biasa.

## Soal
Jika `R3 = 250` dan instruksi adalah `LOAD A, 1000(R3)`, hitung alamat yang diakses.

Ini adalah bentuk lain dari Pengalamatan Indeks di mana offset (1000) ditambahkan ke isi register indeks (R3 = 250). Mode ini memungkinkan referensi memori yang fleksibel di mana base dan offset bisa berubah, berguna untuk mengakses data dalam struktur dengan offset tertentu.

Mode ini menghitung alamat akhir dengan menambahkan nilai dalam instruksi dan register indeks, sehingga fleksibel untuk struktur data dengan offset.

**Jawaban: Alamat yang diakses adalah 1000 + 250 = 1250.**
