# Skenario Use Case SIA, Layanan Hasil Studi (Pertemuan 5)

Tugas SIA: tujuh tabel skenario untuk SIA-UC07 sampai SIA-UC13. Diagram SIA Pertemuan 4 tidak diubah.

## Tabel 5.15 Skenario Use Case SIA-UC07 Lihat Kalender Akademik

| Nama use case | SIA-UC07 Lihat Kalender Akademik |
|---|---|
| Aktor | Civitas Akademika (berlaku untuk Mahasiswa dan Dosen) |
| Tujuan | Civitas Akademika dapat mengetahui kegiatan akademik pada periode yang dipilih |
| Deskripsi | Civitas Akademika membuka fungsi kalender akademik, memilih periode akademik, dan melihat daftar kegiatan akademik beserta tanggalnya |
| **Kegiatan** | **Respon sistem** |
| **Skenario Normal** | |
| 1. Civitas Akademika membuka fungsi Lihat Kalender Akademik | |
| | 2. Sistem menampilkan daftar periode akademik (tahun akademik dan semester) |
| 3. Civitas Akademika memilih periode akademik | |
| | 4. Sistem menampilkan kalender akademik berisi nama kegiatan, tanggal mulai, dan tanggal selesai |
| **Skenario Alternative** | |
| 5. Kalender akademik belum tersedia pada periode yang dipilih (cabang dari langkah 4) | |
| | 6. Sistem menampilkan pesan kalender akademik belum tersedia untuk periode tersebut |
| **Skenario Akhir** | Use case selesai jika kalender akademik periode yang dipilih ditampilkan; jika kalender belum tersedia, use case selesai dengan pesan tersebut. |

Keterangan tabel: skenario ditulis satu kali atas nama Civitas Akademika karena Mahasiswa dan Dosen mewarisi SIA-UC07 Lihat Kalender Akademik dari Civitas Akademika (generalization aktor); perilakunya sama sehingga tidak ada tabel ganda untuk Mahasiswa maupun Dosen. Use case ini tidak mempunyai relasi include, extend, maupun realization pada Tabel 5.14. Sumber kebutuhan: SIA-R07.

## Tabel 5.16 Skenario Use Case SIA-UC08 Input Nilai Mata Kuliah

| Nama use case | SIA-UC08 Input Nilai Mata Kuliah |
|---|---|
| Aktor | Dosen (dosen pengampu mata kuliah) |
| Tujuan | Nilai mahasiswa pada mata kuliah yang diampu tersimpan |
| Deskripsi | Dosen pengampu memilih mata kuliah yang diampu, mengisi nilai mahasiswa, dan menyimpan nilai. Prasyarat: dosen adalah pengampu mata kuliah yang dipilih; masa perkuliahan telah berakhir |
| **Kegiatan** | **Respon sistem** |
| **Skenario Normal** | |
| 1. Dosen membuka fungsi Input Nilai Mata Kuliah | |
| | 2. Sistem menampilkan daftar mata kuliah |
| 3. Dosen memilih mata kuliah yang diampu | |
| | 4. Sistem memeriksa dosen adalah pengampu mata kuliah tersebut dan menampilkan daftar mahasiswa peserta beserta isian nilai |
| 5. Dosen mengisi nilai setiap mahasiswa | |
| | 6. Sistem memeriksa setiap nilai berada dalam rentang yang sah |
| 7. Dosen menyimpan nilai | |
| | 8. Sistem menyimpan nilai dengan status belum terpublikasi dan menampilkan ringkasan nilai yang tersimpan |
| **Skenario Alternative** | |
| 9. Dosen bukan pengampu mata kuliah yang dipilih (cabang dari langkah 4) | |
| | 10. Sistem menolak dan menampilkan pesan dosen bukan pengampu; tidak ada nilai yang tersimpan |
| 11. Ada nilai di luar rentang yang sah (cabang dari langkah 6) | |
| | 12. Sistem menolak nilai tersebut dan meminta dosen mengoreksi nilai; nilai tidak disimpan sampai semua nilai sah |
| **Skenario Akhir** | Use case selesai jika nilai mata kuliah tersimpan dengan status belum terpublikasi; jika dosen bukan pengampu atau ada nilai di luar rentang yang sah, nilai tidak tersimpan. |

Keterangan tabel: use case ini direalisasikan oleh collaboration SIA-CO01 Input Nilai Mata Kuliah. Collaboration tersebut tidak mempunyai langkah kegiatan pada tabel ini. Nilai hanya dapat diinput oleh dosen pengampu mata kuliah tersebut. Rentang nilai yang sah belum ditetapkan skenario (pertanyaan terbuka no. 1 pada kebutuhan P04). Sumber kebutuhan: SIA-R08 dan SIA-R12.

