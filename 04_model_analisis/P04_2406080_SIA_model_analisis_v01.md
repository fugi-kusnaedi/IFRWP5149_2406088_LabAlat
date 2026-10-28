# P04 SIA — Model Analisis: Spesifikasi Hubungan Diagram Kumulatif (18 hubungan)

| Sumber | Hubungan | Tujuan |
|---|---|---|
| Civitas Akademika | Asosiasi | SIA-UC07 Lihat Kalender Akademik |
| Mahasiswa | Asosiasi | SIA-UC01 Lihat Jadwal Kuliah |
| Mahasiswa | Asosiasi | SIA-UC03 Ajukan KRS |
| Mahasiswa | Asosiasi | SIA-UC05 Unduh Bukti Pengajuan KRS |
| Mahasiswa | Asosiasi | SIA-UC09 Lihat KHS |
| Dosen | Asosiasi | SIA-UC08 Input Nilai Mata Kuliah |
| Admin Akademik | Asosiasi | SIA-UC02 Kelola Jadwal Kuliah |
| Admin Akademik | Asosiasi | SIA-UC10 Kelola Data Mahasiswa |
| Dosen Wali | Asosiasi | SIA-UC06 Proses Keputusan KRS |
| Mahasiswa | Generalization → | Civitas Akademika |
| Dosen | Generalization → | Civitas Akademika |
| SIA-UC11 Tambah Data Mahasiswa | Generalization → | SIA-UC10 Kelola Data Mahasiswa |
| SIA-UC12 Ubah Data Mahasiswa | Generalization → | SIA-UC10 Kelola Data Mahasiswa |
| SIA-UC13 Hapus Data Mahasiswa | Generalization → | SIA-UC10 Kelola Data Mahasiswa |
| SIA-UC03 Ajukan KRS | «include» (tetap dari Pertemuan 3) | SIA-UC04 Validasi KRS |
| SIA-UC05 Unduh Bukti Pengajuan KRS | «extend» (tetap dari Pertemuan 3); condition [mahasiswa memilih unduh]; extension point Bukti pengajuan tersedia | SIA-UC03 Ajukan KRS |
| SIA-CO01 Input Nilai Mata Kuliah | Realization → | SIA-UC08 Input Nilai Mata Kuliah |
| SIA-CO02 Lihat KHS | Realization → | SIA-UC09 Lihat KHS |

Catatan: tidak ada garis dari aktor ke collaboration, dan tidak ada asosiasi warisan yang digambar ulang dari Mahasiswa atau Dosen.
