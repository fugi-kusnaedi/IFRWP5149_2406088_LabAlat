# Lembar Skenario Pertemuan 5: Studi Kasus LAB

Skenario Use Case: Dari Diagram ke Langkah Kegiatan
Praktikum Analisis dan Desain Berorientasi Objek (IFRWP5149)

| Identitas | Isi |
|---|---|
| Nama | Fugi Kusnaedi |
| NIM | 2406088 |
| Folder | `IFRWP5149_2406088_LabAlat/01_skenario/` |
| Berkas | `P05_2406088_LAB_skenario_v01.md` |
| Diagram acuan | `03_latihan_tools/P04/LAB/P04_2406080_LAB_notasi_usecase_v01.drawio` (hanya dibaca, tidak diubah) |

---

## 1. Pemeriksaan awal diagram acuan (Langkah 1)

Diagram kumulatif Pertemuan 4 memuat **5 aktor**, **12 use case**, **2 collaboration**, dan **17 hubungan**.

- Aktor: Peminjam, Mahasiswa, Dosen, Petugas Laboratorium, Kepala Laboratorium.
- Use case: LAB-UC01 sampai LAB-UC12.
- Collaboration: LAB-CO01 Ajukan Peminjaman, LAB-CO02 Catat Pengembalian Peralatan.

Rekonstruksi 17 hubungan dari uraian tabel skenario. Cocokkan sekali lagi dengan Tabel 4.5 pada Jobsheet Pertemuan 4.

| No | Jenis relasi | Dari | Ke |
|---|---|---|---|
| 1 | Asosiasi | Peminjam | LAB-UC01 Lihat Ketersediaan Peralatan |
| 2 | Asosiasi | Peminjam | LAB-UC03 Ajukan Peminjaman |
| 3 | Asosiasi (khusus) | Mahasiswa | LAB-UC05 Cetak Bukti Pengajuan |
| 4 | Asosiasi | Petugas Laboratorium | LAB-UC02 Kelola Data Peralatan |
| 5 | Asosiasi | Petugas Laboratorium | LAB-UC06 Proses Keputusan Peminjaman |
| 6 | Asosiasi | Petugas Laboratorium | LAB-UC11 Catat Pengembalian Peralatan |
| 7 | Asosiasi | Kepala Laboratorium | LAB-UC07 Lihat Laporan Peminjaman |
| 8 | Generalization aktor | Mahasiswa | Peminjam |
| 9 | Generalization aktor | Dosen | Peminjam |
| 10 | Include | LAB-UC03 | LAB-UC04 Periksa Ketersediaan |
| 11 | Include | LAB-UC11 | LAB-UC12 Periksa Kondisi Peralatan |
| 12 | Extend (condition [mahasiswa memilih cetak]; extension point Bukti pengajuan tersedia) | LAB-UC05 | LAB-UC03 |
| 13 | Generalization use case | LAB-UC08 Tambah Data Peralatan | LAB-UC02 |
| 14 | Generalization use case | LAB-UC09 Ubah Data Peralatan | LAB-UC02 |
| 15 | Generalization use case | LAB-UC10 Hapus Data Peralatan | LAB-UC02 |
| 16 | Realization | LAB-CO01 | LAB-UC03 |
| 17 | Realization | LAB-CO02 | LAB-UC11 |

Jumlah: 7 asosiasi + 2 generalization aktor + 2 include + 1 extend + 3 generalization use case + 2 realization = **17**. Jumlah ini cocok dengan spesifikasi jobsheet.

---

## 2. Penelusuran tabel skenario terhadap diagram (Langkah 2 sampai 5)

Tiga hal diperiksa pada setiap tabel:
- (a) aktor pada baris Aktor sama dengan diagram;
- (b) setiap langkah kunci menelusur ke satu relasi diagram;
- (c) ID, nama use case, condition, dan extension point sama persis.

