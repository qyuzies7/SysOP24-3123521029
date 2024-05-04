# TUGAS 3
## 1. Siklus CPU (Fetch, Decode, Execute)
- Fetch : CPU mengambil instruksi program dari memori utama, Instruksi berikutnya diambil dari alamat memori yang tersimpan dalam Program Counter(PC), dan disimpan dalam Instruction Regrister(IR).
- Decode : CPU menerjemahkan instruksi menjadi operasi yang mudah dipahami dan memecah instruksi menjadi bagian-bagian yang sederhana.
- Execute : CPU menjalankan instruksi yang telah didecode sebelumnya.
## Fetch Decode Execute in more detail
![siklus cpu 1](https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/3be86826-756a-4d86-b5e7-45bc1c86a28c)

Keterangan : <br/>
LOAD yaitu mengambil nilai dari lokasi memori 10 dan simpan ke dalam akumulator. <br/>
ADD yaitu melakukan penambahan antara nilai yang ada di lokasi memori 11 dan nilai yang saat ini tersimpan di akumulator. <br/>
STORE yaitu menyimpan hasil penjumlahan yang ada di akumulator ke dalam lokasi memori 12.
![siklus cpu 2](https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/0bba3e41-565b-4cf1-88e5-835808e67b44)

Keterangan : CPU memiliki beberapa komponen kunci, termasuk Control Unit, Accumulator, dan Arithmetic Logic Unit. Selain itu, terdapat register-register lain yang meliputi Program Counter, Current Instruction Register, Memory Address Register, dan Memory Data Register.
![siklus cpu 3 drawio](https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/b2185f6a-bde9-4de1-b5fa-53362c707124)

Keterangan : Program Counter menyimpan lokasi memori dari instruksi berikutnya yang akan dieksekusi.
![siklus cpu 4 drawio](https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/d2ab3342-b342-45cf-b6cd-8ae4efbba909)

Keterangan : Program Counter menyimpan data mengenai lokasi memori dari instruksi selanjutnya yang akan dieksekusi.
![siklus cpu 5 drawio](https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/c0d9c7e8-5c15-4671-92ff-3c81ff0d1b38)
![siklus cpu 6 drawio](https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/893c3bf1-08ae-4122-aeca-dc9462d6b474)

Keterangan : Data alamat memori disimpan di Register Alamat Memori (MAR), isi dari alamat memori diambil dan dimuat ke dalam Register Data Memori (MDR), sedangkan instruksi disimpan dalam Register Instruksi Saat Ini (CIR). Program Counter akan meningkat sebanyak satu.
![siklus cpu 7 drawio](https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/0c45dcf1-fed8-41d2-b8e4-8d8054402906)
![siklus cpu 8 drawio](https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/055b9695-a2e3-467a-8662-b2392db55a96)
![siklus cpu 9 drawio](https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/5e2ed7b4-703a-4079-a1bf-81ccdbcc4134)
![siklus cpu 10 drawio](https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/d3d0dcc8-9764-4225-ab60-efc46575515b)
![siklus cpu 11 drawio](https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/3c0d1c3f-3dd0-4390-9339-05c572fe2073)

Keterangan : Setelah instruksi LOAD 10 dieksekusi, CPU akan melanjutkan dengan pengambilan data dari lokasi memori 10. Proses ini melibatkan pembaruan Memory Address Register (MAR) dengan nilai 10. Selanjutnya, konten dari lokasi memori 10 akan diambil dan dimuat ke dalam Memory Data Register (MDR). Setelah itu, data dari MDR akan disalin ke dalam Akumulator.
![siklus cpu 12 drawio](https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/a12cd539-b7ef-4dda-8d25-36f20c59fd4d)
![siklus cpu 13 drawio](https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/8a9b5e8f-bf98-46d3-94b0-6c8df379039e)
![siklus cpu 14 drawio](https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/9958b206-a648-4575-b8e2-1364700dbae5)
![siklus cpu 15 drawio](https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/4a6bd27e-57a0-41b0-806a-fed7a548978a)

