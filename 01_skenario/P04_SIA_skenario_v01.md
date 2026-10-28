1. Tabel aktor
| Aktor | Kedudukan | Tujuan terhadap sistem |
|---|---|---|
| Civitas Akademika | Umum (general), baru pada Pertemuan 4 | Peran umum yang mewariskan fungsi melihat kalender akademik kepada Mahasiswa dan Dosen |
| Mahasiswa | Khusus dari Civitas Akademika | Melihat kalender akademik (diwarisi); melihat jadwal kuliah, mengajukan KRS, mengunduh bukti pengajuan KRS, dan melihat KHS (asosiasi langsung) |
| Dosen | Khusus dari Civitas Akademika, baru | Melihat kalender akademik (diwarisi); menginput nilai mata kuliah (asosiasi langsung) |
| Admin Akademik | Tetap dari Pertemuan 2 | Mengelola jadwal kuliah dan mengelola data mahasiswa |
| Dosen Wali | Tetap dari Pertemuan 3 | Memproses persetujuan atau penolakan KRS |

Lima aktor digambar pada diagram kumulatif. Yang baru: Civitas Akademika dan Dosen.

2. Katalog use case gabungan
ID lama tidak diganti nomornya sesuai jobsheet Pertemuan 4. Katalog ini mengikuti penomoran gabungan jobsheet (SIA-UC01 sampai SIA-UC06 mewakili fungsi Pertemuan 2 dan 3); berkas P03 tetap memakai penomoran aslinya.

| ID | Nama use case | Aktor terkait | Sumber kebutuhan | Tetap / Baru |
|---|---|---|---|---|
| SIA-UC01 | Lihat Jadwal Kuliah | Mahasiswa | SIA-R01 | Tetap (Pertemuan 2) |
| SIA-UC02 | Kelola Jadwal Kuliah | Admin Akademik | SIA-R02 | Tetap (Pertemuan 2) |
| SIA-UC03 | Ajukan KRS | Mahasiswa | SIA-R03, SIA-R05 | Tetap (Pertemuan 3); menyertakan SIA-UC04; diperluas SIA-UC05 |
| SIA-UC04 | Validasi KRS | — (dipanggil SIA-UC03) | SIA-R04 | Tetap (Pertemuan 3); perilaku yang disertakan SIA-UC03 |
| SIA-UC05 | Unduh Bukti Pengajuan KRS | Mahasiswa | SIA-R05 | Tetap (Pertemuan 3); tambahan bersyarat pada SIA-UC03 melalui «extend» |
| SIA-UC06 | Proses Keputusan KRS | Dosen Wali | SIA-R06 | Tetap (Pertemuan 3) |
| SIA-UC07 | Lihat Kalender Akademik | Civitas Akademika (diwarisi Mahasiswa dan Dosen) | SIA-R07 | Baru |
| SIA-UC08 | Input Nilai Mata Kuliah | Dosen | SIA-R08, SIA-R12 | Baru; direalisasikan SIA-CO01 |
| SIA-UC09 | Lihat KHS | Mahasiswa | SIA-R09, SIA-R12 | Baru; direalisasikan SIA-CO02 |
| SIA-UC10 | Kelola Data Mahasiswa | Admin Akademik | SIA-R10 | Baru; use case umum bagi SIA-UC11, UC12, UC13 |
| SIA-UC11 | Tambah Data Mahasiswa | Admin Akademik (melalui SIA-UC10) | SIA-R11 | Baru; khusus dari SIA-UC10 |
| SIA-UC12 | Ubah Data Mahasiswa | Admin Akademik (melalui SIA-UC10) | SIA-R11 | Baru; khusus dari SIA-UC10 |
| SIA-UC13 | Hapus Data Mahasiswa | Admin Akademik (melalui SIA-UC10) | SIA-R11 | Baru; khusus dari SIA-UC10 |

Relasi lama yang dipertahankan: SIA-UC03 «include» SIA-UC04; SIA-UC05 «extend» SIA-UC03 dengan extension point *Bukti pengajuan tersedia* dan kondisi [mahasiswa memilih unduh] (catatan tercantum di diagram).

3. Keputusan generalization aktor
- Mahasiswa adalah bentuk khusus dari Civitas Akademika, dan Dosen adalah bentuk khusus dari Civitas Akademika.
  Alasan: keduanya berbagi fungsi yang sama persis, yaitu melihat kalender akademik (SIA-R07). Kesamaan ini tidak kebetulan pada satu skenario, dan nama peran umum membuat diagram lebih jelas.
- Asosiasi ke SIA-UC07 digambar satu kali, dari Civitas Akademika. Tidak digambar ulang dari Mahasiswa maupun Dosen.
- Fungsi khusus tetap asosiasi langsung dari aktor khusus: Mahasiswa ke SIA-UC01, SIA-UC03, SIA-UC05, SIA-UC09; Dosen ke SIA-UC08. Fungsi ini tidak diwariskan ke aktor lain.
- Ujung segitiga kosong menempel pada Civitas Akademika. Panah Mahasiswa mengarah ke bawah dan panah Dosen mengarah ke atas; keduanya berakhir pada Civitas Akademika.

4. Keputusan generalization use case
Use case umum: **SIA-UC10 Kelola Data Mahasiswa**. Alasan: ketiga use case khusus adalah bentuk khusus pengelolaan data mahasiswa dengan hasil sejenis (data mahasiswa yang terkelola).
