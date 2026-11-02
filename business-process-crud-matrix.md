# Matriks CRUD Aktivitas Sistem Informasi PDKB-TM

## 1. Tujuan dan batasan

Dokumen ini menguraikan **46 subaktivitas dalam 10 tahapan** proses PDKB-TM, mulai dari **input Work Order (WO)** hingga **output Laporan Kinerja Harian dan Bulanan PDKB**. Matriks menghubungkan setiap subaktivitas dengan **14 peran/aktor** dan kode operasi data pada sistem informasi.

Matriks adalah **rancangan operasionalisasi sistem informasi** berdasarkan *Matriks_CRUD_Aktivitas_PDKB_TM.xlsx* dan *Alur_Proses_PDKB_TM_dari_WO_hingga_Laporan.md*; **bukan** penetapan hak akses resmi PLN. Penjelasan di bawah hanya memperjelas operasi dalam mapping tersebut. Penyebutan perubahan status, tanda tangan digital, atau metadata adalah interpretasi implementasi yang perlu divalidasi apabila sistem dikembangkan.

## 2. Definisi kode dan cara membaca

| Kode | Makna | Arti dalam rancangan sistem informasi |
|---|---|---|
| **C** | Create | Membuat record atau dokumen baru. |
| **R** | Read | Membaca, meninjau, atau mengambil informasi yang sudah ada. |
| **U** | Update | Memperbarui data, status, tanda tangan, keputusan persetujuan, atau metadata record yang sudah ada. |
| **D** | Delete | Menghapus record; **tidak ditugaskan** pada matriks ini. |
| **RU** | Read + Update | Membaca atau memverifikasi record, lalu memperbarui bagian yang menjadi kewenangannya. |
| **—** | Tidak terpetakan | Tidak ada operasi CRUD langsung pada aktivitas itu, **bukan berarti aktor tidak menjalankan proses fisik/koordinasi**. |

**Prinsip pembacaan:** kode ditempatkan pada persilangan *aktivitas × aktor*. Operasi CRUD menunjukkan perlakuan terhadap **data/dokumen sistem**, bukan fungsi manajerial maupun seluruh tindakan fisik pada aktivitas tersebut. Sel kosong ditulis sebagai `—`. Bila kode aktor tidak muncul pada suatu baris, jangan menafsirkan secara otomatis sebagai larangan akses global; hanya tidak dipetakan dalam aktivitas itu.

### Kamus aktor

| Kode | Jabatan/pihak |
|---|---|
| **SPM** | Seksi Pemohon WO (Seksi Konstruksi / Seksi HAR / Seksi Operasi / unit Pemeliharaan Terencana) |
| **AJ** | Asman Jaringan |
| **SUP** | Supervisor PDKB |
| **PRE** | Preparator/Surveyor PDKB |
| **KO** | Kepala Operasi (Manajer Area atau pejabat yang mewakili) |
| **KR** | Kepala Regu PDKB/Pengawas Pekerjaan |
| **PK3** | Pengawas K3 |
| **PEL** | Pelaksana PDKB (Linesman dan Groundman) |
| **K3L** | Pejabat K3L |
| **DP** | Direksi Pekerjaan |
| **MR** | Management Representatif |
| **PA** | Piket Area |
| **KU** | Komisi PDKB Unit |
| **KP** | Komisi PDKB Pusat |

## 3. Matriks CRUD lengkap (46 aktivitas × 14 aktor)

> Tabel lebar: gunakan editor Markdown yang mendukung gulir horizontal. Kolom **ID**, **Tahap**, dan **Aktivitas** mengidentifikasi baris; 14 kolom berikutnya adalah peran aktor. Kode pada tabel ini dipertahankan dari workbook CRUD sebelumnya.

