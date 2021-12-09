#### Materi Python for Data Professional Beginner Part 3


<p align="justify"><b>Apa itu Object Oriented Programming?</b></br>
Pemrograman Berbasis Objek (Object Oriented Programming - OOP) merupakan salah satu paradigma pemrograman yang cukup populer di antara paradigma-paradigma lainnya.
</br>
Pada paradigma OOP, struktur dari sebuah program dikemas ke dalam sebuah objek yang memiliki serangkaian properti (properties) dan fungsi (behaviours). Sebagai contoh, aku dapat merepresentasikan seorang karyawan ke dalam sebuah program melalui konsep OOP.
</br>
Seorang karyawan dapat memiliki serangkaian properti seperti nama, usia, keahlian, dll. Kemudian, seorang karyawan juga dapat memiliki fungsi-fungsi seperti hadir ke kantor, absen, lembur, tugas dinas, dll.
</br></br>
<b>Konsep dalam Object Oriented Programming</b></br>
Sebagai salah satu bahasa pemrograman yang bersifat multi-purposive, Python juga mendukung paradigma Object Oriented (OO).
Konsep OO pada Python memiliki tujuan untuk menciptakan potongan-potongan kode yang bersifat reusable dan tidak redundan. Konsep ini dikenal dengan istilah konsep DRY - Don’t Repeat Yourself (berlawanan dengan konsep WET - Write Everything Twice).</p>
</br>
Dalam bahasa pemrograman Python, terdapat 3 konsep utama OO yaitu.
<ol align="justify">
<li>Encapsulation: Menyembunyikan sebagian detail yang dimiliki oleh sebuah objek terhadap objek-objek lainnya.</li>
<li>Inheritance: Menurunkan serangkaian fungsi-fungsi yang dimiliki oleh sebuah objek ke sebuah objek baru tanpa mengubah makna dari objek acuan yang digunakan.</li>
<li>Polymorphism: Konsep untuk menggunakan fungsi-fungsi dengan nama/ tujuan yang sama dengan cara yang berbeda.</li></ol>
<p></p>
Agar dapat membuat class Karyawan dengan baik, pertama, aku akan mempelajari cara merepresentasikan atribut/properti dalam sebuah class.  Dalam sebuah class, aku dapat mendefinisikan dua jenis atribut yaitu :
<ol align="justify"><li>Class Attribute adalah properti/atribut yang bernilai sama untuk oleh seluruh objek dari sebuah</li>
<li>Instance Attribute adalah properti/atribut yang nilainya berbeda-beda untuk setiap objek dari sebuah class.</li></ol>
 

----
#### Class dan Objek dalam Python - Part 3  

Berkaitan dengan kedua jenis atribut yang telah aku pelajari, aku menggunakan contoh berikut untuk memperkuat pemahamanky terkait dengan konsep class attribute.
```plantuml
#Definisikan Class Karyawan 	
class Karyawan:		
  nama_perusahaan = 'ABC'
#Inisiasi object yang dinyatakan dalam variabel aksara dan senja
aksara = Karyawan()
senja = Karyawan()
#Cetak nama perusahaan melalui penggunaan keyword __class__
#pada class attribute nama_perusahaan
print(aksara.__class__.nama_perusahaan)
# Ubah nama_perusahaan menjadi 'DEF'
aksara.__class__.nama_perusahaan = 'DEF'
#Cetak nama_perusahaan objek aksara dan senja
print(aksara.__class__.nama_perusahaan)
print(senja.__class__.nama_perusahaan)
```

<details>
<summary markdown="span">Output :</summary>
ABC </br>
DEF</br>
DEF	
</details>
</br>
<a href="https://academy.dqlab.id/main/livecode/161/301/1354">Link materi : academy.dqlab.id/main/livecode/161/301/1354</a>.

----


