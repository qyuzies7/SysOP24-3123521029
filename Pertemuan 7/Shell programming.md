# Shell Programming
## Tugas Pendahuluan 
1. Apa yang dimaksud redirection
   <br/>
  Jawab : Redirection adalah pembelokan yang dilakukan untuk standard input, output dan error, yaitu untuk mengalihkan file descriptor dari 0, 1 dan 2.
2. Apa yang dimaksud pipeline
   <br/>
   Jawab : Pipeline adalah mekanisme pipa digunakan sebagai alat komunikasi antar proses.
3. Apa yang dimaksud perintah di bawah ini : echo, cat, more, sort, grep, wc, cut, uniq
   <br/>
   Jawab :
   - Echo digunakan untuk menampilkan output kelayar.
   - Cat digunakan untuk menghasilkan output kelayar dan merupakan berasal dari input sebuah keyboard.
   - More merupakan perintah untuk mempaging halaman.
   - sort digunakan untuk mengurutkan masukannya berdasarkan urutan nomor ASCII dari karakter.
   - grep digunakan untuk menyaring masukannya dan menampilkan baris-baris yang hanya mengandung pola yang ditentukan, pola ini disebut regular expression.
   - wc digunakan untuk menghitung jumlah baris, kata dan karakter dari baris-baris masukan yang diberikan kepadanya.
   - cut digunakan untuk mengambil kolom tertentu dari baris-baris masukannya, yang ditentukan pada option –c.
   - uniq digunakan untuk menghilangkan baris-baris berurutan yang mengalami duplikasi.
     
  ## PERCOBAAN :
  1. Login sebagai user.
  2. Bukalah Console Terminal dan lakukan percobaan-percobaan di bawah ini. Perhatikan hasil setiap percobaan.
  3. Selesaikan soal-soal latihan.

  ### Percobaan 1 : File Descriptor
  ```sh
  $ ps
  ```
  <img width="400" alt="image" src="https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/a81989a0-28a2-4eb6-95be-41b217ad9a4c">
  
  Analisis : Perintah $ ps digunakan untuk menampilkan informasi tentang proses yang sedang berjalan di sistem operasi

  
  ```sh
  $ cat
 hallo, apa khabar
 hallo, apa khabar
 exit dengan ^d
 exit dengan ^d
 [Ctrl-d]
```
<img width="200" alt="image" src="https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/766b14f3-5458-46fb-921b-aa8ebb215f05">

Analisis : Perintah $ cat digunakan untuk menggabungkan dan menampilkan isi dari satu atau beberapa file teks secara langsung


```sh
$ mkdir mydir
$ mkdir mydir **(Terdapat pesan error)**
```
<img width="400" alt="image" src="https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/e0efcec4-c0d1-4163-a659-00d525067470">

Analisis : Perintah $ mkdir merupakan perintah untuk membuat direktori yang baru sesuai dengan nama yang disebutkan setelahnya, namun apabila membuat direktori lagi dengan format nama yang sama maka akan muncul pesan cannot create directory, hal tersebut dikarenakan kita tidak memberi nama yang berbeda pada direktori yang baru.

### Percobaan 2 : Pembelokan (redirection)
```sh
$ cat 1> myfile.txt
 Ini adalah teks yang saya simpan ke file myfile.txt
```
<img width="400" alt="image" src="https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/a476815d-14fb-4745-a23e-0dbfb41046ee">

Analisis : Analisis : Perintah $ cat 1> myfile.txt digunakan untuk membelokkan standar input kedalam satu file bernama myfile.txt


```sh
 $ cat 0< myfile.txt
 $ cat myfile.txt
```
<img width="400" alt="image" src="https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/6f63ff7b-0b65-43ae-a8e8-1ab2645bc05e">

Analisis : Perintah $ cat 0< myfile.txt digunakan untuk menampilkan text yang telah disimpan dalam myfile.txt


