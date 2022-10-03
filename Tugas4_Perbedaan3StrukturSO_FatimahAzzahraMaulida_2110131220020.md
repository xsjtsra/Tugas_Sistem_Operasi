### Nama : Fatimah Azzahra Maulida

### NIM : 2110131220020

`Sistem Operasi - Pendidikan Ilmu Komputer FKIP`

---

# <p align=center><b>PERBEDAAN 3 STRUKTUR SISTEM OPERASI</b></p>

<p align=justify>Sebuah sistem yang besar dan kompleks seperti sistem operasi modern harus diatur dengan cara
membagi task kedalam komponen-komponen kecil agar dapat berfungsi dengan baik dan mudah
dimodifikasi. Pada bab ini, kita akan membahas cara komponen-komponen ini dihubungkan satu
sama lain. Menurut Silberschatz dan kawan-kawan, ada tiga cara yaitu:</p>

- Struktur Sederhana.

- Struktur Berlapis.

- Kernel Mikro.

<p align=justify></p>

## **Struktur Sederhana (Monolitic Structure/ Simple Structure)**

<p align=justify>Pada struktur ini, sistem operasi komputer dibuat dari sekumpulan prosedur, yang mana setiap prosedur itu dapat memanggil prosedur yang lainnya, kapan pun prosedur di perlukan.</p>

<p align=justify>MS-DOS adalah contoh dari sistem ini. Di MS-DOS, antarmuka dan tingkat fungsionalitas tidak dipisahkan dengan baik. Misalnya, program aplikasi dapat mengakses rutinitas I/O dasar untuk menulis langsung ke layar dan disk drive. Kebebasan seperti itu meninggalkan MS-DOS rentan terhadap program yang salah (atau berbahaya), menyebabkan seluruh sistem crash ketika program pengguna gagal. Tentu saja, MS-DOS juga dibatasi oleh perangkat keras dari zamannya. Karena Intel 8088 yang ditulisnya tidak menyediakan dual mode dan tidak ada perlindungan perangkat keras, perancang MS-DOS tidak punya pilihan selain untuk membiarkan perangkat keras dasar dapat diakses.</p>

<p align=center><img src="https://user-images.githubusercontent.com/112606990/192268843-aefb7763-2df3-4462-ab21-125718034f17.png"></p>

Penjelasan lapisan gambar di atas:

1. Main Procedure adalah suatu program yang digunakan untuk memanggil salah satu dari service prosedures, dan juga meminta pelayanan dari service procedures.

2. Service Prosedures adalah program yang diginakan untuk menjalankan fungsi pemanggilan procedures yang mana procedures itu harus di aktifkan.

3. Utility Procedures adalah program dasar yang digunakan untuk mengendalikan sistem komputer dan juga untuk mengerjakan apa yang dibutuhkan oleh service procedures.

<p align=justify>Struktur monolitik ini sulit untuk diterapkan dan dijaga. Namun, itu memiliki keunggulan kinerja yang berbeda, sangat sedikit overhead di antarmuka panggilan sistem atau dalam komunikasi di dalam kernel.</p>

Contoh Sistem operasi yang menggunakan struktur ini adalah : UNIX , MS-DOS.

## **Struktur Berlapis (Layered Structure)**

<p align=justify>Struktur Sistem Operasi Layered pada dasarnya dibuat dengan menggunakan
pendekatan top-down, semua fungsi ditentukan dan dibagi menjadi komponen komponen. Modularisasi sistem dilakukan dengan cara memecah sistem operasi menajdi beberapa lapis (tingkat). Lapisan terendah (layer 0) adalah perangkat keras dan lapisan teratas (layer N) adalah user interface. Dengan system modularisasi, setiap lapisan mempunyai fungsi (operasi) tertentu dan melayani lapisan yang lebih rendah.</p>

<p align=center><img src="https://user-images.githubusercontent.com/112606990/192268851-f1662598-09ea-4c9d-b05b-f7e2e48205ed.png"></p>

Berdasarkan pengembangannya ada 6 Layer yang di temukan yaitu :

1. Layer 5 : The operator / user yaitu orang yang mengoperasikan komputer

2. Layer 4 : user program yaitu program yang dipakai oleh operator / user

3. Layer 3 : Input/Output management yaitu menyediakan device driver yang umum

4. Layer 2 : operator-process communication yaitu mengatur komunikasi antar proses

5. Layer 1 : memory and drum management yaitu mengalokasikan memori untuk proses

6. Layer 0 : processor allocation dan multiprogramming yaitu menentukan alokasi proses ke CPU, menangani interupsi dan perpindahan proses (sebagai scheduler)

<p align=justify>Keuntungan utama dari pendekatan berlapis adalah kesederhanaan konstruksi dan debugging. Lapisan dipilih sehingga masing-masing menggunakan fungsi (operasi) dan layanan hanya lapisan tingkat yang lebih rendah. Pendekatan ini menyederhanakan debugging dan verifikasi sistem. Lapisan pertama dapat di-debug tanpa khawatir untuk sisa sistem, karena, menurut definisi, hanya menggunakan perangkat keras dasar (yang dianggap benar) untuk mengimplementasikan fungsinya. Setelah lapisan pertama adalah di-debug, fungsinya yang benar dapat diasumsikan sementara lapisan kedua adalah debug, dan sebagainya. Jika kesalahan ditemukan selama debugging tertentu lapisan, kesalahan harus pada lapisan itu, karena lapisan di bawahnya sudah debug. Dengan demikian, desain dan implementasi sistem disederhanakan.</p>