| ID | Tahap | Aktivitas | SPM | AJ | SUP | PRE | KO | KR | PK3 | PEL | K3L | DP | MR | PA | KU | KP |
|:---:|---|---|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
| 1.1 | Input Work Order | Membuat permintaan WO | C | — | — | — | — | — | — | — | — | — | — | — | — | — |
| 1.2 | Input Work Order | Mengisi informasi jenis pekerjaan, lokasi, dan kebutuhan pekerjaan | U | — | — | — | — | — | — | — | — | — | — | — | — | — |
| 1.3 | Input Work Order | Mengirimkan WO kepada Asman Jaringan | U | R | — | — | — | — | — | — | — | — | — | — | — | — |
| 2.1 | Pemeriksaan Work Order | Menerima dan memeriksa permintaan WO | — | R | — | — | — | — | — | — | — | — | — | — | — | — |
| 2.2 | Pemeriksaan Work Order | Meneruskan WO kepada Supervisor PDKB | — | U | R | — | — | — | — | — | — | — | — | — | — | — |
| 2.3 | Pemeriksaan Work Order | Memeriksa WO, menentukan prioritas, dan menyusun rencana kerja | — | — | RU | — | — | — | — | — | — | — | — | — | — | — |
| 2.4 | Pemeriksaan Work Order | Menugaskan Preparator PDKB untuk melakukan survei | — | — | U | R | — | — | — | — | — | — | — | — | — | — |
| 3.1 | Survei Lokasi | Memeriksa kondisi lokasi, konstruksi, dan jaringan listrik | — | — | — | — | — | — | — | — | — | — | — | — | — | — |
| 3.2 | Survei Lokasi | Mengidentifikasi bahaya dan risiko pekerjaan | — | — | — | — | — | — | — | — | — | — | — | — | — | — |
| 3.3 | Survei Lokasi | Menilai kelayakan pekerjaan menggunakan metode PDKB | — | — | — | — | — | — | — | — | — | — | — | — | — | — |
| 3.4 | Survei Lokasi | Menyusun Form Hasil Survei Lokasi | — | — | — | C | — | — | — | — | — | — | — | — | — | — |
| 3.5 | Survei Lokasi | Memeriksa dan menandatangani hasil survei | — | — | RU | R | — | — | — | — | — | — | — | — | — | — |
| 4.1 | Perencanaan Pekerjaan | Menentukan metode dan Instruksi Kerja (IK) | — | — | — | U | — | — | — | — | — | — | — | — | — | — |
| 4.2 | Perencanaan Pekerjaan | Merencanakan kebutuhan personel PDKB | — | — | — | U | — | — | — | — | — | — | — | — | — | — |
| 4.3 | Perencanaan Pekerjaan | Merencanakan kebutuhan peralatan dan material | — | — | — | U | — | — | — | — | — | — | — | — | — | — |
| 4.4 | Perencanaan Pekerjaan | Menyusun jadwal pelaksanaan pekerjaan | — | — | — | U | — | — | — | — | — | — | — | — | — | — |
| 4.5 | Perencanaan Pekerjaan | Melakukan supervisi terhadap rencana dan jadwal pekerjaan | — | — | R | — | — | — | — | — | — | — | — | — | — | — |
| 5.1 | Persiapan Dokumen | Menyiapkan dokumen SP2B dan SP3B | — | — | — | C | — | — | — | — | — | — | — | — | — | — |
| 5.2 | Persiapan Dokumen | Menyusun IBPPR dan JSA | — | — | — | C | — | — | — | — | — | — | — | — | — | — |
| 5.3 | Persiapan Dokumen | Menyiapkan checklist peralatan, material, dan langkah kerja | — | — | — | C | — | — | — | — | — | — | — | — | — | — |
| 5.4 | Persiapan Dokumen | Menyusun formulir Izin Kerja sesuai mekanisme Working Permit | — | — | — | — | — | — | C | — | — | — | — | — | — | — |
| 5.5 | Persiapan Dokumen | Melakukan pemeriksaan kesehatan dan kesiapan personel PDKB | — | — | — | — | — | — | C | — | — | — | — | — | — | — |
| 6.1 | Otorisasi Pekerjaan | Menerbitkan SP2B dan SP3B | — | — | — | — | U | R | R | — | — | — | — | — | — | — |
| 6.2 | Otorisasi Pekerjaan | Menandatangani SP3B sebagai penerimaan kewenangan pengawasan | — | — | — | — | — | U | — | — | — | — | — | — | — | — |
| 6.3 | Otorisasi Pekerjaan | Menandatangani SP3B sebagai penerimaan kewenangan pengawasan K3 | — | — | — | — | — | — | U | — | — | — | — | — | — | — |
| 6.4 | Otorisasi Pekerjaan | Menandatangani penerimaan SP2B | — | — | — | — | — | — | — | U | — | — | — | — | — | — |
| 6.5 | Otorisasi Pekerjaan | Melakukan persetujuan Izin Kerja sesuai kewenangan masing-masing | — | — | — | — | — | RU | — | — | RU | RU | RU | — | — | — |
| 7.1 | Pelaksanaan Pekerjaan | Melaksanakan job briefing | — | — | — | — | — | R | — | — | — | — | — | — | — | — |
| 7.2 | Pelaksanaan Pekerjaan | Melaksanakan safety briefing | — | — | — | — | — | — | R | — | — | — | — | — | — | — |
| 7.3 | Pelaksanaan Pekerjaan | Berkoordinasi dengan Kepala Operasi dan Piket Area mengenai pemberlakuan Syarat Operasi Khusus (SOK) | — | — | — | — | — | — | — | — | — | — | — | — | — | — |
| 7.4 | Pelaksanaan Pekerjaan | Melaksanakan pekerjaan sesuai Instruksi Kerja | — | — | — | — | — | — | — | R | — | — | — | — | — | — |
| 7.5 | Pelaksanaan Pekerjaan | Mengawasi pelaksanaan teknis pekerjaan | — | — | — | — | — | R | — | — | — | — | — | — | — | — |
| 7.6 | Pelaksanaan Pekerjaan | Mengawasi keselamatan personel dan kondisi lingkungan kerja | — | — | — | — | — | — | R | — | — | — | — | — | — | — |
| 8.1 | Penyelesaian & Dokumentasi | Mengevaluasi hasil pekerjaan | — | — | — | — | — | U | — | — | — | — | — | — | — | — |
| 8.2 | Penyelesaian & Dokumentasi | Berkoordinasi dengan Piket Area mengenai penormalan kondisi jaringan | — | — | — | — | — | — | — | — | — | — | — | — | — | — |
| 8.3 | Penyelesaian & Dokumentasi | Melaporkan penyelesaian pekerjaan | — | — | — | — | — | C | — | — | — | — | — | — | — | — |
| 8.4 | Penyelesaian & Dokumentasi | Mengarsipkan dokumen survei, SP2B, SP3B, dan dokumen pekerjaan lainnya | — | — | — | U | — | — | — | — | — | — | — | — | — | — |
| 9.1 | Penyusunan Laporan | Mengumpulkan dan merekapitulasi data hasil pekerjaan | — | — | — | R | — | — | — | — | — | — | — | — | — | — |
| 9.2 | Penyusunan Laporan | Menginput Laporan Kinerja Harian melalui aplikasi pelaporan PDKB | — | — | — | C | — | — | — | — | — | — | — | — | — | — |
| 9.3 | Penyusunan Laporan | Merekapitulasi kinerja pekerjaan bulanan | — | — | — | R | — | — | — | — | — | — | — | — | — | — |
| 9.4 | Penyusunan Laporan | Menyusun Laporan Kinerja Bulanan PDKB | — | — | — | C | — | — | — | — | — | — | — | — | — | — |
| 10.1 | Validasi & Pengiriman | Memeriksa dan menandatangani Laporan Kinerja Bulanan | — | — | RU | — | — | — | — | — | — | — | — | — | — | — |
| 10.2 | Validasi & Pengiriman | Memeriksa dan menandatangani Laporan Kinerja Bulanan | — | RU | — | — | — | — | — | — | — | — | — | — | — | — |
| 10.3 | Validasi & Pengiriman | Mengesahkan Laporan Kinerja Bulanan | — | — | — | — | RU | — | — | — | — | — | — | — | — | — |
| 10.4 | Validasi & Pengiriman | Menyampaikan laporan melalui jalur pelaporan PDKB kepada Komisi PDKB Unit | — | — | — | U | — | — | — | — | — | — | — | — | R | — |
| 10.5 | Validasi & Pengiriman | Meneruskan laporan kepada Komisi PDKB Pusat | — | — | — | — | — | — | — | — | — | — | — | — | U | R |

