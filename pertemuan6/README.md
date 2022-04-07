## Sebelum Normalisasi:

#### Tabel santri
|🔑id_santri|id_kelas|id_setoran|password|nama|kontak|tanggal_lahir|
|---|---|---|---|---|---|---|
|1|01A|2|nenti01|Nenti|087745677969|30/09/2001|
|2|02B|1|BlaBlaBla|Nurul|087899880101|29/02/2000|
|3|01B|2|iniPW|Rifa'i |0888272721111|02/02/2002|
#### Tabel kelas
|🔑id_kelas|id_santri|id_pembimbing|link_meeting|
|---|---|---|---|
|01A|1|2|https://linkmeet1|
|01B|3|2|https://linkmeet2|
|02B|2|1|https://linkmeet12|

#### Tabel pembimbing
|🔑id_pembimbing|id_kelas|password|nama|kontak|
|---|---|---|---|---|
|1|01A|halhal01|Halimah|089923230001|
|2|02B|zainAB|Zainab|089923230001|
|3|01B|haigais|Haikal|087726260506|

#### Tabel setoran
|🔑id_setoran|id_santri|id_pembimbing|id_item_setoran|tanggal|keterangan|
|---|---|---|---|---|---|
|1|1|1|8|07/04/2022|Ziyadah|
|2|2|2|13|07/04/2022|Murajaah|
|3|3|3|5|07/04/2022|Ziyadah|

#### Tabel item setoran
|🔑id_item_setoran|id_setoran|id_surat|no_ayat|juz|
|---|---|---|---|---|
|5|3|3|21|3|
|8|1|2|50|1|
|13|2|3|90|4|

#### Tabel surat
|🔑id_surat|id_item_setoran|nama_surat|
|---|---|---|
|1|2|Al-Fatihah|
|2|2|Al-Baqarah|
|3|1|Ali Imran|

---
### Normalilasi Bentuk ke-1
Karena semua tabel sudah memiliki primary key, dan tidak ada sel yang memiliki nilai lebih dari 1, maka tabel sudah tersertifikasi normalisasi bentuk ke 1

---
### Normalisasi Bentuk ke-2
Karena tabel sudah tersertifikasi normalisasi bentuk ke-1, dan setiap tabel hanya memiliki 1 primary key saja (tidak ada yang menggunakan composite key), maka tabel sudah tersertifikasi normalisasi bentuk ke-2.

---
### Normalisasi Bentuk ke-3
Pada tabel surat, terdapat kolom non-key yang yang tidak bergantung pada primary key, kolom **id_item_setoran** tidak bergantung pada kolom apapun pada tabel surat. maka kolom id_item_setoran dihapus dari tabel surat.

#### Tabel surat sebelum dinormalisasi
|🔑id_surat|🔴id_item_setoran|nama_surat|
|---|---|---|
|1|🔴2|Al-Fatihah|
|2|🔴2|Al-Baqarah|
|3|🔴1|Ali Imran|

#### Tabel surat setelah dinormalisasi
|🔑id_surat|nama_surat|
|---|---|
|1|Al-Fatihah|
|2|Al-Baqarah|
|3|Ali Imran|

Pada tabel santri, terdapat kolom non-key yang yang tidak bergantung pada primary key, kolom **id_setoran** tidak bergantung pada kolom apapun pada tabel surat. karena pada tabel setoran sendiri, id_setoran sudah mencakup id_santri itu sendiri. maka kolom id_setoran dihapus dari tabel santri.

#### Tabel santri sebelum dinormalisasi
|🔑id_santri|id_kelas|🔴id_setoran|password|nama|kontak|tanggal_lahir|
|---|---|---|---|---|---|---|
|1|01A|🔴2|nenti01|Nenti|087745677969|30/09/2001|
|2|02B|🔴1|BlaBlaBla|Nurul|087899880101|29/02/2000|
|3|01B|🔴2|iniPW|Rifa'i |0888272721111|02/02/2002|

#### Tabel santri setelah dinormalisasi
|🔑id_santri|id_kelas|password|nama|kontak|tanggal_lahir|
|---|---|---|---|---|---|---|

Sekarang semua tabel sudah tersertifikasi normalisasi bentuk ke-3.

---
## Hasil Akhir Tabel

#### Tabel santri
|🔑id_santri|id_kelas|password|nama|kontak|tanggal_lahir|
|---|---|---|---|---|---|---|
|1|01A|nenti01|Nenti|087745677969|30/09/2001|
|2|02B|BlaBlaBla|Nurul|087899880101|29/02/2000|
|3|01B|iniPW|Rifa'i |0888272721111|02/02/2002|
#### Tabel kelas
|🔑id_kelas|id_santri|id_pembimbing|link_meeting|
|---|---|---|---|
|01A|1|2|https://linkmeet1|
|01B|3|2|https://linkmeet2|
|02B|2|1|https://linkmeet12|

#### Tabel pembimbing
|🔑id_pembimbing|id_kelas|password|nama|kontak|
|---|---|---|---|---|
|1|01A|halhal01|Halimah|089923230001|
|2|02B|zainAB|Zainab|089923230001|
|3|01B|haigais|Haikal|087726260506|

#### Tabel setoran
|🔑id_setoran|id_santri|id_pembimbing|id_item_setoran|tanggal|keterangan|
|---|---|---|---|---|---|
|1|1|1|8|07/04/2022|Ziyadah|
|2|2|2|13|07/04/2022|Murajaah|
|3|3|3|5|07/04/2022|Ziyadah|

#### Tabel item setoran
|🔑id_item_setoran|id_setoran|id_surat|no_ayat|juz|
|---|---|---|---|---|
|5|3|3|21|3|
|8|1|2|50|1|
|13|2|3|90|4|

#### Tabel surat
|🔑id_surat|nama_surat|
|---|---|
|1|Al-Fatihah|
|2|Al-Baqarah|
|3|Ali Imran|