### Class dan Objek dalam Python - Part 4 
Atribut nama, usia dan pendapatan merupakan contoh dari instance variabel. Sebagai tambahan, fungsi __init__() di dalam class Karyawan secara khusus disebut sebagai constructor. Melalui sebuah constructor, aku dapat meng-assign (menginisialisasi) atribut-atribut milik sebuah objek. Pada bahasa pemrograman Python, setiap fungsi (termasuk constructor) akan menerima dirinya sendiri (self) sebagai parameter pertama dari fungsi. Kemudian, aku dapat menambahkan parameter-parameter lain setelah parameter self sesuai dengan kebutuhan. Seperti pada contoh di atas, saat objek dibuat (diinisialisasi), aku dapat melemparkan nama, usia dan pendapatan melalui syntax,Terakhir, aku belajar bahwa objek aksara dan senja diizinkan untuk memiliki nama, usia dan pendapatan yang berbeda. Untuk mengakses instance attribute dalam sebuah class, aku perlu menuliskan sintaks self diikuti dengan tanda titik (.) sebelum nama atribut.
```plantuml
#Definisikan class Karyawan
class Karyawan:
    nama_perusahaan = 'ABC'
    def __init__(self, nama, usia, pendapatan):
        self.nama = nama
        self.usia = usia
        self.pendapatan = pendapatan
#Buat object bernama aksara dan senja
aksara = Karyawan('Aksara', 25, 8500000)
senja = Karyawan('Senja', 28, 12500000)
#Cetak objek bernama aksara
print(aksara.nama + ', Usia: ' + str(aksara.usia) + ', Pendapatan ' + str(aksara.pendapatan))
#Cetak objek bernama senja
print(senja.nama + ', Usia: ' + str(senja.usia) + ', Pendapatan ' + str(senja.pendapatan))
```
<details>
<summary markdown="span">Output :</summary>
Aksara, Usia: 25, Pendapatan 8500000</br>
Senja, Usia: 28, Pendapatan 12500000	
</details>
</br>
<a href="https://academy.dqlab.id/main/livecode/161/301/1355">Link materi : academy.dqlab.id/main/livecode/161/301/1355</a>

----


### Behavior pada Class 
Selain dapat mendefinisikan atribut, dalam sebuah class, aku diperbolehkan untuk mendefinisikan fungsi-fungsi (behavior) dari sebuah class.

Dari potongan kode yang telah aku gunakan, aku dapat menambahkan fungsi-fungsi berkaitan dengan class Karyawan. Sebagai contoh, seorang karyawan tentunya mungkin saja memiliki pendapatan tambahan berdasarkan banyaknya kerja lembur dan jumlah proyek yang telah diselesaikan. Untuk menghitung pendapatan tambahan dari jumlah kerja lembur  dan jumlah proyek yang diselesaikan oleh seorang karyawan dan mengakses pendapatan total dari seorang karyawan, aku dapat menuliskan potongan kode berikut.
```plantuml
#Definisikan class Karyawan berikut dengan attribut dan fungsinya
class Karyawan:
    nama_perusahaan = 'ABC'
    insentif_lembur = 250000
    def __init__(self, nama, usia, pendapatan):
        self.nama = nama
        self.usia = usia
        self.pendapatan = pendapatan
        self.pendapatan_tambahan = 0
    def lembur(self):
        self.pendapatan_tambahan += self.insentif_lembur
    def tambahan_proyek(self, insentif_proyek):
    	self.pendapatan_tambahan += insentif_proyek
    def total_pendapatan(self):
    	return self.pendapatan + self.pendapatan_tambahan
#Buat object dari karwayan bernama Aksara dan Senja
aksara = Karyawan('Aksara', 25, 8500000)
senja = Karyawan('Senja', 28, 12500000)
#Aksara melaksanakan lembur
aksara.lembur()
#Senja memiliki proyek tambahan
senja.tambahan_proyek(2500000)
# Cetak pendapatan total Aksara dan Senja
print('Pendapatan Total Aksara: ' + str(aksara.total_pendapatan()))
print('Pendapatan Total Senja: ' +str(senja.total_pendapatan()))
```
<details>
<summary markdown="span">Output :</summary>
Pendapatan Total Aksara: 8750000</br>
Pendapatan Total Senja: 15000000	
</details>
</br>
<a href="https://academy.dqlab.id/main/livecode/161/301/1358">Link materi : academy.dqlab.id/main/livecode/161/301/1358</a>

----


### Tugas Praktek 