| Tabel skenario | Relasi yang ditelusur | Hasil pencocokan |
|---|---|---|
| Tabel 5.1 LAB-UC03 Ajukan Peminjaman | Asosiasi Peminjam ke UC03 (baris Aktor); generalization aktor Mahasiswa dan Dosen ke Peminjam (catatan aktor); include UC03 ke UC04 (langkah 2); extend UC05 ke UC03 (langkah 11 dan 12, condition [mahasiswa memilih cetak], extension point Bukti pengajuan tersedia); realization LAB-CO01 (keterangan) | **Sesuai.** (a) Peminjam. (b) 5 relasi tertelusur. (c) ID, nama, condition, dan extension point sama. |
| Tabel 5.3 LAB-UC01 Lihat Ketersediaan Peralatan | Asosiasi Peminjam ke UC01; generalization aktor Mahasiswa dan Dosen ke Peminjam. Tidak ada include, extend, atau realization | **Sesuai.** Aktor Peminjam (berlaku untuk Mahasiswa dan Dosen). Tidak ada langkah tanpa dasar diagram. |
| Tabel 5.4 LAB-UC04 Periksa Ketersediaan | Include dari UC03 (langkah 1 dan 4 mewakili pemanggilan dan kelanjutan alur UC03) | **Sesuai dengan catatan.** Aktor Peminjam berjalan di dalam UC03, tanpa asosiasi langsung. Lihat catatan T3 dan T5. |
| Tabel 5.5 LAB-UC05 Cetak Bukti Pengajuan | Asosiasi khusus Mahasiswa ke UC05; extend UC05 ke UC03 dengan condition dan extension point | **Sesuai.** Condition dan extension point sama dengan Tabel 5.1 langkah 11. |
| Tabel 5.6 LAB-UC02 Kelola Data Peralatan | Asosiasi Petugas Laboratorium ke UC02; sisi umum dari generalization UC08, UC09, UC10 ke UC02 | **Sesuai.** Memuat perilaku bersama. Lihat catatan T4. |
| Tabel 5.7 LAB-UC08 Tambah Data Peralatan | Generalization UC08 ke UC02; aktor Petugas Laboratorium melalui UC02 | **Sesuai.** Hanya memuat perilaku pembeda (data baru tersimpan), merujuk Tabel UC02. |
| Tabel 5.8 LAB-UC09 Ubah Data Peralatan | Generalization UC09 ke UC02; aktor Petugas Laboratorium melalui UC02 | **Sesuai.** Perilaku pembeda: data peralatan berubah. |
| Tabel 5.9 LAB-UC10 Hapus Data Peralatan | Generalization UC10 ke UC02; aktor Petugas Laboratorium melalui UC02 | **Sesuai.** Perilaku pembeda: terhapus dengan syarat tidak dipinjam dan tidak ada pengajuan aktif. |
| Tabel 5.10 LAB-UC06 Proses Keputusan Peminjaman | Asosiasi Petugas Laboratorium ke UC06; tidak ada relasi lain | **Sesuai dengan catatan.** Relasi dan nama cocok. Lihat catatan T1. |
| Tabel 5.11 LAB-UC07 Lihat Laporan Peminjaman | Asosiasi Kepala Laboratorium ke UC07, satu-satunya use case aktor ini; tanpa include, extend, generalization, atau realization | **Sesuai.** Tabel berdiri sendiri. Tidak ditemukan langkah include, extend, generalization, atau realization. |
| Tabel 5.12 LAB-UC11 Catat Pengembalian Peralatan | Asosiasi Petugas Laboratorium ke UC11; include UC11 ke UC12 (langkah 6, tanpa menyalin langkah UC12); realization LAB-CO02 (keterangan) | **Sesuai dengan catatan.** Include ditulis sebagai langkah rujukan pada Skenario Normal, bukan alternatif. Lihat catatan T2. |
| Tabel 5.13 LAB-UC12 Periksa Kondisi Peralatan | Include dari UC11; aktor Petugas Laboratorium berjalan di dalam UC11, tanpa asosiasi langsung | **Sesuai.** Nilai kondisi Baik, Rusak Ringan, dan Rusak Berat konsisten dengan Tabel 5.12 langkah 13. Lihat catatan T3. |

---

## 3. Checklist penilaian (bagian C.4)