Keterangan : Setelah Program Counter menunjuk ke lokasi memori baru, tahap berikutnya adalah menyalin lokasi memori tersebut ke Memory Address Register. Kemudian, isi dari lokasi memori 101 akan diambil dan disimpan dalam Memory Data Register. Instruksi yang berada di lokasi memori 101 juga akan disimpan dalam Current Instruction Register. Setelah proses tersebut, nilai Program Counter akan ditambah 1 untuk merujuk ke instruksi berikutnya.
![siklus cpu 16 drawio](https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/86fb87fd-f70b-41a6-a833-d1921f83d688)
![siklus cpu 17 drawio](https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/af50cd74-e576-4d69-beaf-b6de9908a352)
![siklus cpu 18 drawio](https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/99c59f07-82ec-4bec-814a-fd1d129c0e17)
![siklus cpu 19 drawio](https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/d22beb34-413a-4d0e-8cc7-05b034ef13bf)
![siklus cpu 20 drawio](https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/6a094b7f-aa7f-4388-a13a-ad3f50de3d51)
![siklus cpu 21 drawio](https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/e6166bbb-5843-447a-bbe4-70f60030c3da)
![siklus cpu 22 drawio](https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/6e532ba8-319a-4458-97fb-826913b62088)
![siklus cpu 23 drawio](https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/44edb915-5fd7-478d-9506-f5ae15d057f1)

Keterangan : Setelah mendekode instruksi kedua dengan metode yang sama seperti instruksi pertama dan mengirimkannya ke Unit Kontrol, Unit Kontrol kemudian menginterpretasikan bahwa instruksi tersebut adalah operasi penambahan (add). Oleh karena itu, instruksi penambahan diteruskan ke Unit Logika Aritmetika (ALU). Selanjutnya, isi Akumulator disalin ke ALU. Setelah itu, alamat memori 11 disalin ke Register Alamat Memori (MAR) karena data dari alamat tersebut akan diambil. Kemudian, isi dari alamat memori 11 disalin ke Register Data Memori (MDR). Data dari MDR kemudian ditransfer ke Akumulator. ALU akan melakukan operasi penambahan antara angka 3 dan 2, dan hasilnya akan dikembalikan ke Akumulator untuk menjaga total yang sedang berjalan.
![siklus cpu 24 drawio](https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/8a76d745-559f-4f5b-9931-dea6daeac93c)
![siklus cpu 25 drawio](https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/4239514f-c57a-4c8f-8379-46234da7a0cf)
![siklus cpu 26 drawio](https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/7726c1ba-2c14-49c0-b5d0-900bcbd9fbb8)
![siklus cpu 27 drawio](https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/3b91c3fd-0bda-405f-93b4-5243adeca798)

Keterangan : Alamat memori 102 akan ditransfer ke Register Alamat Memori. Isi dari alamat memori 102 akan ditransfer ke Register Data Memori. Instruksi yang ada akan dipindahkan ke Current Instruction Register. Setelah itu, Program Counter akan dinaikkan sebesar 1 menjadi 103. Biasanya, pada titik ini, akan ada instruksi henti atau berhenti yang menunjukkan akhir dari program.
![siklus cpu 28 drawio](https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/22858e44-aa9c-4998-ae87-16f7dc40615f)
![siklus cpu 29 drawio](https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/6fbd90ee-a53c-4386-bddc-d832e43d5b66)
![siklus cpu 30 drawio](https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/c064d126-b758-4619-8cd0-974d1c873547)
![siklus cpu 31 drawio](https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/b75c9001-57e4-4c60-ba3a-762f783fcd48)

Keterangan : Instruksi ketiga akan didekode dan disimpan dalam Unit Kontrol. Instruksi tersebut adalah STORE, yang berarti menyimpan hasil ke alamat memori 12. Oleh karena itu, alamat memori 12 akan disimpan dalam Register Alamat Memori. Kemudian, hasil dari Akumulator akan dipindahkan ke Register Data Memori, dan nilai dari Register Data Memori akan disalin ke alamat memori 12. Dengan ini, eksekusi program telah selesai.
### Peran bahasa pemrograman
Bahasa pemrograman berperan sebagai sistem komunikasi antara manusia dan mesin yang digunakan untuk menginstruksikan komputer dalam menjalankan tugas tertentu dengan menulis kode yang terstruktur dan dapat dipahami oleh perangkat komputer.
### Peran compiler
Sebagai alat untuk menerjemahkan source code dari bahasa pemrograman tingkat tinggi menjadi bahasa komputer yang dapat dieksekusi oleh komputer.
### Peran Sistem operasi 
Peran sistem operasi sebagai pengelola sumber daya utama dalam sebuah sistem komputer meliputi alokasi dan pengaturan CPU, memori, perangkat input/output, dan penyimpanan.

## 3. Melakukan clone

![Screenshot 2024-03-18 042235](https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/f6e1522c-2845-445b-8958-0cb9451ae8cb)

### Build Binaries

```sh
$ make
```
![Screenshot 2024-03-18 090933](https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/a3476367-33e2-4853-bfdf-4e69b3c918fb)

Analisis : Perintah $ make digunakan untuk mengompilasi program dari kode sumber.

### Cleaning Old Build

```sh
$ make clean
```
<img width="600" alt="image" src="https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/999df92e-6aed-45af-ae2f-b8c511dc275f">

