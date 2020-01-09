# **VERSION CONTROL**


![vcs scheme](https://blog.cpanel.com/wp-content/uploads/2018/05/image2018-2-8_17-46-1.png)

## Pengertian

Version control adalah sebuah sistem yang mencatat setiap perubahan terhadap sebuah berkas atau kumpulan berkas sehingga pada suatu saat kita dapat kembali kepada salah satu versi dari berkas tersebut. kemampuan tersebut dapat mendukung kolaborasi antar anggota di dalam tim ketika mengerjakan suatu project.

## Jenis Version Control

1. Local Version Control
   
![local](https://git-scm.com/book/en/v2/images/local.png)
   
   developer melakukan backup file-file kerjanya secara manual ke suatu tempat yang telah disediakan. Jadi developer menentukan sendiri tempat backup untuk seluruh file-file kerja, menentukan skema penyimpanan file-file tersebut, menentukan mekanisme pelacakan versi untuk setiap file. dan semua hal tersebut dilakukan di dalam komputer lokal tanpa terhubung ke komputer lainnya.

2. Centralized Version Control

![centralized](https://git-scm.com/book/en/v2/images/centralized.png)

   System ini menggunakan sebuah tempat penyimpanan utama (biasa sebut dengan repository) dan hanya satu buah di server pusat. Karena itulah makanya disebut sebagai centralized VCS. Jenis ini biasanya juga disebut dengan client server model. kita menarik file yang kita butuhkan, tetapi kita tidak pernah memiliki salinan lengkap proyek di komputer lokal. Beberapa contoh version control yang menerapkan adalah Subversion (SVN) dan Perforce.

3. Distributed Version Control
   
   ![distributed](https://git-scm.com/book/en/v2/images/distributed.png)

   Dengan sistem kontrol versi terdistribusi (DVCS), kita tidak bergantung pada server pusat untuk menyimpan semua versi file proyek. Sebagai gantinya, kita mengkloning repositori secara lokal sehingga kita memiliki sejarah (history) lengkap proyek. Dua sistem kontrol versi terdistribusi yang umum adalah Git dan Mercurial.
