<h1> Branching Model With GitFLow </h1>

<details>
    <summary> Getting Started </summary>

    Gitflow adalah sebuah branching model git yang diciptakan oleh Vincent Driessen. Gitflow sangat ideal untuk proyek yang memiliki siklus rilis yang terjadwal. Untuk lebih jelasnya saya akan menjelaskan satu siklus penggunaan gitflow.
</details>

## DEVELOP AND MASTER BRANCHES

Gunakan command git flow init dalam folder repositori.

```
$ git flow init
```

![gitflow](https://miro.medium.com/max/929/0*mdbFVAu6MBm_zWWY)

Gunakan command git branch untuk melihat branch yang telah terbentuk

```
$ git branch
```

![](https://miro.medium.com/max/690/0*i7ZDks3Y92nvFXJU)

Create sebuah ```file.txt``` yang akan digunakan sebagai bahan praktik dalam penggunaan gitflow. Sebaiknya file yang dibuat langsung di push ke master untuk mempermudah membandingkan ketika melakukan merge dalam tahap selanjutnya.

## Feature Branches

![](https://wac-cdn.atlassian.com/dam/jcr:b5259cce-6245-49f2-b89b-9871f9ee3fa4/03%20(2).svg?cdnVersion=743)

Feature branches digunakan untuk membangun fitur yang akan digunakan. Esensi dari feature branch adalah branch akan ada selama proses development. Singkatnya, feature branch hanya ada di developer bukan di origin. Proses di feature branch yaitu :

```
$ git flow feature start MyFeature
```

![](https://miro.medium.com/max/980/0*n0YbjU1Bt9OBmhPL)

Selama pengerjaan fitur di sistem, developer akan berada di branch MyFeature. Sebagai ganti dari fitur, tuliskan sesuatu di dalam file yang telah dibuat sebelumnya sebagai pertanda bahwa sudah ada penambahan. Jangan lupa untuk melakukan proses commit agar gitnya terupdate.

```
$ git flow feature finish MyFeature
```
![](https://miro.medium.com/max/1005/0*FdLY0ysb12WU2PQ4)

Sebelum dilakukan proses finish pada branch, terlebih dahulu yang dilakukan adalah proses testing. Hal ini dilakukan untuk mencegah adanya error ketika branch dimerge ke develop.

## RELEASE BRANCHES

![](https://wac-cdn.atlassian.com/dam/jcr:a9cea7b7-23c3-41a7-a4e0-affa053d9ea7/04%20(1).svg?cdnVersion=743)

Setelah selesai dari branch develop, langkah selanjutnya yaitu proses release. Branch release biasanya digunakan untuk persiapan ke production, dalam branch ini masih diperbolehkan untuk melakukan perubahan tetapi hanya untuk skala kecil saja. Jika terdapat bug yang memerlukan banyak perubahan seperti fitur tambahan maka branch akan dikembalikan ke develop. Branch release dibuat dari branch develop dengan penambahan version number. Langkah pembuatan branch release yaitu :

```
$ git flow release start 0.1.0
```

![](https://miro.medium.com/max/930/0*uty7WzOqORjlm4q8)

Setelah sistem telah melalui proses testing maka proses release dapat diakhiri.

```
$ git flow release finish 0.1.0
```
Setelah proses release selesai maka branch akan di merge ke branch master dan develop.

## HOTFIX BRANCHES

![](https://wac-cdn.atlassian.com/dam/jcr:61ccc620-5249-4338-be66-94d563f2843c/05%20(2).svg?cdnVersion=743)

Tidak dapat dipungkiri bahwa akan ada masanya branch di master terdapat error oleh karena itu diperlukan branch hotfix untuk melakukan perbaikan secepatnya. Oleh karena itu branch hotfix hanya akan di buat dari master. Berikut adalah tahapan dalam branch hotfix.

```
$ git flow hotfix start branch_hotfix
```

![](https://miro.medium.com/max/1058/0*WBU9-d7G_0U0vOo5)

```
$ git flow hotfix finish branch_hotfix
```

## SUMMARY

Kesimpulannya Gitflow adalah:

1. Develop branch dibuat oleh master
2. Release branch dibuat oleh develop
3. Feature branches dibuat develop
4. Ketika sebuah feature selesai maka akan di merge ke develop branch
5. Ketika sebuah release branch selesai akan di merge ke develop dan master
6. Jika ada issue didalam master ditemukan maka hotfix branch dibuat oleh master
7. Ketika hotfix sudah selesai maka akan di merge ke develop dan master