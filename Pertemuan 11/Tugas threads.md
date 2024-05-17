1. Berikan tiga contoh pemrograman di mana multithreading memberikan kinerja yang lebih baik daripada solusi berulir tunggal
   
   Jawab:
   
   a. Server web yang melayani setiap permintaan dalam thread terpisah.
   
   b. Aplikasi yang diparalelkan seperti perkalian matriks di mana bagian yang berbeda dari matriks dapat dikerjakan secara paralel.
   
   c. Program GUI interaktif seperti debugger di mana sebuah thread digunakan untuk memonitor input pengguna, utas lain mewakili aplikasi yang sedang berjalan aplikasi yang sedang berjalan, dan thread ketiga memonitor kinerja.
2. Apa saja dua perbedaan antara thread tingkat pengguna dan thread tingkat kernel? Dalam kondisi apa salah satu jenis lebih baik daripada yang lain?
   
   Jawab :

   a. Thread tingkat pengguna tidak diketahui oleh kernel, sedangkan kernel mengetahui thread kernel.
   
   b. Pada sistem yang menggunakan pemetaan M:1 atau M:N, thread pengguna dijadwalkan oleh pustaka thread dan kernel menjadwalkan kernel thread kernel.

   c. Kernel threads tidak perlu diasosiasikan dengan proses dimana setiap thread pengguna adalah milik sebuah proses, Thread kernel pada umumnya lebih mahal untuk dipelihara daripada thread pengguna.

3. Jelaskan tindakan yang diambil oleh kernel untuk melakukan perpindahan konteks di antara thread tingkat kernel

   Jawab :  Pengalihan konteks antara thread kernel biasanya membutuhkan penyimpanan nilai register CPU dari thread yang dialihkan dan mengembalikan register CPU dari thread baru yang dijadwalkan.

4. Sumber daya apa yang digunakan saat thread dibuat? Bagaimana perbedaannya dengan yang digunakan saat proses dibuat?

   Jawab : Karena thread lebih kecil daripada proses, pembuatan thread biasanya menggunakan sumber daya yang lebih sedikit daripada pembuatan proses. Membuat proses membutuhkan
 mengalokasikan blok kontrol proses (PCB), sebuah struktur data yang cukup besar. PCB mencakup peta memori, daftar file yang terbuka, dan lingkungan variabel. Mengalokasikan dan mengelola peta memori biasanya merupakan aktivitas yang paling memakan waktu. Membuat thread pengguna atau kernel melibatkan pengalokasian struktur data kecil untuk menampung set register, stack, dan prioritas.

5. Asumsikan bahwa sistem operasi memetakan thread tingkat pengguna ke kernel menggunakan model banyak-ke-banyak dan pemetaan dilakukan melalui LWP. Lebih jauh lagi, sistem ini memungkinkan pengembang untuk membuat thread real time untuk digunakan dalam sistem real time. Apakah perlu untuk mengikat thread real time ke LWP? Jelaskan.

   Jawab : Iya, pengaturan waktu sangat penting untuk aplikasi real time. Jika sebuah thread ditandai sebagai real time tetapi tidak terikat ke LWP, thread mungkin harus menunggu untuk dilampirkan ke LWP sebelum berjalan. Pertimbangkan jika sebuah thread real time adalah
 berjalan (dilampirkan ke LWP) dan kemudian melanjutkan untuk memblokir (yaitu harus melakukan I/O, telah didahului oleh thread real-time dengan prioritas lebih tinggi,
 sedang menunggu kunci pengecualian bersama, dll.) Saat thread real time diblokir, LWP yang dilampirkan telah dialihkan ke thread lain.
 Ketika thread real time telah dijadwalkan untuk berjalan lagi, ia harus terlebih dahulu menunggu untuk dilampirkan ke LWP. Dengan mengikat LWP ke sebuah thread real-time
 Anda memastikan bahwa thread akan dapat berjalan dengan penundaan minimal sekali setelah dijadwalkan
 

