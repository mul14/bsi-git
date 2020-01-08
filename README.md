# HOW TO RESOLVE A CONFLICT

Conflict (pada git) adalah suatu kondisi dimana terjadi perbedaan antara file asli(yang ada di _remote repository_) dengan file yang akan kita _push_ ketika kita melakukan `merge`. perbedaan yang dimaksudkan adalah perbedaan pada baris yang sama.

![contoh conflict di github][0]

## Cara mengatasi _conflict_ di `github`
- tanda "<<<<<<<<<" merupakan branch asal, sedangakan tanda ">>>>>>>>>" merupakan branch tujuan merging. Pilih konten yang akan dipertahankan, dan hapus sisanya (termasuk tanda "<<<<<<<<<" dan ">>>>>>>>>").
- scroll ke bagian atas editor. Di sebelah kanan atas terdapat tombol "Mark as resolve", tekan tombol tersebut jika anda telah yakin atas perubahan yang dilakukan.
- jika sudah, maka akan muncul konfirmasi untuk "Commit Merge" yang berarti proses _merge_ akan dilakukan. Tekan tombol tersebut jika dirasa sudah _solved_.






[0]: https://help.github.com/assets/images/help/pull_requests/view-merge-conflict-with-markers.png