```plantuml
#Definisikan class Karyawan
class Karyawan:
    def __init__(self, nama, usia, pendapatan, insentif_lembur): 
        self.nama = nama
        self.usia = usia
        self.pendapatan = pendapatan 
        self.pendapatan_tambahan = 0
        self.insentif_lembur = insentif_lembur
    def lembur(self):
        self.pendapatan_tambahan += self.insentif_lembur 
    def tambahan_proyek(self, jumlah_tambahan):
        self.pendapatan_tambahan += jumlah_tambahan 
    def total_pendapatan(self):
        return self.pendapatan + self.pendapatan_tambahan
#Definisikan class Perusahaan
class Perusahaan:
    def __init__(self, nama, alamat, nomor_telepon): 
        self.nama = nama
        self.alamat = alamat 
        self.nomor_telepon = nomor_telepon
        self.list_karyawan = []
    def aktifkan_karyawan(self, karyawan): 
        self.list_karyawan.append(karyawan)
    def nonaktifkan_karyawan(self, nama_karyawan): 
        karyawan_nonaktif = None
        for karyawan in self.list_karyawan:
            if karyawan.nama == nama_karyawan: 
                karyawan_nonaktif = karyawan 
                break
        if karyawan_nonaktif is not None: 
            self.list_karyawan.remove(karyawan_nonaktif)
```
</br>
<a href="https://academy.dqlab.id/main/livecode/161/301/1359">Link materi : academy.dqlab.id/main/livecode/161/301/1359</a>

----

### Tugas Praktek


```plantuml
#Definisikan perusahaan
perusahaan = Perusahaan('ABC', 'Jl. Jendral Sudirman, Blok 11', '(021) 95205XX')
#Definisikan nama-nama karyawan
karyawan_1 = Karyawan('Ani', 25, 8500000, 100000)
karyawan_2 = Karyawan('Budi', 28, 12000000, 150000)
karyawan_3 = Karyawan('Cici', 30, 15000000, 200000)
#Aktifkan karyawan di perusahaan ABC
perusahaan.aktifkan_karyawan(karyawan_1)
perusahaan.aktifkan_karyawan(karyawan_2)
perusahaan.aktifkan_karyawan(karyawan_3)
```

</br>
<a href="https://academy.dqlab.id/main/livecode/161/301/1360">Link materi : academy.dqlab.id/main/livecode/161/301/1360</a>

----

### Encapsulation pada Python - Part 2

Terdapat 2 macam access modifier dalam Python, yakni :
<ol><li> Public access: dapat aku definisikan dengan secara langsung menuliskan nama dari atribut/ fungsi. Dalam sebuah objek, atribut/fungsi yang bersifat public access dapat diakses di luar scope sebuah class</li> 
<li> Private access: dapat aku definisikan dengan menambahkan double underscore (__) sebelum menuliskan nama dari atribut/fungsi. Dalam sebuah objek, atribut/fungsi yang bersifat private access hanya dapat diakses di dalam scope sebuah class.</li> </ol>
<p>Kemudian, atribut __nama, __usia, __pendapatan_tambahan, __insentif_lembur dan pendapatan bersifat private sehingga atribut ini hanya dapat diakses di dalam scope class Karyawan.

Saat aku mencoba mengakses atribut-atribut ini di luar scope class Karyawan, Python akan mengembalikan error yang menyatakan bahwa class Karyawan tidak memiliki atribut tersebut.</p>

```plantuml
#Definisikan class Karyawan
class Karyawan: 
    nama_perusahaan = 'ABC' 
    __insentif_lembur = 250000
    def __init__(self, nama, usia, pendapatan): 
        self.__nama = nama
        self.__usia = usia 
        self.__pendapatan = pendapatan 
        self.__pendapatan_tambahan = 0
    def lembur(self):
        self.__pendapatan_tambahan += self.__insentif_lembur 
    def tambahan_proyek(self, insentif_proyek):
        self.__pendapatan_tambahan +=insentif_proyek 
    def total_pendapatan(self):
        return self.__pendapatan + self.__pendapatan_tambahan
#Buat objek karyawan bernama Aksara
aksara = Karyawan('Aksara', 25, 8500000)
#Akses ke attribute class Karyawan
print(aksara.__class__.Karyawan)
#Akan menimbulkan error ketika di run
print(aksara.nama)
```
<details>
<summary markdown="span">Output :</summary>
AttributeError                            Traceback (most recent call last)</br>
<ipython-input-6-fcf12fb9db71> in <module></br>
     17 aksara = Karyawan('Aksara', 25, 8500000)</br>
     18 # Akses ke attribute class Karyawan</br>
