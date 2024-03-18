# TUGAS 3
## 1. Siklus CPU (Fetch, Decode, Execute)
- Fetch : CPU mengambil instruksi program dari memori utama, Instruksi berikutnya diambil dari alamat memori yang tersimpan dalam Program Counter(PC), dan disimpan dalam Instruction Regrister(IR).
- Decode : CPU menerjemahkan instruksi menjadi operasi yang mudah dipahami dan memecah instruksi menjadi bagian-bagian yang sederhana.
- Execute : CPU menjalankan instruksi yang telah didecode sebelumnya.
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
