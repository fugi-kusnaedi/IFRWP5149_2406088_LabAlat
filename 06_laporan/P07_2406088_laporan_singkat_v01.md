# Laporan Singkat Pertemuan 7 — Sequence Diagram

| Identitas | Isi |
|---|---|
| Nama | Fugi Kusnaedi / 2406088 |
| Sumber | Jobsheet Pertemuan 7, Tabel 7.2, Tabel 7.3, dan checklist Bagian C.4 |
| Logbook terkait | `00_administrasi/P07_2406088_logbook_v01.md` |

## A. Temuan dan perbaikan

| No | Temuan | Perbaikan yang dilakukan | Alasan |
|---|---|---|---|
| 1 | Diagram peminjaman lama memakai lifeline `Peminjaman` sebagai aktor dan `Sistem Peminjaman` tanpa tanda titik dua | Aktor diubah menjadi `Peminjam`; objek antarmuka menjadi `:Sistem Peminjaman` | Checklist C.4 butir 3 dan 4: aktor mengikuti tabel skenario, objek diawali titik dua |
| 2 | Lifeline `:Pertalatan` dan guard `[Peralatan Tidal Tersedia]` mengandung kesalahan ketik | Diubah menjadi `:Peralatan` dan `[peralatan tidak tersedia]` | Nama class dan guard harus terbaca serta konsisten dengan Tabel 5.1 |
| 3 | Extend LAB-UC05 digambar dengan bingkai `alt`, padahal relasinya adalah extend | Diubah menjadi fragmen `opt` yang memuat kondisi `[mahasiswa memilih cetak]` dan titik ekstensi `Bukti pengajuan tersedia` | Kaidah 4.g dan checklist butir 8 |
| 4 | Diagram pengembalian tidak memiliki berkas sumber (`.drawio` masih 0 byte) | Diagram disusun dari Tabel 5.12 dan 5.13 dengan peserta `Petugas Laboratorium`, `:Sistem Peminjaman`, `:Pengembalian`, `:Peminjaman`, dan `:Peralatan` | Sesuai Langkah 6 pada jobsheet |
| 5 | Tabel 5.10 langkah 3 menggabungkan dua aksi, dan cabang penolakannya merujuk ke langkah setelah persetujuan | Aksi dipecah menjadi `3a. memilih pengajuan` dan `3b. menetapkan keputusan`; cabang tolak ditempatkan sebelum perubahan status | Catatan T1 Pertemuan 5 dan checklist butir 2 |
| 6 | Tugas SIA di jobsheet tidak menyediakan contoh jawaban | Alur disusun dari SIA-UC08, SIA-UC09, dan activity SIA Pertemuan 6; KHS sengaja tidak dijadikan lifeline | Aturan khusus Bagian C.3 pada jobsheet |
| 7 | Berkas pembanding Lampiran dan kandidat class pendamping tidak tersedia | Pemeriksaan memakai Tabel 5.10, Tabel 7.2, dan checklist; keterbatasan ini saya catat di logbook | Tidak mengarang isi berkas pembanding yang tidak ada |
| 8 | Penomoran pesan peminjaman belum sinkron dengan Tabel 7.2 dan label guard menimpa pesan | Nomor dikembalikan ke `7. ajukan()`, `8. nomor pengajuan`, `9. cetak bukti`, `10. bukti pengajuan` (pesan pada `alt` tanpa nomor); guard diperkecil dan ditempatkan berdampingan di header bingkai | Urutan langkah harus dapat ditelusur kembali ke Tabel 7.2 dan label tidak boleh saling menutupi |
| 9 | Lifeline peminjaman tertutup kotak keterangan dan activation bar kehilangan warna | Lifeline dipendekkan, kotak keterangan dihapus, warna activation bar dikembalikan; semua PNG hasil kerja diekspor ulang berlatar putih | Diagram perlu rapi dan tetap memenuhi checklist butir 10 |

## B. Perbandingan tugas mandiri — LAB-UC06 Proses Keputusan Peminjaman

Diagram digambar dari Tabel 5.10 tanpa membuka berkas pembanding, lalu diperiksa dengan checklist Bagian C.4.

| No | Pembanding (ketentuan jobsheet Langkah 7) | Diagram saya | Perbedaan dan perbaikan |
|---|---|---|---|
| 1 | Peserta: Petugas Laboratorium, `:Sistem Peminjaman`, `:Peminjaman` | Sama | Tidak ada perbedaan |
| 2 | Pengambilan daftar pengajuan berstatus Menunggu Keputusan | Pesan 1 dan 2: membuka daftar, lalu daftar ditampilkan | Sesuai; status ditulis eksplisit pada label |
| 3 | `alt` untuk pengajuan tidak ditemukan atau status sudah berubah | `alt` dengan operand `[pengajuan tersedia]` dan `[tidak ditemukan / status sudah berubah]` | Sesuai; operand kosong dipakai untuk keadaan normal |
| 4 | Operand `[petugas menyetujui]` memanggil `prosesKeputusan()` dan status menjadi Disetujui | Pesan 4 memanggil `prosesKeputusan()` pada `:Peminjaman`, disusul pesan balasan status Disetujui | Sesuai; balasan putus-putus ditambahkan |
| 5 | Operand `[petugas menolak]` mengubah status menjadi Ditolak | Pesan 6 mengubah status menjadi Ditolak pada `:Peminjaman`, disusul konfirmasi penolakan | Sesuai |
| 6 | Pemilihan pengajuan dan penetapan keputusan | Dipisah menjadi `3a` dan `3b` | Perbaikan terhadap Tabel 5.10 yang menggabungkan dua aksi |

**Kesimpulan:** tidak ada perbedaan unsur atau alur dengan ketentuan jobsheet. Satu perbaikan dilakukan pada pemisahan aksi, dan satu catatan ditulis mengenai tidak tersedianya berkas pembanding. Diagram dinyatakan lolos checklist C.4 dan siap dilengkapi dengan logbook perbaikan.

## C. Status berkas yang dikumpulkan

| Berkas | Status |
|---|---|
| `04_model_analisis/P07/LAB/P07_2406088_LAB_sequence_peminjaman_v01.drawio` + `.png` | ✅ |
| `04_model_analisis/P07/LAB/P07_2406088_LAB_sequence_pengembalian_v01.drawio` + `.png` | ✅ |
| `04_model_analisis/P07/LAB/P07_2406088_LAB_sequence_keputusan_v01.drawio` + `.png` | ✅ |
| `04_model_analisis/P07/SIA/P07_2406088_SIA_sequence_v01.drawio` + `.png` | ✅ |
| `00_administrasi/P07_2406088_logbook_v01.md` | ✅ |

Pemeriksaan akhir: tidak ada tabrakan teks pada keempat diagram yang dikumpulkan; seluruh PNG berlatar putih. Penomoran pesan peminjaman telah mengikuti Tabel 7.2.
