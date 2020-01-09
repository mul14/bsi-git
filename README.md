# DIFFERENCE BETWEEN MERGE AND REBASE

![gambar branching][0]
##### Gambar 1. Ilustrasi branch (Atlassian)

## `git rebase`
Perintah `git rebase` digunakan ketika kita akan menyatukan antara _branch master_ dengan _branch_ fitur yang sedang kita buat. Penggabungan bersifat menghilangkan _branch_, sehingga apa yang di `commit` pada repository seakan-akan menyambung di depan _branch_ master. Contoh gambar 1 jika dilakukan `git rebase` maka `commit` _branch feature_ akan disambungkan di depan _branch master_.
![gambar rebase][1]
##### Gambar 2. Ilustrasi `git rebase` (Atlassian)

Rebase tidak dianjurkan digunakan untuk push remote repository. Hal ini disebabkan karena rawan terjadi conflict ketika terdapat orang lain yang bekerja di repository tersebut.

## `git merge`
Perintah ini hampir sama dengan perintah git rebase. Yang membedakan adalah branch feature tetap dipertahankan dan penggabungan akan dilakukan pada commit baru di branch feature. Untuk lebih mudah memahaminya, gambar 3 merupakan ilustrasi git merge.
![gambar rebase][2]
##### Gambar 2. Ilustrasi `git merge` (Atlassian)


[0]: https://wac-cdn.atlassian.com/dam/jcr:01b0b04e-64f3-4659-af21-c4d86bc7cb0b/01.svg?cdnVersion=745
[1]: https://wac-cdn.atlassian.com/dam/jcr:5b153a22-38be-40d0-aec8-5f2fffc771e5/03.svg?cdnVersion=745
[2]: https://wac-cdn.atlassian.com/dam/jcr:e229fef6-2c2f-4a4f-b270-e1e1baa94055/02.svg?cdnVersion=745