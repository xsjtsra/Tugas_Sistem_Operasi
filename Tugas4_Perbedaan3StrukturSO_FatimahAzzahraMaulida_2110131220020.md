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

## **Struktur Sederhana (Monolitic Structure)**

<p align=justify>Pada struktur ini, sistem operasi komputer dibuat dari sekumpulan prosedur, yang mana setiap prosedur itu dapat memanggil prosedur yang lainnya, kapan pun prosedur di perlukan.</p>

<p align=center><img src="https://user-images.githubusercontent.com/112606990/192268843-aefb7763-2df3-4462-ab21-125718034f17.png"></p>

Penjelasan lapisan gambar di atas:

1. Main Procedure adalah suatu program yang digunakan untuk memanggil salah satu dari service prosedures, dan juga meminta pelayanan dari service procedures.

2. Service Prosedures adalah program yang diginakan untuk menjalankan fungsi pemanggilan procedures yang mana procedures itu harus di aktifkan.

3. Utility Procedures adalah program dasar yang digunakan untuk mengendalikan sistem komputer dan juga untuk mengerjakan apa yang dibutuhkan oleh service procedures.

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

Contoh Sistem operasi yang menggunakan struktur ini adalah : THE, MULTICS

## **Kernel Mikro**

<p align=justify>Pada Struktur ini, Seolah-olah semua user memiliki komputer sendiri. Namun secara fisik kenyataanya hanya ada satu komputer saja, tetapi secara logic ada beberapa mesin komputer. Struktur ini biasa disebut CP/CMS (Conversational Monitor System), kemudian menjadi virtual Machine/370 yang dikembangkan oleh Seawright dan Mackinnon tahun 1979. Inti dari Virtual Machine adalah Virtual Machine Monitor, yang berjalan diatas hardware. Disini multiprogramming tidak disediakan dan baru bisa dilakukan pada layer diatas yaitu pada VM/370.</p>

<p align=center><img src="https://user-images.githubusercontent.com/112606990/192268840-131032fb-c3fe-4043-8969-50618a3b7384.png"></p>

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
