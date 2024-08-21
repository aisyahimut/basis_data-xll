# DESC
**Penjelasan** : Dalam MySQL, `DESC` adalah singkatan dari "DESCRIBE". Perintah `DESCRIBE` digunakan untuk menampilkan struktur dari tabel yang ada dalam database. Dengan menggunakan `DESCRIBE`, Anda bisa mendapatkan informasi mengenai kolom-kolom dalam tabel, termasuk nama kolom, tipe data, apakah kolom tersebut dapat bernilai `NULL` atau tidak, dan atribut lainnya seperti kunci primer (primary key) atau default value.

**Contoh Program :
~~~sql
desc Pegawai;
~~~
**Hasilnya :

![](aset/d.jpg)

**Analisisnya :**
**NIP INT PRIMARY KEY :
- `NIP`: Ini biasanya merujuk pada nama kolom dalam tabel basis data. Dalam konteks basis data, NIP sering digunakan sebagai singkatan untuk "Nomor Induk Pegawai," yang merupakan identifikasi unik untuk pegawai dalam sistem.
- `INT`: Ini adalah tipe data dalam SQL yang berarti "integer" atau bilangan bulat. Tipe data ini digunakan untuk menyimpan angka tanpa pecahan desimal.
- `PRIMARY KEY`: Ini adalah sebuah constraint (kekangan) dalam SQL yang menandakan bahwa kolom tersebut adalah kunci utama. Tidak ada dua baris yang boleh memiliki nilai yang sama pada kolom kunci utama, dan kolom ini tidak boleh berisi nilai NULL.
**NDep VARCHAR(255) NOT NULL :
-  `NDep` : Ini adalah nama kolom dalam tabel basis data.
- `VARCHAR`: Singkatan dari "Variable Character," adalah tipe data yang digunakan untuk menyimpan teks dengan panjang variabel.
- `(255)`: dapat menyimpan hingga 255 karakter.
- `NOT NULL`: Ini adalah constraint (kekangan) yang menunjukkan bahwa kolom ini tidak boleh mengandung nilai NULL.
**NBlk VARCHAR(255)** :
- `NBlk` : Kolom ini menyimpan Nama Belakang pegawai bertipe data string dengan panjang maksimum 255 karakter
- `VARCHAR(255))` : Kolom ini tidak memiliki batasan NOT NULL, sehingga nilai kosong (NULL) diizinkan.
**JK ENUM('L', 'P') NOT NULL**:
- `JK` : Kolom ini menyimpan Jenis Kelamin pegawai dengan tipe data ENUM. Hanya dua nilai yang diperbolehkan: 'L' (Laki-laki) atau 'P' (Perempuan).
- `ENUM` :Anda memastikan bahwa hanya nilai-nilai tertentu yang bisa dimasukkan ke dalam kolom. Misalnya, untuk kolom `JenisKelamin`, Anda hanya mengizinkan 'Laki-laki' atau 'Perempuan'. Ini membantu menjaga konsistensi data.
- `NOT NULL` : Menandakan bahwa kolom ini tidak boleh kosong; artinya, setiap baris harus memiliki nilai untuk kolom ini.
**Alamat TEXT NOT NULL**:
- `Alamat` : Kolom ini menyimpan alamat pegawai dengan tipe data TEXT.
- `TEXT` : dapat menyimpan data teks dengan panjang hingga 65.535 karakter (untuk `TEXT` standar), yang biasanya cukup untuk alamat yang panjang.
- `NOT NULL` Menandakan bahwa kolom ini harus diisi dengan nilai; nilai kosong (NULL) tidak diperbolehkan.
**Telp VARCHAR(255) NOT NULL**:
- `Telp` : Kolom ini menyimpan nomor telepon pegawai dengan tipe data string dan panjang maksimum 255 karakter (VARCHAR(255)).
- `NOT NULL` : Menandakan bahwa kolom ini harus diisi; nilai kosong (NULL) tidak diperbolehkan.
**Jabatan ENUM('Manager', 'Supervisor', 'Staff')** :
- `Jabatan` : Kolom ini menyimpan jabatan pegawai dengan tipe data ENUM. Nilai yang diperbolehkan adalah 'Manager', 'Supervisor', atau 'Staff'.
- Kolom ini tidak memiliki batasan NOT NULL, sehingga nilai kosong (NULL) diizinkan.

**Gaji BIGINT NOT NULL** :
- `Gaji` : Kolom ini menyimpan gaji pegawai dengan tipe data BIGINT, yang dapat menampung bilangan bulat yang sangat besar.
- `BIGINT` adalah tipe data dalam SQL yang digunakan untuk menyimpan bilangan bulat (integer) dengan rentang yang lebih besar dibandingkan dengan tipe data `INT`.
- `NOT NULL`: Menandakan bahwa kolom ini harus diisi; nilai kosong (NULL) tidak diperbolehkan.

- **NoCab VARCHAR(255) NOT NULL**:
- `NoCab` : Kolom ini menyimpan nomor cabang pegawai dengan tipe data string dan panjang maksimum 255 karakter (VARCHAR(255)).
- `NOT NULL`: Menandakan bahwa kolom ini harus diisi; nilai kosong (NULL) tidak diperbolehkan.

**Kesimpulan :**
Secara keseluruhan, tabel `pegawai` dirancang dengan kolom `id` sebagai identifikasi unik yang bertambah otomatis, sementara kolom `nama` adalah wajib diisi, dan kolom `jabatan` serta `tanggal_lahir` bersifat opsional. Ini mencerminkan struktur dasar dari tabel yang mungkin digunakan untuk menyimpan data pegawai dengan informasi kunci seperti nama, jabatan, dan tanggal lahir.

