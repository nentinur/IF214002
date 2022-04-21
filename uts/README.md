### SOAL
1. Basis data relasional dapat langsung dibangun menggunakan perintah SQL di sistem basis data seperti MySQL, dsb tanpa ada perancangan terlebih dahulu. 
  Jelaskan apa keuntungan melakukan perancangan basis data terlebih dahulu (menggunakan ERD ataupun Class Diagram) !

2. Jelaskan bagaimana cara mentransformasikan proses bisnis sebuah organisasi menjadi struktur data di basis data !

3. Rancang solusi digital dari satu permasalahan yang ada di sekitar Anda. 
    - a. Deskripsikan solusi digital tersebut dalam satu paragraf
    - b. Buat list fitur-fitur yang ada pada solusi digital tersebut
    - c. Buat ERD notasi Chen dari struktur data yang mewakili fitur2 di solusi digital tersebut
    - d. Buat ERD notasi Crow Foot dari struktur data logical yang mewakili fitur2 di solusi digital tersebut, lengkap dengan keys, tipe data, dan normalisasi hingga bentuk ke 3
  
### JAWABAN
1. Membuat perancangan basis data terlebih dahulu membuat kita lebih mudah saat membangun data menggunakan SQL, dan memudahkan juga untuk mengkomunikasiskan rancangan data dengan orang lain, terutama dengan orang yang tidak punya latar belakang IT, tentunya tanpa ada ERD atau Diagram, orang tersebut tidak akan mengerti jika langsung diberi kode SQL saja. 

2. - Menentukan terlebih dahulu proses bisnisnya, menentukan fitur-fitur yang akan dibangun
   - Menentukan entitas dan atribut yang dibutuhkan
   - Membuat ERD, menentukan relasi, primary key, foreign key
   - Melakukan normalisasi pada basis data

3. - a. Dimasa pandemi ini banyak kegitan yang sebelumnya dilakukan secara offline, kini harus berpindah ke online, tak terkecuali di bidang pembelajaran. Program tahfidz yang dulunya dilakukan secara offline, mau tidak mau harus beradaptasi juga. Aplikasi ini bertujuan untuk mempermudah proses pembelajaran program tahfidz melalui media online. Aplikasi akan melakukan pendataan santri yang mengikuti program, kemudian santri akan dikelompokkan berdasarkan jumlah hafalan menjadi beberapa kelas, setiap kelas memiliki 1 pembimbing tetap, sehingga 1 santri hanya memiliki 1 pembimbing, sedangkan 1 pembimbing memiliki beberapa santri. Proses setoran dilakukan memalui media meeting online. setiap kali santri melakukan setoran, maka data jumlah hafalan santri akan berubah, sistem akan otomatis mentrack data hafalan santri dan menentukan jumlah juz hafalan santri.
  - b. 
