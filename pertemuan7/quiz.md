## Contoh pemanfaatan data historis
1. Pencatatan data traksaksi tahunan
2. Pemantauan ketinggian air sungai
3. Data cuaca harian


## SQL
```
CREATE table karyawan (
  id_karyawan INT(4),
  nama VARCHAR(50),
  PRIMARY KEY(id_karyawan)
  );
  
 CREATE TABLE histori_gaji (
   id_karyawan INT(4),
   tanggal_gaji DATE,
   gaji_bulanan VARCHAR(20),
   PRIMARY KEY(id_karyawan, tanggal_gaji)
   );
   
 CREATE TABLE histori_tempat_tinggal (
   id_karyawan INT(4),
   tanggal DATE,
   alamat VARCHAR(100),
   PRIMARY KEY(id_karyawan, tanggal)
   );
   
 CREATE TABLE histori_gaji (
   id_karyawan INT(4),
   tanggal DATE,
   jabatan VARCHAR(20),
   PRIMARY KEY(id_karyawan, tanggal)
   );
   
   ```
