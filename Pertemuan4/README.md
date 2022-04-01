# Aplikasi Pembelajaran Program Tahfidz Berbasis Online

## Deskripsi:
Dimasa pandemi ini banyak kegitan yang sebelumnya dilakukan secara offline, kini harus berpindah ke online, tak terkecuali di bidang pembelajaran.
Program tahfidz yang dulunya dilakukan secara offline, mau tidak mau harus beradaptasi juga.
Aplikasi ini bertujuan untuk mempermudah proses pembelajaran program tahfidz melalui media online, dan mempermudah proses pendataannya.

## Fitur-Fitur:
1. Melakukan pendataan santri yang mendaftar
2. Mengelompokan santri kedalam kelas-kelas agar pengajar lebih mudah dalam mengawasi hafalan santri
3. Melakukan pendataan progress hafalan santri
4. Menyediakan fitur meet conference untuk proses setoran

## Entitas dan Atribut:
### Santri
- */ ID
- Nama Santri
- Usia
- Jumlah Hafalan
- Kontak
- Kelas

### Pembimbing
- */ ID
- Nama Pembimbing
- Kontak

### Kelas
- */ ID
- ID santri
- ID Pembimbing
- Link Meeting
- Kriteria

### Setoran
- */ ID santri
- ID pembimbing
- Tanggal

### Item Setoran
- */ ID Setoran
- Ayat
- Surat
- Keterangan

## Relasionship
- Santri 1 1 - 0 N Setoran Hafalan
- Santri 1 N - 1 1 Kelas
- Kelas 1 1 - 1 1 Pembimbing
- Pembimbing 1 1 - 0 N Setoran Hafalan
- Setoran Hafalan 1 1 - 1 N Item Setoran