```sh
 $ mkdir mydir (Terdapat pesan error)
 $ mkdir mydir 2> myerror.txt
 $ cat myerror.txt
```
<img width="400" alt="image" src="https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/e3525d63-879b-48d4-911e-069eeccc6340">

Analisis : Perintah mkdir mydir yang pertama error disebabkan nama yang diberikan pada direktori baru sama,perintah kedua mkdir mydir 2> myerror.txt, menggunakan operator pembelokan (2>) untuk membelokkan standard error (stderr) dari perintah mkdir ke dalam file yang disebut myerror.txt. pesan error tersebut akan disimpan dalam file dan tidak akan ditampilkan dalam layar


```sh
 $ ls filebaru (Terdapat pesan error)
 $ ls filebaru 2> out.txt
 $ cat out.txt
 $ ls filebaru 2> out.txt 2>&
 $ cat out.txt
```
<img width="400" alt="image" src="https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/d06c25ec-4ebb-4517-a2a7-23c53405fc94">

Analisis : perintah ls filebaru terjadi error kemungkinan dikarenakan tidak ada filebaru atau tidak memiliki izin untuk membaca direktori tersebut, dengan menambahkan 2> ke perintah,  mengarahkan pesan error (stderr) dari perintah ls ke dalam file "out.txt". hal ini memungkinkan untuk menyimpan pesan error untuk diperiksa nanti. Perintah $ cat out.txt digunakan untuk menampilkan isi file "out.txt" yang berisi pesan error yang dihasilkan oleh perintah ls sebelumnya. Perintah $ ls filebaru 2> out.txt 2>&1  mengarahkan baik stdout (keluaran standar) maupun stderr (keluaran kesalahan) ke dalam file "out.txt". Perintah$ cat out.txt  untuk menampilkan isi file "out.txt" setelah kedua jenis keluaran (stdout dan stderr) diarahkan ke dalamnya


```sh
$ echo “mencoba menulis file” 1> baru
$ cat filebaru 2> baru 1>&
$ cat baru
```
<img width="400" alt="image" src="https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/18740e8c-ab2f-42bc-aa79-070a7ee278e9">

Analisis : : Perintah $ echo “mencoba menulis file” 1> baru untuk menulis teks "mencoba menulis file" ke dalam file yang bernama "baru" dengan menggunakan operator redireksi 1>, perintah $ cat filebaru 2> baru 1>&2  untuk membaca isi dari file "filebaru" dan mengarahkan stderr ke stdout (1>&2), perintah $ cat baru untuk menampilkan isi dari file "baru," yang dihasilkan oleh perintah sebelumnya.


```sh
$ echo “kata pertama” > surat
$ echo “kata kedua” >> surat
$ echo “kata ketiga” >> surat
$ cat surat
$ echo “kata keempat” > surat
$ cat surat
```
<img width="400" alt="image" src="https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/f43dfdfb-1e86-41b4-be9f-dd147f45e8cf">

Analisis : Perintah pertama sampai ketiga menghasilkan file "surat" dengan isi "kata pertama", "kata kedua", dan "kata ketiga", perintah $ cat surat menampilkan isi file "surat" setelah penambahan kata ketiga, perintah $ echo “kata keempat” > surat menggantikan isi file "surat" dengan "kata keempat", dan perintah $ cat surat menampilkan isi file "surat" setelah penggantian, sehingga isi sebelumnya ("kata pertama", "kata kedua", dan "kata ketiga") telah digantikan dengan "kata keempat".


```sh
$ cat <<++
Hallo, apa kabar?
Baik-baik saja?
Ok!
++
$ cat <<%%%
Hallo, apa kabar?
Baik-baik saja?
Ok!
%%%
```
<img width="200" alt="image" src="https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/e3349512-fe2c-44a5-a01d-7d0b44764b1e">

Analisis : Perintah cat <<++ dan cat <<%%% digunakan untuk memasukkan teks ke dalam perintah cat tanpa menggunakan file eksternal


