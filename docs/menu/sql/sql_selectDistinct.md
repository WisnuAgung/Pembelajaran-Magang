# **SQL Select Distinct**
***

## **A. Penjelasan** 
Pernyataan SELECT DISTINCT digunakan untuk mengembalikan hanya nilai yang berbeda.
Di dalam sebuah tabel, kolom sering berisi banyak nilai duplikat; Dan terkadang Anda hanya ingin membuat daftar perbedaan nilai yang berbeda.
Pernyataan SELECT DISTINCT digunakan untuk mengembalikan hanya nilai yang berbeda.
***

## **B. Bentuk Syntax Umum**

		SELECT DISTINCT column1, column2, ...
		FROM table_name;
***

## **C. Implementasi** 
* Desaigner Database : 

		Database = db_magang_2
![Screenshot](img/img_selectDistinct/a.png) 

* Soal dan Penyelesaian :

**1. Menampilkan data dengan kolom (nama kabupaten)**

** NOTE : menurut id kecamatan dengan tidak berduplikat**

		SELECT DISTINCT kabupaten.nama as "nama_kabupaten"
		FROM kabupaten , kecamatan
		WHERE kabupaten.id = kecamatan.id_kabupaten;

* Output                                                                                           
![Screenshot](img/img_selectDistinct/a1.png) 

**2. Menghitung total jumlah dengan kolom (nama siswa)** 

**NOTE : dengan tidak berduplikat**

		SELECT COUNT(DISTINCT nama) FROM siswa; 

* Output                                                                                
![Screenshot](img/img_selectDistinct/a2.png) 

**3. Menghitung total jumlah dengan kolom (nama siswa)**

**NOTE : dengan tidak berduplikat memakai Alias**

		SELECT COUNT(DISTINCT nama) AS Distinctsiswa FROM siswa;

* Output                                                                                                
![Screenshot](img/img_selectDistinct/a3.png) 
