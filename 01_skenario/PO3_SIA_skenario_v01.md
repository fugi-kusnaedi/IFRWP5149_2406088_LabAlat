<!-- Skenario -->

Mahasiswa mengajukan KRS dengan memilih mata kuliah. Setiap pengajuan menjalankan validasi KRS yang memeriksa kelengkapan, prasyarat mata kuliah, dan benturan jadwal. Jika validasi berhasil, sistem menyimpan pengajuan berstatus menunggu persetujuan dosen wali. Pada konfirmasi penyimpanan, mahasiswa dapat memilih mengunduh bukti pengajuan. Dosen wali menyetujui atau menolak KRS dan memberikan catatan keputusan.

<!-- Tabel Kebutuhan -->
ID      |Kebutuhan tugas
SIA-R01 |Mahasiswa dapat melihat jadwal kuliah
SIA-R02 |Admin akademik dapat mengelola jadwal kuliah
SIA-R03 |Mahasiswa dapat mengajukan KRS
SIA-R04 |Sistem memvalidasi KRS sebagai bagian pengajuan
SIA-R05 |Mahasiswa dapat mengunduh bukti jika memilihnya pada konfirmasi pengajuan
SIA-R06 |Dosen wali dapat memproses persetujuan atau penolakan KRS

<!-- Batas Sistem Aturan -->
• Pengguna telah terautentikasi.
• Data mata kuliah, prasyarat, dan jadwal tersedia.
• Validasi gagal menyebabkan pengajuan belum berhasil tersimpan.
• Unduh bukti tidak menjadi syarat keberhasilan pengajuan.
• KRS tersimpan belum berarti disetujui.
• Pembayaran, pengisian nilai, dan implementasi basis data berada di luar tugas.

<!-- Tentukan Aktor -->
Aktor Utama     | Tujuan Terhadap Sistem
Mahasiswa       | Melihat jadwal kuliah, mengajukan KRS, mengunduh bukti pengajuan.
Dosen Wali      | Memproses persetujuan atau penolakan KRS.
Admin Akademik  | Mengelola jadwal kuliah.

<!-- Tabel katalog use case -->
| ID,Nama Use Case,Peran dalam Model                                                             |
| :--------------------------------------------------------------------------------------------- |
| SIA-R01 (atau SIA-UC01),Lihat jadwal kuliah,Fungsi utama mahasiswa                             |
| SIA-R02 (atau SIA-UC02),Kelola jadwal kuliah,Fungsi utama admin akademik                       |
| SIA-R03 (atau SIA-UC03),Ajukan KRS,Fungsi utama mahasiswa                                      |
| SIA-R04 (atau SIA-UC04),Validasi KRS,Perilaku yang disertakan SIA-R03 (<<include>>)            |
| SIA-R05 (atau SIA-UC05),Unduh bukti pengajuan KRS,Tambahan bersyarat pada SIA-R03 (<<extend>>) |
| SIA-R06 (atau SIA-UC06),Proses keputusan KRS,Fungsi utama dosen wali                           |

Relasi include
Use Case Penyerta (Base)  ,Jenis Relasi  ,Use Case yang Disertakan (Target),Alasan / Penjelasan 
Ajukan KRS (SIA-R03)      ,<<include>>   ,Validasi KRS (SIA-R04)           ,"Pemeriksaan kelengkapan, prasyarat mata kuliah, dan benturan jadwal selalu dijalankan secara mutlak sebagai bagian inti dari alur pengajuan KRS."

Relasi Extend
Use Case Tambahan,Jenis Relasi,Use Case Dasar (Base),Extension Point,Kondisi (Condition),Alasan / Penjelasan
Unduh bukti pengajuan KRS (SIA-R05),<<extend>>,Ajukan KRS (SIA-R03),Konfirmasi penyimpanan pengajuan KRS,[mahasiswa memilih unduh],"Pengunduhan bukti bersifat opsional; tanpa mengunduh bukti pun, pengajuan KRS tetap berhasil tersimpan dengan sah."