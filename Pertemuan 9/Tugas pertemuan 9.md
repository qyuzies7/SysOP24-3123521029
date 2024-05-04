
# Hubungan Arsitektur CPU dengan Arsitektur OS
   Hubungan antara arsitektur CPU dan arsitektur OS sangat penting karena arsitektur CPU menetapkan batasan dan kemampuan perangkat keras yang dapat dimanfaatkan oleh sistem operasi dalam menjalankan tugas-tugasnya.
   CPU menentukan instruksi-instruksi yang dapat dieksekusi, cara akses memori, dan interaksi dengan perangkat I/O. Sementara itu, sistem operasi bertindak sebagai perantara antara aplikasi dan perangkat keras,
   mengelola sumber daya seperti memori dan CPU, serta menyediakan antarmuka yang diperlukan bagi pengguna untuk berinteraksi dengan sistem. 
   Hal tersebut menciptakan sebuah situasi di mana aplikasi dapat berjalan secara efisien dan diatur oleh sistem operasi sesuai dengan kemampuan serta batasan yang ditetapkan oleh arsitektur CPU.

# Fork : Parent - Child Process

- Akses dan clonning repo : https://github.com/ferryastika/operatingsystem.git
  
  ![2024-04-28 at 21 34 12_c21c1a8b](https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/d87ecdcc-b4bc-43ee-acda-0c2d732a72e6)

- Deskripsikan dan visualisasikan pohon proses hasil eksekusi dari kode program fork01.c dan fork02.c

  Sebelum mengeksekusi kode program, install g++ terlebih dahulu
  ```
  $ apt install g++
  ```
  
  ![Screenshot 2024-04-29 225639](https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/7f051032-2dfe-42da-929f-5967a1620ca4)

- setelah selesai menginstall, masuk ke direktori operatingsystem terlebih dahulu
  ```
  $ cd operatingsystem
  ```
  
  ![Screenshot 2024-04-30 000841](https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/d717d9e0-e735-4a2d-b4d0-5162544a1ff5)

- Kemudian masuk ke teks editor
  ```
  $ nano fork01.cpp
  ```
  
  ![Screenshot 2024-04-30 004122](https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/5b051da2-2061-4370-84fd-0e8c3c958555)


- inputkan source code fork01.cpp seperti dibawah ini
  
  <img width="497" alt="image" src="https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/bf1ee904-93f9-4c73-8854-e1b07655d786">

  simpan file diatas dengan ctrl + s lalu keluar dengan ctrl + x

- ubah file.cpp menjadi file.exe dengan menggunakan compiler g++

  ```
  $ g++ fork01.cpp -o fork01.exe
  ```
  
  <img width="344" alt="image" src="https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/68a0ad32-f246-44c1-b638-d9104e7d7306">

- Selanjutnya menggunakan perintah ./fork01.exe untuk menjalankannya
  
  <img width="293" alt="image" src="https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/18f58a70-7e25-4b07-8967-4cda4c673feb">

  Keterangan : Program ini menampilkan ID proses (PID), ID proses induk (PPID), dan ID pengguna (UID) dan memprosesnya sebanyak 3 kali.

 - Pada fork02.cpp juga menggunakan cara yang sama seperti fork01.cpp
   masuk ke teks editor fork02.cpp

   ```
   $ nano fork02.cpp
   ```
   
    <img width="279" alt="image" src="https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/bf2a58f2-6a29-49c5-b034-03f5665b935d">

- inputkan source code fork02.cpp seperti dibawah ini
  <img width="494" alt="image" src="https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/7ea96a10-b8cf-446e-9f5a-9f81e94ca883">
  
  simpan file diatas dengan ctrl + s lalu keluar dengan ctrl + x

- ubah file.cpp menjadi file.exe dengan menggunakan compiler g++

  ```
  $ g++ fork02.cpp -o fork02.exe
  ```
  
  <img width="335" alt="image" src="https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/1897dfa9-007f-4679-99ea-8692c95ed753">