## 4. Penjelasan per baris (per aktivitas)

Di bawah ini, setiap ID mengacu persis ke **satu baris matriks**. Kolom aktor yang tidak disebutkan pada penjelasan memiliki kode `—`.

### 4.1. Tahap 1 — Input Work Order (WO)

**1.1. Membuat permintaan WO**
- **Objek data/dokumen:** Work Order (WO).
- **Aktor dan kode:** SPM (**C**).
- **Penjelasan:** Seksi pemohon menghasilkan entri WO baru untuk mengawali permintaan pekerjaan PDKB. Kode C adalah rancangan pencatatan WO digital.

**1.2. Mengisi informasi jenis pekerjaan, lokasi, dan kebutuhan pekerjaan**
- **Objek data/dokumen:** WO.
- **Aktor dan kode:** SPM (**U**).
- **Penjelasan:** Seksi pemohon melengkapi atau mengoreksi informasi jenis pekerjaan, lokasi, dan kebutuhan pada WO yang telah dibuat.

**1.3. Mengirimkan WO kepada Asman Jaringan**
- **Objek data/dokumen:** WO.
- **Aktor dan kode:** SPM (**U**); AJ (**R**).
- **Penjelasan:** Seksi pemohon memperbarui status/tujuan pengajuan WO (U), sementara Asman Jaringan memperoleh akses untuk membaca WO yang diterima (R).