---> 19 print(aksara.__class__.Karyawan)</br>
     20 # Akan menimbulkan error ketika di run</br>
     21 print(aksara.nama)</br>

AttributeError: type object 'Karyawan' has no attribute 'Karyawan'	
</details>
</br>
<a href="https://academy.dqlab.id/main/livecode/161/301/1362">Link materi : academy.dqlab.id/main/livecode/161/301/1362</a>

----

### Inheritance pada Python – Part 1

Inheritance adalah salah satu mekanisme di konsep OO yang mengizinkan aku untuk mendefinisikan sebuah class baru berdasarkan class yang sebelumnya telah dideklarasikan.

Melalui konsep inheritance, sebuah class baru dapat memiliki atribut dan fungsi pada class yang sebelumnya telah didefinisikan. Pada konsep inheritance, atribut/fungsi yang akan diwariskan hanyalah atribut/fungsi dengan access modifier public, atribut/fungsi dengan access modifier private tidak akan diturunkan.

```plantuml
#Definisikan class Karyawan (sebagai base class)
class Karyawan: 
    nama_perusahaan = 'ABC' 
    insentif_lembur = 250000
    def __init__(self, nama, usia, pendapatan): 
        self.nama = nama
        self.usia = usia 
        self.pendapatan = pendapatan 
        self.pendapatan_tambahan = 0
    def lembur(self):
        self.pendapatan_tambahan += self.insentif_lembur 
    def tambahan_proyek(self, insentif_proyek):
        self.pendapatan_tambahan += insentif_proyek 
    def total_pendapatan(self):
        return self.pendapatan + self.pendapatan_tambahan
#Buat class turunan (sebagai inherit class) dari class karyawan, 
#yaitu class AnalisData
class AnalisData(Karyawan):
    def __init__(self, nama, usia, pendapatan):
    #melakukan pemanggilan konstruktur class Karyawan 
        super().__init__(nama, usia, pendapatan)
#Buat kembali class turunan (sebagai inherit class) dari class karyawan,  
#yaitu class IlmuwanData
class IlmuwanData(Karyawan):
    def __init__(self, nama, usia, pendapatan):
        #melakukan pemanggilan konstruktur class Karyawan 
        super().__init__(nama, usia, pendapatan)
#Buat objek karyawan yang bekerja sebagai AnalisData
aksara = AnalisData('Aksara', 25, 8500000)
aksara.lembur()
print(aksara.total_pendapatan())
#Buat objek karyawan yang bekerja sebagai IlmuwanData
senja = IlmuwanData('Senja', 28, 13000000)
senja.tambahan_proyek(2000000)
print(senja.total_pendapatan())
```
<details>
<summary markdown="span">Output :</summary>
8750000</br>
15000000	
</details>
</br>
<a href="https://academy.dqlab.id/main/livecode/161/301/1365">Link materi : academy.dqlab.id/main/livecode/161/301/1365</a>

----

### Inheritance pada Python – Part 2
child class mewarisi fungsi/atribut dari parent class dengan menggunakan fungsi super(). Melalui konsep inheritance, child class dapat memodifikasi atribut/ fungsi yang diwarisi oleh sebuah parent class dengan mendefinisikan ulang atribut/ fungsi menggunakan nama yang sama. 

```plantuml
#Definisikan class Karyawan (sebagai base class)
class Karyawan: 
    nama_perusahaan = 'ABC' 
    insentif_lembur = 250000
    def __init__(self, nama, usia, pendapatan): 
        self.nama = nama
        self.usia = usia 
        self.pendapatan = pendapatan 
        self.pendapatan_tambahan = 0
    def lembur(self):
        self.pendapatan_tambahan += self.insentif_lembur 
    def tambahan_proyek(self, insentif_proyek):
        self.pendapatan_tambahan += insentif_proyek 
    def total_pendapatan(self):
        return self.pendapatan + self.pendapatan_tambahan
#Buat class turunan (sebagai inherit class) dari class karyawan, 
#yaitu class AnalisData
class AnalisData(Karyawan):
    def __init__(self, nama, usia, pendapatan):
    #melakukan pemanggilan konstruktur class Karyawan 
        super().__init__(nama, usia, pendapatan)
#Buat kembali class turunan (sebagai inherit class) dari class karyawan,  
#yaitu class IlmuwanData
class IlmuwanData(Karyawan):
    # mengubah atribut insentif_lembur yang digunakan pada fungsi lembur()
    insentif_lembur = 500000
    def __init__(self, nama, usia, pendapatan):
        super().__init__(nama, usia, pendapatan)
#Buat objek karyawan yang bekerja sebagai AnalisData
aksara = AnalisData('Aksara', 25, 8500000)
aksara.lembur()
print(aksara.total_pendapatan())
#Buat objek karyawan yang bekerja sebagai IlmuwanData
senja = IlmuwanData('Senja', 28, 13000000)
senja.lembur()
print(senja.total_pendapatan())
```
<details>
<summary markdown="span">Output :</summary>
8750000</br>
13500000	
</details>
</br>
<a href="https://academy.dqlab.id/main/livecode/161/301/1370">Link materi : academy.dqlab.id/main/livecode/161/301/1370</a>