Analisis : Perintah $ make clean digunakan untuk membersihkan proyek dari file sementara atau hasil kompilasi yang dihasilkan selama proses kompilasi.

### Install Binaries

```sh
$ sudo make install
```
<img width="600" alt="image" src="https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/3e2209c5-6d9a-40fe-832f-381295ee0b01">

Analisis : Perintah $ sudo make install digunakan untuk menginstal perangkat lunak atau paket yang telah dikompilasi dari kode sumber ke sistem.

### Uninstall Binaries

```sh
$ sudo make uninstall
```
<img width="600" alt="image" src="https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/981438d6-a082-4800-bcb2-dd2099d373fe">

Analisis : Perintah $ sudo make uninstall digunakan untuk menghapus perangkat lunak atau paket yang telah diinstal sebelumnya.

## Usage 

```sh
$ iops32 $(nproc)
```
<img width="600" alt="image" src="https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/83925da8-9abf-4206-a40c-990f250070d7">


```sh
$ iops64 $(nproc)
```
<img width="600" alt="image" src="https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/dd65dd41-eb61-4ee5-a94e-c3b9490913b5">

```sh
$ flops32 $(nproc)
```
<img width="600" alt="image" src="https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/01f8eb30-d42c-49ac-bc8d-beee02d26cbd">


```sh
$ flops64 $(nproc)
```
<img width="600" alt="image" src="https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/8eeccd3a-d4c6-4a83-b46e-6bb84a30a18f">


## Percobaan iops
- Percobaan 1

<img width="600" alt="image" src="https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/dd65dd41-eb61-4ee5-a94e-c3b9490913b5">

- Percobaan 2

<img width="600" alt="image" src="https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/fe89a104-f439-4dce-af3a-ee08a7525f1f">

- Percobaan 3

<img width="600" alt="image" src="https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/1e28c0d5-d2ec-4fb1-a268-9a80bcff4f75">

- Percobaan 4

<img width="600" alt="image" src="https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/4face27d-6988-4570-9897-8e0e01c8eb78">

- Percobaan 5

<img width="600" alt="image" src="https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/138b5b3a-e814-4871-8606-7bf8f6550fe5">

Analisis : IOPS (Input/Output Operations Per Second): IOPS mengukur seberapa cepat sistem dapat melakukan operasi masukan/keluaran. Semakin tinggi angka IOPS, semakin baik kinerja sistem dalam menangani operasi masukan/keluaran seperti membaca atau menulis data pada disk atau penyimpanan lainnya. Jika hasil $ iops64 $(nproc) menunjukkan angka yang tinggi, itu menunjukkan bahwa sistem memiliki kinerja yang baik dalam menangani operasi masukan/keluaran.

## Percobaan flops
- Percobaan 1

<img width="600" alt="image" src="https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/8eeccd3a-d4c6-4a83-b46e-6bb84a30a18f">

- Percobaan 2

<img width="600" alt="image" src="https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/d5a78ce6-2cca-4025-b330-1ec50be884ae">

- Percobaan 3

<img width="600" alt="image" src="https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/35d0365f-5700-414f-b400-a8aa3df48978">

- Percobaan 4

<img width="600" alt="image" src="https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/806c14c7-c474-4dbd-9381-4e0c8fa8d658">

- Percobaan 5

<img width="600" alt="image" src="https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/bda85d75-1c79-40b6-a942-857bb37fb393">


Analisis : FLOPS (Floating Point Operations Per Second): FLOPS mengukur seberapa cepat sistem dapat melakukan operasi floating point, yang umumnya terkait dengan kinerja komputasi numerik atau ilmiah. Semakin tinggi angka FLOPS, semakin baik sistem dalam menangani operasi matematika yang intensif, seperti dalam pemrosesan gambar, simulasi fisika, atau analisis data. Jika hasil $ flops64 $(nproc) menunjukkan angka yang tinggi, itu menunjukkan bahwa sistem memiliki kinerja yang baik dalam komputasi numerik.

## Perbandingan Percobaan Hasil Eksekusi 

![WhatsApp Image 2024-03-18 at 12 05 00_3d652453](https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/14b3e1a4-4e38-4299-977c-12c2df6b4c7d)

## Kesimpulan 
Hasil dari kedua perintah tersebut memberikan gambaran tentang kinerja sistem dalam menangani operasi masukan/keluaran (IOPS) dan operasi matematika floating-point (FLOPS). Semakin tinggi nilai yang diperoleh, semakin baik kinerja sistem dalam aspek yang diukur. Namun, untuk mendapatkan gambaran yang lebih lengkap, perlu dilakukan analisis lebih lanjut dan pembandingan dengan standar kinerja atau hasil percobaan sebelumnya.