### 4.2. Tahap 2 — Pemeriksaan Work Order

**2.1. Menerima dan memeriksa permintaan WO**
- **Objek data/dokumen:** WO.
- **Aktor dan kode:** AJ (**R**).
- **Penjelasan:** Asman Jaringan membaca isi permintaan WO untuk pemeriksaan awal; matriks belum menetapkan perubahan data pada aktivitas ini.

**2.2. Meneruskan WO kepada Supervisor PDKB**
- **Objek data/dokumen:** WO dan informasi penerusan.
- **Aktor dan kode:** AJ (**U**); SUP (**R**).
- **Penjelasan:** Asman Jaringan memperbarui status atau tujuan penerusan WO (U), lalu Supervisor PDKB membaca WO yang diteruskan (R).

**2.3. Memeriksa WO, menentukan prioritas, dan menyusun rencana kerja**
- **Objek data/dokumen:** WO, prioritas, dan rencana kerja.
- **Aktor dan kode:** SUP (**RU**).
- **Penjelasan:** Supervisor PDKB membaca WO (R) dan memperbarui atribut prioritas maupun rencana kerja (U) pada catatan pekerjaan yang sama.

**2.4. Menugaskan Preparator PDKB untuk melakukan survei**
- **Objek data/dokumen:** Penugasan survei dalam WO.
- **Aktor dan kode:** SUP (**U**); PRE (**R**).
- **Penjelasan:** Supervisor PDKB mencatat penugasan Preparator (U); Preparator PDKB dapat membaca rincian penugasan dan WO yang ditanganinya (R).

### 4.3. Tahap 3 — Survei Lokasi

**3.1. Memeriksa kondisi lokasi, konstruksi, dan jaringan listrik**
- **Objek data/dokumen:** Kondisi lokasi, konstruksi, dan jaringan.
- **Aktor operasional:** Preparator/Surveyor PDKB. **CRUD:** `—` (tidak ada operasi data langsung yang dipetakan).
- **Penjelasan:** Preparator PDKB memeriksa kondisi lapangan secara langsung. Hasil pemeriksaan menjadi bahan pengisian Form Hasil Survei pada aktivitas 3.4; belum dipisahkan sebagai transaksi CRUD tersendiri.

**3.2. Mengidentifikasi bahaya dan risiko pekerjaan**
- **Objek data/dokumen:** Potensi bahaya dan risiko lapangan.
- **Aktor operasional:** Preparator/Surveyor PDKB. **CRUD:** `—` (tidak ada operasi data langsung yang dipetakan).
- **Penjelasan:** Preparator PDKB mengidentifikasi bahaya dan risiko di lokasi. Pencatatan digital hasil identifikasi belum diberi operasi khusus di baris ini; dokumen IBPPR/JSA disusun pada 5.2.

**3.3. Menilai kelayakan pekerjaan menggunakan metode PDKB**
- **Objek data/dokumen:** Hasil penilaian kelayakan PDKB.
- **Aktor operasional:** Preparator/Surveyor PDKB. **CRUD:** `—` (tidak ada operasi data langsung yang dipetakan).
- **Penjelasan:** Preparator PDKB menilai apakah pekerjaan layak dilaksanakan dengan metode PDKB. Matriks menempatkan pembuatan dokumen hasil survei pada 3.4, bukan pada langkah penilaian ini.

**3.4. Menyusun Form Hasil Survei Lokasi**
- **Objek data/dokumen:** Form Hasil Survei Lokasi.
- **Aktor dan kode:** PRE (**C**).
- **Penjelasan:** Preparator PDKB membuat dokumen hasil survei baru, memuat temuan lokasi, kondisi jaringan, dan kesimpulan yang diperlukan untuk perencanaan.

