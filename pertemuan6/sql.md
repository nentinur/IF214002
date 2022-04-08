```
CREATE TABLE pembimbing (
  id_pembimbing INT(4),
  kode_kelas VARCHAR(3),
  pass VARCHAR(50),
  nama VARchar(50),
  kontak varchar(13),
  link_meeting varchar(50)
  );
  
CREATE TABLE santri (
  id_santri int(4),
  id_pembimbing int(4),
  pass varchar(50),
  nama varchar(50),
  kontak varchar(13),
  tanggal_lahir date
  );
  
CREATE TABLE setoran (
  id_setoran int(4),
  id_santri INT(4),
  waktu datetime,
  keterangan varchar(8)
  );

CREATE table surat (
  id_surat INT(3),
  nama_surat VARChar(20)
  );
  
CREATE TABLE ayat_surat (
  id_ayat INT(3),
  id_surat INT(3),
  no_ayat INT(3),
  juz INt(2)
  );

CREATE TABLE item_setoran (
  id_setoran INT(4),
  id_ayat INT(3)
  );
```
