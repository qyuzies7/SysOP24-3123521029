## Perbedaan Concurrent dan Serial
![serial concurrent](https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/586ccdc2-0fec-4b28-a0b6-236b3d2097b7)
**Concurrent** menjalankan  beberapa tugas secara bersamaan. Waktu mulainya tugas akan sesuai dengan urutan penambahannya, 
artinya Tugas 0 dimulai terlebih dahulu, kemudian Tugas 1 akan dimulai setelah itu, dan seterusnya.

sebagai contoh, yaitu saat kita memiliki beberapa tugas seperti memasak, mencuci pakaian dan membersihkan rumah. pada concurrent queue mungkin kita akan mulai memasak terlebih dahulu,
sementara makanan sedang dimasak kita mulai mencuci pakaian, dan sambil menunggu pakaian dicuci, kita membersihkan rumah. kita berganti antara tugas satu dengan tugas lainnya, sehingga semuanya tampak berjalan bersamaan.

**Serial** hanya menjalankan satu tugas dalam satu waktu. Setelah tugas pertama berakhir maka hanya tugas kedua yang akan dimulai. 
Semua tugas mengikuti urutan yang sama, mereka harus menunggu hingga tugas yang sedang berjalan selesai.

sebagai contoh, pada serial queue kita akan menyelesaikan memasak sepenuhnya sebelum mulai mencuci pakaian, dan setelah memasak selesai, kita mencuci pakaian sampai selesai baru kemudian membersihkan rumah.
Setiap tugas diselesaikan satu per satu tanpa tumpang tindih.

## Perbedaan Parallel dan Concurrent
![concurrent parallel](https://github.com/qyuzies7/SysOP24-3123521029/assets/149217967/3c85f01f-8a40-4380-9bd2-0231ed4c8c49)
**Parallel** menjalankan beberapa tugas secara bersamaan di waktu yang sama menggunakan multicore

sebagai contoh, saya memasak nasi dan teman saya menggoreng ayam. Masing-masing orang mengerjakan tugasnya sendiri dalam waktu yang sama dan tidak ada yang berpindah-pindah tugas.

**Concurrent** menjalankan beberapa tugas secara bersamaan dengan saling berpindah-pindah dengan cepat. setiap core bisa menangani beberapa tugas secara bergantian.

sebagai contoh, saya bergantian antara memasak nasi dan memotong sayuran, sementara teman saya bergantian antara menggoreng ayam dan memotong sayuran. Kedua orang tidak menjalankan tugas-tugas ini secara simultan, tetapi berpindah-pindah dengan cepat di antara tugas-tugas tersebut.

## Dining Philosopher’s Problem
Dining Philosopher problem adalah salah satu masalah klasik dalam ilmu komputer yang menggambarkan tantangan pengelolaan sumber daya.

Masalah ini menceritakan tentang lima orang filsuf yang sedang duduk mengelilingi sebuah meja bulat. Setiap filsuf memiliki dua kegiatan yaitu berpikir dan makan. Makanan disajikan di atas meja dengan lima piring dan lima garpu, dengan satu garpu di antara setiap pasang filsuf. Namun, ada aturan khusus yang harus diikuti yaitu:

1. Setiap filsuf membutuhkan dua garpu untuk makan.
2. Seorang filsuf hanya boleh mengambil satu garpu pada satu waktu.
3. Seorang filsuf hanya boleh mulai makan jika sudah memiliki dua garpu.
   
Tantangan utama muncul ketika setiap filsuf mencoba untuk makan. Mereka harus mengambil dua garpu yang berdekatan untuk memulai makan, tetapi jika semua garpu telah diambil oleh filsuf-filsuf di sekitarnya, maka akan terjadi kondisi yang disebut deadlock, di mana tidak ada yang bisa melanjutkan.

Solusi pertama yang muncul adalah dengan menggunakan semafor, yang digunakan untuk mengatur akses ke sumber daya bersama.Filosof harus mengambil kedua garpu sebelum bisa makan. Namun, solusi ini memiliki kelemahan, yaitu dapat menghasilkan deadlock jika semua filsuf mencoba untuk mengambil garpu kiri mereka secara bersamaan.

Solusi kedua mencoba membatasi jumlah filsuf yang diperbolehkan masuk ke dalam ruangan menjadi empat saja. Dengan cara ini, salah satu filsuf akhirnya akan mendapatkan kedua garpu dan dapat melanjutkan makan, sehingga deadlock dapat dihindari.

Solusi ketiga menggunakan pendekatan asimetris, di mana empat filsuf pertama mengikuti solusi asli, tetapi filsuf kelima menunggu untuk mengambil garpu kanan terlebih dahulu, baru kemudian garpu kiri. Hal ini juga dikenal sebagai Solusi Chandy/Mishra.

## Reader - Writer Problem
Reader Writer problem adalah masalah yang terkait dengan pembaca dan penulis yang berbagi sumber daya yang sama.

Masalah ini menceritakan tentang sebuah ruangan di mana beberapa penulis dan pembaca bersaing untuk mengakses sebuah sumber daya bersama, mungkin sebuah database atau file. Penulis bertugas untuk menulis atau memodifikasi data, sementara pembaca hanya membaca data tanpa mengubahnya. Namun, ada aturan yang harus diikuti yaitu:

1. Penulis harus mendapatkan akses eksklusif saat menulis untuk mencegah ketidak-konsistenan data.
2. Pembaca dapat berbagi akses ke data dan dapat membacanya bersamaan, selama tidak ada penulis yang sedang menulis.

Permasalahan utama muncul saat penulis dan pembaca saling beradu untuk mendapatkan akses ke sumber daya. Sementara pembaca dapat berbagi akses dengan aman, penulis harus menunggu sampai tidak ada pembaca yang sedang membaca atau menulis sebelum mendapatkan akses eksklusif.

Solusi awal dalam menyelesaikan permasalahan ini adalah dengan menggunakan semafor atau mutex. Dengan semafor, penulis mendapatkan prioritas saat ada penulisan yang sedang berlangsung, sementara pembaca dapat membaca data jika tidak ada penulis yang aktif.

Solusi kedua mencoba untuk menyeimbangkan antara akses penulis dan pembaca dengan menggunakan variabel kondisi. Dengan variabel kondisi, penulis dapat menunggu saat pembaca sedang membaca, dan sebaliknya.

Solusi ketiga melakukan pendekatan yang lebih maju adalah dengan menggunakan monitor, yang mengatur akses ke sumber daya bersama dengan lebih efisien. Monitor memastikan bahwa hanya satu penulis atau sekelompok pembaca yang dapat mengakses data pada satu waktu.

Dengan demikian, Masalah Penulis-Pembaca adalah sebuah tantangan yang menggambarkan kompleksitas dalam manajemen akses bersama terhadap sumber daya.