**3.5. Memeriksa dan menandatangani hasil survei**
- **Objek data/dokumen:** Form Hasil Survei Lokasi.
- **Aktor dan kode:** SUP (**RU**); PRE (**R**).
- **Penjelasan:** Supervisor PDKB membaca dan memeriksa hasil survei, kemudian membubuhkan persetujuan atau pengesahan (RU). Preparator PDKB hanya mendapat R pada tahap pemeriksaan ini.

### 4.4. Tahap 4 — Perencanaan Pekerjaan

**4.1. Menentukan metode dan Instruksi Kerja (IK)**
- **Objek data/dokumen:** Rencana pekerjaan: metode dan IK.
- **Aktor dan kode:** PRE (**U**).
- **Penjelasan:** Preparator PDKB memperbarui rencana pekerjaan dengan metode serta Instruksi Kerja yang dipilih; U tidak berarti mengubah dokumen SOP/IK baku.

**4.2. Merencanakan kebutuhan personel PDKB**
- **Objek data/dokumen:** Rencana pekerjaan: kebutuhan personel.
- **Aktor dan kode:** PRE (**U**).
- **Penjelasan:** Preparator PDKB memperbarui daftar kebutuhan personel atau rencana penugasan untuk WO yang sama.

**4.3. Merencanakan kebutuhan peralatan dan material**
- **Objek data/dokumen:** Rencana pekerjaan: peralatan dan material.
- **Aktor dan kode:** PRE (**U**).
- **Penjelasan:** Preparator PDKB memperbarui kebutuhan alat dan material hasil perencanaan berdasarkan survei dan metode kerja.

**4.4. Menyusun jadwal pelaksanaan pekerjaan**
- **Objek data/dokumen:** Rencana jadwal pekerjaan.
- **Aktor dan kode:** PRE (**U**).
- **Penjelasan:** Preparator PDKB memasukkan atau mengubah jadwal rencana pelaksanaan yang terkait dengan WO.

**4.5. Melakukan supervisi terhadap rencana dan jadwal pekerjaan**
- **Objek data/dokumen:** Rencana pekerjaan dan jadwal.
- **Aktor dan kode:** SUP (**R**).
- **Penjelasan:** Supervisor PDKB membaca rencana dan jadwal untuk supervisi. Tidak ada U karena pada mapping awal tidak ada pembaruan/persetujuan digital yang ditetapkan pada baris ini.

### 4.5. Tahap 5 — Persiapan Dokumen

**5.1. Menyiapkan dokumen SP2B dan SP3B**
- **Objek data/dokumen:** SP2B dan SP3B.
- **Aktor dan kode:** PRE (**C**).
- **Penjelasan:** Preparator PDKB membuat draf atau record awal SP2B dan SP3B untuk pekerjaan yang telah direncanakan. Pengesahan dokumen berada pada aktivitas 6.1–6.3.

**5.2. Menyusun IBPPR dan JSA**
- **Objek data/dokumen:** IBPPR dan JSA.
- **Aktor dan kode:** PRE (**C**).
- **Penjelasan:** Preparator PDKB membuat dokumen identifikasi/penilaian/pengendalian risiko dan Job Safety Analysis berdasarkan temuan survei dan tahapan kerja.

**5.3. Menyiapkan checklist peralatan, material, dan langkah kerja**
- **Objek data/dokumen:** Checklist peralatan, material, dan langkah kerja.
- **Aktor dan kode:** PRE (**C**).
- **Penjelasan:** Preparator PDKB membuat checklist awal yang akan dipakai pada pemeriksaan kesiapan pelaksanaan.

**5.4. Menyusun formulir Izin Kerja sesuai mekanisme Working Permit**
- **Objek data/dokumen:** Formulir Izin Kerja / Working Permit.
- **Aktor dan kode:** PK3 (**C**).
- **Penjelasan:** Pengawas K3 membuat record/formulir Izin Kerja. Persetujuan oleh pihak berwenang dipetakan terpisah pada aktivitas 6.5.

