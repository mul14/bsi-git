<h1> How To Deploy Application Using Git </h1>

## Login To Server

Buka terminal dan login ke dalam servermu menggunakgan command sebagai berikut
```
ssh your_user@server_ip_address
```

Jangan lupa masukan password untuk masuk ke dalam servermu

## Installing Git

Untuk menginstall git ke dalam servermu , ikuti contoh berikut 

```
$ sudo apt-get update
$ sudo apt-get install git
```

## Buat Folder untuk menyimpan code yang akan di deploy

Source code yang akan dideploy perlu kamu taruh didalam salah satu direktori,secara mudahnya masuk ke dalam folder berikut ``` var/www/ ``` menggunakan cara sebagai berikut :
```
cd /var/www
```

Selanjutnya buatlah sebuah folder untuk menyimpan file source code tersebut dengan menggunakan code berikut :
```
mkdir website_folder
```

Sekarang full path dari direktori untuk menyimpan file tersebut yaitu ``` /var/www/website_folder```. Ini akan sangat penting untuk diingat karena path ini akan kamu gunakan mengatur  git repository

## Initialise Git Repository dalam Server

Git repository memerlukan sebuah folder untuk menjadi host . Contohnya bisa menggunakan folder dengan nama berikut website_name.git. Di dalam /var , buatlah suatu folder bernama *repo* yang nantinya akan berisi git repositorimu. Dengan melakukan command sebagai berikut : 

```
mkdir -p /var/repo/website.git
```
Lalu selanjutnya arahkan ke dalam ``` var/repo/website.git ``` dan lakukan inisialisasi ke dalam git repositorymu sebagai berikut : 
```
cd /var/repo/website.git/
git init --bare
```

## Membuat Hook

> Hook adalah sebuah program yang bisa kamu taruh didalam sebuah folder hooks untuk mentrigger sebuah aksi pada beberapa titik dalam mengeksekusi git 

Git mempunyai beberapa hooks yang bisa dipanggil secara otomatis setelah melakukan beberapa step. Kamu akan menggunakan *post-recieve* hook yang dipanggil setelah repositorimu diterima code yang di push.

Setelah melakukan sebuah inisiasi dalam git repositorimu,sebuah folder baru akan muncul didalam folder berikut ```/var/repo/website.git/``` . Arahkan ke ```hooks``` dan buatlah sebuah bash baru yang disebut dengan ```post-received``` menggunakan text editor 
```
$ cd hooks
$ nano post-receive
```

Didalam file yang sudah kamu buat, kamu perlu memberi tahu git dimana kamu menaruh file yang telah kamu push.paste contoh berikut ke dalam file yang kamu buat :
```
#!/bin/shgit --work-tree=path_to_website_folder --git-dir=path_to_git_directory checkout -f name_of_branch
```

Pastikan kamu menyimpan file tersebut dengan ```post-received```

## Membuat script tersebut executable 

Untuk menjalankan sebuah command itu tereksekusi maka kamu perlu mengubah permision dengan cara sebagai berikut 
```
chmod +x post-receive
```

Pekerjaan didalam servermu sudah selesai 

## Push local code menuju server

Dari dalam terminal , arahkan menuju local foldermu dan semisal belum tersedia maka buatlah . Lalu lakukan setting seperti berikut 
```
git initgit remote add name_of_repository ssh://your_user@server_ip_address/path_to_git_directory
```

Lalu setelah itu untuk melakukan push code kedalam remote server jalan instruksi sebagai berikut ke dalam local git repository :
```
git push name_of_repository name_of_branch
```

Masukkan kode , dan sekarang codemu sudah live dan bisa dilihat didalam folder ```var/www/website_folder```