<p align=justify>Setiap lapisan diimplementasikan hanya dengan operasi yang disediakan oleh tingkat yang lebih rendah
lapisan. Sebuah layer tidak perlu mengetahui bagaimana operasi ini diimplementasikan;
ia hanya perlu mengetahui apa yang dilakukan operasi-operasi ini. Oleh karena itu, setiap lapisan menyembunyikan
keberadaan struktur data, operasi, dan perangkat keras tertentu dari tingkat yang lebih tinggi
lapisan.</p>

<p align=justify>Kekurangan dari implementasi berlapis adalah bahwa mereka cenderung kurang efisien dibandingkan jenis lainnya. Misalnya, ketika program pengguna menjalankan I/O operasi, itu mengeksekusi panggilan sistem yang terjebak ke lapisan I/O, yang memanggil lapisan manajemen memori, yang pada gilirannya memanggil lapisan penjadwalan CPU, yang kemudian diteruskan ke perangkat keras. Pada setiap lapisan, parameternya mungkin:
dimodifikasi, data mungkin perlu diteruskan, dan sebagainya. Setiap lapisan menambahkan overhead ke panggilan sistem. Hasil bersihnya adalah panggilan sistem yang membutuhkan waktu lebih lama daripada yang dilakukan pada sistem yang tidak berlapis.</p>

Contoh Sistem operasi yang menggunakan struktur ini adalah : THE, MULTICS

## **Kernel Mikro**

<p align=justify>Pada Struktur ini, Seolah-olah semua user memiliki komputer sendiri. Namun secara fisik kenyataanya hanya ada satu komputer saja, tetapi secara logic ada beberapa mesin komputer. Struktur ini biasa disebut CP/CMS (Conversational Monitor System), kemudian menjadi virtual Machine/370 yang dikembangkan oleh Seawright dan Mackinnon tahun 1979. Inti dari Virtual Machine adalah Virtual Machine Monitor, yang berjalan diatas hardware. Disini multiprogramming tidak disediakan dan baru bisa dilakukan pada layer diatas yaitu pada VM/370.</p>

<p align=justify>Metode ini menyusun sistem operasi dengan menghapus semua komponen yang tidak penting dari kernel dan mengimplementasikannya sebagai sistem dan program tingkat pengguna. Hasilnya lebih kecil inti. Ada sedikit konsensus mengenai layanan mana yang harus tetap di kernel dan mana yang harus diimplementasikan di ruang pengguna. Biasanya, bagaimanapun, mikrokernel menyediakan proses minimal dan manajemen memori, sebagai tambahan ke fasilitas komunikasi. Fungsi utama dari mikrokernel adalah untuk menyediakan komunikasi antara program klien dan berbagai layanan yang juga berjalan di ruang pengguna.</p>

<p align=center><img src="https://user-images.githubusercontent.com/112606990/192268840-131032fb-c3fe-4043-8969-50618a3b7384.png"></p>

<p align=justify>Salah satu manfaat dari pendekatan mikrokernel adalah membuat perluasan sistem operasi lebih mudah. Semua layanan baru ditambahkan ke ruang pengguna dan akibatnya tidak memerlukan modifikasi kernel. Ketika kernel melakukannya harus dimodifikasi, perubahannya cenderung lebih sedikit, karena mikrokernelnya kernel yang lebih kecil. Sistem operasi yang dihasilkan lebih mudah untuk port dari satu desain perangkat keras ke yang lain. Mikrokernel juga memberikan lebih banyak keamanan dan keandalan, karena sebagian besar layanan berjalan sebagai pengguna—bukan kernel— proses. Jika layanan gagal, sisa sistem operasi tetap tidak tersentuh.</p>

<p align=justify>Sayangnya, kinerja mikrokernel dapat menurun karena peningkatan overhead fungsi sistem. Pertimbangkan sejarah Windows NT. Pertama rilis memiliki organisasi mikrokernel berlapis. Performa versi ini rendah dibandingkan dengan Windows 95. Windows NT 4.0 sebagian memperbaiki masalah kinerja dengan memindahkan lapisan dari ruang pengguna ke ruang kernel dan mengintegrasikannya lebih dekat. Pada saat Windows XP dirancang, arsitektur Windows telah menjadi lebih monolitik daripada mikrokernel.</p>

Contoh Virtual machine adalah : VMWare, Virtual Box

## **Perbedaan Ketiga Struktur Operasi**

**Struktur sederhana**:

- Struktur sistem operasi di sistem ini tidak terstruktur.
- Sistem operasi sebagai kumpulan prosedur yang masing-masing dapat saling dipanggil jika dibutuhkan.
- Setiap prosedur yang ada di dalam sistem ini mempunyai interface yang sudah didefinisikan dengan baik (masing-masing prosedur bebas untuk saling memanggil jika dibutuhkan).
- Sangat simpel, sehingga aktivitas organisasi berjalan fleksibel dan cepat.

**Struktur berlapis**:

- Sistem operasi dibentuk secara hirarki berdasar lapisan-lapisan, dimana lapisan-lapisan bawah memberi layanan lapisan lebih atas.
- Memiliki rancangan modular, yaitu sistem dibagi menjadi beberapa modul & tiap modul dirancang secara independen.
- Pendekatan berlapis menyederhanakan rancangan, spesifikasi dan implementasi sistem operasi.

**Kernel Mikro**:

- Menghilangkan komponen-komponen yang tidak diperlukan dari kernel dan mengimplementasikannya sebagai sistem dan program-program level user.
- menyediakan fasilitas komunikasi antara program client dan bermacam pelayanan yang berjalan pada ruang user.
- Mudah dalam memperluas sistem operasi.
- Mudah untuk diubah ke bentuk arsitektur baru.
- Kode yang kecil dan lebih aman.
