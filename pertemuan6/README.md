# PERTEMUAN 6: NORMALISASI 
* Nama: Nenti Nurnaningsih
* NIM: 1207050090
* Kelas: IF-E
* Tanggal: 07-08/04/2022

---
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
### Penyuaian dengan Proses Bisnis
* Setelah dianalisis, terdapat tabel yang tidak sesuai dengan proses bisnis. atribut pada tabel kelas seperti kode_kelas dan link_meeting sebenarnya menempel pada tabel pembimbing, sehingga membuat redundan, maka tabel kelas lebih baik dihilangkan.
* Setelah tabel kelas dihilangkan, maka foreign key di tabel santri diubah menjadi id_pembimbing.
* Nama kolom "passwod" pada tabel santri dan pembimbing menjadi "pass" karena ada aturan nama-nama yang tidak boleh dijadikan nama kolom maupun tabel, dan "password" merupakan salah satunya.
* Pada tabel setoran, kolom tanggal diubah menjadi waktu, agar lebih spesifik. kolom id_pembimbing dihilangkan, karena informasi pembimbing bisa didapat dari id_santri.

---
### Normalilasi Bentuk ke-1
Pada tabel item_setoran, sebenarnya untuk primary key nya cukup menggunakan perpaduan antara id_setoran dan id_surat. tidak perlu membuat id_item_setoran.
Karena semua tabel sudah memiliki primary key, dan tidak ada sel yang memiliki nilai lebih dari 1, maka tabel sudah tersertifikasi normalisasi bentuk ke 1

#### Tabel item setoran
|🔑id_setoran|🔑id_surat|no_ayat|juz|
|---|---|---|---|---|
|5|3|3|21|3|
|8|1|2|50|1|
|13|2|3|90|4|

---
### Normalisasi Bentuk ke-2
Pada tabel item setoran, primary merupakan compite key, dan terdapat kolom non key yang bergantung pada sebagian composite key, sehingga tabel ini harus di normalisasi dengan cara memekarkan tabel. 
dibuat tabel baru yaitu tabel ayat_surat, yang berisi id_ayat, id_surat, no_ayat, dan juz.
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
|1|01A|nenti01|Nenti|087745677969|30/09/2001|
|2|02B|BlaBlaBla|Nurul|087899880101|29/02/2000|
|3|01B|iniPW|Rifa'i |0888272721111|02/02/2002|

Sekarang semua tabel sudah tersertifikasi normalisasi bentuk ke-3.

---
## Hasil Akhir Tabel

#### Tabel santri
|🔑id_santri|id_pembimbing|pass|nama|kontak|tanggal_lahir|
|---|---|---|---|---|---|---|
|1|01A|nenti01|Nenti|087745677969|30/09/2001|
|2|02B|BlaBlaBla|Nurul|087899880101|29/02/2000|
|3|01B|iniPW|Rifa'i |0888272721111|02/02/2002|

#### Tabel pembimbing
|🔑id_pembimbing|kode_kelas|pass|nama|kontak|link_meeting|
|---|---|---|---|---|---|
|1|01A|halhal01|Halimah|089923230001||https://linkmeet1|
|2|02B|zainAB|Zainab|089923230001|https://linkmeet2|
|3|01B|haigais|Haikal|087726260506|https://linkmeet12|

#### Tabel setoran
|🔑id_setoran|id_santri|waktu|keterangan|
|---|---|---|---|---|---|
|1|1|1|8|07/04/2022|Ziyadah|
|2|2|2|13|07/04/2022|Murajaah|
|3|3|3|5|07/04/2022|Ziyadah|

#### Tabel item setoran
|🔑id_setoran|🔑id_ayat|
|---|---|
|5|3|
|8|1|
|13|2|

## Tabel ayat_surat
|🔑id_ayat|id_surat|no_ayat|juz|
|---|---|---|---|
|8|2|1|1|
|200|2|208|2|
|108|2|100|1|

#### Tabel surat
|🔑id_surat|nama_surat|
|---|---|
|1|Al-Fatihah|
|2|Al-Baqarah|
|3|Ali Imran|