## Tabel 5.17 Skenario Use Case SIA-UC09 Lihat KHS

| Nama use case | SIA-UC09 Lihat KHS |
|---|---|
| Aktor | Mahasiswa |
| Tujuan | Mahasiswa dapat melihat hasil studi berupa nilai yang sudah dipublikasikan |
| Deskripsi | Mahasiswa membuka fungsi KHS, memilih semester, dan melihat nilai mata kuliah yang sudah dipublikasikan |
| **Kegiatan** | **Respon sistem** |
| **Skenario Normal** | |
| 1. Mahasiswa membuka fungsi Lihat KHS | |
| | 2. Sistem menampilkan daftar semester milik mahasiswa tersebut |
| 3. Mahasiswa memilih semester | |
| | 4. Sistem menampilkan KHS yang hanya memuat mata kuliah dengan nilai berstatus Dipublikasikan |
| **Skenario Alternative** | |
| 5. Semester yang dipilih belum memiliki nilai yang dipublikasikan (cabang dari langkah 4) | |
| | 6. Sistem menampilkan pesan KHS belum tersedia untuk semester tersebut |
| **Skenario Akhir** | Use case selesai jika KHS berisi nilai yang sudah dipublikasikan ditampilkan; jika semester belum memiliki nilai yang dipublikasikan, KHS tidak ditampilkan dan use case selesai dengan pesan tersebut. |

Keterangan tabel: use case ini direalisasikan oleh collaboration SIA-CO02 Lihat KHS. Collaboration tersebut tidak mempunyai langkah kegiatan pada tabel ini. KHS hanya menampilkan nilai yang sudah dipublikasikan. Sumber kebutuhan: SIA-R09 dan SIA-R12.

## Tabel 5.18 Skenario Use Case SIA-UC10 Kelola Data Mahasiswa

| Nama use case | SIA-UC10 Kelola Data Mahasiswa |
|---|---|
| Aktor | Admin Akademik |
| Tujuan | Data mahasiswa terkelola melalui satu fungsi pengelolaan bersama |
| Deskripsi | Admin Akademik membuka fungsi pengelolaan data mahasiswa, memilih bentuk pengelolaan, dan menyimpan perubahan. Bentuk tambah, ubah, dan hapus dijabarkan pada tabel khususnya masing-masing |
| **Kegiatan** | **Respon sistem** |
| **Skenario Normal** | |
| 1. Admin Akademik membuka fungsi Kelola Data Mahasiswa | |
| | 2. Sistem menampilkan daftar data mahasiswa |
| 3. Admin Akademik memilih bentuk pengelolaan, yaitu tambah, ubah, atau hapus | |
| | 4. Sistem menampilkan formulir sesuai bentuk pengelolaan yang dipilih |
| 5. Admin Akademik mengisi atau mengonfirmasi data | |
| | 6. Sistem memeriksa kelengkapan dan keabsahan data |
| 7. Admin Akademik menyimpan perubahan | |
| | 8. Sistem menyimpan perubahan dan menampilkan konfirmasi |
| **Skenario Alternative** | |
| 9. Data tidak lengkap atau tidak sah (cabang dari langkah 6) | |
| | 10. Sistem menolak penyimpanan dan menampilkan pesan kesalahan data |
| **Skenario Akhir** | Use case selesai jika perubahan data mahasiswa tersimpan; jika data tidak lengkap atau tidak sah, perubahan tidak tersimpan. |

Keterangan tabel: use case umum yang memuat perilaku bersama. Langkah bersama ini dirujuk oleh SIA-UC11 Tambah Data Mahasiswa, SIA-UC12 Ubah Data Mahasiswa, dan SIA-UC13 Hapus Data Mahasiswa (generalization use case). Sumber kebutuhan: SIA-R10.

## Tabel 5.19 Skenario Use Case SIA-UC11 Tambah Data Mahasiswa