| ✓ | Butir | Keterangan hasil telaah |
|---|---|---|
| ✓ | Seluruh field tabel terisi | Dua belas tabel memuat Nama use case, Aktor, Tujuan, Deskripsi, kolom Kegiatan dan Respon sistem, Skenario Normal, Skenario Alternative, dan Skenario Akhir. |
| ✓ | Langkah berurutan, satu aksi per langkah, penomoran berlanjut | Penomoran berlanjut dari Normal ke Alternative pada semua tabel. Pengecualian satu aksi per langkah ada pada T1 (Tabel 5.10 langkah 3). Langkah "menyimpan dan menampilkan konfirmasi" mengikuti gaya Tabel 5.1 langkah 6, jadi diterima. |
| ✓ | Kolom Kegiatan hanya aksi aktor, Respon sistem hanya tanggapan sistem | Terpenuhi, dengan dua catatan: T2 (Tabel 5.12 langkah 5) dan T3 (langkah pemanggilan oleh alur pada Tabel 5.4 dan 5.13). |
| ✓ | Data masukan dan data tampilan disebut eksplisit | Terpenuhi. Contohnya tanggal pinjam, tanggal rencana kembali, keperluan peminjaman, status Menunggu Keputusan, Disetujui, Ditolak, Dipinjam, Selesai, dan nilai kondisi Baik, Rusak Ringan, Rusak Berat. |
| ✓ | Include sebagai langkah rujukan pada Skenario Normal | UC03 ke UC04 (Tabel 5.1 langkah 2) dan UC11 ke UC12 (Tabel 5.12 langkah 6). Keduanya dengan nama, ID, dan rujukan tabel, tanpa menyalin langkah. |
| ✓ | Extend sebagai cabang bersyarat pada Skenario Alternative | UC05 ke UC03 (Tabel 5.1 langkah 11 dan 12) dengan condition [mahasiswa memilih cetak] dan extension point Bukti pengajuan tersedia, serta rujukan ke Tabel 5.5. |
| ✓ | Generalization aktor: satu tabel atas nama aktor umum | Tabel 5.1 dan 5.3 ditulis atas nama Peminjam (berlaku untuk Mahasiswa dan Dosen). Tidak ada tabel ganda. |
| ✓ | Generalization use case: umum memuat bersama, khusus memuat pembeda | Tabel 5.6 (UC02) memuat perilaku bersama. Tabel 5.7, 5.8, dan 5.9 memuat perilaku pembeda dan merujuk ke Tabel UC02. |
| ✓ | Collaboration disebut pada keterangan, tanpa langkah sendiri | LAB-CO01 pada Tabel 5.1 dan LAB-CO02 pada Tabel 5.12. Tidak ada tabel atau langkah untuk collaboration. |
| ✓ | Setiap tabel punya Skenario Alternative dan Skenario Akhir | Terpenuhi pada ke-12 tabel, termasuk UC01, UC07, dan UC12 yang jalurnya sederhana. |
| ✓ | Nama, ID, aktor, condition, extension point sama dengan diagram P04 | Terpenuhi (lihat bagian 2). |
| ✓ | Catatan aktor Kepala Laboratorium | Kepala Laboratorium hanya berhubungan dengan LAB-UC07, dan UC07 tidak punya relasi lain. Tabel 5.11 berdiri sendiri tanpa include, extend, generalization, atau realization. |
| ✓ | Berkas diagram P04 tidak diubah; dokumen disimpan pada 01_skenario dengan nama dan versi benar | Diagram hanya dibaca. Dokumen ini disimpan sebagai `P05_2406088_LAB_skenario_v01.md` pada `01_skenario`. Arsip `P04_LAB_skenario_v01.md` tidak diganti. |

---

## 4. Catatan temuan telaah

Temuan ini tidak mengubah isi tabel jobsheet. Temuan menjadi bahan diskusi atau review.