# SELECT
**Penjelasan :** Perintah `SELECT` dalam MySQL digunakan untuk mengambil data dari tabel dalam database. Ini adalah perintah dasar dan paling sering digunakan dalam SQL untuk menampilkan data. Anda bisa menggunakan `SELECT` untuk memilih kolom tertentu, menggabungkan tabel, melakukan filter data, dan banyak lagi.

**Contoh Program :**
~~~sql
select * from pegawai;
~~~

**Hasil :**
![](aset/s.jpg)

**Analisisnya:**
1. **SELECT**: Ini adalah perintah SQL yang digunakan untuk memilih data dari database. Dalam hal ini, `SELECT` digunakan untuk mengambil data dari tabel.

2. **;** Simbol ini adalah wildcard yang berarti "semua kolom". Jadi, `SELECT *` akan memilih semua kolom yang ada dalam tabel.

3. **FROM pegawai**: Bagian ini menunjukkan tabel dari mana data akan diambil. Dalam hal ini, tabelnya adalah `pegawai`.


**Kesimpulan :**
Perintah `SELECT * FROM pegawai;` berguna untuk melihat seluruh data dalam tabel `pegawai` tanpa batasan atau filter. Ini adalah cara cepat untuk mendapatkan gambaran lengkap tentang data yang ada di tabel, tetapi untuk analisis yang lebih spesifik atau untuk meningkatkan performa query, sebaiknya Anda memilih kolom tertentu dan menerapkan kondisi yang sesuai.

# Menghitung Jumlah Baris

**Penjelasan :**

**Contoh Program** :
~~~sql
SELECT COUNT(NIP) AS JumlahPegawai, COUNT(Jabatan) AS JumlahJabatan FROM pegawai;
~~~
**Hasilnya :**
![](aset/basdat1.jpg)

**Analisisnya :**
**`SELECT`**:Digunakan untuk memilih data dari tabel.
**`COUNT(NIP)` AS `JumlahPegawai`**:
 Fungsi `COUNT(NIP)` menghitung jumlah baris di tabel `pegawai` di mana kolom `NIP` tidak bernilai NULL.Alias `JumlahPegawai` digunakan untuk memberikan nama hasil kolom ini pada output query.
**`COUNT(Jabatan)` AS `JumlahJabatan`**:
Fungsi `COUNT(Jabatan)` menghitung jumlah baris di tabel `pegawai` di mana kolom `Jabatan` tidak bernilai NULL.Alias `JumlahJabatan` digunakan untuk memberikan nama hasil kolom ini pada output query.
**`FROM pegawai`**:Menunjukkan bahwa data diambil dari tabel `pegawai`.

**Kesimpulannya:**
Query ini memberikan informasi tentang kelengkapan data di dua kolom penting (`NIP` dan `Jabatan`) dalam tabel `pegawai`. Ini berguna untuk melakukan analisis terhadap kualitas data, memastikan bahwa kolom-kolom penting diisi dengan informasi yang diperlukan, dan membantu dalam perencanaan lebih lanjut atau pemeliharaan data.

# Contoh 2

**Contoh Program :**
~~~sql
SELECT COUNT(NIP) AS JumlahPegawai 
-> FROM pegawai 
-> WHERE NoCab = 'C102';
~~~
**Hasilnya :**
![](aset/basdat2.jpg)

**Analisisnya :**
**`SELECT COUNT(NIP) AS JumlahPegawai`**:
**`COUNT(NIP)`**: Fungsi agregat `COUNT` menghitung jumlah baris di mana kolom `NIP` tidak bernilai NULL.
**`AS JumlahPegawai`**: Alias `JumlahPegawai` diberikan pada hasil fungsi `COUNT(NIP)`. Alias ini memberi nama pada kolom hasil query untuk kejelasan.
**`FROM pegawai`**:Menunjukkan tabel `pegawai` sebagai sumber data untuk query.
**`WHERE NoCab = 'C102'`**:
**`WHERE`**: Klausa ini digunakan untuk menyaring baris yang memenuhi kondisi tertentu.
**`NoCab = 'C102'`**: Kondisi ini memfilter baris-baris dalam tabel `pegawai` sehingga hanya baris dengan nilai `NoCab` sama dengan 'C102' yang diperhitungkan.

**Kesimpulannya :**
Query ini memberikan informasi spesifik tentang jumlah pegawai yang terdaftar di cabang dengan kode 'C102' dan yang memiliki nilai pada kolom `NIP`. Ini membantu dalam memantau atau menganalisis distribusi pegawai berdasarkan lokasi atau cabang tertentu.

# Contoh 3
**Penjelasan :**

**Contoh Program :**
~~~sql
SELECT NoCab, COUNT(NIP) AS Jumlah_Pegawai 
-> FROM pegawai
-> GROUP BY NoCab;
~~~
**Hasilnya :**
![](aset/basdat3.jpg)

**Analisisnya :**
**`SELECT NoCab, COUNT(NIP) AS Jumlah_Pegawai`**:
**`NoCab`**: Kolom ini ditampilkan dalam hasil query. Biasanya berisi kode cabang atau lokasi.
**`COUNT(NIP)`**: Fungsi agregat `COUNT` menghitung jumlah baris di mana kolom `NIP` tidak bernilai NULL. Ini memberikan jumlah pegawai di setiap cabang.
 **`AS Jumlah_Pegawai`**: Alias `JumlahPegawai` digunakan untuk memberi nama pada kolom hasil `COUNT(NIP)`. Ini memberikan kejelasan bahwa hasil ini adalah jumlah pegawai.