----

### Polymorphism pada Python - Part 1
Selain dapat mendefinisikan ulang nilai dari atribut yang diwarisi oleh parent class seperti pada contoh di atas, juga dapat mendefinisikan ulang fungsi yang telah diwarisi oleh parent class.

Saat mendefinisikan kembali fungsi yang telah diwarisi oleh parent class, secara tidak langsung aku telah menerapkan salah satu mekanisme yang secara khusus pada paradigma OO disebut dengan istilah polymorphism.
Melakukan pemanggilan konstruktur class Karyawan, menerapkan polymorphism dengan mendefinisikan kembali fungsi lembur() pada AnalisData, dan menambahkan 10% atau 0,1 tambahan pendapatan pada class AnalisData.
Fungsi lembur() pada objek aksara sebagai bagian dari class AnalisData akan menambahkan total_pendapatan milik objek sebesar 850000 (10% dari pendapatannya) mengikuti definisi dari fungsi lembur() pada class AnalisData akan menghasilkan output: 9350000.

```plantuml
#Definisikan class Karyawan (sebagai base class)
class Karyawan: 
    nama_perusahaan = 'ABC' 
    insentif_lembur = 250000
    def __init__(self, nama, usia, pendapatan): 
        self.nama = nama
        self.usia = usia 
        self.pendapatan = pendapatan 
        self.pendapatan_tambahan = 0
    def lembur(self):
        self.pendapatan_tambahan += self.insentif_lembur 
    def tambahan_proyek(self, insentif_proyek):
        self.pendapatan_tambahan += insentif_proyek 
    def total_pendapatan(self):
        return self.pendapatan + self.pendapatan_tambahan
#Buat class turunan (sebagai inherit class) dari class karyawan, 
#yaitu class AnalisData
class AnalisData(Karyawan):
    def __init__(self, nama, usia, pendapatan):
    #melakukan pemanggilan konstruktur class Karyawan 
        super().__init__(nama, usia, pendapatan)
    #menerapkan polymorphism dengan mendefinisikan kembali fungsi 
    #lembur() pada class AnalisData 
    def lembur(self):
        #pendapatan tambahan pada class AnalisData sebesar
        #10 % dari pendapatannya.
        self.pendapatan_tambahan += int(self.pendapatan * 0.1)
#Buat objek karyawan yang bekerja sebagai AnalisData
aksara = AnalisData('Aksara', 25, 8500000)
aksara.lembur()
print(aksara.total_pendapatan())
```
<details>
<summary markdown="span">Output :</summary>
9350000	
</details>
</br>
<a href="https://academy.dqlab.id/main/livecode/161/304/1373">Link materi : academy.dqlab.id/main/livecode/161/304/1373</a>.

----

