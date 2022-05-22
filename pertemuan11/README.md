## Asesmen 
- Buat DDL, sampel DML, dan DQL untuk proyek besar teman-teman
  - Contoh DDL : CREATE TABLE santri ( . . . ), dsb.
  - Contoh DML : INSERT INTO santri ( . . . ) VALUES ( . . . ), dsb.
  - Contoh DQL : 
    - Santri dengan setoran hafalan terbanyak : SELECT nama FROM santri INNER JOIN . . .
    - Agregat pemasukan kencleng per bulan tahun 2022 : SELECT bulan, pemasukan FROM . . . INNER JOIN . . .

### DDL   
- CREATE TABLE
```sql
CREATE TABLE pembimbing (
  id_pembimbing INT NOT NULL AUTO_INCREMENT PRIMARY KEY,
  kode_kelas VARCHAR(3) NOT NULL,
  pass VARCHAR(50) NOT NULL,
  nama VARCHAR(50) NOT NULL,
  kontak VARCHAR(13) NOT NULL,
  link_meeting VARCHAR(50) NOT NULL
);

CREATE TABLE santri (
  id_santri INT NOT NULL AUTO_INCREMENT PRIMARY KEY,
  id_pembimbing INT NOT NULL,
  pass VARCHAR(50) NOT NULL,
  nama VARCHAR(50) NOT NULL,
  kontak VARCHAR(13) NOT NULL,
  tanggal_lahir DATE NOT NULL
);

CREATE TABLE setoran (
  id_setoran INT NOT NULL AUTO_INCREMENT PRIMARY KEY,
  id_santri INT NOT NULL,
  waktu DATETIME NOT NULL,
  keterangan VARCHAR(50) NOT NULL,
);

CREATE TABLE ayat_surat (
  id_ayat INT NOT NULL AUTO_INCREMENT PRIMARY KEY,
  id_surat INT NOT NULL,
  no_ayat INT NOT NULL,
  juz INT NOT NULL
);

CREATE TABLE surat (
  id_surat INT NOT NULL AUTO_INCREMENT PRIMARY KEY,
  nama_surat VARCHAR(20) NOT NULL
);

CREATE TABLE item_setoran (
  id_surat INT NOT NULL AUTO_INCREMENT,
  id_ayat INT NOT NULL,
  PRIMARY KEY (id_surat, id_ayat)
);
```