**`FROM pegawai`**:Menunjukkan tabel `pegawai` sebagai sumber data untuk query.
 **`GROUP BY NoCab`**:Klausa ini mengelompokkan hasil berdasarkan nilai yang sama pada kolom `NoCab`,Setiap kelompok akan berisi baris-baris yang memiliki nilai yang sama di kolom `NoCab`.

**Kesimpulannya:**
Query ini memberikan ringkasan jumlah pegawai di setiap cabang atau lokasi yang ditunjukkan oleh kolom `NoCab`. Dengan mengelompokkan data berdasarkan `NoCab` dan menghitung jumlah pegawai dalam setiap kelompok, query ini membantu dalam analisis distribusi pegawai dan perencanaan sumber daya di berbagai cabang atau lokasi.

# Contoh 4
**Penjelasan  :**
**Contoh Program :**
~~~sql
SELECT NoCab, COUNT(NIP) AS JumlNIP) >- 3;
~~~
**Hasilnya :**
![](aset/basdat4.jpg)ah_Pegawai 
-> FROM pegawai
-> GROUP BY NoCab HAVNG COUNT(
**Analisisnya :**
**`SELECT NoCab, COUNT(NIP) AS Jumlah_Pegawai`**:
**`NoCab`**: Kolom ini ditampilkan dalam hasil query. Biasanya berisi kode cabang atau lokasi.
**`COUNT(NIP)`**: Fungsi agregat `COUNT` menghitung jumlah baris di mana kolom `NIP` tidak bernilai NULL.
**`AS Jumlah_Pegawai`**: Alias `Jumlah_Pegawai` digunakan untuk memberi nama pada hasil fungsi `COUNT(NIP)`, menunjukkan jumlah pegawai di setiap cabang.
**`FROM pegawai`**: Menunjukkan tabel `pegawai` sebagai sumber data untuk query.
 **`GROUP BY NoCab`**:Klausa ini mengelompokkan baris dalam tabel berdasarkan nilai yang sama di kolom `NoCab`. Ini memungkinkan kita untuk menghitung jumlah pegawai di setiap cabang.
**`HAVING COUNT(NIP) > 3`**: Klausa `HAVING` digunakan untuk menyaring hasil agregat setelah `GROUP BY` diterapkan.
**`COUNT(NIP) > 3`**: Menyaring kelompok cabang sehingga hanya cabang yang memiliki lebih dari 3 pegawai yang ditampilkan dalam hasil query.

**Kesimpulannya :**
Query ini menghasilkan daftar cabang yang memiliki lebih dari 3 pegawai. Dengan menggunakan `GROUP BY` dan `HAVING`, query ini memfokuskan pada cabang-cabang dengan jumlah pegawai yang cukup besar, yang bisa digunakan untuk analisis lebih lanjut mengenai distribusi pegawai dan kebutuhan sumber daya di cabang-cabang tersebut.

# Contoh 5
**Penjelasan :**
**Contoh Program :**
~~~sql
	SELECT SUM(Gaji) AS Total_Gaji
	-> FROM pegawai;
~~~
**Hasilnaya :**
![](aset/basdat5.jpg)

**Analisisnya :**`
**`SELECT`**: Ini adalah perintah untuk memilih data dari tabel dalam database.
`
**`SUM(Gaji)`**: Fungsi agregat `SUM()` digunakan untuk menjumlahkan semua nilai dalam kolom `Gaji`. Fungsi ini akan mengembalikan total dari semua nilai `Gaji` yang ada dalam tabel.

 **`AS Total_Gaji`**: Alias `AS Total_Gaji` memberikan nama sementara pada hasil kolom yang dihasilkan oleh `SUM(Gaji)`. Dalam hal ini, hasil dari `SUM(Gaji)` akan ditampila kolom `Total_Gaji`.

 **`FROM pegawai`**: Menunjukkan tabel `pegawai` sebagai sumber data yang akan diambil.

**Kesimpulannya:**
Query ini menghitung total jumlah gaji dari semua pegawai yang terdaftar di tabel pegawai,Hasilnya adalah satu nilai yang menunjukkan jumlah total gaji seluruh pegawai, dan kolom hasil tersebut dinamakan `Total_Gaji`.
Berguna untuk analisis keuangan atau perhitungan total biaya gaji dalam laporan atau aplikasi yang memerlukan informasi total gaji, Dengan kata lain, query ini memberikan total keseluruhan gaji yang harus dibayarkan kepada semua pegawai berdasarkan data di tabel `pegawai`.


# Menghitung total gaji dari semua pegawai yang memiliki jabatan
**Penjelasan :**

**Contoh Program :**
~~~sql
 	SELECT SUM(Gaji) AS Gaji_Manajer
 	-> FROM pegawai
 	-> WHERE Jabatan = 'Manajer';
~~~
**Hasilnya :**
![](aset/basdat6.jpg)

**Analisisnya :**
**`SELECT`**: Digunakan untuk memilih data dari tabel.
**`SUM(Gaji)`**: Fungsi agregat `SUM()` digunakan untuk menjumlahkan semua nilai dalam kolom `Gaji`Dalam konteks ini, `SUM(Gaji)` hanya akan menghitung total gaji untuk baris yang memenuhi kondisi yang diberikan.
 **`AS Gaji_Manajer`**: Memberikan alias `Gaji_Manajer` pada hasil dari fungsi `SUM(Gaji)`. Jadi, hasil dari query ini akan muncul dengan nama kolom `Gaji_Manajer`.
**`FROM pegawai`**: Menunjukkan tabel `pegawai` sebagai sumber data.
**`WHERE Jabatan = 'Manajer'`**: Kondisi ini memfilter data sehingga hanya baris di mana kolom `Jabatan` bernilai `'Manajer'` yang akan diperhitungkan dalam perhitungan `SUM(Gaji)`.

**Kesimpulannya  :**
Query ini digunakan untuk mendapatkan jumlah total gaji yang dibayarkan kepada semua pegawai dengan jabatan `'Manajer'` di tabel `pegawai`. Hasilnya menunjukkan total keseluruhan gaji dari pegawai yang menjabat sebagai manajer.


# Menghitung total gaji pegawai untuk setiap cabang atau unit
**Penjelasan :**
**Contoh Program :**
~~~sql
SELECT NoCab, SUM(Gaji) AS TotalGaji
-> FROM pegawai
-> GROUP BY NoCab;
~~~
**Hasilnya :**
![](aset/basdat7.jpg)

**Analisisnya :**
**SELECT NoCab**:
 `NoCab`: Kolom ini akan ditampilkan dalam hasil query. Berdasarkan nama kolomnya, `NoCab` mungkin merujuk pada nomor cabang atau identifikasi unit dalam tabel `pegawai`.
`SUM(Gaji) AS TotalGaji`: Fungsi agregat `SUM` digunakan untuk menghitung jumlah total dari kolom `Gaji`. `AS TotalGaji` memberikan alias (nama) `TotalGaji` pada hasil agregat ini untuk kemudahan pembacaan.
**FROM Pegawai**:
`pegawai`: Ini adalah nama tabel yang digunakan dalam query. Tabel ini diasumsikan berisi data mengenai pegawai, termasuk kolom `NoCab` dan `Gaji`.
 **GROUP BY NoCab**:
`NoCab`: Kolom ini digunakan untuk mengelompokkan baris-baris dalam tabel `pegawai`. Query akan menghitung total `Gaji` untuk setiap nilai unik dari `NoCab`.

**Kesimpulannya :**
Dengan menggunakan fungsi agregat `SUM` dan klausa `GROUP BY`, query ini mengelompokkan data berdasarkan kolom `NoCab` (nomor cabang) dan menjumlahkan gaji (`Gaji`) untuk setiap kelompok tersebut. Hasilnya adalah daftar nomor cabang berserta total gaji yang dibayarkan di masing-masing cabang. Ini membantu dalam analisis biaya gaji per unit dalam organisasi.

# Menampilkan total gaji pegawai yang melebihi batas
**Penjelasan :**
**Contoh Program :**
~~~sql
SELECT NoCab, SUM(Gaji) AS Total_Gaji
    -> FROM pegawai
	-> GROUP BY NoCab HAVING SUM(Gaji) >= 8000000;
~~~
**Hasilnya :**
![](aset/basdat8.jpg)

**Analisisnya :**
- **SELECT NoCab**:
`NoCab`: Kolom ini menunjukkan nomor cabang atau unit. Hasil query akan mencantumkan nomor cabang.
`SUM(Gaji) AS Total_Gaji`: Fungsi agregat `SUM` digunakan untuk menghitung total gaji (`Gaji`) untuk setiap nomor cabang. Alias `Total_Gaji` diberikan untuk memudahkan pembacaan hasil.
**FROM pegawai**:
`pegawai`: Nama tabel yang berisi data pegawai, termasuk kolom `NoCab` dan `Gaji`.
-**GROUP BY NoCab**:
 `NoCab`: Kolom ini digunakan untuk mengelompokkan hasil berdasarkan nomor cabang. Ini berarti bahwa query akan menghitung total gaji untuk setiap nomor cabang yang berbeda.
**HAVING SUM(Gaji) >= 8000000**:
`HAVING SUM(Gaji) >= 8000000`: Klausa `HAVING` digunakan untuk memfilter kelompok hasil berdasarkan kondisi agregat. Dalam hal ini, hanya cabang-cabang dengan total gaji yang lebih besar atau sama dengan 8.000.000 yang akan ditampilkan dalam hasil query.

**Kesimpulannya :**
Query ini efektif untuk memfilter dan menampilkan hanya cabang-cabang yang memiliki total gaji pegawai yang melebihi batas tertentu (8.000.000 dalam hal ini). Ini membantu dalam fokus analisis pada cabang-cabang dengan biaya gaji tinggi.

# Menghitung rata-rata gaji dari semua pegawai
**Penjelasan  :**
**Contoh Program :**
~~~sql
SELECT AVG(Gaji) AS Rata_rata
-> FROM pegawai;
~~~
**Hasilnya :**
![](aset/basdat9.jpg)
**Analisisnya :**
`AVG(Gaji) AS Rata_rata`: Fungsi agregat `AVG` digunakan untuk menghitung rata-rata dari kolom `Gaji`. Alias `Rata_rata` diberikan untuk memudahkan pembacaan hasil.
**FROM pegawai**:
 `pegawai`: Nama tabel yang berisi data pegawai, termasuk kolom `Gaji`.

**Kesimpulannya :**
Query ini memberikan informasi tentang rata-rata gaji pegawai di tabel `pegawai`. Ini berguna untuk analisis kompensasi, seperti memahami seberapa besar gaji rata-rata yang dibayar kepada pegawai dalam organisasi. 

# Menghitung rata-rata gaji dari semua pegawai yang memiliki jabatan Manajer
**Penjelasan :**
Query SQL yang diberikan digunakan untuk menghitung rata-rata gaji dari pegawai yang memiliki jabatan 'Manajer'. Pertama-tama, query ini menyaring data dari tabel `pegawai` dengan menggunakan klausa `WHERE` untuk hanya memilih baris-baris di mana kolom `Jabatan` bernilai 'Manajer'. Setelah data tersebut disaring, fungsi agregat `AVG` digunakan untuk menghitung rata-rata nilai dari kolom `Gaji` untuk baris yang memenuhi kriteria tersebut. Hasil rata-rata ini kemudian diberi alias `GajiRataMgr`, yang memudahkan interpretasi hasil query. Secara keseluruhan, query ini memberikan satu nilai yang merupakan rata-rata gaji dari semua pegawai dengan jabatan 'Manajer', memungkinkan analisis tentang kompensasi rata-rata dalam kategori jabatan tersebut.
**Contoh Program :**
~~~sql
SELECT AVG(Gaji) AS GajiRataMgr
-> FROOM pegawai
-> WHERE Jabatan = 'Manajer' ;
~~~

**Hasilnya :**
![](aset/basdat10.jpg)

**Analisisnya:**
**`SELECT AVG(Gaji) AS GajiRataMgr`**:
 `SELECT` adalah klausa yang digunakan untuk menentukan kolom-kolom yang ingin ditampilkan dalam hasil query.
`AVG(Gaji)` adalah fungsi agregat yang menghitung nilai rata-rata dari kolom `Gaji`. `AVG` mengacu pada "average" atau rata-rata.
`AS GajiRataMgr` memberikan alias (nama samaran) pada hasil dari fungsi `AVG(Gaji)`. Dalam hal ini, hasil rata-rata gaji akan ditampilkan dengan nama kolom `GajiRataMgr` dalam hasil query.
**`FROM pegawai`**:
`FROM` menunjukkan tabel mana yang akan digunakan dalam query. Dalam hal ini, tabel yang digunakan adalah `pegawai`.
**`WHERE Jabatan = 'Manajer'`**:
 `WHERE` adalah klausa yang digunakan untuk menyaring data berdasarkan kondisi tertentu.
 `Jabatan = 'Manajer'` adalah kondisi yang menyaring baris-baris di tabel `pegawai` sehingga hanya baris yang memiliki nilai `Jabatan` sama dengan `'Manajer'` yang akan dipertimbangkan. Dengan kata lain, hanya pegawai dengan jabatan 'Manajer' yang akan dihitung rata-rata gajinya.

**Kesimpuannya :**
Kesimpulan dari query SQL ini adalah bahwa query digunakan untuk menghitung dan menampilkan rata-rata gaji dari semua pegawai yang memiliki jabatan 'Manajer'. Dengan menyaring data berdasarkan jabatan dan menggunakan fungsi agregat `AVG`, query ini menghasilkan satu nilai yang menunjukkan nilai rata-rata gaji dalam kelompok jabatan tersebut, memberikan wawasan tentang kompensasi rata-rata untuk manajer di organisasi.

# Menghitung rata-rata gaji pegawai di setiap cabang 
**Penjelasannya :**
Query SQL ini menghitung rata-rata gaji pegawai di setiap cabang dengan mengelompokkan data berdasarkan kolom `NoCab`, yang menunjukkan nomor cabang. `AVG(Gaji)` digunakan untuk menghitung rata-rata gaji dalam setiap kelompok cabang. Hasil query menampilkan nomor cabang (`NoCab`) dan rata-rata gaji (`RataGaji`) untuk setiap cabang. Dengan demikian, query ini memberikan informasi tentang rata-rata gaji pegawai di setiap cabang organisasi.
**Contoh Program :**
~~~sql
	SELECT NoCab, AVG(Gaji) AS RataGaji
	-> FROM pegawai
	-> GROUP BY NoCab;
~~~
**Hasilnya:**
![](aset/basdat11.jpg)

**Analisisnya:**
**`SELECT NoCab, AVG(Gaji) AS RataGaji`**:
 `SELECT` menentukan kolom-kolom yang akan ditampilkan dalam hasil query.
`NoCab` adalah kolom yang menunjukkan nomor cabang dari pegawai.
`AVG(Gaji)` adalah fungsi agregat yang menghitung rata-rata nilai dari kolom `Gaji` untuk setiap kelompok data. `AVG` mengacu pada "average" atau rata-rata.
 `AS RataGaji` memberikan alias (nama samaran) pada hasil dari fungsi `AVG(Gaji)`, sehingga hasil rata-rata gaji ditampilkan dengan nama kolom `RataGaji` dalam hasil query.
**`FROM pegawai`**:
 `FROM` menunjukkan tabel yang digunakan dalam query. Dalam hal ini, tabel yang digunakan adalah `pegawai`.
**`GROUP BY NoCab`**:
 `GROUP BY` adalah klausa yang digunakan untuk mengelompokkan data berdasarkan nilai dari kolom tertentu. Dalam query ini, data dikelompokkan berdasarkan kolom `NoCab`, yaitu nomor cabang. Artinya, setiap kelompok terdiri dari pegawai yang berada di cabang yang sama.

**Kesimpulannya :**
Query ini menghitung rata-rata gaji pegawai untuk setiap cabang yang ada, memungkinkan analisis gaji berdasarkan lokasi atau cabang tertentu. Hasilnya memberikan wawasan tentang kompensasi rata-rata di masing-masing cabang organisasi.

# Menghitung rata-rata gaji pegawai di cabang yaitu 'C101' dan 'C102'.
**Penjelasanya :**
Query SQL untuk menghitung rata-rata gaji pegawai untuk cabang-cabang dengan nomor 'C101' dan 'C102'. Dengan menggunakan `GROUP BY NoCab`, query mengelompokkan pegawai berdasarkan nomor cabang dan menghitung rata-rata gaji di setiap cabang. Klausa `HAVING` kemudian menyaring hasil untuk hanya menampilkan rata-rata gaji dari cabang 'C101' dan 'C102', mengecualikan cabang lainnya dari hasil akhir.
**Contoh Program :**
~~~sql
	SELECT NoCab, AVG(Gaji) AS RataGaji
	-> FROM pegawai
	-> GROUP BY NoCab HAVING NoCab = 'C101' OR NoCab = 'C102';
~~~
**Hasilnya :**
![](aset/basdat12.jpg)

**Analisisnya :**
**`SELECT NoCab, AVG(Gaji) AS RataGaji`**:
`SELECT` digunakan untuk menentukan kolom yang akan ditampilkan dalam hasil query.
`NoCab` adalah kolom yang menunjukkan nomor cabang.
 `AVG(Gaji)` menghitung rata-rata gaji untuk setiap kelompok cabang.
 `AS RataGaji` memberikan alias pada hasil rata-rata gaji.
**`FROM pegawai`**:
 `FROM` menunjukkan tabel yang digunakan, yaitu `pegawai`.
**`GROUP BY NoCab`**:
`GROUP BY` mengelompokkan data berdasarkan kolom `NoCab`. Setiap kelompok mewakili pegawai di cabang yang sama.
**`HAVING NoCab = 'C101' OR NoCab = 'C102'`**:
`HAVING` adalah klausa yang digunakan untuk menyaring hasil setelah pengelompokan (`GROUP BY`).
Di sini, `HAVING` digunakan untuk hanya menyertakan cabang dengan nomor 'C101' atau 'C102' dalam hasil akhir. Ini menyaring kelompok yang sudah terbentuk untuk menampilkan hanya cabang-cabang tersebut.

**Kesimpulannya :**
Query ini menghitung dan menampilkan rata-rata gaji untuk pegawai di cabang-cabang tertentu ('C101' dan 'C102'). Hasilnya menunjukkan rata-rata gaji hanya untuk cabang yang sesuai dengan kondisi yang ditentukan.

# Menampilkan gaji terbesar dan terkecil di tabel pegawai
**Penjelasannya :**
Query SQL ini menampilkan gaji tertinggi dan terendah di tabel `pegawai`. `MAX(Gaji)` memberikan gaji tertinggi, sementara `MIN(Gaji)` memberikan gaji terendah. Hasilnya menunjukkan dua kolom: `GajiTerbesar` untuk gaji tertinggi dan `GajiTerkecil` untuk gaji terendah, memberikan wawasan tentang rentang gaji dalam tabel.
**Contoh Program :**
~~~sql
SELECT MAX(Gaji) AS GajiTerbesar, MIN(Gaji) AS GajiTerkecil
	-> FROM pegawai;
~~~

**Hasilnya :**
![](aset/basdat13.jpg)

**Analisisnya :**
**`SELECT MAX(Gaji) AS GajiTerbesar, MIN(Gaji) AS GajiTerkecil`**:
 `SELECT` menentukan kolom yang akan ditampilkan dalam hasil query.
`MAX(Gaji)` adalah fungsi agregat yang mengembalikan nilai gaji tertinggi di seluruh tabel `pegawai`. Alias `GajiTerbesar` diberikan untuk kolom hasil dari fungsi ini.
 `MIN(Gaji)` adalah fungsi agregat yang mengembalikan nilai gaji terendah di seluruh tabel `pegawai`. Alias `GajiTerkecil` diberikan untuk kolom hasil dari fungsi ini.
**`FROM pegawai`**:
`FROM` menunjukkan tabel yang digunakan, yaitu `pegawai`.

**Kesimpulannya :**
Query ini memberikan informasi tentang gaji tertinggi dan terendah di tabel `pegawai`. Hasilnya memudahkan pemahaman tentang rentang gaji dalam dataset yang ada.

# Menghitung gaji tertinggi dan terendah di bagian pegawai yang memiliki jabatan Manajer
**Penjelasannya :**
Query SQL ini menghitung gaji tertinggi dan terendah di antara pegawai yang memiliki jabatan 'Manajer'. Menggunakan `MAX(Gaji)` dan `MIN(Gaji)`, query ini menyaring data berdasarkan jabatan 'Manajer' dan menampilkan dua kolom: `GajiTerbesar` untuk gaji tertinggi dan `GajiTerkecil` untuk gaji terendah dalam kelompok manajer.
**Contoh Program :**
~~~sql
SELECT MAX(Gaji) AS GajiTerbesar, MIN(Gaji) AS GajiTerkecil
	-> FROM pegawai;
	-> WHERE Jabatan = 'Manajer';
~~~
**Hasilnya :**
![](aset/basdat14.jpg)

**Analisisnya :**
**`SELECT MAX(Gaji) AS GajiTerbesar, MIN(Gaji) AS GajiTerkecil`**:
`SELECT` digunakan untuk menentukan kolom yang akan ditampilkan dalam hasil query.
`MAX(Gaji)` adalah fungsi agregat yang menghitung nilai gaji tertinggi dari baris yang dipilih. Alias `GajiTerbesar` diberikan untuk hasil ini.
`MIN(Gaji)` adalah fungsi agregat yang menghitung nilai gaji terendah dari baris yang dipilih. Alias `GajiTerkecil` diberikan untuk hasil ini.
**`FROM pegawai`**:
`FROM` menunjukkan tabel yang digunakan, yaitu `pegawai`.
**`WHERE Jabatan = 'Manajer'`**:
`WHERE` adalah klausa yang digunakan untuk menyaring data berdasarkan kondisi tertentu. Di sini, kondisi `Jabatan = 'Manajer'` menyaring data sehingga hanya baris dengan jabatan 'Manajer' yang dipertimbangkan dalam perhitungan.

**Kesimpulannya :**
Query ini memberikan informasi tentang gaji tertinggi dan terendah khusus untuk pegawai dengan jabatan 'Manajer'. Ini membantu dalam memahami rentang gaji di kategori jabatan tersebut.

# Menampilkan gaji tertinggi dan terendah di setiap cabang
**Penjelasannya :**
Query SQL ini menghitung gaji tertinggi dan terendah untuk setiap cabang. Menggunakan `GROUP BY NoCab`, query mengelompokkan pegawai berdasarkan nomor cabang, lalu menghitung `MAX(Gaji)` dan `MIN(Gaji)` untuk setiap cabang. Hasilnya menampilkan nomor cabang, gaji tertinggi (`GajiTerbesar`), dan gaji terendah (`GajiTerkecil`) di masing-masing cabang.
**Contoh Program :**
~~~sql
SELECT NoCab, MAX(Gaji) AS GajiTerbesar, MIN(Gaji) AS GajiTerkecil
	-> FROM pegawai
	-> GROUP BY NoCab;
~~~
**Hasilnya :**
![](aset/basdat15.jpg)

**Penjelasannya :**
**`SELECT NoCab, MAX(Gaji) AS GajiTerbesar, MIN(Gaji) AS GajiTerkecil`**:
 `SELECT` menentukan kolom-kolom yang akan ditampilkan dalam hasil query.
`NoCab` adalah kolom yang menunjukkan nomor cabang.
`MAX(Gaji)` menghitung nilai gaji tertinggi dalam setiap kelompok cabang. Alias `GajiTerbesar` diberikan untuk hasil ini.
`MIN(Gaji)` menghitung nilai gaji terendah dalam setiap kelompok cabang. Alias `GajiTerkecil` diberikan untuk hasil ini.
**`FROM pegawai`**:
 `FROM` menunjukkan tabel yang digunakan, yaitu `pegawai`.
**`GROUP BY NoCab`**:
 `GROUP BY` mengelompokkan data berdasarkan kolom `NoCab`, sehingga fungsi agregat `MAX` dan `MIN` dihitung untuk setiap kelompok cabang.

**Kesimpulanya :**
Query ini memberikan informasi tentang gaji tertinggi dan terendah di setiap cabang. Hasilnya membantu dalam memahami rentang gaji dalam setiap cabang organisasi.

# Menghitung gaji terbesar dan terkecil, tetapi hanya untuk cabang yang memenuhi kriteria jumlah pegawai.
**Penjelasannya :**
Query SQL ini menampilkan gaji tertinggi dan terendah untuk setiap cabang, tetapi hanya untuk cabang yang memiliki minimal tiga pegawai. Dengan `GROUP BY NoCab`, query mengelompokkan data berdasarkan cabang dan menggunakan `HAVING COUNT(NIP) >= 3` untuk menyaring cabang dengan setidaknya tiga pegawai. Hasilnya menunjukkan nomor cabang, gaji tertinggi (`GajiTerbesar`), dan gaji terendah (`GajiTerkecil`) hanya untuk cabang-cabang yang memenuhi kriteria jumlah pegawai.
**Contoh Program :**
~~~sql
SELECT NoCab, MAX(Gaji) AS GajiTerbesar, MIN(Gaji) AS GajiTerkecil
	-> FROM pegawai
	-> GROUP BY NoCab HAVING COUNT(NIP) >= 3;
~~~
**Hasilnya :**
![](aset/basdat16.jpg)

**Analisisnya :**
**`SELECT NoCab, MAX(Gaji) AS GajiTerbesar, MIN(Gaji) AS GajiTerkecil`**:
`SELECT` menentukan kolom yang akan ditampilkan dalam hasil query.
`NoCab` adalah kolom yang menunjukkan nomor cabang.
`MAX(Gaji)` menghitung gaji tertinggi di setiap kelompok cabang, dengan alias `GajiTerbesar`.
`MIN(Gaji)` menghitung gaji terendah di setiap kelompok cabang, dengan alias `GajiTerkecil`.
 **`FROM pegawai`**:
`FROM` menunjukkan tabel yang digunakan, yaitu `pegawai`.
**`GROUP BY NoCab`**:
`GROUP BY` mengelompokkan data berdasarkan kolom `NoCab`, sehingga fungsi agregat `MAX` dan `MIN` dihitung untuk setiap kelompok cabang.
**`HAVING COUNT(NIP) >= 3`**:
 `HAVING` digunakan untuk menyaring hasil setelah pengelompokan.
 `COUNT(NIP)` menghitung jumlah pegawai di setiap cabang.
  `HAVING COUNT(NIP) >= 3` memastikan hanya cabang-cabang dengan tiga pegawai atau lebih yang ditampilkan.

**Kesimpulannya :**
Query ini memberikan informasi tentang gaji tertinggi dan terendah di setiap cabang, tetapi hanya untuk cabang-cabang yang memiliki tiga pegawai atau lebih. Hasilnya memfokuskan pada cabang yang memiliki cukup banyak pegawai untuk memastikan data yang lebih representatif.

# Menampilkan lima nilai agregat yang memberikan gambaran menyeluruh mengenai distribusi gaji dalam tabel
**Penjelasannya :**
Query SQL ini memberikan ringkasan informasi tentang gaji pegawai dari tabel `pegawai` dengan menghitung jumlah pegawai, total gaji, rata-rata gaji, gaji tertinggi, dan gaji terendah. Hasilnya menampilkan lima nilai agregat yang memberikan gambaran menyeluruh mengenai distribusi gaji dalam tabel.
**Contoh Program :**
~~~sql
SELECT COUNT(NIP) AS JumlahPegawai, SUM(Gaji) AS TotalGaji,
	-> AVG(Gaji) AS RataGaji, MAX(Gaji) AS GajiMaks, MIN(Gaji) AS GajiMin
	-> FROM pegawai ;
~~~
**Hasilnya :**
![](aset/basdat17.jpg)

**Analisisnya :**
**`SELECT COUNT(NIP) AS JumlahPegawai`**:
`COUNT(NIP)` menghitung jumlah pegawai berdasarkan kolom `NIP`, yang berfungsi sebagai identifikasi unik pegawai. Alias `JumlahPegawai` menampilkan hasil hitungan ini.
**`SUM(Gaji) AS TotalGaji`**:
`SUM(Gaji)` menghitung total semua gaji pegawai yang ada di tabel. Alias `TotalGaji` memberikan label pada hasil penjumlahan ini.
**`AVG(Gaji) AS RataGaji`**:
`AVG(Gaji)` menghitung rata-rata gaji pegawai di tabel. Alias `RataGaji` menunjukkan nilai rata-rata ini.
**`MAX(Gaji) AS GajiMaks`**:
`MAX(Gaji)` mencari nilai gaji tertinggi di antara semua pegawai. Alias `GajiMaks` menandai gaji tertinggi tersebut.
**`MIN(Gaji) AS GajiMin`**:
 `MIN(Gaji)` mencari nilai gaji terendah di antara semua pegawai. Alias `GajiMin` menunjukkan gaji terendah ini.
**`FROM pegawai`**:
`FROM` menentukan tabel yang digunakan, yaitu `pegawai`.

**Kesimpulannya :**
Query ini memberikan ringkasan lengkap tentang data gaji pegawai, termasuk jumlah pegawai, total gaji, rata-rata gaji, gaji tertinggi, dan gaji terendah. Ini memberikan gambaran menyeluruh tentang distribusi gaji dalam tabel `pegawai`.

# 18
**Penjelasannya :**
Query ini menghitung jumlah, total, rata-rata, gaji tertinggi, dan terendah pegawai dengan jabatan 'Staf' atau 'Sales' untuk setiap cabang, tetapi hanya untuk cabang yang total gajinya tidak melebihi 2.600.000. Data dikelompokkan berdasarkan nomor cabang (`NoCab`) dan hanya cabang yang memenuhi batas gaji ini yang ditampilkan.
**Contoh Program :**
~~~sql
SELECT COUNT(NIP) AS JumlahPegawai, SUM(Gaji) AS TotalGaji,
	-> AVG(Gaji) AS RataGaji, MAX(Gaji) AS GajiMaks, MIN(Gaji) AS GajiMin
	-> FROM pegawai
	-> WHERE Jabatan = 'Staf' OR jabatan = 'Sales'
	-> GROUP BY Nocab HAVING SUM(Gaji) <= 2600000;
~~~
**Hasilnya :**
![](aset/basdat18.jpg)

**Analisisnya :**
**`SELECT COUNT(NIP) AS JumlahPegawai, SUM(Gaji) AS TotalGaji, AVG(Gaji) AS RataGaji, MAX(Gaji) AS GajiMaks, MIN(Gaji) AS GajiMin`**:
`COUNT(NIP) AS JumlahPegawai`: Menghitung jumlah pegawai dengan jabatan 'Staf' atau 'Sales' untuk setiap cabang.
`SUM(Gaji) AS TotalGaji`: Menghitung total gaji pegawai dengan jabatan 'Staf' atau 'Sales' di setiap cabang.
 `AVG(Gaji) AS RataGaji`: Menghitung rata-rata gaji pegawai dengan jabatan 'Staf' atau 'Sales' di setiap cabang.
`MAX(Gaji) AS GajiMaks`: Menentukan gaji tertinggi di antara pegawai dengan jabatan 'Staf' atau 'Sales' di setiap cabang.
`MIN(Gaji) AS GajiMin`: Menentukan gaji terendah di antara pegawai dengan jabatan 'Staf' atau 'Sales' di setiap cabang.
**`FROM pegawai`**: Menunjukkan tabel `pegawai` sebagai sumber data.
- **`WHERE Jabatan = 'Staf' OR Jabatan = 'Sales'`**:
Menyaring data untuk hanya mencakup pegawai dengan jabatan 'Staf' atau 'Sales'.
- **`GROUP BY NoCab`**:
 Mengelompokkan hasil berdasarkan nomor cabang (`NoCab`), sehingga fungsi agregat dihitung untuk setiap cabang.
- **`HAVING SUM(Gaji) <= 2600000`**:
 Menyaring hasil agregat untuk hanya menyertakan cabang di mana total gaji pegawai dengan jabatan 'Staf' atau 'Sales' tidak melebihi 2.600.000.


**Kesimpulannya :**
Query ini memberikan ringkasan data gaji untuk pegawai dengan jabatan 'Staf' atau 'Sales' di setiap cabang yang memenuhi syarat total gaji maksimum. Ini membantu dalam memahami distribusi gaji dan memastikan anggaran gaji tetap dalam batas yang ditetapkan.