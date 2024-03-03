### **Boot Process**
![Boot Process](https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/2dee70fe-c2cb-4fde-b473-3741c29d23dc)

Penjelasan : 
1. Power on, komputer dinyalakan dengan menekan tombol power
2. Processor Starts BIOS, setelah menyalakan komputer, proses pertama yang dilakukan terjadi pada BIOS (Basic Input Output System)
3. POST (Power on Self Test), Mengecek hardware seperti cd, ram, hard disk, dan lainnya untuk memastikan sistem berjalan dengan baik, jika ada kesalahan maka komputer akan menampilkan pesan
4. Setelah POST melakukan testing, BIOS membaca MBR (Master Boot Record). MBR disimpan pada sektor pertama hard disk yang berisi boot loader
5. Windows Boot Manager bertanggung jawab untuk memilih sistem operasi yang akan di-boot. Jika komputer memiliki lebih dari satu sistem operasi yang terinstall, boot manager memungkinkan pengguna untuk memilih sistem operasi yang diinginkan.
6. Windows Boot Loader, program kecil yang memuat kernel ke memori komputer yang ada di RAM. Terdapat tiga file boot dalam sistem operasi Windows, yaitu NTLDR, NTDETECT.COM, dan Boot.ini
7. Kernel, Windows Boot Loader bertanggung jawab untuk memuat kernel Windows (Ntoskrnl.exe), Hardware Abstraksi Layer (HAL), file Hal.dll yang membantu kernel berinteraksi dengan perangkat keras. Selanjutnya, Windows menjalankan informasi konfigurasi yang disimpan dalam registri di HKLM\SYSTEM\CurrentControlSet dan memulai layanan dan driver. Winlogon.exe memulai prosedur login mesin windows.
8. Windows executable digunakan untuk mengeksekusi atau menjalankan sebuah aplikasi yang disimpan dalam format file executable
9. Services are started and winlogon.exe is first, sistem sedang memulai proses kunci dan layanan-layanan yang diperlukan untuk interaksi pengguna.

### **Identifikasi Laptop pada CPU-Z**

- Spesifikasi CPU

<img width="302" alt="image" src="https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/5c19be97-f359-4ffe-b86d-f796321bd69d">

Tab CPU memuat informasi prosessor, core speed, dan cache.

- prosessor : menggunakan processor Intel core i5 1235u Menampilkan nama dari processor yang digunakan pada laptop atau komputer

- core speed : kecepatan clock pada saat ini pada inti prosesor adalah 1795.61 MHz dan bus speed yang menghubungkan prosesor ke memori dan perangkat lain adalah 99.76 MHz

- cache : L1 data memiliki ukuran "2 x 48 KByte", L2 inst. memiliki ukuran "2 x 32 KByte ", level 2 memiliki ukuran "2 x 1.25 MBytes", level 3 memiliki ukuran " 12 MBytes" laptop ini menggunakan 2 cores dan 1 soket.

<img width="297" alt="image" src="https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/f66d5578-7269-4af8-9aa4-502c072282e7">

Tab mainboard memuat informasi matherboard, bios, dan graphic interface

- Motherboard manufacturer yaitu ASUSTek COMPUTER INC, menggunakan model X1402ZA, spesifikasi bus yaitu PCI-Express 3.0 (8.0 GT/S), chipset motherboard menggunakan Intel Alder Lake dan Southbridge Intel Alder Lake PCH

- BIOS menggunakan brand American Megatrends International LLC, dan dibuat pada 09/06/2022

<img width="293" alt="image" src="https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/db4fb125-f689-4969-99bd-e200047efd67">

Tab memory memuat informasi general dan timings

- general laptop ini menngunakan type memory DDR4 yang berukuran 8 GBytes

- Timings clock speed memori 1330.1 MHz dengan rasio FSB dan DRAM adalah 1:20

<img width="299" alt="image" src="https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/2d016d97-e64d-458d-959c-ba9c0c86e69f"> 

Tab SPD memuat informasi Memory Slot Selection pada laptop ini terpasang 1 slot memory yang berukuran 8 GBytes, model manuf Micron Technology

<img width="302" alt="image" src="https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/6d4ae9dc-588a-4cad-95a1-09c70b88c144"> 

Tab Graphiscs memuat informasi GPU dan kapasitas memory
- GPU menggunakan Intel UHD Graphics dengan ASUSTek Computer Inc.
- Type memory DDR4

<img width="296" alt="image" src="https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/42ea6aa1-e3a2-4fd5-bb46-dbd67eaebac6">

Menggunakan Benchmark version 17.01.64

<img width="299" alt="image" src="https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/fb8898a0-7874-4da7-8162-ff4570a97a9c">

Tab about memuat informasi tentang CPUID dan spesifikasi laptop yang menggunakan Microsoft Windows 11 Home Single Language (x64) versi 23H2, Build 22631.3155 Directx 12.0
