# **BRANCH DI DALAM VERSION CONTROL**

## Pengertian 

Branch di dalam version control adalah sebuah metode yang dilakukan ketika akan membuat suatu perubahan namun perubahan tersebut belum pasti akan digunakan. ibaratnya branch adalah sebuah jalur yang akan mewadahi commit atau perubahan baru sebelum akan disimpan secara tetap di dalam branch utama yang biasa disebut dengan master.

## Command untuk membuat branch baru

```
git switch --create 'namabranchbaru'
```

## Command untuk mengganti branch yang aktif

```
git switch 'namabranch'
```

## Command untuk menghapus branch pada lokal repo

```
git branch -d namaBranch
```
*command tersebut akan berjalan apabila pekerjaan terakhir sudah dicommit.*

```
git branch -D namaBranch
```
*command tersebut akan langsung menghapus branch (tidak peduli apakah sudah dilakukan commit atau tidak)*

## Skema Branch

![branch](https://miro.medium.com/max/618/1*GwR8-aZXPvJhhcacl4_x6Q.png)


