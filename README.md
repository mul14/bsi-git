#  DIFFERENCES BETWEEN PULL & FETCH

Pada dasarnya perintah `git pull` dan `git fetch` sama-sama mengambil commit terakhit dari _remote repository_. perbedaan yang mendasar dari kedua perintah tersebut adalah pada perintah `git fetch` kita akan mengambil `commit` terakhir dari _remote repository_ dan tidak langsung melakukan `merge` dengan _local repository_, sedangkan dengan perintah `git pull` kita akan menarik seluruh `commit` terakhir dari _remote repository_ dan langsung melakukan `_merge_`. 

## `git pull`
![git pull][0]
- Digunakan ketika kita belum melakukan apa-apa terhadap sebuah _local repository_, atau belum melakukan `commit`, atau baru menambah file dan belum mengubah suatu isi file. 
- Hal ini dapat membahayakan karena rawan terjadi conflict. _Conflict_ terjadi karena setelah mangambil data dari _remote repository_, akan langsung dilakukan `merge` di branch master.
- `git pull` lebih cocok dilakukan ketika kita selesai men-setup _version control_ baru (melakukan `git init`) di local repository tanpa menggunakan `git clone`.

## `git fetch`
![git fetch][1]
- Menggunakan `git fetch` kita akan mengambil _commit_ terakhir dari _remote repository_ dan menyimpannya di _local repository_ pada _branch_ `origin/master`, bukan `master`.
- Perintah `git merge` harus kita lakukan secara manual ketika sudah yakin akan perubahan yang kita lakukan di _branch_ master. 


[0]: https://www.petanikode.com/img/git/pull/menggunakan-pull.png

[1]: https://www.petanikode.com/img/git/pull/menggunakan-fetch.png