### Polymorphism pada Python - Part 2
Pada konsep inheritance, melalui fungsi super(), selain dapat mengakses constructor milik parent class, child class juga dapat mengakses atribut/fungsi yang dimiliki oleh parent class akan menghasilkan output: 9175000
```plantuml
#Definisikan class Karyawan (sebagai base class)
class Karyawan: 
    nama_perusahaan = 'ABC' 
    insentif_lembur = 250000
    def __init__(self, nama, usia, pendapatan): 
        self.nama = nama
        self.usia = usia 
        self.pendapatan = pendapatan 
        self.pendapatan_tambahan = 0
    def lembur(self):
        self.pendapatan_tambahan += self.insentif_lembur 
    def tambahan_proyek(self, insentif_proyek):
        self.pendapatan_tambahan += insentif_proyek 
    def total_pendapatan(self):
        return self.pendapatan + self.pendapatan_tambahan
#Buat class turunan (sebagai inherit class) dari class karyawan, 
#yaitu class AnalisData
class AnalisData(Karyawan):
    def __init__(self, nama, usia, pendapatan): 
        super().__init__ (nama, usia, pendapatan)
    #mendefinisikan kembali fungsi lembur() pada class AnalisData 
    def lembur(self):
        #memanggil fungsi lembur pada class Karyawan 
        super().lembur()
        #pendapatan tambahan pada class AnalisData sebesar
        #5 % dari pendapatannya.
        self.pendapatan_tambahan += int(self.pendapatan * 0.05)
#Buat objek karyawan yang bekerja sebagai AnalisData
aksara = AnalisData('Aksara', 25, 8500000)
aksara.lembur()
print(aksara.total_pendapatan())
```

</br>
<a href="https://academy.dqlab.id/main/livecode/161/304/1374">Link materi : academy.dqlab.id/main/livecode/161/304/1374</a>

----

### Tugas Praktek

```plantuml
#Definisikan class Karyawan
class Karyawan:
    def __init__(self, nama, usia, pendapatan, insentif_lembur): 
        self.nama = nama
        self.usia = usia 
        self.pendapatan = pendapatan 
        self.pendapatan_tambahan = 0
        self.insentif_lembur = insentif_lembur 
    def lembur(self):
        self.pendapatan_tambahan += self.insentif_lembur 
    def tambahan_proyek(self,jumlah_tambahan):
        self.pendapatan_tambahan += jumlah_tambahan 
    def total_pendapatan(self):
        return self.pendapatan + self.pendapatan_tambahan
#Definisikan class TenagaLepas sebagai child class dari
#class Karyawan
class TenagaLepas(Karyawan):
    def __init__(self, nama, usia, pendapatan):
        super().__init__(nama, usia, pendapatan,0)
    def tambahan_proyek(self, nilai_proyek):
        self.pendapatan_tambahan += nilai_proyek * 0.01
```

</br>
<a href="https://academy.dqlab.id/main/livecode/161/304/1375">Link materi : academy.dqlab.id/main/livecode/161/304/1375</a>

----

### Tugas Praktek

```plantuml
#Definisikan class Karyawan sebagai parent class
class Karyawan:
    def __init__(self, nama, usia, pendapatan, insentif_lembur): 
        self.nama = nama
        self.usia = usia 
        self.pendapatan = pendapatan 
        self.pendapatan_tambahan = 0
        self.insentif_lembur = insentif_lembur 
    def lembur(self):
        self.pendapatan_tambahan += self.insentif_lembur 
    def tambahan_proyek(self,jumlah_tambahan):
        self.pendapatan_tambahan += jumlah_tambahan 
    def total_pendapatan(self):
        return self.pendapatan + self.pendapatan_tambahan
#Definisikan class TenagaLepas sebagai child class dari
#class Karyawan
class TenagaLepas(Karyawan):
    def __init__(self, nama, usia, pendapatan):
        super().__init__(nama, usia, pendapatan, 0)
    def tambahan_proyek(self, nilai_proyek):
        self.pendapatan_tambahan += nilai_proyek * 0.01
#Definisikan class AnalisData sebagai child class dari
#class Karyawan
class AnalisData(Karyawan):
	pass
#Definisikan class IlmuwanData sebagai child class dari
#class Karyawan
class IlmuwanData(Karyawan):
    def tambahan_proyek(self, nilai_proyek): 
        self.pendapatan_tambahan += 0.1 * nilai_proyek
#Definisikan class PembersihData sebagai child class dari
#class TenagaLepas
class PembersihData(TenagaLepas):
	pass
#Definisikan class DokumenterTeknis sebagai child class dari
#class TenagaLepas
class DokumenterTeknis(TenagaLepas):
    def tambahan_proyek(self, jumlah_tambahan): 
        return
```
</br>
<a href="https://academy.dqlab.id/main/livecode/161/304/1376">Link materi : academy.dqlab.id/main/livecode/161/304/1376</a>.

----

### Tugas Praktek

| Nama | Usia | Pendapatan |
| :--- |:---: |      :---: |   
| Budi | ? | ? |
| Didi | 25 | ? |  
| Hadi | ? | 8000000 | 



