
# Hubungan Arsitektur CPU dengan Arsitektur OS
   Hubungan antara arsitektur CPU dan arsitektur OS sangat penting karena arsitektur CPU menetapkan batasan dan kemampuan perangkat keras yang dapat dimanfaatkan oleh sistem operasi dalam menjalankan tugas-tugasnya.
   CPU menentukan instruksi-instruksi yang dapat dieksekusi, cara akses memori, dan interaksi dengan perangkat I/O. Sementara itu, sistem operasi bertindak sebagai perantara antara aplikasi dan perangkat keras,
   mengelola sumber daya seperti memori dan CPU, serta menyediakan antarmuka yang diperlukan bagi pengguna untuk berinteraksi dengan sistem. 
   Hal tersebut menciptakan sebuah situasi di mana aplikasi dapat berjalan secara efisien dan diatur oleh sistem operasi sesuai dengan kemampuan serta batasan yang ditetapkan oleh arsitektur CPU.

# Fork : Parent - Child Process

- Akses dan clonning repo : https://github.com/ferryastika/operatingsystem.git
  
  ![Screenshot 2024-05-05 231552](https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/ee400007-d3bc-4116-9129-f93ebf00bd81)

- Deskripsikan dan visualisasikan pohon proses hasil eksekusi dari kode program fork01.c dan fork02.c

  Sebelum mengeksekusi kode program, install g++ terlebih dahulu di dalam root
  ```
  $ apt install g++
  ```
  
  ![Screenshot 2024-04-29 225639](https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/7f051032-2dfe-42da-929f-5967a1620ca4)

- setelah selesai menginstall, masuk ke direktori operatingsystem terlebih dahulu
  ```
  $ cd operatingsystem
  ```
  
  <img width="494" alt="image" src="https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/9597d67e-61dc-4341-88eb-b740348e0969">

- masuk ke teks editor yang berfungsi untuk menambah, menghapus, dan mengedit teks
  ```
  nano fork01.cpp
  ```
  <img width="496" alt="image" src="https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/a9b592fc-debd-4003-b4f5-8fad270807eb">
  
  simpan file diatas dengan ctrl + s lalu keluar dengan ctrl + x

- mengompilasi fork01.cpp menjadi fork01 menggunakan g++
  
  ```
  $ g++ fork01.cpp -o fork01
  ```
  <img width="329" alt="image" src="https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/f223c94a-0199-4332-923d-98b5a780f458">

- Selanjutnya menggunakan perintah ./fork01 untuk menjalankannya
  
  <img width="309" alt="image" src="https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/7f859b08-271b-41b0-a3df-0f653c01ca57">

  Keterangan : Program ini menampilkan ID proses (PID), ID proses induk (PPID), dan ID pengguna (UID) dan memprosesnya sebanyak 3 kali. Setiap proses sleep selama 3 detik menggunakan sleep(3).

 - Pada fork02.cpp juga menggunakan cara yang sama seperti fork01.cpp

   Masuk ke dalam teks editor

   ```
   nano fork02.cpp
   ```
   <img width="499" alt="image" src="https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/140d9f9c-bdcd-4bf6-8613-850d1984b8b9">
   
   simpan file diatas dengan ctrl + s lalu keluar dengan ctrl + x
   
  - kompilasi fork02.cpp menjadi fork02 menggunakan g++

   ```
   $ g++ fork02.cpp -o fork02
   ```
      <img width="335" alt="image" src="https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/9d78a5db-27a4-48a1-a01b-b59971757f74">

- Selanjutnya menggunakan perintah ./fork02 untuk menjalankannya
  
  <img width="493" alt="image" src="https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/d17a3658-cb4a-4a60-9417-73aa075e78b5">

  Keterangan : Program ini menampilkan PID dan nilai dari variabel x. program ini melakukan proses looping dan setelah mencetak PID dan nilai variabel x program akan sleep selama 2 detik menggunakan fungsi sleep(2) lalu nilai variabel x akan ditambah 1 tiap iterasi, untuk menghentikannya ketik ctrl + c

- Fork03.cpp juga menggunakan cara yang sama seperti sebelumnya
  Masuk kedalam teks editor

  ```
  $ nano fork03.cpp
  ```

  <img width="494" alt="image" src="https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/dd86fff1-5631-4e21-a6d8-e44c2a15994f">

   simpan file diatas dengan ctrl + s lalu keluar dengan ctrl + x

 - Kompilasi fork03.cpp menjadi fork03 menggunakan g++

   ```
   $ g++ fork03.cpp -o fork03
   ```

   <img width="324" alt="image" src="https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/abe22751-f06b-40d8-9a46-931a6bb881b5">

  - Selanjutnya, gunakan perintah ./fork03 untuk menjalankannya

    <img width="258" alt="image" src="https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/69fe73fe-2328-4a0b-b446-ace2923def73">

    Keterangan : Kedua proses, baik parent maupun child, mencetak pesan secara bergantian. Hal ini terjadi karena kedua proses berbagi sumber daya terminal dan saling bersaing dalam menulis ke terminal.
    
