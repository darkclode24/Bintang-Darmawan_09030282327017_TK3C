## Nama : Bintang Darmawan (09030282327017)
## Kelas : TK III C

## 1. Buatlah laporan proses instalasi di computer mahasiswa dan tampilkan screenshootnya.

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