Aku di minta untuk mengisi tabel, dengan detail berikut:
</br>Budi berusia = 21 dan pendapatan = 5000000
</br>Didi berusia 25 dan pendapatan = 5000000
</br>Hadi berusia 21 dan pendapatan = 8000000
```plantuml
class Karyawan: 
    nama_perusahaan = 'ABC' 
    insentif_lembur = 250000
    #usia akan di-set nilainya menjadi 21 saat tidak
    #dispesifikasikan dan pendapatan akan di-set nilainya
    #menjadi 5000000 saat tidak dispesifikasikan
    def __init__(self, nama, usia=21, pendapatan=5000000): 
        self.nama = nama
        self.usia = usia 
        self.pendapatan = pendapatan 
        self.pendapatan_tambahan = 0
    def lembur(self):
        self.pendapatan_tambahan += self.insentif_lembur 
    def tambahan_proyek(self, insentif_proyek):
        self.pendapatan_tambahan += insentif_proyek 
    def total_pendapatan(self):
        return self.pendapatan + self.pendapatan_tambahan
#Karyawan baru pertama yang bernama Budi
karyawan_baru1 = Karyawan('Budi')
print(karyawan_baru1.nama)
print(karyawan_baru1.usia)
print(karyawan_baru1.total_pendapatan())
#Karyawan baru ke-2 yang bernama Didi, umur 25
karyawan_baru2 = Karyawan('Didi', 25)
print(karyawan_baru2.nama)
print(karyawan_baru2.usia)
print(karyawan_baru2.total_pendapatan())
#Karyawan baru ke-3 yang bernama Hadi, pendapatan 8000000
karyawan_baru3 = Karyawan('Hadi', pendapatan=8000000)
print(karyawan_baru3.nama)
print(karyawan_baru3.usia)
print(karyawan_baru3.total_pendapatan())
```
<details>
<summary markdown="span">Output :</summary>
Budi</br>
21</br>
5000000</br>
Didi</br>
25</br>
5000000</br>
Hadi</br>
21</br>
8000000	
</details>
</br>
<a href="https://academy.dqlab.id/main/livecode/161/304/1378">Link materi : academy.dqlab.id/main/livecode/161/304/1378</a>

----

### Studi Kasus dari Senja
Di perusahaan ini, seorang analis data yang masuk umumnya berusia 21, memiliki pendapatan senilai 6.500.000 dan insentif lembur senilai 100.000. Kemudian, untuk seorang ilmuwan data yang masuk umumnya berusia 25, memiliki pendapatan senilai 12.000.000, dan insentif lembur senilai 150.000. Di sisi lain, untuk tenaga lepas, hanya terdapat pendapatan umum senilai 4000000 untuk pembersih data dan 2500000 untuk dokumenter teknis. 

| Nama | Usia | Pekerjaan        |Pendapatan|
| :--- |:---: |       :--- 	 |   :---:  |
| Ani  | 25   | Pembersih Data   |    -     |
| Budi | 18   | Dokumenter Teknis|    -     |
| Cici | -    | Ilmuwan Data     |    -     |
| Didi | 32   | Ilmuwan Data     | 20000000 |
| Efi  | -    | Analis Data      |    -     |
| Febi | 28   | Analis Data      | 12000000 |

Note: saat usia/pendapatan kosong maka usia/pendapatan mengikuti standar perusahaan.

“Dengan kasus ini, berarti di akhir aku harus mencetak total pengeluaran perusahaan untuk menguji kelancaranku dalam menerapkan OOP dengan Python nih,” gumamku sambil berkutat pada baris-baris code di code editor.