Pada setiap iterasi loop, salah satu dari proses induk atau anak akan mencetak pesan terlebih dahulu, kemudian proses yang lain akan mengambil alih dan mencetak pesan berikutnya.

Output yang dihasilkan menunjukkan bahwa kedua proses berjalan secara paralel, dengan masing-masing proses memiliki ID proses yang berbeda (PID 2259 untuk proses induk dan PID 2260 untuk proses anak).



# Orphan dan Zombie

- Sebelum menjalankan orphan, install gcc terlebih dahulu karena orphan menggunakan bahasa c

   <img width="365" alt="image" src="https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/70dec41c-02e1-444d-b24f-58d72741b026">

- Setelah selesai menginstall, login kedalam user lalu masuk ke direktori operatingsystem dan buka teks editor

  ```
  $ nano orphan.c
  ```

     <img width="497" alt="image" src="https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/57e24455-00ca-459d-8ca4-44a96cf76a39">

untuk menyimpannya ketik ctrl + s dan keluar dengan ctrl + x

- Ubah orphan.c menjadi orphan menggunakan compiler gcc
  ```
  $ gcc orphan.c -o orphan
  ```
  
  <img width="305" alt="image" src="https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/e0a8c0bf-67de-4b82-948e-d33066c3f5b2">

- Jalankan kode dengan menggunakan perintah ./orphan
  
  <img width="273" alt="image" src="https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/e98d86b4-b2c4-48ed-a0e2-0696c66f8c8d">

   keterangan : PID dari parent process adalah 2154.
  
   PID process dari child process adalah 2155 dan Parent ID 1138 menunjukkan bahwa child process memiliki Parent ID 1138.
  
   Setelah tidur selama 10 detik dengan menggunakan fungsi sleep(10) child process tetap memiliki parent process yang sama seperti sebelumnya, hal tersebut menunjukkan parent process telah selesai sebelum child process sehingga process tersebut dinamakan "orphan".
    

  masuk pada teks editor
  ```
  $ nano zombie.c
  ```

  <img width="495" alt="image" src="https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/c121e48a-cbca-40fc-b45d-98bd4bdb4db3">

  untuk menyimpannya ketik ctrl + s dan keluar dengan ctrl + x

- Ubah zombie.c menjadi zombie menggunakan compiler g++
  ```
  $ gcc zombie.c -o zombie
  ```

  <<img width="319" alt="image" src="https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/d204b7d1-73c2-4136-8e44-570e99036e41">

- Jalankan kode dengan menggunakan perintah ./zombie
    
  <img width="233" alt="image" src="https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/3afdde88-c784-463b-bb20-c427ccfe8302">

  keterangan : Parent process akan mencetak PIDnya sendiri dan tidur selama 60 detik menggunakan sleep(60), Child process akan segera keluar dari program setelah diciptakan dengan memanggil fungsi exit(0).


# Producer - Consumer problem 
Masalah Produsen-Konsumen adalah sebuah masalah klasik dalam sinkronisasi multi-proses dalam sistem operasi, yang berkaitan dengan penggunaan sumber daya bersama seperti buffer. Dalam masalah ini, terdapat sebuah buffer dengan ukuran tertentu yang digunakan oleh seorang produsen untuk memasukkan item ke dalamnya, dan oleh seorang konsumen untuk mengeluarkan item dari buffer tersebut. Masalah utamanya adalah mencegah produsen memasukkan item ke dalam buffer saat buffer sudah penuh, serta mencegah konsumen mengeluarkan item dari buffer saat buffer kosong.

Untuk mengatasi masalah tersebut, konsep semaphores digunakan. Semaphore adalah tipe data variabel atau abstrak yang digunakan untuk mengontrol akses ke sumber daya bersama oleh beberapa proses dalam sistem bersamaan. Dalam implementasi kode menggunakan bahasa C, semaphore digunakan untuk mengatur akses ke buffer, sehingga hanya satu proses (produsen atau konsumen) yang dapat mengakses buffer pada satu waktu.

Dalam kode contoh yang diberikan, terdapat implementasi masalah Produsen-Konsumen dengan satu produsen dan satu konsumen, serta dengan satu produsen dan tiga konsumen. Setiap proses (baik produsen maupun konsumen) diimplementasikan sebagai sebuah thread, dan semaphore digunakan untuk mengontrol akses ke buffer.

Dalam implementasi dengan satu produsen dan satu konsumen, terdapat sebuah buffer dengan ukuran satu, sedangkan dalam implementasi dengan satu produsen dan tiga konsumen, buffer dengan ukuran satu juga digunakan, dan konsumen mengonsumsi item dari buffer sesuai dengan pembagian yang sudah ditentukan.

Dengan menggunakan semaphore dan mutex lock, masalah sinkronisasi antara produsen dan konsumen dapat diatasi dengan baik, sehingga menghindari terjadinya kondisi balapan (race condition) dan masalah bagian kritis (critical section problem). Dengan demikian, masalah Produsen-Konsumen dapat dipecahkan dengan efektif dalam lingkungan pemrograman thread seperti dalam bahasa C.







    


  
  

