# GIT SUBMODULE & SUBTREE
## Git SubModule

- What is Git Submodule ???
  
  ![Git Submodule][SubModule]  

  Git Submodule memungkinkan Anda untuk menyimpan repositori git sebagai subdirektori dari repositori git lainnya. Git submodule memungkinkan repositori Git untuk menggabungkan dan melacak riwayat versi kode eksternal.
  Git submodule adlaah record di dalam repositori host git yang menunjuk commit tertentu di repositori eksternal lain. Submodules sangat statis dan hanya melacak commit tertentu. Submodules tidak melacak referensi atau branch dan tidak secara otomatis diperbarui ketika repositori host diperbarui. Saat menambahkan submodule ke repositori, file baru .gitmodules baru akan dibuat. File .gitmodules berisi meta data tentang mapping antara URL proyek submodule dan direktori lokal. Jika repositori host memiliki banyak submodul, file .gitmodules akan memiliki entri untuk setiap submodul.

- Why and When should you use a git submodule?
  
  Jika Anda perlu mempertahankan manajemen versi yang ketat atas dependensi eksternal Anda, masuk akal untuk menggunakan git submodule. Berikut ini adalah beberapa kasus penggunaan terbaik untuk git submodule :
  1. Ketika komponen atau sub proyek eksternal berubah terlalu cepat atau perubahan yang akan datang akan merusak API, Anda dapat mengunci kode ke commit khusus untuk keselamatan.
  2. Ketika Anda memiliki komponen yang tidak terlalu sering diperbarui dan Anda ingin melacaknya sebagai ketergantungan vendor.
  3. Ketika Anda mendelegasikan sebagian proyek ke pihak ketiga dan Anda ingin mengintegrasikan pekerjaan mereka pada waktu atau rilis tertentu. Sekali lagi ini berfungsi ketika pembaruan yang tidak terlalu sering.

## Git SubTree
- What is Git SubTree ?
  
  Git SubTree adalah perintah git yang dapat membuat folder di dalam suatu repositori dapat terhubung dengan remote repositori, tanpa membuat repositori di dalam repositori. 

  ![Git SubTree][SubTree]

  Dari gambar di atas, bisa kita simpulkan bahwa kita dapat memasukkan sebuah folder (Local Machine Repo 2) ke dalam suatu repositori (Local Machine Repo 1) dan kita tetap dapat meng-update baik ke Bitbucket Repo 1 atau pun Bitbucket Repo 2. Atau dengan kata lain, melihat kasus kita di atas, semisal kita melakukan perubahan terhadap plugin di dalam aplikasi, kita dapat melakukan commit-nya dan push perubahan tersebut ke repositori aplikasi. Selanjutnya, kita juga bisa melakukan push lagi ke repositori khusus plugin telah kita siapkan.
  
- Why and When you use a git subtree ?
  1. Manajemen alur kerja sederhana yang mudah
  2. Versi Git yang lebih lama didukung (bahkan lebih tua dari v1.5.2).
  3. Kode sub-proyek tersedia tepat setelah clone super project selesai.
  4. git subtree tidak mengharuskan pengguna repositori Anda untuk mempelajari sesuatu yang baru. Mereka dapat mengabaikan fakta bahwa Anda menggunakan subtree git untuk mengelola dependensi.
  5. git subtree tidak menambahkan file metadata baru seperti git submodule (misalnya .gitmodule).
  6. Isi modul dapat dimodifikasi tanpa memiliki salinan repositori terpisah dari dependensi di tempat lain.

[SubModule]: https://ardupilot.org/dev/_images/git-submodules.png
[SUbTree]: https://refactory.id/storage/post/32.jpg
  
  