```plantuml
#Definisikan class Karyawan sebagai parent class
class Karyawan:
    def __init__(self, nama, usia, pendapatan, insentif_lembur):
        self.nama = nama
        self.usia = usia 
        self.pendapatan = pendapatan 
        self.pendapatan_tambahan = 0
        self.insentif_lembur = insentif_lembur 
    def lembur(self):
        self.pendapatan_tambahan += self.insentif_lembur
    def tambahan_proyek(self,jumlah_tambahan):
        self.pendapatan_tambahan += jumlah_tambahan 
    def total_pendapatan(self):
        return self.pendapatan + self.pendapatan_tambahan 

#Definisikan class TenagaLepas sebagai child class dari class Karyawan 
class TenagaLepas(Karyawan):
    def __init__(self, nama, usia, pendapatan): 
        super().__init__(nama, usia, pendapatan, 0)
    def tambahan_proyek(self, nilai_proyek): 
        self.pendapatan_tambahan += nilai_proyek  * 0.01
#Definisikan class AnalisData sebagai child class dari class Karyawan 
class AnalisData(Karyawan):
    def __init__(self, nama, usia = 21, pendapatan = 6500000,
				 insentif_lembur = 100000):
        super().__init__(nama, usia, pendapatan, insentif_lembur)
#Definisikan class IlmuwanData sebagai child class dari class Karyawan
class IlmuwanData(Karyawan):
    def __init__(self, nama, usia = 25, pendapatan = 12000000,
				 insentif_lembur = 150000):
        super().__init__(nama, usia, pendapatan,insentif_lembur)
    def tambahan_proyek(self, nilai_proyek):
        self.pendapatan_tambahan += 0.1 * nilai_proyek
#Definisikan class PembersihData sebagai child class dari class TenagaLepas
class PembersihData(TenagaLepas):
    def __init__(self, nama, usia, pendapatan = 4000000):
        super().__init__(nama, usia, pendapatan)
#Definisikan class DokumenterTeknis sebagai child class dari class TenagaLepas
class DokumenterTeknis(TenagaLepas):
    def __init__(self, nama, usia, pendapatan = 2500000):
        super().__init__(nama, usia, pendapatan)
        def tambahan_proyek(self, jumlah_tambahan):
            return
#Definisikan class Perusahaan 
class Perusahaan:
    def __init__(self, nama, alamat, nomor_telepon):
        self.nama = nama
        self.alamat = alamat
        self.nomor_telepon = nomor_telepon
        self.list_karyawan = []
    def aktifkan_karyawan(self, karyawan): 
        self.list_karyawan.append(karyawan)
    def nonaktifkan_karyawan(self, nama_karyawan): 
        karyawan_nonaktif = None
        for karyawan in self.list_karyawan:
            if karyawan.nama == nama_karyawan: 
                karyawan_nonaktif = karyawan 
                break
        if karyawan_nonaktif is not None: 
            self.list_karyawan.remove(karyawan_nonaktif)
    def total_pengeluaran(self): 
        pengeluaran = 0
        for karyawan in self.list_karyawan:
            pengeluaran += karyawan.total_pendapatan() 
        return pengeluaran
    def cari_karyawan(self, nama_karyawan): 
        for karyawan in self.list_karyawan:
            if karyawan.nama == nama_karyawan: 
                return karyawan
        return None
#Create object karyawan sesuai dengan tugasnya masing-masing
#seperti yang dinyatakan dalam tabel.
ani = PembersihData('Ani', 25)
budi = DokumenterTeknis('Budi', 18)
cici = IlmuwanData('Cici')
didi = IlmuwanData('Didi', 32, 20000000)
efi = AnalisData('Efi')
febi = AnalisData('Febi', 28, 12000000)
#Create object perusahaan
perusahaan = Perusahaan('ABC','Jl. Jendral Sudirman, Blok 11', '(021) 95812XX')
#Aktifkan setiap karyawan yang telah didefinisikan
perusahaan.aktifkan_karyawan(ani)
perusahaan.aktifkan_karyawan(budi)
perusahaan.aktifkan_karyawan(cici)
perusahaan.aktifkan_karyawan(didi)
perusahaan.aktifkan_karyawan(efi)
perusahaan.aktifkan_karyawan(febi)
#Cetak keseluruhan total pengeluaran perusahaan
print(perusahaan.total_pengeluaran())
```

<details>
<summary markdown="span">Output :</summary>
57000000	
</details>
</br>
<a href="https://academy.dqlab.id/main/livecode/161/305/1380">Link materi : academy.dqlab.id/main/livecode/161/305/1380</a>

----

<p align="center"><b>E-Sertifikat </b></br></p>

![44d4ca105e5f446a87fa0507d4876ac0-0001](https://user-images.githubusercontent.com/81500429/145325785-df971954-c306-4dd9-86c2-640c2825b5a1.jpg)
</br>
<p align="center"></br>Catatan Kaki &copy; Yenni Syafitri</p>
