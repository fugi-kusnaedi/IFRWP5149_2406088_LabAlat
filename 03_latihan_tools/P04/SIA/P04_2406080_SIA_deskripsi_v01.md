# P04 SIA — Use Case Description (v01)

Template sama dengan Pertemuan 3, ditambah baris Collaboration dan Generalization bila relevan. Deskripsi ditulis untuk use case, bukan untuk collaboration.

## SIA-UC08 — Input Nilai Mata Kuliah

| Elemen | SIA-UC08: Input Nilai Mata Kuliah |
|---|---|
| ID dan nama | SIA-UC08: Input Nilai Mata Kuliah |
| Sumber kebutuhan | SIA-R08 dan SIA-R12 |
| Tujuan | Nilai mata kuliah yang diampu dosen tersimpan |
| Aktor utama | Dosen |
| Aktor pendukung | — |
| Pemicu | Dosen memilih fungsi input nilai dan menentukan mata kuliah yang diampunya |
| Prasyarat | Dosen telah terautentikasi; dosen adalah pengampu mata kuliah tersebut; masa perkuliahan telah berakhir |
| Pascakondisi berhasil | Nilai mata kuliah tersimpan dengan status belum terpublikasi |
| Pascakondisi gagal | Tidak ada nilai baru yang tersimpan |
| Collaboration | SIA-CO01: Input Nilai Mata Kuliah |
| Aturan bisnis/asumsi | Hanya dosen pengampu yang dapat menginput nilai. Nilai yang diinput belum terpublikasi; KHS hanya menampilkan nilai yang sudah dipublikasikan. Rentang nilai yang sah belum ditetapkan skenario (pertanyaan terbuka no. 1) |

Alur utama:

| Langkah | Tindakan dosen | Respons sistem |
|---|---|---|
| 1 | Memilih fungsi input nilai dan mata kuliah yang diampu | Memeriksa bahwa dosen adalah pengampu; menampilkan daftar mahasiswa peserta mata kuliah |
| 2 | Mengisi nilai setiap mahasiswa | Menampung isian |
| 3 | Mengirim nilai | Memeriksa bahwa setiap nilai berada dalam rentang yang sah |
| 4 | — | Menyimpan nilai dengan status belum terpublikasi |
| 5 | Melihat konfirmasi | Menampilkan ringkasan nilai yang tersimpan |

Alur alternatif/pengecualian:

| Ref | Kondisi | Penanganan |
|---|---|---|
| A1 (langkah 1) | Dosen bukan pengampu mata kuliah | Sistem menolak dan menampilkan pesan; tidak ada nilai tersimpan; pascakondisi gagal berlaku |
| A2 (langkah 3) | Ada nilai di luar rentang yang sah | Sistem menolak nilai tersebut dan meminta koreksi; nilai tidak disimpan sampai semua nilai sah atau dosen membatalkan; bila dibatalkan, pascakondisi gagal berlaku |

## SIA-UC09 — Lihat KHS (ringkas)

| Elemen | SIA-UC09: Lihat KHS |
|---|---|
| ID dan nama | SIA-UC09: Lihat KHS |
| Sumber kebutuhan | SIA-R09 dan SIA-R12 |
| Tujuan | Mahasiswa memperoleh KHS untuk semester yang nilainya sudah dipublikasikan |
| Aktor utama | Mahasiswa |
| Pemicu | Mahasiswa memilih fungsi lihat KHS dan menentukan semester |
| Prasyarat | Mahasiswa telah terautentikasi |
| Pascakondisi berhasil | KHS tampil dan hanya memuat nilai yang sudah dipublikasikan; tidak ada data berubah |
| Pascakondisi gagal | KHS tidak tampil; tidak ada data berubah |
| Collaboration | SIA-CO02: Lihat KHS |
| Aturan bisnis/asumsi | Hanya nilai yang sudah dipublikasikan yang ditampilkan; nilai belum terpublikasi tidak muncul |