**5.5. Melakukan pemeriksaan kesehatan dan kesiapan personel PDKB**
- **Objek data/dokumen:** Catatan/checklist kesehatan dan kesiapan personel.
- **Aktor dan kode:** PK3 (**C**).
- **Penjelasan:** Pengawas K3 melakukan pemeriksaan dan mencatat hasil pemeriksaan sebagai record baru. Akses terhadap rincian kesehatan harus dibatasi sesuai kewenangan.

### 4.6. Tahap 6 — Otorisasi Pekerjaan

**6.1. Menerbitkan SP2B dan SP3B**
- **Objek data/dokumen:** SP2B dan SP3B.
- **Aktor dan kode:** KO (**U**); KR (**R**); PK3 (**R**).
- **Penjelasan:** Kepala Operasi mengubah status dokumen menjadi diterbitkan/disahkan (U); Kepala Regu/Pengawas Pekerjaan dan Pengawas K3 membaca perintah serta kewenangan yang diterbitkan (R).

**6.2. Menandatangani SP3B sebagai penerimaan kewenangan pengawasan**
- **Objek data/dokumen:** SP3B.
- **Aktor dan kode:** KR (**U**).
- **Penjelasan:** Kepala Regu/Pengawas Pekerjaan memperbarui dokumen dengan tanda tangan atau konfirmasi penerimaan kewenangan pengawasan.

**6.3. Menandatangani SP3B sebagai penerimaan kewenangan pengawasan K3**
- **Objek data/dokumen:** SP3B.
- **Aktor dan kode:** PK3 (**U**).
- **Penjelasan:** Pengawas K3 memperbarui dokumen dengan tanda tangan atau konfirmasi penerimaan kewenangan pengawasan K3.

**6.4. Menandatangani penerimaan SP2B**
- **Objek data/dokumen:** SP2B / tanda terima SP2B.
- **Aktor dan kode:** PEL (**U**).
- **Penjelasan:** Linesman dan Groundman memperbarui bukti penerimaan perintah, misalnya tanda tangan pada record SP2B.

**6.5. Melakukan persetujuan Izin Kerja sesuai kewenangan masing-masing**
- **Objek data/dokumen:** Izin Kerja / Working Permit.
- **Aktor dan kode:** KR (**RU**); K3L (**RU**); DP (**RU**); MR (**RU**).
- **Penjelasan:** Pengawas Pekerjaan, Pejabat K3L, Direksi Pekerjaan, dan Management Representatif masing-masing membaca isi izin (R) lalu memperbarui persetujuan sesuai kewenangan (U). U hanya menyasar keputusan persetujuan, bukan seluruh kolom isi izin.

### 4.7. Tahap 7 — Pelaksanaan Pekerjaan

**7.1. Melaksanakan job briefing**
- **Objek data/dokumen:** Dokumen briefing / IK.
- **Aktor dan kode:** KR (**R**).
- **Penjelasan:** Kepala Regu/Pengawas Pekerjaan menggunakan akses baca atas instruksi kerja atau rencana untuk memimpin job briefing. Pelaksanaan briefing itu sendiri bukan operasi Read.

**7.2. Melaksanakan safety briefing**
- **Objek data/dokumen:** JSA / instruksi keselamatan.
- **Aktor dan kode:** PK3 (**R**).
- **Penjelasan:** Pengawas K3 membaca informasi risiko dan pengendalian sebagai dasar safety briefing. Pemberian briefing sendiri tidak menambah record pada rancangan CRUD ini.

**7.3. Berkoordinasi dengan Kepala Operasi dan Piket Area mengenai pemberlakuan Syarat Operasi Khusus (SOK)**
- **Objek data/dokumen:** Koordinasi pemberlakuan SOK.
- **Aktor operasional:** Kepala Regu PDKB/Pengawas Pekerjaan; Kepala Operasi; Piket Area. **CRUD:** `—` (tidak ada operasi data langsung yang dipetakan).
- **Penjelasan:** Kepala Regu PDKB berkoordinasi dengan Kepala Operasi dan Piket Area mengenai status jaringan. Matriks belum memasukkan pencatatan log koordinasi/SOK sebagai entitas digital.

**7.4. Melaksanakan pekerjaan sesuai Instruksi Kerja**
- **Objek data/dokumen:** Instruksi Kerja (IK).
- **Aktor dan kode:** PEL (**R**).
- **Penjelasan:** Linesman dan Groundman membaca atau merujuk IK selama pelaksanaan. Pekerjaan fisik di lapangan bukan operasi CRUD.

