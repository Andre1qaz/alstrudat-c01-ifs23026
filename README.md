Soal Buatan Andre Christian Saragih

dengan struktur kode sebagai berikut:
Proyek Java
├── App.java
├── Data.java
├── DataBarang.java
├── DataMobilKBT.java
├── BarangLoader.java
├── MobilKBT.java
├── LinkedList.java
├── LinkedListHelper.java
└── Util.java

📄 Deskripsi Tugas
Judul:
Manajemen Data Barang dan Mobil KBT 

Tujuan:
Anda diminta untuk mempelajari dan memahami implementasi struktur data Linked List dalam proyek Java sederhana. Proyek ini mengelola dua jenis data, yaitu Barang dan Mobil KBT, menggunakan struktur data dan utilitas yang telah disediakan.

Struktur Proyek:
App.java: Program utama yang menjalankan aplikasi.
Data.java: Kelas dasar yang digunakan untuk menyimpan informasi umum.
DataBarang.java: Kelas turunan dari Data untuk data barang.
DataMobilKBT.java: Kelas turunan dari Data untuk data mobil KBT.
BarangLoader.java: Kelas untuk memuat data barang.
MobilKBT.java: Kelas untuk memuat data mobil KBT.
LinkedList.java: Implementasi struktur data Linked List.
LinkedListHelper.java: Kelas pembantu untuk operasi-operasi khusus pada Linked List.
Util.java: Berisi fungsi-fungsi utilitas umum untuk mendukung aplikasi.

Tugas:
Pahami masing-masing kelas dan fungsinya dalam proyek.
Jelaskan bagaimana hubungan antar kelas dalam bentuk diagram sederhana.
Jelaskan alur program dari mulai aplikasi dijalankan hingga data ditampilkan.

untuk class diagram dari kode yang dapat langsung di akses ataupun kode yang digunakan dalam proyek ini adalah sebagai berikut


class diagram App.java
+-------------------------------------------------+
|                     App                         |
+-------------------------------------------------+
| - mobilManager: MobilKBT                        |
| - barangLoader: BarangLoader                    |
+-------------------------------------------------+
| + main(args: String[]): void                    |
| - tampilkanMenu(): void                         |
| - bacaInputAngka(prompt: String): int           |
+-------------------------------------------------+

+-------------------------------------------------+
|                   MobilKBT                      |
+-------------------------------------------------+
| + tampilkanSemuaMobil(): void                   |
| + tambahMobil(): void                           |
| + tampilkanDetailMobil(): void                  |
| + updateMobil(): void                           |
| + hapusMobil(): void                            |
| + cariMobilByNama(): void                       |
| + cariMobilByKapasitasPenumpang(): void         |
| + sortMobilByDaya(): void                       |
| + sortMobilByKapasitasBaterai(): void           |
+-------------------------------------------------+

+-------------------------------------------------+
|                BarangLoader                     |
+-------------------------------------------------+
| + tampilkanBarang(): void                       |
| + tambahBarang(): void                          |
+-------------------------------------------------+

+-------------------------------------------------+
|                    Util                         |
+-------------------------------------------------+
| + getScanner(): Scanner                         |
| + closeScanner(): void                          |
+-------------------------------------------------+

class diagram BarangLoader.java
+-------------------------------------------------------------+
|                       BarangLoader                          |
+-------------------------------------------------------------+
| - daftarBarang: LinkedList<DataBarang>                      |
+-------------------------------------------------------------+
| + BarangLoader()                                            |
| - initData(): void                                          |
| + tampilkanBarang(): void                                   |
| + tambahBarang(): void                                      |
| + close(): void                                             |
+-------------------------------------------------------------+

Class diagram Data.java
+-----------------------------------------------------------+
|                  <<abstract>> Data                        |
+-----------------------------------------------------------+
| # id: String                                              |
| # nama: String                                            |
+-----------------------------------------------------------+
| + Data(id: String, nama: String)                          |
| + getId(): String                                         |
| + setId(id: String): void                                 |
| + getNama(): String                                       |
| + setNama(nama: String): void                             |
| + tampilData(): void   <<abstract>>                       |
+-----------------------------------------------------------+


Class diagram DataBarang.java
+----------------------------------------------------------------------+
|                       DataBarang                                     |
+----------------------------------------------------------------------+
| - jenis: String                                                      | 
| - harga: double                                                      | 
+----------------------------------------------------------------------+
| + DataBarang(id: String, nama: String, jenis: String, harga: double) |
| + getJenis(): String                                                 |
| + setJenis(jenis: String): void                                      |
| + getHarga(): double                                                 |
| + setHarga(harga: double): void                                      | 
| + tampilData(): void (override)                                      | 
+----------------------------------------------------------------------+
| <<extends>> Data                                                     |
+----------------------------------------------------------------------+

Class diagram DataMobilKBT.java
+--------------------------------------------------------------------+
|                          DataMobilKBT                              |
+--------------------------------------------------------------------+
| - jenis: String                                                    |
| - dayaListrik: double                                              |
| - kapasitasBaterai: int                                            |
| - kapasitasPenumpang: int                                          |
| - jangkauan: double                                                |
+--------------------------------------------------------------------+
| + DataMobilKBT(id: String, nama: String, jenis: String,            |
|                dayaListrik: double, kapasitasBaterai: int,         |
|                kapasitasPenumpang: int, jangkauan: double)         |
| + getJenis(): String                                               |
| + setJenis(jenis: String): void                                    |
| + getDayaListrik(): double                                         |
| + setDayaListrik(dayaListrik: double): void                        |
| + getKapasitasBaterai(): int                                       |
| + setKapasitasBaterai(kapasitasBaterai: int): void                 |
| + getKapasitasPenumpang(): int                                     |
| + setKapasitasPenumpang(kapasitasPenumpang: int): void             |
| + getJangkauan(): double                                           |
| + setJangkauan(jangkauan: double): void                            |
| + tampilData(): void (override)                                    |
+--------------------------------------------------------------------+
| <<extends>> Data                                                   |
+--------------------------------------------------------------------+


Class diagram LinkedList.java
+-------------------------------------------------------------------+
|                        LinkedListHelper                           |
+-------------------------------------------------------------------+
| + sortList(list: LinkedList<T>, comparator: Comparator<T>): void  |
+-------------------------------------------------------------------+

Class diagram LinkedListHelper.java
+-------------------------------------------------------------------+
|                           LinkedListHelper                        |
+-------------------------------------------------------------------+
| + sortList(list: LinkedList<T>, comparator: Comparator<T>): void  |
+-------------------------------------------------------------------+

Class diagram MobilKBT.java
+------------------------------------------------------+
|                      MobilKBT                        |
+------------------------------------------------------+
| - daftarMobil: LinkedList<DataMobilKBT>              |
+------------------------------------------------------+
| + MobilKBT()                                         |
| + initializeData()                                   |
| + tambahMobil()                                      |
| + tampilkanSemuaMobil()                              |
| + tampilkanDetailMobil()                             |
| + updateMobil()                                      |
| + hapusMobil()                                       |
| + cariMobilByNama()                                  |
| + cariMobilByKapasitasPenumpang()                    |
| + sortMobilByDaya()                                  |
| + sortMobilByKapasitasBaterai()                      |
| - cariMobilById(id: String): DataMobilKBT            |
+------------------------------------------------------+