- Selanjutnya menggunakan perintah ./fork02.exe untuk menjalankannya
  
  <img width="303" alt="image" src="https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/ea01ee7d-c46a-4731-9d03-3544b833cceb">
  
  Keterangan : Program ini menampilkan PID dan nilai dari variabel x. program ini melakukan proses looping dan untuk menghentikannya ketik ctrl + c

# Orphan dan Zombie

- Sebelum menjalankan orphan, masuk pada teks editor dengan cara seperti fork01 dan fork02
  ```
  $ nano orphan.c
  ```
  
  <img width="491" alt="image" src="https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/d29f3c28-80c6-4976-aa5e-33946d39c3dc">

  simpan file diatas dengan ctrl + s lalu keluar dengan ctrl + x

- Ubah file.c menjadi file.exe menggunakan compiler g++
  ```
  $ g++ orphan.c -o orphan.exe
  ```
  
  <img width="337" alt="image" src="https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/509526f6-4a2a-4f2b-b931-10bc114aba28">

- Jalankan kode dengan menggunakan perintah ./orphan.exe
  
  <img width="315" alt="image" src="https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/332405f6-d328-4294-983e-2ed3342748fc">

- untuk menjalankan zombie, gunakan cara yang sama seperti pada proses orphan

  masuk pada teks editor
  ```
  $ nano zombie.c
  ```

  <img width="493" alt="image" src="https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/924f3fcc-92c5-4c12-99b0-6cf95ec1c263">

  untuk menyimpannya ketik ctrl + s dan keluar dengan ctrl + x

- Ubah file.c menjadi file.exe menggunakan compiler g++
  ```
  $ g++ zombie.c -o zombie.exe
  ```

  <img width="336" alt="image" src="https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/58bbddf2-6f72-4f7f-adac-495307efd758">

- Jalankan kode dengan menggunakan perintah ./zombie.exe
    
  <img width="273" alt="image" src="https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/858285e5-7a9a-43aa-a271-e79de847d6d4">

# Producer - Consumer problem 
Masalah Produsen-Konsumen adalah sebuah masalah klasik dalam sinkronisasi multi-proses dalam sistem operasi, yang berkaitan dengan penggunaan sumber daya bersama seperti buffer. Dalam masalah ini, terdapat sebuah buffer dengan ukuran tertentu yang digunakan oleh seorang produsen untuk memasukkan item ke dalamnya, dan oleh seorang konsumen untuk mengeluarkan item dari buffer tersebut. Masalah utamanya adalah mencegah produsen memasukkan item ke dalam buffer saat buffer sudah penuh, serta mencegah konsumen mengeluarkan item dari buffer saat buffer kosong.

Untuk mengatasi masalah tersebut, konsep semaphores digunakan. Semaphore adalah tipe data variabel atau abstrak yang digunakan untuk mengontrol akses ke sumber daya bersama oleh beberapa proses dalam sistem bersamaan. Dalam implementasi kode menggunakan bahasa C, semaphore digunakan untuk mengatur akses ke buffer, sehingga hanya satu proses (produsen atau konsumen) yang dapat mengakses buffer pada satu waktu.

Dalam kode contoh yang diberikan, terdapat implementasi masalah Produsen-Konsumen dengan satu produsen dan satu konsumen, serta dengan satu produsen dan tiga konsumen. Setiap proses (baik produsen maupun konsumen) diimplementasikan sebagai sebuah thread, dan semaphore digunakan untuk mengontrol akses ke buffer.

Dalam implementasi dengan satu produsen dan satu konsumen, terdapat sebuah buffer dengan ukuran satu, sedangkan dalam implementasi dengan satu produsen dan tiga konsumen, buffer dengan ukuran satu juga digunakan, dan konsumen mengonsumsi item dari buffer sesuai dengan pembagian yang sudah ditentukan.

Dengan menggunakan semaphore dan mutex lock, masalah sinkronisasi antara produsen dan konsumen dapat diatasi dengan baik, sehingga menghindari terjadinya kondisi balapan (race condition) dan masalah bagian kritis (critical section problem). Dengan demikian, masalah Produsen-Konsumen dapat dipecahkan dengan efektif dalam lingkungan pemrograman thread seperti dalam bahasa C.







    


  
  

