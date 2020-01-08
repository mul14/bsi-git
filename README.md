# GIT LOG


## What is Git Log ???
Git Log adalah salah satu perintah dalam git yang apabila dijalankan akan menampilkan daftar commits yang ada di branch beserta detail-nya. Dengan menggunakan perintah git log dapat melihat catatan log perubahan pada repositori.

## Format Git Log ???
```
git log
```
Contoh Penggunaan :
![Git Log Format][FormatGItLog]


## Specific Commit ??
```
git log --oneline
```
### Contoh Penggunaan :
![Git Log Format Commit][FormatGItLogCommit]
## Filter Logs by date, file name, author ??
1. by date
   ```
   $ git log --after="yy-mm-dd"  
   ```
   ### Contoh Penggunaan :
   ![Git Log Format Date][FormatGitLogDate]
2. by file name
   ```
   git log <filename>
   ```
   ### Contoh Penggunaan :
   ![Git Log Format File Name][FormatGitLogFileName]
3. by author
   ```
   git log --author="NamaAuthor"
   ```
   ### Contoh Penggunaan :
      ![Git Log Format Author][FormatGitLogAuthor]

[FormatGitLog]:https://1.bp.blogspot.com/-BEp5Qadw3U0/WKJkMIVKV4I/AAAAAAAAD50/p7u0PSctYIkLDOnV_zLMhN29ZwIlImv2ACPcB/s1600/Log%2Brevisi%2Byang%2Bsudah%2Bdibuat.png
[FormatGitLogCommit]:https://1.bp.blogspot.com/-d_yfxMviMs4/W2HIoMV68YI/AAAAAAAAAa4/4Uv7O52Wm4gGLu9yJoPR0KuDeDB-PlykQCLcBGAs/s400/log%2Bsetelah%2Bkonflik.jpg
[FormatGitLogDate]:https://static.javatpoint.com/tutorial/git/images/git-log-5.png
[FormatGitLogAuthor]:https://static.javatpoint.com/tutorial/git/images/git-log-8.png
[FormatGitLogFileName]:https://www.toolsqa.com/wp-content/gallery/git/git_log_filename_2.png
