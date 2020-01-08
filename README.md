# How to Add Git in Existing Project

- **Membuat Repository Baru di dalam Version Control (misalnya GitHub)** <br/>
  
  Siapkan Repository di dalam GitHub dengan menekan tombol New Repository.
   
   ![newrepository](https://help.github.com/assets/images/help/repository/repo-create.png)

- **Buka Git Bash** <br/>
  
  Membuka git bash di dalam komputer lokal

- **Ganti working direktoy sesuai dengan posisi project yang sudah ada melalui gitbash** <br/>

- **Menginisialisasi Repository** <br/>
  
  Membuat direktory project pada komputer lokal sebagai Git Repository baru menggunakan command berikut

  ```
  git init
  ```

- **Menambahkan file ke dalam Staging Area** <br/>

    Membuat semua source code file pada project masuk ke dalam staging area menggunakan command berikut

    ```
    git add .
    ```

 - **Melakukan Commit** <br/>

    Melakukan commit pertama agar semua file di dalam project dapat disimpan perubahannya. command yang digunakan sebagai berikut

    ```
    git commit -m 'komentar dan pesan'
    ```
 - **Menambahkan repository sebagai remote** <br/>

    Membuat repository GitHub yang telah dibuat tadi sebagai Remote dari lokal komputer kita. command yang digunakan sebagai berikut 
    ```
    git remote add origin remote 'alamat repository'
    ```

- **Melakukan push** <br/>

    Melakukan push kepada remote origin (Repository di dalam Git Hub) yang sudah diinisialisasi. command yang digunakan sebagai berikut

    ```
    git push origin 'nama branch'
    ```