Alur utama: (1) Mahasiswa memilih fungsi lihat KHS dan semester; (2) sistem mengambil nilai yang sudah dipublikasikan untuk semester itu; (3) sistem menampilkan KHS.
Alur alternatif: A1 (langkah 2) semester belum memiliki nilai terpublikasi, sistem menampilkan pesan bahwa KHS belum tersedia dan pascakondisi gagal berlaku.

## SIA-UC07 — Lihat Kalender Akademik

| Elemen | SIA-UC07: Lihat Kalender Akademik |
|---|---|
| Sumber kebutuhan | SIA-R07 |
| Tujuan | Civitas Akademika memperoleh agenda resmi institusi |
| Aktor utama | Civitas Akademika (aktor umum); Mahasiswa dan Dosen menjalankannya melalui pewarisan |
| Pemicu | Aktor memilih fungsi lihat kalender akademik |
| Prasyarat | Aktor telah terautentikasi |
| Pascakondisi berhasil | Agenda kalender akademik tampil; tidak ada data berubah |
| Pascakondisi gagal | Kalender tidak tampil; tidak ada data berubah |
| Aturan bisnis/asumsi | Kalender akademik adalah agenda resmi institusi, bukan jadwal kuliah (SIA-UC01) |

Alur utama: (1) aktor memilih fungsi kalender akademik; (2) sistem menampilkan agenda kalender. Alternatif: A1 (langkah 2) data kalender belum tersedia, sistem menampilkan pesan dan pascakondisi gagal berlaku.

## SIA-UC10 — Kelola Data Mahasiswa

| Elemen | SIA-UC10: Kelola Data Mahasiswa |
|---|---|
| Sumber kebutuhan | SIA-R10 |
| Tujuan | Data mahasiswa terkelola melalui tiga bentuk khusus |
| Aktor utama | Admin Akademik |
| Pemicu | Admin Akademik memilih fungsi pengelolaan data mahasiswa |
| Prasyarat | Admin Akademik telah terautentikasi |
| Generalization | Use case umum bagi SIA-UC11, SIA-UC12, dan SIA-UC13 |
| Pascakondisi berhasil | Data mahasiswa terkelola sesuai bentuk khusus yang dijalankan |
| Pascakondisi gagal | Data mahasiswa tidak berubah |

## SIA-UC11 — Tambah Data Mahasiswa

| Elemen | SIA-UC11: Tambah Data Mahasiswa |
|---|---|
| Sumber kebutuhan | SIA-R11 |
| Generalization | Khusus dari SIA-UC10 |
| Perilaku pembeda | Menghasilkan data mahasiswa baru yang tersimpan |
| Pascakondisi berhasil | Data mahasiswa baru tersimpan |
| Pascakondisi gagal | Tidak ada data mahasiswa baru yang tersimpan |

## SIA-UC12 — Ubah Data Mahasiswa

| Elemen | SIA-UC12: Ubah Data Mahasiswa |
|---|---|
| Sumber kebutuhan | SIA-R11 |
| Generalization | Khusus dari SIA-UC10 |
| Perilaku pembeda | Menghasilkan data mahasiswa yang berubah |
| Pascakondisi berhasil | Perubahan data mahasiswa tersimpan |
| Pascakondisi gagal | Data mahasiswa tetap seperti semula |

## SIA-UC13 — Hapus Data Mahasiswa

| Elemen | SIA-UC13: Hapus Data Mahasiswa |
|---|---|
| Sumber kebutuhan | SIA-R11 |
| Generalization | Khusus dari SIA-UC10 |
| Perilaku pembeda | Menghasilkan data mahasiswa yang terhapus, hanya untuk mahasiswa tanpa data akademik aktif |
| Prasyarat | Admin Akademik telah terautentikasi |
| Pascakondisi berhasil | Data mahasiswa terhapus |
| Pascakondisi gagal | Data mahasiswa tetap ada |
| Aturan bisnis/asumsi | Arti "data akademik aktif" belum dirinci skenario (pertanyaan terbuka no. 3) |

Alur alternatif: A1, mahasiswa terpilih masih memiliki data akademik aktif; sistem menolak penghapusan dan menampilkan alasannya; data tetap ada; pascakondisi gagal berlaku.
