## A. Temuan dan perbaikan

| No. | Temuan | Perbaikan yang dilakukan | Alasan |
|---|---|---|---|
| 1 | Activity Pengembalian pada jobsheet memuat action "Menyerahkan peralatan yang dipinjam" (Mahasiswa), padahal Tabel 5.12 (LAB-UC11) hanya memuat langkah Petugas Laboratorium dan Sistem | Mengikuti urutan Langkah 5 jobsheet; asal action ini dicatat pada metadata | Jobsheet menetapkan urutan ini; pada tabel skenario P05 langkah tersebut tidak ada, sehingga keterlacakannya perlu dicatat |
| 2 | Nama action "Mencatat hasil keputusan pengajuan" (Langkah 2) dan "Mencatat hasil akhir pengajuan" (Langkah 3) berbeda | Memakai "Mencatat hasil akhir pengajuan" pada diagram final | Diagram final mengikuti Langkah 3 dan Gambar 6.1 agar satu action tidak punya dua nama |
| 3 | Swimlane Activity Lihat Ketersediaan memakai "Peminjam", sedangkan Activity Peminjaman memakai "Mahasiswa" | Tiap diagram mengikuti jobsheet | Tabel 5.3 dan 5.1 menulis aktor Peminjam (berlaku untuk Mahasiswa dan Dosen); jobsheet menyebut lane Mahasiswa untuk Peminjaman |
| 4 | Action SIA "Memeriksa dan mengesahkan nilai", "Menyiapkan publikasi hasil studi", dan "Mengirim pemberitahuan hasil studi" tidak ada pada tabel SIA-UC08 dan SIA-UC09 Pertemuan 5 | Digambar sesuai Bagian C.3 dan ditandai sebagai unsur dari jobsheet pada metadata; tabel P05 tidak diubah | Tugas SIA menetapkan unsur ini untuk melatih empat swimlane serta fork dan join |
| 5 | Guard Pengembalian berubah dari [baik] dan [rusak] (Tahap 4) menjadi [baik dan lengkap] dan [rusak atau tidak lengkap] (Tahap 5) | Diagram final memakai guard Tahap 5 | Setelah fork dan join, keputusan bergantung pada dua pemeriksaan |
| 6 | Decision "Peralatan tersedia?" pada Activity Lihat Ketersediaan terjadi setelah daftar ditampilkan | Mengikuti Langkah 7 jobsheet | Cabang [tidak tersedia] merepresentasikan skenario Alternative "tidak ada peralatan yang tersedia" |
| 7 | Activity Kelola Data Peralatan memuat satu persilangan garis (jalur [tidak ditemukan] dan jalur [hapus]) | Dipertahankan; hanya ada satu activity final node | Memisahkan activity final node akan melanggar "tepat satu activity final node" pada Tujuan 1 |

## B. Catatan perbandingan tugas mandiri (Activity Proses Keputusan Peminjaman, LAB-UC06)

Diagram digambar dari Tabel 5.10 lalu diperiksa dengan checklist C.4, kemudian dibandingkan dengan Gambar 6.6.

| No. | Pembanding (Gambar 6.6) | Diagram saya | Perbedaan dan perbaikan |
|---|---|---|---|
| 1 | Action Disetujui dan Ditolak diletakkan bertumpuk di lane Sistem | Diletakkan berdampingan sehingga lebih ringkas | Hanya tata letak; alur dan guard sama |
| 2 | Jalur [tidak dapat diproses] bermuara ke activity final node dari sisi kanan | Sama | Tidak ada perbedaan |
| 3 | Memilih pengajuan dan menetapkan keputusan digabung dalam satu action | Digabung mengikuti Tabel 5.10 langkah 3 | Sesuai temuan T1 pada Pertemuan 5, action ini sebaiknya dipecah bila Tabel 5.10 direvisi |

Kesimpulan: tidak ada perbedaan unsur atau alur dengan pembanding; satu perbedaan tata letak dan satu catatan tindak lanjut terhadap tabel skenario.
