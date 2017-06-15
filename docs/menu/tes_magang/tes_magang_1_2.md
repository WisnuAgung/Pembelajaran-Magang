# Tes Magang PT. Lintang Kawuryan Malang
***

## A. Tes Magang 1
* Soal

![Screenshot](img/soalTes1_a.png)
![Screenshot](img/soalTes1_b.png)
![Screenshot](img/soalTes1_c.png)
![Screenshot](img/soalTes1_d.png)  

* Penyelesaian

		<?php
		Class NilaiMataKuliah
		{
			var $namaMataKuliah; 
			var $jumlahSKS; 
			var $nilaiAngka;

			public function NilaiMataKuliah($namaMataKuliah, $jumlahSKS, $nilaiAngka)
			{
			$this->namaMataKuliah = strtoupper($namaMataKuliah);
			$this->jumlahSKS = $jumlahSKS;
			$this->nilaiAngka = $nilaiAngka; 
			}
		}

		Class Mahasiswa
		{
			var $nim;
			var $nama;
			var $alamat;
			var $listNilaiMataKuliah = array();

			public function setNim($nim)
			{
				$this->nim = $nim;
			}

			public function setNama($nama)
			{
				$this->nama = $nama;
			}

			public function setAlamat($alamat)
			{
				$this->alamat = $alamat;
			}

			public function addNilaiMataKuliah($nilaiMataKuliah)
			{
				array_push($this->listNilaiMataKuliah, $nilaiMataKuliah);
			}

			public function getNim()
			{
				return $this->nim;
			}

			public function getNama()
			{
				return $this->nama;
			}

			public function getAlamat()
			{
				return $this->alamat;
			}

			public function showListNilaiMataKuliah()
			{
				sort($this->listNilaiMataKuliah); $no = 1; $totalSKS = 0;
				echo "Hasil Nilai Matakuliah :
		
			>-----------------------------------------------------------<
			No.	Nama Matkul		SKS	Nilai Angka
			>-----------------------------------------------------------<";
		
			foreach ($this->listNilaiMataKuliah as $key => $value){
				echo "\n ";
				echo "";
				echo "$no";
				echo "	";
				echo "$value->namaMataKuliah";
				echo "		";
				echo "$value->jumlahSKS";
				echo "	";
				echo "$value->nilaiAngka";
				echo "\n";
				$totalSKS += $value->jumlahSKS;$no++;}

				echo ">-----------------------------------------------------------<";
				echo "\nTotal SKS		: " . $totalSKS;}
		}

		$mhs = new Mahasiswa();
		$mhs->setNim("07410100271");
		$mhs->setNama("Yondi Tri Hardianto");
		$mhs->setAlamat("Nganjuk, Jawa Timur");

		$mhs->addNilaiMataKuliah(new NilaiMataKuliah("Pemrograman OOP", 3, 73));
		$mhs->addNilaiMataKuliah(new NilaiMataKuliah("pemrograman GUI", 2, 60));
		$mhs->addNilaiMataKuliah(new NilaiMataKuliah("database", 3, 70));
		$mhs->addNilaiMataKuliah(new NilaiMataKuliah("web desain", 2, 80));
		$mhs->addNilaiMataKuliah(new NilaiMataKuliah("basis data", 3, 40));
		$mhs->addNilaiMataKuliah(new NilaiMataKuliah("algoritma", 3, 75));
		$mhs->addNilaiMataKuliah(new NilaiMataKuliah("jaringan", 2, 68));
		$mhs->addNilaiMataKuliah(new NilaiMataKuliah("analiSA BisNIS", 3, 71));
		$mhs->addNilaiMataKuliah(new NilaiMataKuliah("StrukTUR DATA", 3, 98));

		echo "\n";
		echo "\nNim    : " . $mhs->getNim();
		echo "\nNama   : " . $mhs->getNama();
		echo "\nAlamat : " . $mhs->getAlamat();
		echo "\n";
		echo "\n";
		echo $mhs->showListNilaiMataKuliah(); 
		?>

	* Output

Dijalankan menggunakan `Command Prompt`
![Screenshot](img/jawabanTes1.png)
***

## B. Tes Magang 2

* Soal

	a. Buatlah Relasi Database                                                    
![Screenshot](img/soalTes2_a.png) 

	b. Tampilkan nama provinsi, nama kabupaten, jumlah penduduk menurut nama kabupaten
![Screenshot](img/soalTes2_b.png) 

	c. Tampilkan nama provinsi, jumlah penduduk menurut id provinsi                               
![Screenshot](img/soalTes2_c.png) 

* Penyelesaian

	a. Relasi Database                                    
![Screenshot](img/jawabanTes2_a.png) 

	b. Menampilkan nama provinsi, nama kabupaten, jumlah penduduk menurut nama kabupaten

			SELECT provinsi.nama_provinsi, Kabupaten.nama_kabupaten, kabupaten.jumlah_penduduk 
			FROM provinsi INNER JOIN kabupaten 
			ON provinsi.id_provinsi=kabupaten.id_provinsi	
			
	* Output                                       
	![Screenshot](img/jawabanTes2_b.png)

	c. Menampilkan nama provinsi, jumlah penduduk menurut id provinsi

			SELECT provinsi.nama_provinsi, SUM(kabupaten.jumlah_penduduk) AS 'Total' 
			FROM provinsi INNER JOIN kabupaten 
			ON provinsi.id_provinsi = kabupaten.id_provinsi GROUP BY provinsi.id_provinsi

	* Output                     
	![Screenshot](img/jawabanTes2_c.png)