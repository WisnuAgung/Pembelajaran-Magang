# SQL Left Join dan Right Join
***

##### (Selasa, 11-04-2017) Case 3
## A. Membuat SQL Join Tabel konsep Left Join dan Right Join (Berdasarkan case yang diberikan)
#### a) Contoh Database

		person
		- id
		- name

		phonenumber
		- id
		- id_person
		- number

		person
		P01 - yondi
		P02 - eko

		phoneNumber
		1 - P01 - 093182739
		2 - P01 - 843873874
		3 - NULL – 02100000
		4 – P02 - NULL		

#### b) Case 3 : Membuat SQL Join Tabel konsep Left Join dan Right Join berdasarkan case
1. Tampilkan nama orang yang tidak memiliki nomer telepon

		SELECT person.nama phoneNumber.number
		FROM phonenumber LEFT JOIN person 
		ON person.id = phoneNumber.id_person

2. Tampilkan nomer telepon yang tidak memiliki nama

		SELECT person.nama, phoneNumber.number
		FROM phonenumber RIGHT JOIN person 
		ON person.id = phoneNumber.id_person