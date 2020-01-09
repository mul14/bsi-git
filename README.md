<h1> Basic Git Usage </h1>

## Buat Repositori Baru

Pertama hal yang perlu dilakukan ialah membuat repositori baru , dengan membuat direktori / folder baru , buka folder masuk dan jalankan ini : 

```
$ git init
```

fungsi diatas adalah untuk membuat repository baru,semisal anda sudah mempunyai sebuah repository dan ingin melakukan pengunduahan file repository / melakukan cloning file ada dua cara

1. Membuat salinan kerja dari repository lokal dengan menjalankan perintah sebagai berikut
```
$ git clone /jalur/ke/repositori
```

2.  Ketika repository berada pada server yang jauh dan tidak ada pada lokal repository maka lakukan sebagai berikut : 
```
$ git clone namapengguna@host:/jalur/ke/repositori
```

## Add dan Commit 

Untuk melakukan penambahan perubahan file yang kamu lakukan ke dalam repository yang kamu kerjakan langkah yang pertama kamu lakukan adalah dengan melakukan sebagai berikut : 
```
$ git add <namaberkas>
$ git add *
```

Ketika kamu sudah menentukan file mana saja yang akan kamu tambahankan ke dalam repository , langkah selanjutnya kamu perlu melakukan commit , sebagai berikut : 
```
$ git commit -m "Pesan komit"
```
Sekarang file anda sudah berada pada ```HEAD``` namun belum masuk kedalam Repository Server 


## PUSH ( MENGIRIM PERUBAHAN )

Saat ini perubahan sudah ada pada ```HEAD``` yang ada pada server lokalmu, Untuk mengirimkan ke repository server yang online perlu kamu lakukan sebagai berikut : 
```
$ git push origin master
```
Ubah master sesuai cabang yang kamu inginkan,Jika repositori yang ada belum dikloning dan ingin dihubungkan ke server jarak-jauh, kamu perlu menambahkan
```
$ git remote add origin <server>
```

## BRANCHING

Percabangan atau branching digunakan untuk mengembangkan fitur-fitur secara terisolasi. Cabang utama atau master merupakan cabang bawaan ketika kamu membuat repositori. Gunakan cabang lain untuk pengembangan, setelah selesai, gabungkan kembali ke cabang utama.

![](https://rogerdudler.github.io/git-guide/img/branches.png)

buat cabang baru dengan nama "fitur_x" dan beralih kedalamnya menggunakan

```
$ git switch --create=fitur_x
```

Untuk berpindah branch bisa melakukan dengan menggunakan command ```switch```

## PULL dan MERGE

untuk memperbarui repositori lokal ke komit terkini, lakukan

```
$git pull
```

dari direktori kerja kamu untuk mengambil dan menggabungkan perubahan jarak-jauh. untuk menggabungkan cabang lain ke cabang aktif (misal master), gunakan

```
$ git merge <cabang>
```

pada kasus diatas, git mencoba menggabungkan perubahan secara otomatis. Sayangnya hal ini tak selalu berjalan mulus dan bisa menyebabkan konflik. Kamu lah yang bertanggung jawab menggabungkan konflik tersebut secara manual dengan menyunting berkas yang ditunjukkan git. Setelah itu, kamu perlu memarkahinya dengan

```
$ git add <namaberkas>
```

sebelum penggabungan berlaku, kamu bisa melakukan pratinjau menggunakan

```
$ git diff <cabang_asal> <cabang_tujuan>
```

## TAG

Sangat dianjurkan membuat penanda atau tags untuk perangkat lunak yang dirilis. Hal ini amat lah lazim, yang juga terjadi di SVN. Kamu bisa membuat penanda baru dengan nama 1.0.0 dengan menjalankan

```
$ git tag 1.0.0 1b2e1d63ff
```

1b2e1d63ff adalah 10 karakter pertama dari identitas komit yang ingin kamu referensikan ke penanda. Kamu bisa mendapatkan identitas komit dengan melihat

## LOG

dalam bentuknya yang paling sederhana, kamu bisa mempelajari riwayat repositori menggunakan ``` git log ``` kamu bisa menambahkan banyak parameter untuk menampilkan log sesuai keinginan. Untuk melihat komit penulis tertentu ```git log --author=bob``` Untuk melihat log yang dimampatkan, satu baris per komit ```git log --pretty=oneline``` Atau mungkin kamu ingin melihat pohon ASCII art seluruh percabangan disertai nama dan penandanya ``` git log --graph --oneline --decorate --all ``` Sekedar melihat berkas yang berubah ```git log --name-status``` Ini baru sedikit saja dari sekian banyak parameter yang bisa kamu gunakan. Lebih jauh lagi, lihat ```git log --help```

## Mengembalikan perubahan lokal 

Seandainya kamu melakukan kesalahan kamu bisa mengembalikannya menggunakan perintah ```git checkout -- <namaberkas>``` perintah di atas mengembalikan perubahan di dalam pokok kerja kamu dengan konten terakhir dari HEAD. Perubahan dan berkas baru yang telah ditambahkan ke indeks akan tetap tersimpan. Jika kamu ingin menggugurkan perubahan dan komit lokal seutuhnya, ambil riwayat terakhir dari server dan arahkan ke cabang master lokal seperti ini 
```
$ git fetch origin
$ git reset --hard origin/master
```