**7.5. Mengawasi pelaksanaan teknis pekerjaan**
- **Objek data/dokumen:** Rencana/IK yang menjadi acuan pengawasan.
- **Aktor dan kode:** KR (**R**).
- **Penjelasan:** Kepala Regu/Pengawas Pekerjaan membaca acuan teknis untuk membandingkan dengan pelaksanaan di lapangan. Matriks belum memberi U untuk pencatatan temuan pengawasan.

**7.6. Mengawasi keselamatan personel dan kondisi lingkungan kerja**
- **Objek data/dokumen:** JSA / dokumen pengendalian risiko.
- **Aktor dan kode:** PK3 (**R**).
- **Penjelasan:** Pengawas K3 membaca acuan risiko dan keselamatan untuk melakukan pengawasan. Pencatatan hasil pengawasan belum dipetakan sebagai U di baris ini.

### 4.8. Tahap 8 — Penyelesaian dan Dokumentasi

**8.1. Mengevaluasi hasil pekerjaan**
- **Objek data/dokumen:** Evaluasi/hasil pekerjaan.
- **Aktor dan kode:** KR (**U**).
- **Penjelasan:** Kepala Regu/Pengawas Pekerjaan memperbarui catatan evaluasi atau hasil pekerjaan yang terkait dengan WO. Objek evaluasi digital merupakan interpretasi desain dari kode U sebelumnya.

**8.2. Berkoordinasi dengan Piket Area mengenai penormalan kondisi jaringan**
- **Objek data/dokumen:** Koordinasi penormalan jaringan.
- **Aktor operasional:** Kepala Regu PDKB/Pengawas Pekerjaan; Piket Area. **CRUD:** `—` (tidak ada operasi data langsung yang dipetakan).
- **Penjelasan:** Kepala Regu PDKB dan Piket Area berkoordinasi agar kondisi jaringan dinormalkan. Tidak ditetapkan perubahan data sistem dalam matriks pada baris ini.

**8.3. Melaporkan penyelesaian pekerjaan**
- **Objek data/dokumen:** Laporan atau berita acara penyelesaian pekerjaan.
- **Aktor dan kode:** KR (**C**).
- **Penjelasan:** Kepala Regu/Pengawas Pekerjaan membuat record pemberitahuan/penyelesaian pekerjaan baru. Bentuk dokumen digitalnya harus disepakati pada desain sistem.

**8.4. Mengarsipkan dokumen survei, SP2B, SP3B, dan dokumen pekerjaan lainnya**
- **Objek data/dokumen:** Arsip dan metadata dokumen pekerjaan.
- **Aktor dan kode:** PRE (**U**).
- **Penjelasan:** Preparator PDKB memperbarui status, lokasi simpan, atau informasi arsip dokumen yang sudah tersedia; tidak berarti menghapus dokumen aslinya.

### 4.9. Tahap 9 — Penyusunan Laporan

**9.1. Mengumpulkan dan merekapitulasi data hasil pekerjaan**
- **Objek data/dokumen:** Dokumen dan data hasil pekerjaan.
- **Aktor dan kode:** PRE (**R**).
- **Penjelasan:** Preparator PDKB membaca data hasil pekerjaan dari dokumen yang telah terkumpul. Pembentukan laporan harian baru ditangani pada 9.2.

**9.2. Menginput Laporan Kinerja Harian melalui aplikasi pelaporan PDKB**
- **Objek data/dokumen:** Laporan Kinerja Harian PDKB.
- **Aktor dan kode:** PRE (**C**).
- **Penjelasan:** Preparator PDKB membuat entri laporan harian pada aplikasi pelaporan PDKB berdasarkan hasil pekerjaan.

**9.3. Merekapitulasi kinerja pekerjaan bulanan**
- **Objek data/dokumen:** Data kinerja harian untuk rekap bulanan.
- **Aktor dan kode:** PRE (**R**).
- **Penjelasan:** Preparator PDKB membaca data harian sebagai bahan rekapitulasi. Penulisan dokumen bulanan baru dipetakan pada 9.4, bukan sebagai U di baris ini.

**9.4. Menyusun Laporan Kinerja Bulanan PDKB**
- **Objek data/dokumen:** Laporan Kinerja Bulanan PDKB.
- **Aktor dan kode:** PRE (**C**).
- **Penjelasan:** Preparator PDKB membuat laporan bulanan baru dengan menggabungkan data kinerja harian selama periode pelaporan.