| Nama use case | SIA-UC11 Tambah Data Mahasiswa |
|---|---|
| Aktor | Admin Akademik |
| Tujuan | Data mahasiswa baru tersimpan sebagai bentuk khusus dari pengelolaan data mahasiswa |
| Deskripsi | Admin Akademik mengisi data mahasiswa baru dan menyimpan data tersebut; langkah bersama mengikuti Tabel skenario SIA-UC10 |
| **Kegiatan** | **Respon sistem** |
| **Skenario Normal** | |
| 1. Admin Akademik membuka fungsi Tambah Data Mahasiswa | |
| | 2. Sistem menampilkan formulir data mahasiswa baru |
| 3. Admin Akademik mengisi data mahasiswa baru (NIM, nama, dan program studi) | |
| | 4. Sistem memeriksa kelengkapan data |
| 5. Admin Akademik menyimpan data | |
| | 6. Sistem menyimpan data mahasiswa baru dan menampilkan konfirmasi |
| **Skenario Alternative** | |
| 7. Data tidak lengkap (cabang dari langkah 4) | |
| | 8. Sistem menolak penyimpanan dan meminta Admin Akademik melengkapi data |
| **Skenario Akhir** | Use case selesai jika data mahasiswa baru tersimpan; jika data tidak lengkap, data tidak tersimpan. |

Keterangan: use case khusus dari SIA-UC10 Kelola Data Mahasiswa. Perilaku pembeda: data mahasiswa baru tersimpan. Langkah bersama mengikuti Tabel skenario SIA-UC10. Sumber kebutuhan: SIA-R11.

## Tabel 5.20 Skenario Use Case SIA-UC12 Ubah Data Mahasiswa

| Nama use case | SIA-UC12 Ubah Data Mahasiswa |
|---|---|
| Aktor | Admin Akademik |
| Tujuan | Data mahasiswa berubah sebagai bentuk khusus dari pengelolaan data mahasiswa |
| Deskripsi | Admin Akademik memilih data mahasiswa, mengubah datanya, dan menyimpan perubahan; langkah bersama mengikuti Tabel skenario SIA-UC10 |
| **Kegiatan** | **Respon sistem** |
| **Skenario Normal** | |
| 1. Admin Akademik memilih data mahasiswa yang akan diubah | |
| | 2. Sistem menampilkan data mahasiswa saat ini |
| 3. Admin Akademik mengubah data mahasiswa | |
| | 4. Sistem memeriksa perubahan data |
| 5. Admin Akademik menyimpan perubahan | |
| | 6. Sistem menyimpan data yang diubah dan menampilkan konfirmasi |
| **Skenario Alternative** | |
| 7. Data mahasiswa tidak ditemukan (cabang dari langkah 2) | |
| | 8. Sistem menampilkan pesan data mahasiswa tidak ditemukan |
| **Skenario Akhir** | Use case selesai jika perubahan data mahasiswa tersimpan; jika data tidak ditemukan, perubahan tidak tersimpan. |

Keterangan: use case khusus dari SIA-UC10 Kelola Data Mahasiswa. Perilaku pembeda: data mahasiswa berubah. Langkah bersama mengikuti Tabel skenario SIA-UC10. Sumber kebutuhan: SIA-R11.

## Tabel 5.21 Skenario Use Case SIA-UC13 Hapus Data Mahasiswa

| Nama use case | SIA-UC13 Hapus Data Mahasiswa |
|---|---|
| Aktor | Admin Akademik |
| Tujuan | Data mahasiswa terhapus sebagai bentuk khusus dari pengelolaan data mahasiswa |
| Deskripsi | Admin Akademik memilih data mahasiswa, mengonfirmasi penghapusan, dan sistem menghapus data tersebut; langkah bersama mengikuti Tabel skenario SIA-UC10 |
| **Kegiatan** | **Respon sistem** |
| **Skenario Normal** | |
| 1. Admin Akademik memilih data mahasiswa yang akan dihapus | |
| | 2. Sistem memeriksa mahasiswa tidak memiliki data akademik aktif |
| 3. Admin Akademik mengonfirmasi penghapusan | |
| | 4. Sistem menghapus data mahasiswa dan menampilkan konfirmasi penghapusan |
| **Skenario Alternative** | |
| 5. Mahasiswa memiliki data akademik aktif (cabang dari langkah 2) | |
| | 6. Sistem menolak penghapusan dan menampilkan pesan mahasiswa masih memiliki data akademik aktif |
| **Skenario Akhir** | Use case selesai jika data mahasiswa terhapus; jika mahasiswa memiliki data akademik aktif, data tidak terhapus. |

Keterangan: use case khusus dari SIA-UC10 Kelola Data Mahasiswa. Perilaku pembeda: data mahasiswa terhapus, dengan syarat mahasiswa tidak memiliki data akademik aktif. Langkah bersama mengikuti Tabel skenario SIA-UC10. Sumber kebutuhan: SIA-R11.