```sh
$ cat myfile.txt – surat
```
<img width="400" alt="image" src="https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/90d3bf33-eab5-4b1e-a75d-47f3bc288239">

Analisis : Perintah $ cat myfile.txt – surat digunakan untuk menggabungkan isi dari dua file, yaitu "myfile.txt" dan "surat", dengan menggunakan perintah cat

### Percobaan 3 : Pipa (pipeline)
```sh
$ who
$ who | sort
$ who | sort –r
$ who > tmp
$ sort tmp
$ rm tmp
$ ls –l /etc | more
$ ls –l /etc | sort | more
```
<img width="227" alt="image" src="https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/2b0c95fc-868c-4d7f-be1a-a1f929635d6a">
<br/>
<img width="311" alt="image" src="https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/76c20ded-7192-4910-9e5c-fa997181b3ed">
<br/>
<img width="293" alt="image" src="https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/68231d51-697f-4bec-a435-2086d6a77296">

Analisis : Perintah $ who menampilkan daftar pengguna yang saat ini masuk ke sistem. Dengan menambah | sort daftar pengguna yang sedang masuk diurutkan secara alfabet berdasarkan nama pengguna.menambahkan sort -r untuk mengurutkan daftar pengguna yang sedang masuk secara terbalik (dari Z ke A). menambahkan > tmp digunakan untuk menyimpan output dari who ke dalam file "tmp". Sort tmp digunakan untuk mengurutkan isi file "tmp" secara alfabet. Rm tmp digunakan untuk menghapus file "tmp" yang telah digunakan sebelumnya. Perintah $ ls -l /etc | more untuk menampilkan detail file dan direktori dalam /etc dengan menggunakan perintah ls -l dan more untuk mengatur hasil keluaran dengan paging. Perintah $ ls –l /etc | sort | more menampilkan detail file dan direktori dalam /etc, mengurutkannya secara alfabetis menggunakan sort, dan menampilkannya dengan paging menggunakan more.


```sh
$ echo hello
$ echo hello > output
$ cat output
```
<img width="250" alt="image" src="https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/6d2dabc3-d8fe-4d6d-8c7f-1869404a268a">

Analisis : Perintah  $ echo hello digunakan untuk menampilkan teks "hello" di layar, perintah $ echo hello > output digunakan untuk menampilkan “hello”  ke dalam "output". Perintah ketiga digunakan untuk menampilkan isi dari file "output"


```sh
$ echo bye >> output
$ cat output
```
<img width="280" alt="image" src="https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/06e5d167-4572-401a-a990-5073af2d5dd2">

Analisis : Perintah $ echo bye >> output digunakan untuk menambahkan teks "bye" ke dalam "output" tanpa menghapus isi yang sudah ada sebelumnya. Jika file "output" belum ada, maka akan dibuat. $ cat output untuk menampilkan isi dari file "output". Outputnya akan mencakup "hello" (perintah sebelumnya) dan "bye" (perintah saat ini).


```sh
$ cat < output
```
<img width="300" alt="image" src="https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/282f09a4-e7ca-4095-8175-226f7a9fa585">

Analisis : Perintah $ cat < output digunakan untuk menampilkan isi dari file "output" ke layar


```sh
$ cat < output > out
$ cat out
$ cat < output >> out
$ cat out
$ cat < output > output
$ cat output
$ cat < out >> out (Proses tidak berhenti)
[Ctrl-c]
$ cat out
```
<img width="300" alt="image" src="https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/7eeee74d-7853-4c44-a97c-1f3c0b3596cf">

Analisis : Perintah pertama sampai dengan perintah keempat menunjukkan proses menyalin dan menambahkan isi file "output" ke dalam file "out". Perintah kelima digunakan untuk menggantikan isi file "output" dengan salinan yang baru. Perintah kelima digunakan untuk menampilkan isi dari file "output" perintah keempat. Perintah tujuh untuk menambahkan isi file "out" ke akhir file "out" dan [Ctrl-c] untuk menghentikan proses tersebut. Perintah kedelapan menunjukkan isi dari file "out" setelah semua langkah di atas.