### 4.10. Tahap 10 — Validasi dan Pengiriman Laporan

**10.1. Memeriksa dan menandatangani Laporan Kinerja Bulanan**
- **Objek data/dokumen:** Laporan Kinerja Bulanan PDKB.
- **Aktor dan kode:** SUP (**RU**).
- **Penjelasan:** Supervisor PDKB membaca dan memeriksa laporan (R) lalu memperbarui kolom tanda tangan/validasi (U).

**10.2. Memeriksa dan menandatangani Laporan Kinerja Bulanan**
- **Objek data/dokumen:** Laporan Kinerja Bulanan PDKB.
- **Aktor dan kode:** AJ (**RU**).
- **Penjelasan:** Asman Jaringan membaca dan memeriksa laporan (R) lalu memperbarui kolom tanda tangan/validasi (U).

**10.3. Mengesahkan Laporan Kinerja Bulanan**
- **Objek data/dokumen:** Laporan Kinerja Bulanan PDKB.
- **Aktor dan kode:** KO (**RU**).
- **Penjelasan:** Kepala Operasi membaca laporan (R) dan memperbarui status pengesahan atau tanda tangan (U).

**10.4. Menyampaikan laporan melalui jalur pelaporan PDKB kepada Komisi PDKB Unit**
- **Objek data/dokumen:** Laporan/metadata pengiriman ke Komisi PDKB Unit.
- **Aktor dan kode:** PRE (**U**); KU (**R**).
- **Penjelasan:** Preparator PDKB memperbarui status penyerahan laporan (U), sedangkan Komisi PDKB Unit memperoleh hak membaca laporan yang diterima (R). U di sini menyasar alur pengiriman, bukan perubahan isi laporan yang sudah disahkan.

**10.5. Meneruskan laporan kepada Komisi PDKB Pusat**
- **Objek data/dokumen:** Laporan/metadata penerusan ke Komisi PDKB Pusat.
- **Aktor dan kode:** KU (**U**); KP (**R**).
- **Penjelasan:** Komisi PDKB Unit memperbarui status penerusan (U), sedangkan Komisi PDKB Pusat membaca laporan yang disampaikan (R).

## 5. Ringkasan hasil pemetaan

- **Total:** 46 aktivitas, 14 aktor, 10 tahapan.
- **Aktivitas tanpa operasi CRUD langsung (5):** 3.1, 3.2, 3.3, 7.3, 8.2.
- **Operasi Delete (D):** tidak dialokasikan kepada aktor mana pun dalam tabel ini.
- **Input pertama:** Work Order (WO) dibuat/diajukan oleh Seksi Pemohon WO (SPM).
- **Output terakhir:** Laporan Kinerja Harian dan Laporan Kinerja Bulanan PDKB, dengan jalur pemeriksaan, pengesahan, dan penerusan laporan sesuai aktivitas 9.2–10.5.

### Batas interpretasi yang perlu dijaga

1. **Operasi `U` untuk tanda tangan/approval** berarti pembaruan keputusan atau atribut otorisasi, bukan hak bebas mengedit seluruh isi dokumen.
2. **Aktivitas fisik maupun koordinasi** tetap memiliki penanggung jawab operasional, walaupun tidak menghasilkan operasi CRUD langsung pada baris tersebut.
3. **Tidak ada kode `D`** bukan berarti kebijakan retensi dan penghapusan data sudah ditetapkan; fitur pembatalan, arsip, dan audit trail perlu keputusan desain tersendiri.
4. **Penetapan input digital oleh aktor** (terutama WO, kesehatan personel, serta status koordinasi) adalah mapping desain. Dokumen SOP yang digunakan tidak seluruhnya mengatur operator input aplikasi secara eksplisit.

## 6. Dokumen rujukan internal

- `Matriks_CRUD_Aktivitas_PDKB_TM.xlsx` — sumber utama seluruh nilai sel CRUD pada tabel.
- `Alur_Proses_PDKB_TM_dari_WO_hingga_Laporan.md` — sumber uraian tahap, urutan kegiatan, dan aktor operasional.
- `SOP 001 PDKB TM MB PEMELIHARAAN JUMPER (1).pdf` — referensi proses, khususnya bagian 7.3, 8.1–8.4, dan Gambar 9.2 (sebagaimana tercantum dalam dokumen alur sebelumnya).
