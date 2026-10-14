<!-- Tabel Kebutuhan -->
| Elemen                | Keterangan                                                                                 |
| :-------------------- | :----------------------------------------------------------------------------------------- |
| Tujuan                | Menghasilkan pengajuan KRS yang tersimpan di dalam sistem dengan status menunggu keputusan |
| Aktor utama           | Mahasiswa                                                                                  |
| Sumber kebutuhan      | SIA-R03 dan SIA-R04                                                                        |
| Pemicu                | Mahasiswa memilih menu/fungsi pengajuan KRS                                                |
| Prasyarat             | Mahasiswa telah terautentikasi; data mata kuliah, prasyarat, dan jadwal tersedia           |
| Pascakondisi berhasil | Pengajuan KRS tersimpan dengan nomor referensi dan status Menunggu persetujuan dosen wali  |
| Pascakondisi gagal    | Tidak ada pengajuan KRS baru yang berhasil tersimpan di dalam sistem                       |
| Include               | SIA-UC04 Validasi KRS                                                                      |
| Extension point       | Konfirmasi penyimpanan, pada langkah 6                                                     |
| Extend                | SIA-UC05 Unduh bukti pengajuan jika [mahasiswa memilih unduh]                              |