### Percobaan 4 : Filter
```sh
 $ w –h | grep <user>
 $ grep <user> /etc/passwd
 $ ls /etc | wc
 $ ls /etc | wc –l
 $ cat > kelas1.txt
 Badu
 Zulkifli
 Yulizir
 Yudi
 Ade
 [Ctrl-d]
 $ cat > kelas2.txt
 Budi
 Gama
 Asep
 Muchlis
 [Ctrl-d]
 $ cat kelas1.txt kelas2.txt | sort
 $ cat kelas1.txt kelas2.txt > kelas.txt
 $ cat kelas.txt | sort | uniq
```
<img width="395" alt="image" src="https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/9c65d3d0-d4b7-48f0-8380-c9242a410f13">
<br/>
<img width="261" alt="image" src="https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/56c54441-3622-4eb8-a0b4-ba56ba14c1c3">

Analisis : Perintah $ w –h | grep <user>  untuk menampilkan informasi pengguna yang sedang masuk, lalu mengonversi outputnya menggunakan grep <user> untuk mencari baris yang mencakup nama pengguna tertentu. Perintah $ grep <user> /etc/passwd untuk menampilkan informasi pengguna yang sedang masuk, lalu mengonversi outputnya menggunakan grep <user> untuk mencari baris yang mencakup nama pengguna tertentu.
Perintah $ ls /etc | wc untuk menampilkan daftar file dan direktori dalam /etc, lalu menghitung jumlah baris menggunakan wc. Perintah $ ls /etc | wc –l sama seperti perintah sebelumnya, tetapi hanya menghitung jumlah baris menggunakan opsi -l pada wc. Perintah $ cat > kelas1.txt untuk membuat dan mengisi file "kelas1.txt" dengan nama-nama mahasiswa. Input diakhiri dengan [Ctrl-d]. Perintah $ cat > kelas2.txt sama dengan perintah sebelumnya, tetapi untuk file "kelas2.txt". Perintah $ cat kelas1.txt kelas2.txt | sort untuk menggabungkan isi kedua file, lalu mengurutkannya secara alfabetis dengan menggunakan sort. Perintah $ cat kelas1.txt kelas2.txt > kelas.txt menggabungkan isi kedua file "kelas1.txt" dan "kelas2.txt" ke dalam file baru "kelas.txt". Perintah $ cat kelas.txt | sort | uniq menggunakan cat untuk menampilkan isi file "kelas.txt", mengurutkannya secara alfabetis dengan sort, dan menghapus baris duplikat dengan uniq.

## Latihan
1. Lihat daftar secara lengkap pada direktori aktif, belokkan tampilan standard output ke file baru.
<img width="272" alt="image" src="https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/ae3ab3c0-b256-4df4-83a4-d9a237034dcd">

Analisis : ls – digunakan untuk melihat daftar secara lengkap pada direktori aktif, operator  > digunakan untuk membelokkan tampilan standard output ke dalam file baru yang disebut "file.txt"

2. Lihat daftar secara lengkap pada direktori /etc/passwd, belokkan tampilan standard output ke file baru tanpa menghapus file baru sebelumnya.
<img width="249" alt="image" src="https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/2732ef8c-7153-409b-b48d-e2cf6149fb80">

Analisis : Dengan menggunakan perintah ls -l,  dapat melihat daftar lengkap dengan informasi detail dari file /etc/passwd dan menyimpannya ke dalam file "file.txt".

3. Urutkan file baru dengan cara membelokkan standard input.
<img width="394" alt="image" src="https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/a9e88cf3-52aa-4bec-87a2-c19b2ef34a43">

