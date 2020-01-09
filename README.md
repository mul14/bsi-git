# Cherry Pick

Cherry picking pada Git mengartikan untuk memilih sebuah commit pada salah satu cabang dan kemudian diaplikasikan untuk cabang yang lain. Cara ini berbeda dari konsep merge dan rebase yang mana diaplikasikan untuk banyak commit pada salah satu cabang. Contoh melakukan Cherry Picking:
- Pastikan dir pada salah cabang yang akan diaplikasikan commit
```
git checkout master
```
- Jalankan perintah ini
```
git cherry-pick <commit-hash>
```