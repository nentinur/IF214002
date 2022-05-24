## Asesmen 
- Buat DDL, sampel DML, dan DQL untuk proyek besar teman-teman

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
  keterangan VARCHAR(50) NOT NULL
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
  id_setoran INT NOT NULL,
  id_ayat INT NOT NULL,
  PRIMARY KEY (id_setoran, id_ayat)
);
```
- ALTER TABLE
``` sql
ALTER TABLE pembimbing ADD COLUMN(jenis_kelamin VARCHAR(1));
ALTER table santri ADD COLUMn(jenis_kelamin VARCHAR(1));
```

### DML
- INSERT
``` sql
INSERT into pembimbing (id_pembimbing, kode_kelas, pass, nama, kontak, link_meeting) VALUES (1, "01A", "halohalo", "Halimatus Sholihah", "089923230001", "https://linkmeet01");
INSERT into pembimbing (id_pembimbing, kode_kelas, pass, nama, kontak, link_meeting) VALUES (2, "02B", "sifat", "Siti Fatimah", "089923230002", "https://linkmeet02");
INSERT into pembimbing (id_pembimbing, kode_kelas, pass, nama, kontak, link_meeting) VALUES (3, "01B", "haihai", "Haikal Sholihudin", "089923230003", "https://linkmeet03");

INSERT into santri (id_santri, id_pembimbing, pass, nama, kontak, tanggal_lahir) VALUES (1, 1, "nenur", "Nenti Nurnaningsih", "087745677969", "2001-09-30");
INSERT into santri (id_santri, id_pembimbing, pass, nama, kontak, tanggal_lahir) VALUES (2, 2, "nurnur", "Nurul Fauziyah", "089923230006", "2000-02-20");
INSERT into santri (id_santri, id_pembimbing, pass, nama, kontak, tanggal_lahir) VALUES (3, 3, "abri", "Abdul Rifa'i", "089923230007", "2002-02-02");

INSERT into setoran (id_setoran, id_santri, waktu, keterangan) VALUES (1, 1, "2022-05-20 07:30:34", "Ziyadah");
INSERT into setoran (id_setoran, id_santri, waktu, keterangan) VALUES (2, 2, "2022-05-20 07:48:22", "Murajaah");
INSERT into setoran (id_setoran, id_santri, waktu, keterangan) VALUES (3, 3, "2022-05-20 08:17:18", "Ziyadah");

INSERT into item_setoran (id_setoran, id_ayat) VALUES (1, 110);
INSERT into item_setoran (id_setoran, id_ayat) VALUES (2, 56);
INSERT into item_setoran (id_setoran, id_ayat) VALUES (3, 89);

INSERT into ayat_surat (id_ayat, id_surat, no_ayat, juz) VALUES (7, 2, 1, 1);
INSERT into ayat_surat (id_ayat, id_surat, no_ayat, juz) VALUES (57, 2, 50, 1);
INSERT into ayat_surat (id_ayat, id_surat, no_ayat, juz) VALUES (3, 1, 3, 1);

INSERT into surat (id_surat, nama_surat) VALUES (1, "Al-Fatihah");
INSERT into surat (id_surat, nama_surat) VALUES (2, "Al-Baqarah");
INSERT into surat (id_surat, nama_surat) VALUES (3, "Ali Imran");
```
- UPDATE
``` sql
UPDATE pembimbing set jenis_kelamin = 'P' WHERE id_pembimbing = 1;
UPDATE pembimbing set jenis_kelamin = 'P' WHERE id_pembimbing = 2;
UPDATE pembimbing set jenis_kelamin = 'L' WHERE id_pembimbing = 3;

UPDATE santri set jenis_kelamin = 'P' WHERE id_pembimbing = 1;
UPDATE santri set jenis_kelamin = 'P' WHERE id_pembimbing = 2;
UPDATE santri set jenis_kelamin = 'L' WHERE id_pembimbing = 3;
```

### DQL
- SELECT
``` sql
SELECT nama FROM pembimbing WHERE jenis_kelamin = 'P';
```
- COUNT
``` sql
SELECT COUNT(*) FROM santri;
```
- SUM, CASE
``` sql
SELECT keterangan,
    COUNT(*) AS jumlah_setoran,
    ( SUM(
        CASE WHEN keterangan="Ziyadah" THEN 1 ELSE 0 END)
    ) AS jumlah_ziyadah,
    (SUM(
        CASE WHEN keterangan="Murajaah" THEN 1 ELSE 0 END)
    ) AS jumlah_murajaah
FROM setoran;
```
- JOIN (mencari santri dengan hafalan terbanyak
``` sql
SELECT santri.nama, setoran.id_setoran, item_setoran.id_ayat FROM setoran 
JOIN santri ON setoran.id_santri = santri.id_santri
JOIN item_setoran On setoran.id_setoran = item_setoran.id_setoran
ORDER by item_setoran.id_ayat DESC;
```
