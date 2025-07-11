# 🛒 Aplikasi Kasir C++

Aplikasi kasir sederhana berbasis C++ yang memungkinkan pengguna untuk mengelola inventaris barang, memproses transaksi penjualan, dan membuat laporan penjualan.

## ✨ Fitur Utama

### 📋 Menu Utama
- **➕ Tambah Barang** - Menambahkan barang baru ke dalam inventaris
- **✏️ Edit Barang** - Mengubah informasi (nama, harga, stok) barang yang sudah ada
- **🗑️ Hapus Barang** - Menghapus barang dari inventaris
- **📄 Tampilkan Semua Barang** - Menampilkan daftar semua barang yang tersedia di inventaris
- **🔍 Cari Barang** - Mencari barang berdasarkan ID-nya
- **💳 Proses Transaksi** - Melakukan transaksi penjualan, menghitung total pembayaran, dan mengelola stok
- **📊 Buat Laporan Penjualan** - Menampilkan laporan penjualan secara langsung
- **💾 Simpan Transaksi ke File** - Menyimpan data transaksi ke file `datatransaksi.doc`
- **📈 Tampil Semua Laporan Transaksi** - Menampilkan riwayat transaksi yang tersimpan, dengan opsi filter harian, bulanan, atau tahunan

## 📊 Struktur Data

### 📦 `struct Item`
Menyimpan data untuk setiap barang:
- 🆔 ID
- 🏷️ Nama
- 💰 Harga
- 📦 Stok

### 🧾 `struct Transaksi`
Menyimpan rincian transaksi:
- 📦 Item yang terjual
- 💰 Total harga
- 💳 Metode pembayaran
- ⏰ Waktu transaksi
- 💵 Uang kembalian

## 📁 File yang Digunakan

### 📄 `databarang.doc`
File teks untuk menyimpan data inventaris barang.
**Format:** `ID,Nama,Harga,Stok`
**Contoh:** `1,Kopi Susu,2000,18`

### 🧾 `datatransaksi.doc`
File teks untuk menyimpan riwayat transaksi.
**Format:** `| Nama Barang | Jumlah | Total | Metode | Tanggal`
**Contoh:** `| Kopi Susu | 2 | 4000 | Tunai | 25-04-2025`

### 🧾 `struk_penjualan.doc`
File yang dibuat/diperbarui otomatis setiap kali transaksi selesai, berisi rincian penjualan dalam format struk.

## ⚙️ Fungsi Program

### 📦 Manajemen Barang
- `simpanBarangKeFile()` - Menyimpan data inventaris dari array `inventaris` ke file `databarang.doc`
- `bacaBarangDariFile()` - Memuat data barang dari file `databarang.doc` ke dalam array `inventaris` saat program dimulai
- `tambahBarang()` - Memungkinkan pengguna memasukkan detail barang baru, memvalidasi ID dan nama yang unik, lalu menyimpan data ke file
- `editBarang()` - Memperbarui detail barang yang sudah ada setelah pengguna memasukkan ID-nya
- `hapusBarang()` - Menghapus data barang dari array dan file berdasarkan ID yang dimasukkan
- `tampilkanSemuaBarang()` - Menampilkan semua data barang dalam format tabel
- `cariBarang()` - Mencari dan menampilkan detail barang tertentu menggunakan ID

### 💳 Transaksi
- `ProsesTransaksi()` - Mengelola alur penjualan lengkap:
  - 📝 Input nama barang dan jumlah
  - ✅ Pemeriksaan ketersediaan stok
  - 🧮 Perhitungan total
  - 💳 Pemilihan metode pembayaran
  - 💰 Proses pembayaran tunai dengan perhitungan kembalian
- `dapatkanWaktuSekarang()` - Mengambil tanggal sistem saat ini untuk digunakan dalam catatan transaksi

### 📊 Laporan
- `BuatStrukPenjualan(const Transaksi& transaksi)` - Menghasilkan struk penjualan dalam format yang mudah dibaca dan menyimpannya ke file `struk_penjualan.doc`
- `BuatLaporanPenjualan()` - Menampilkan laporan semua transaksi yang ada di memori
- `SimpanTransaksikeFile()` - Menyimpan semua transaksi dari memori ke file `datatransaksi.doc`
- `laporanTransaksi()` - Membaca data transaksi dari file `datatransaksi.doc` dan menampilkannya dengan opsi filter berdasarkan tanggal, bulan, atau tahun

## 🏪 Informasi Toko

**Nama Toko:** SUKA MAJU BERSAMA 

## 📖 Cara Penggunaan

1. 🚀 Jalankan program
2. 📋 Pilih menu yang diinginkan dari menu utama
3. 📝 Ikuti instruksi yang diberikan untuk setiap fungsi
4. 💾 Data akan tersimpan otomatis ke file yang sesuai

## 📋 Catatan

- 💽 Program menggunakan sistem file lokal untuk penyimpanan data
- 📥 Semua transaksi akan tersimpan secara permanen di file
- 🧾 Struk penjualan akan dibuat otomatis setiap kali transaksi selesai
- 📊 Laporan dapat difilter berdasarkan periode waktu (harian, bulanan, tahunan)