Analisis :Menggunakan  $ sort < file.txt. menggunakan operator < untuk membelokkan isi file "file.txt" ke dalam perintah sort dimana sort akan mengurutkan baris-baris yang berasal dari file "file.txt" dan menampilkannya di layar.

4. Urutkan file baru dengan cara membelokkan standard input dan standard output ke file baru.urut.
<img width="251" alt="image" src="https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/bfd3d103-0bb4-4bcc-a46f-a16bf8b2f4f3">

Analisis : Perintah cat baru.urut akan menampilkan isi dari file baru.urut

5. Buatlah direktori latihan 2 sebanyak 2 kali dan belokkan standard error ke file rmdirerror.txt.
<img width="250" alt="image" src="https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/9f1e14f2-bc54-41f7-9982-fe516a6649ff">

Analisis : Menggunakan mkdir untuk membuat direktori "latihan2" sebanyak dua kali.Jika direktori sudah ada sebelumnya, perintah ini mungkin menghasilkan pesan error. menggunakan rmdir untuk mencoba menghapus direktori "latihan2". Jika berhasil, tidak akan ada keluaran ke layar. Namun, jika ada kesalahan, pesan kesalahan akan ditangkap dan dibelokkan ke file "rmdirerror.txt" dengan menggunakan operator 2>.


6. Urutkan kalimat berikut :
   Jakarta
  Bandung
  Surabaya
  Padang
  Palembang
  Lampung
  Dengan menggunakan notasi here document (<@@@ ...@@@).
<img width="200" alt="image" src="https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/2799fcdf-27ac-4f6a-86d5-59890a15281c">

Analisis : menggunakan notasi  (<<@@@) untuk memberikan input langsung ke perintah sort dari beberapa baris kalimat. Kalimat-kalimat yang diberikan diurutkan oleh perintah sort.

7. Hitung jumlah baris, kata dan karakter dari file baru.urut dengan menggunakan filter dan tambahkan data tersebut ke file baru.
<img width="250" alt="image" src="https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/2aaa0f0b-f1ca-4f90-b66e-9688077c7da4">

Analisis : cat baru.urut | wc digunakan untukn menghitung jumlah baris, kata, dan byte dalam file. cat baru.urut | wc -l digunakakn untuk menghitung jumlah baris dalam file. cat baru.urut | wc -c digunakan untuk menghitung jumlah byte. cat baru.urut | wc -w digunakan untuk menghitung jumlah kata dalam file  

8. Gunakan perintah dibawah ini dan perhatikan hasilnya.
```sh
 $ cat > hello.txt
 dog cat
 cat duck
 dog chicken
 chicken duck
 chicken cat
 dog duck
 [Ctrl-d]
 $ cat hello.txt | sort | uniq
 $ cat hello.txt | grep “dog” | grep –v “cat”
```
<img width="300" alt="image" src="https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/a271b12a-fda4-40bd-bdbb-cba703dce368">

Analisis : Perintah pertama menggunakan cat > hello.txt untuk membuat dan mengisi file "hello.txt" dengan beberapa baris teks. Input diakhiri dengan [Ctrl-d]. Perintah kedua mengurutkan dan menghapus duplikat dari isi file "hello.txt". Perintah ketiga mencari baris yang mengandung kata "dog" dan menghindari baris yang mengandung kata "cat" dari isi file "hello.txt".

## KESIMPULAN : 
Dari percobaan dan latihan yang telah saya lakukan, memberikan pemahaman tentang penggunaan perintah dasar linux seperti :
- pengunaan perintah-perintah seperti echo, cat, dan rm untuk manipulasi file dan direktori.
- sort, uniq, dan grep untuk menyaring, mengurutkan, dan menganalisis isi file.
- [Ctrl-d] digunakan untuk menunjukkan End Of File, terutama ketika memasukkan data atau menyelesaikan sesi pengeditan pada beberapa program atau editor
- ls, cat, dan wc digunakan untuk mengakses dan mengelola informasi sistem, seperti daftar file, isi file, dan statistik file.

