# alstrudat-c01-ifs23026

## Description

Buatlah program sederhana untuk menerima inputan `name` dan `age` dari pengguna. Setelah itu tampilkan informasi sesuai dengan inputan pengguna pada terminal.


## DATA
Data Mobil KBT
No	Nama Mobil	Jenis Bahan Bakar	Daya	Kapasitas Maksimum
1	KBT-101	            Diesel	150	   1000 kg
2	KBT-102	            Listrik	200	   1200 kg
3	KBT-103	            Hybrid	180	   1100 kg
4	KBT-104	            Diesel	170	   950  kg
5	KBT-105	            Listrik	220	   1300 kg 

Data Barang
No	Kode  Barang	    Jenis Barang	  Tipe Barang	Berat Maksimum
1	BRG-001	Elektronik	Fragile         50 kg
2	BRG-002	Makanan	    Non-Fragile	    80 kg
3	BRG-003	Bahan       Kimia	Berbahaya	60 kg
4	BRG-004	Pakaian	    Non-Fragile	    70 kg
5	BRG-005	Perkakas	  Berat	          90 kg

## Implementation Requirements
Validasi Data:

Mobil KBT dan barang harus terdaftar dalam data yang tersedia. Jika tidak, input ulang.
Berat barang tidak boleh melebihi berat maksimum yang ditentukan.

Pengurutan Data:
Mobil KBT diurutkan berdasarkan nama (A-Z).
Barang diurutkan berdasarkan berat tertinggi. Jika berat sama, urutkan berdasarkan kode barang (A-Z).

Prioritas Pengiriman:
Barang dengan jenis "Berbahaya" atau "Fragile" diprioritaskan.
Jika total berat barang fragile lebih besar dari non-fragile, mobil KBT akan mengangkut barang fragile terlebih dahulu.

Fitur Tambahan:
Hitung total berat barang yang diangkut oleh setiap mobil KBT.
Tampilkan daftar barang yang belum terkirim jika kapasitas mobil tidak mencukupi.

## Source Codes

| No | File         | Deskripsi         |
|----|--------------|-------------------|
| 1  | App.java     | Bawaan            |
| 2  | Program.java | Melengkapi Fungsi |
| 3  | Other.java   | Membuat Sendiri   |

## Functions Structure
src/
└── main/
    └── java/
        └── del/
            └── ifs18005/
                ├── DataMobilKBT.java
                ├── DataBarang.java
                ├── Data.java
                ├── BarangLoader.java
                ├── MobilKBT.java
                ├── LinkedList.java
                ├── LinkedListHelper.java
                └── App.java

## clas diagram
_______________________________________________
| DataMobilKBT        | Data                  |
|---------------------|-----------------------|
| +nama : String      | +static dataMobilKBT  |
| +bahanBakar : String| +static dataBarang    |
| +daya : int         | +static init() : void |
| +kapasitas : int    |                       |
|_____________________|_______________________|
___________________________________________________
| DataBarang         | DataHelper                 |
|--------------------|----------------------------|
| +kode : String     | +static findMobilKBTByName |
| +jenis : String    | +static findBarangByKode   |
| +tipe : String     |                            |
| +berat : int       |                            |
|____________________|____________________________|

________________________________________________________________
| LinkedList<T>      | BarangLoader : Comparable<BarangLoader> |
|--------------------|-----------------------------------------|
|                    | +kode : String                          |
|                    | +berat : int                            |
|                    | +BarangLoader(kode, berat)              |
|                    | +compareTo(other) : int                 | 
|                    | +toString() : String                    |
|____________________|_________________________________________|

___________________________________________________________________________________
| MobilKBT : Comparable<MobilKBT>          | LinkedListHelper                     |
|------------------------------------------|--------------------------------------|
| +nama : String                           | +static sortMobilKBT                 |
| +barangLoaded : LinkedList<BarangLoader> | +static getBarangByTipe              |
| +MobilKBT(nama)                          | +static calculateTotalBerat          |
| +compareTo(other) : int                  | +static prioritizeFragileBarang      |
| +toString() : String                     |                                      |
|__________________________________________|______________________________________|


## Test Case

package del.alstrudat-c01-ifs23026;

public class DataMobilKBT {
    public String nama;
    public String bahanBakar;
    public int daya;
    public int kapasitas;

    public DataMobilKBT(String nama, String bahanBakar, int daya, int kapasitas) {
        this.nama = nama;
        this.bahanBakar = bahanBakar;
        this.daya = daya;
        this.kapasitas = kapasitas;
    }
}

package del.alstrudat-c01-ifs23026;

public class DataBarang {
    public String kode;
    public String jenis;
    public String tipe;
    public int berat;

    public DataBarang(String kode, String jenis, String tipe, int berat) {
        this.kode = kode;
        this.jenis = jenis;
        this.tipe = tipe;
        this.berat = berat;
    }
}


package del.alstrudat-c01-ifs23026;

public class Data {
    public static LinkedList<DataMobilKBT> dataMobilKBT = new LinkedList<>();
    public static LinkedList<DataBarang> dataBarang = new LinkedList<>();

    public static void init() {
        // Data Mobil KBT
        dataMobilKBT.append(new DataMobilKBT("KBT-101", "Diesel", 150, 1000));
        dataMobilKBT.append(new DataMobilKBT("KBT-102", "Listrik", 200, 1200));
        dataMobilKBT.append(new DataMobilKBT("KBT-103", "Hybrid", 180, 1100));
        dataMobilKBT.append(new DataMobilKBT("KBT-104", "Diesel", 170, 950));
        dataMobilKBT.append(new DataMobilKBT("KBT-105", "Listrik", 220, 1300));

        // Data Barang
        dataBarang.append(new DataBarang("BRG-001", "Elektronik", "Fragile", 50));
        dataBarang.append(new DataBarang("BRG-002", "Makanan", "Non-Fragile", 80));
        dataBarang.append(new DataBarang("BRG-003", "Bahan Kimia", "Berbahaya", 60));
        dataBarang.append(new DataBarang("BRG-004", "Pakaian", "Non-Fragile", 70));
        dataBarang.append(new DataBarang("BRG-005", "Perkakas", "Berat", 90));
    }
}

## Compile



## Run