| Kode | Tabel | Temuan | Dasar kaidah | Saran |
|---|---|---|---|---|
| T1 | Tabel 5.10 LAB-UC06 | Langkah 3 memuat dua aksi: memilih pengajuan dan menetapkan persetujuan. Langkah 5 (penolakan) ditulis "cabang dari langkah 4", padahal keputusan tolak terjadi sebagai pengganti keputusan setuju pada langkah 3, sebelum sistem mengubah status pada langkah 4. | B.3.a dan B.3.e | Pisahkan langkah 3 menjadi memilih pengajuan, lalu menetapkan keputusan. Tulis rujukan cabang penolakan ke langkah keputusan, bukan langkah 4. |
| T2 | Tabel 5.12 LAB-UC11 | Berdasarkan tata letak teks, langkah 5 "Sistem memeriksa status peminjaman" tampak pada kolom Kegiatan, sedangkan isinya tanggapan sistem. Langkah 4, 5, dan 6 berturut-turut dari sistem. Langkah 9 "Petugas melihat konfirmasi" bersifat pasif. | B.3.b | Pindahkan pemeriksaan status ke kolom Respon sistem (sudah dilakukan pada lembar drawio), dan periksa tata letak pada dokumen asli. |
| T3 | Tabel 5.4 dan 5.13 | Langkah 1 ditulis oleh "Alur pengajuan" atau "Alur pengembalian", bukan aktor, karena use case yang disertakan tidak berinteraksi langsung dengan aktor. | B.3.b | Dapat diterima sebagai ciri use case include, tetapi sebutkan dasarnya saat review. |
| T4 | Tabel 5.6 LAB-UC02 | Langkah 5 "mengisi atau mengonfirmasi data" menggabung dua aksi. | B.3.a | Dapat diterima karena UC02 adalah skenario umum untuk tambah, ubah, dan hapus. |

| T5 | Tabel 5.4 LAB-UC04 | Pada pola ganjil di kolom Kegiatan dan genap di kolom Respon sistem, langkah 3 "Sistem menyatakan peralatan tersedia" jatuh di kolom Kegiatan dan langkah 4 "Alur pengajuan melanjutkan…" di kolom Respon sistem, sehingga tampak tertukar. | B.3.b | Pada lembar drawio, langkah 3 ditempatkan di Respon sistem dan langkah 4 di Kegiatan. Periksa halaman 78 jobsheet. |

Ketidakkonsistenan pada teks jobsheet:

| Kode | Temuan |
|---|---|
| J1 | Bagian B.6.d menyebut "Tabel 5.0", sedangkan tabel aturan pemetaan berjudul "Tabel 5". |
| J2 | Berkas SIA tertulis `.drawio` pada bagian C.1 dan C.5, tetapi `.md` pada pohon folder. Deliverable SIA dibuat sebagai `.drawio` mengikuti bagian C.5. |
| J3 | Bagian C.1 melarang menulis tabel skenario di berkas drawio (maksudnya berkas diagram P04), tetapi tugas SIA tetap berformat `.drawio`. Ini ditafsirkan sebagai dokumen skenario terpisah dari berkas diagram P04. |
| J4 | Langkah 7 tugas SIA menyebut berkas `LAB/P05_2406088_LAB_skenario_v01.drawio`, padahal seharusnya berkas SIA. Deliverable SIA disimpan sebagai `P05_2406088_SIA_skenario_v01.drawio`. |

---

## 5. Logbook singkat

| Kegiatan | Status | Keterangan |
|---|---|---|
| Buka diagram P04 LAB sebagai acuan | Selesai | 5 aktor, 12 use case, 2 collaboration, 17 hubungan dicocokkan |
| Telaah kelompok peminjaman (UC01, UC03, UC04, UC05) | Selesai | Sesuai |
| Telaah kelompok pengelolaan data (UC02, UC08, UC09, UC10) | Selesai | Sesuai; catatan T4 |
| Telaah kelompok keputusan dan laporan (UC06, UC07) | Selesai | UC06 catatan T1; UC07 berdiri sendiri |
| Telaah kelompok pengembalian (UC11, UC12) | Selesai | Catatan T2 dan T3 |
| Periksa catatan Kepala Laboratorium | Selesai | Hanya UC07, tanpa relasi lain |
| Tulis 7 tabel skenario tugas SIA (UC07 sampai UC13) | Selesai | Tabel 5.15 sampai 5.21 pada `P05_2406088_SIA_skenario_v01.drawio` (7 halaman) |
| Periksa tabel SIA dengan checklist C.4 | Selesai | Lihat catatan pada berkas SIA |
