# P04 SIA — Kebutuhan dan Batas (v01)

## Skenario (ditetapkan jobsheet, fiktif)
Mahasiswa dan dosen sama-sama merupakan Civitas Akademika yang dapat melihat kalender akademik. Dosen menginput nilai mata kuliah yang diampunya setelah masa perkuliahan berakhir. Mahasiswa melihat Kartu Hasil Studi (KHS) untuk semester yang nilainya sudah dipublikasikan. Admin Akademik mengelola data mahasiswa: menambah data mahasiswa baru, mengubah data mahasiswa, dan menghapus data mahasiswa. Dua use case utama, Input Nilai Mata Kuliah dan Lihat KHS, ditunjukkan realisasinya oleh collaboration yang bersesuaian.

## Kebutuhan baru Pertemuan 4
| ID | Kebutuhan tugas |
|---|---|
| SIA-R07 | Mahasiswa dan Dosen, sebagai Civitas Akademika, dapat melihat kalender akademik |
| SIA-R08 | Dosen dapat menginput nilai mata kuliah yang diampunya |
| SIA-R09 | Mahasiswa dapat melihat KHS untuk semester yang nilainya sudah dipublikasikan |
| SIA-R10 | Admin Akademik dapat mengelola data mahasiswa |
| SIA-R11 | Pengelolaan data mahasiswa terdiri dari tiga bentuk khusus: tambah, ubah, dan hapus data mahasiswa |
| SIA-R12 | Model menunjukkan collaboration yang merealisasikan Input Nilai Mata Kuliah dan Lihat KHS |

SIA-R01 dan SIA-R02 (Pertemuan 2) serta SIA-R03 sampai SIA-R06 (Pertemuan 3) tetap berlaku, tidak berubah arti, dan tidak disalin ulang; rujuk berkas P02 dan P03.

## Batas dan asumsi yang sudah ditetapkan
- Kode kebutuhan dimulai dari SIA-R07 agar SIA-R01 sampai SIA-R06 tetap mempunyai identitas berbeda.
- Pengguna telah terautentikasi dan memiliki hak akses sesuai peran.
- Kalender akademik adalah agenda resmi institusi (awal semester, batas KRS, masa ujian, dan sejenisnya), bukan jadwal kuliah Pertemuan 2.
- Nilai hanya dapat diinput oleh dosen pengampu mata kuliah tersebut. Nilai yang diinput belum terpublikasi; KHS hanya menampilkan nilai yang sudah dipublikasikan.
- Hapus Data Mahasiswa hanya untuk mahasiswa yang tidak memiliki data akademik aktif (ketentuan fiktif untuk latihan).
- Pengajuan KRS tetap digambar sebagai bagian diagram kumulatif dari Pertemuan 3.
- Pembayaran dan perancangan basis data berada di luar tugas.

## Pertanyaan belum terjawab (tidak diputuskan sendiri)
1. Rentang nilai yang sah pada Input Nilai Mata Kuliah belum ditetapkan skenario.
2. Siapa dan melalui fungsi apa nilai dinyatakan resmi (dipublikasikan) belum dimodelkan.
3. Apa yang dimaksud "data akademik aktif" pada Hapus Data Mahasiswa belum dirinci.
4. Dosen Wali dan Dosen dimodelkan sebagai aktor terpisah; apakah Dosen Wali bentuk khusus dari Dosen tidak ditetapkan jobsheet, sehingga tidak digambar sebagai generalization.

## Metadata tambahan P04
- Generalization yang digunakan: aktor (Mahasiswa → Civitas Akademika, Dosen → Civitas Akademika); use case (SIA-UC11, UC12, UC13 → SIA-UC10).
- Collaboration yang digunakan: SIA-CO01 Input Nilai Mata Kuliah (merealisasikan SIA-UC08), SIA-CO02 Lihat KHS (merealisasikan SIA-UC09).
- Sumber kebutuhan baru: SIA-R07 sampai SIA-R12.

## Uji konsistensi (Langkah 8)

### Situasi A — Mahasiswa melihat kalender akademik tanpa garis langsung ke SIA-UC07
Hasilnya sah. Di diagram, Mahasiswa adalah bentuk khusus Civitas Akademika, dan satu-satunya asosiasi ke SIA-UC07 ada pada Civitas Akademika. Karena aktor khusus mengambil alih seluruh kemampuan aktor umum, Mahasiswa dapat menjalankan SIA-UC07 tanpa garis sendiri. Kalau garis itu digambar ulang dari Mahasiswa dan Dosen, justru melanggar aturan generalization.

### Situasi B — Dosen yang bukan pengampu mencoba menginput nilai
Sistem menolak. Menurut deskripsi SIA-UC08, langkah 1 memeriksa apakah dosen pengampu mata kuliah terpilih. Bila bukan, alur alternatif A1 berjalan: tidak ada nilai tersimpan dan pascakondisi gagal berlaku. Diagram hanya menyatakan bahwa Dosen berhak menjalankan fungsi input nilai; pembatasan mata kuliah diatur di deskripsi, bukan di garis diagram.

### Situasi C — Admin Akademik menghapus data mahasiswa yang masih memiliki data akademik aktif
Penghapusan tidak dilakukan. Menurut aturan tugas dan alur alternatif A1 pada SIA-UC13, sistem menolak dan data mahasiswa tetap ada (pascakondisi gagal). Admin Akademik tetap berhak menjalankan SIA-UC13 lewat asosiasi ke SIA-UC10; yang ditolak hanya eksekusinya pada data dengan kondisi itu.

Diagram dan deskripsi konsisten untuk ketiga situasi.
