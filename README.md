{
 "metadata": {
  "language_info": {
   "codemirror_mode": {
    "name": "ipython",
    "version": 3
   },
   "file_extension": ".py",
   "mimetype": "text/x-python",
   "name": "python",
   "nbconvert_exporter": "python",
   "pygments_lexer": "ipython3",
   "version": "3.7.9-final"
  },
  "orig_nbformat": 2,
  "kernelspec": {
   "name": "python3",
   "display_name": "Python 3",
   "language": "python"
  }
 },
 "nbformat": 4,
 "nbformat_minor": 2,
 "cells": [
  {
   "source": [
    "# [Class dan Objek dalam Python - Part 3](https://academy.dqlab.id/main/livecode/161/301/1354)"
   ],
   "cell_type": "markdown",
   "metadata": {}
  },
  {
   "cell_type": "code",
   "execution_count": 1,
   "metadata": {},
   "outputs": [
    {
     "output_type": "stream",
     "name": "stdout",
     "text": [
      "ABC\nDEF\nDEF\n"
     ]
    }
   ],
   "source": [
    "# Definisikan class Karyawan\n",
    "class Karyawan:\n",
    "    nama_perusahaan = 'ABC'\n",
    "# Inisiasi object yang dinyatakan dalam variabel aksara dan senja\n",
    "aksara = Karyawan()\n",
    "senja = Karyawan()\n",
    "# Cetak nama perusahaan melalui penggunaan keyword __class__\n",
    "# pada class attribute nama_perusahaan\n",
    "print(aksara.__class__.nama_perusahaan)\n",
    "# Ubah nama_perusahaan menjadi 'DEF'\n",
    "aksara.__class__.nama_perusahaan = 'DEF'\n",
    "# Cetak nama_perusahaan objek aksara dan senja\n",
    "print(aksara.__class__.nama_perusahaan)\n",
    "print(senja.__class__.nama_perusahaan)"
   ]
  },
  {
   "source": [
    "# [Class dan Objek dalam Python - Part 4](https://academy.dqlab.id/main/livecode/161/301/1355)"
   ],
   "cell_type": "markdown",
   "metadata": {}
  },
  {
   "cell_type": "code",
   "execution_count": 2,
   "metadata": {},
   "outputs": [
    {
     "output_type": "stream",
     "name": "stdout",
     "text": [
      "Aksara, Usia: 25, Pendapatan 8500000\nSenja, Usia: 28, Pendapatan 12500000\n"
     ]
    }
   ],
   "source": [
    "# Definisikan class Karyawan\n",
    "class Karyawan:\n",
    "    nama_perusahaan = 'ABC'\n",
    "    def __init__(self, nama, usia, pendapatan):\n",
    "        self.nama = nama\n",
    "        self.usia = usia\n",
    "        self.pendapatan = pendapatan\n",
    "# Buat object bernama aksara dan senja\n",
    "aksara = Karyawan('Aksara', 25, 8500000)\n",
    "senja = Karyawan('Senja', 28, 12500000)\n",
    "# Cetak objek bernama aksara\n",
    "print(aksara.nama + ', Usia: ' + str(aksara.usia) + ', Pendapatan ' + str(aksara.pendapatan))\n",
    "# Cetak objek bernama senja\n",
    "print(senja.nama + ', Usia: ' + str(senja.usia) + ', Pendapatan ' + str(senja.pendapatan))"
   ]
  },
  {
   "source": [
    "# [Behavior pada Class](https://academy.dqlab.id/main/livecode/161/301/1358)"
   ],
   "cell_type": "markdown",
   "metadata": {}
  },
  {
   "cell_type": "code",
   "execution_count": 3,
   "metadata": {},
   "outputs": [
    {
     "output_type": "stream",
     "name": "stdout",
     "text": [
      "Pendapatan Total Aksara: 8750000\nPendapatan Total Senja: 15000000\n"
     ]
    }
   ],
   "source": [
    "# Definisikan class Karyawan berikut dengan attribut dan fungsinya\n",
    "class Karyawan:\n",
    "    nama_perusahaan = 'ABC'\n",
    "    insentif_lembur = 250000\n",
    "    def __init__(self, nama, usia, pendapatan):\n",
    "        self.nama = nama\n",
    "        self.usia = usia\n",
    "        self.pendapatan = pendapatan\n",
    "        self.pendapatan_tambahan = 0\n",
    "    def lembur(self):\n",
    "        self.pendapatan_tambahan += self.insentif_lembur\n",
    "    def tambahan_proyek(self, insentif_proyek):\n",
    "    \tself.pendapatan_tambahan += insentif_proyek\n",
    "    def total_pendapatan(self):\n",
    "    \treturn self.pendapatan + self.pendapatan_tambahan\n",
    "# Buat object dari karwayan bernama Aksara dan Senja\n",
    "aksara = Karyawan('Aksara', 25, 8500000)\n",
    "senja = Karyawan('Senja', 28, 12500000)\n",
    "# Aksara melaksanakan lembur\n",
    "aksara.lembur()\n",
    "# Senja memiliki proyek tambahan\n",
    "senja.tambahan_proyek(2500000)\n",
    "# Cetak pendapatan total Aksara dan Senja\n",
    "print('Pendapatan Total Aksara: ' + str(aksara.total_pendapatan()))\n",
    "print('Pendapatan Total Senja: ' +str(senja.total_pendapatan()))"
   ]
  },
  {
   "source": [
    "# [Tugas Praktek](https://academy.dqlab.id/main/livecode/161/301/1359)"
   ],
   "cell_type": "markdown",
   "metadata": {}
  },
  {
   "cell_type": "code",
   "execution_count": 4,
   "metadata": {},
   "outputs": [],
   "source": [
    "# Definisikan class Karyawan\n",
    "class Karyawan:\n",
    "    def __init__(self, nama, usia, pendapatan, insentif_lembur): \n",
    "        self.nama = nama\n",
    "        self.usia = usia\n",
    "        self.pendapatan = pendapatan \n",
    "        self.pendapatan_tambahan = 0\n",
    "        self.insentif_lembur = insentif_lembur\n",
    "    def lembur(self):\n",
    "        self.pendapatan_tambahan += self.insentif_lembur \n",
    "    def tambahan_proyek(self, jumlah_tambahan):\n",
    "        self.pendapatan_tambahan += jumlah_tambahan \n",
    "    def total_pendapatan(self):\n",
    "        return self.pendapatan + self.pendapatan_tambahan\n",
    "\n",
    "# Definisikan class Perusahaan\n",
    "class Perusahaan:\n",
    "    def __init__(self, nama, alamat, nomor_telepon): \n",
    "        self.nama = nama\n",
    "        self.alamat = alamat \n",
    "        self.nomor_telepon = nomor_telepon\n",
    "        self.list_karyawan = []\n",
    "    def aktifkan_karyawan(self, karyawan): \n",
    "        self.list_karyawan.append(karyawan)\n",
    "    def nonaktifkan_karyawan(self, nama_karyawan): \n",
    "        karyawan_nonaktif = None\n",
    "        for karyawan in self.list_karyawan:\n",
    "            if karyawan.nama == nama_karyawan: \n",
    "                karyawan_nonaktif = karyawan \n",
    "                break\n",
    "        if karyawan_nonaktif is not None: \n",
    "            self.list_karyawan.remove(karyawan_nonaktif)"
   ]
  },
  {
   "source": [
    "# [Tugas Praktek](https://academy.dqlab.id/main/livecode/161/301/1360)"
   ],
   "cell_type": "markdown",
   "metadata": {}
  },
  {
   "cell_type": "code",
   "execution_count": 5,
   "metadata": {},
   "outputs": [],
   "source": [
    "# Definisikan perusahaan\n",
    "perusahaan = Perusahaan('ABC', 'Jl. Jendral Sudirman, Blok 11', '(021) 95205XX')\n",
    "# Definisikan nama-nama karyawan\n",
    "karyawan_1 = Karyawan('Ani', 25, 8500000, 100000)\n",
    "karyawan_2 = Karyawan('Budi', 28, 12000000, 150000)\n",
    "karyawan_3 = Karyawan('Cici', 30, 15000000, 200000)\n",
    "# Aktifkan karyawan di perusahaan ABC\n",
    "perusahaan.aktifkan_karyawan(karyawan_1)\n",
    "perusahaan.aktifkan_karyawan(karyawan_2)\n",
    "perusahaan.aktifkan_karyawan(karyawan_3)"
   ]
  },
  {
   "source": [
    "# [Encapsulation pada Python - Part 2](https://academy.dqlab.id/main/livecode/161/302/1362)"
   ],
   "cell_type": "markdown",
   "metadata": {}
  },
  {
   "cell_type": "code",
   "execution_count": 6,
   "metadata": {},
   "outputs": [
    {
     "output_type": "error",
     "ename": "AttributeError",
     "evalue": "type object 'Karyawan' has no attribute 'Karyawan'",
     "traceback": [
      "\u001b[1;31m---------------------------------------------------------------------------\u001b[0m",
      "\u001b[1;31mAttributeError\u001b[0m                            Traceback (most recent call last)",
      "\u001b[1;32m<ipython-input-6-fcf12fb9db71>\u001b[0m in \u001b[0;36m<module>\u001b[1;34m\u001b[0m\n\u001b[0;32m     17\u001b[0m \u001b[0maksara\u001b[0m \u001b[1;33m=\u001b[0m \u001b[0mKaryawan\u001b[0m\u001b[1;33m(\u001b[0m\u001b[1;34m'Aksara'\u001b[0m\u001b[1;33m,\u001b[0m \u001b[1;36m25\u001b[0m\u001b[1;33m,\u001b[0m \u001b[1;36m8500000\u001b[0m\u001b[1;33m)\u001b[0m\u001b[1;33m\u001b[0m\u001b[1;33m\u001b[0m\u001b[0m\n\u001b[0;32m     18\u001b[0m \u001b[1;31m# Akses ke attribute class Karyawan\u001b[0m\u001b[1;33m\u001b[0m\u001b[1;33m\u001b[0m\u001b[1;33m\u001b[0m\u001b[0m\n\u001b[1;32m---> 19\u001b[1;33m \u001b[0mprint\u001b[0m\u001b[1;33m(\u001b[0m\u001b[0maksara\u001b[0m\u001b[1;33m.\u001b[0m\u001b[0m__class__\u001b[0m\u001b[1;33m.\u001b[0m\u001b[0mKaryawan\u001b[0m\u001b[1;33m)\u001b[0m\u001b[1;33m\u001b[0m\u001b[1;33m\u001b[0m\u001b[0m\n\u001b[0m\u001b[0;32m     20\u001b[0m \u001b[1;31m# Akan menimbulkan error ketika di run\u001b[0m\u001b[1;33m\u001b[0m\u001b[1;33m\u001b[0m\u001b[1;33m\u001b[0m\u001b[0m\n\u001b[0;32m     21\u001b[0m \u001b[0mprint\u001b[0m\u001b[1;33m(\u001b[0m\u001b[0maksara\u001b[0m\u001b[1;33m.\u001b[0m\u001b[0mnama\u001b[0m\u001b[1;33m)\u001b[0m\u001b[1;33m\u001b[0m\u001b[1;33m\u001b[0m\u001b[0m\n",
      "\u001b[1;31mAttributeError\u001b[0m: type object 'Karyawan' has no attribute 'Karyawan'"
     ]
    }
   ],
   "source": [
    "# Definisikan class Karyawan\n",
    "class Karyawan: \n",
    "    nama_perusahaan = 'ABC' \n",
    "    __insentif_lembur = 250000\n",
    "    def __init__(self, nama, usia, pendapatan): \n",
    "        self.__nama = nama\n",
    "        self.__usia = usia \n",
    "        self.__pendapatan = pendapatan \n",
    "        self.__pendapatan_tambahan = 0\n",
    "    def lembur(self):\n",
    "        self.__pendapatan_tambahan += self.__insentif_lembur \n",
    "    def tambahan_proyek(self, insentif_proyek):\n",
    "        self.__pendapatan_tambahan +=insentif_proyek \n",
    "    def total_pendapatan(self):\n",
    "        return self.__pendapatan + self.__pendapatan_tambahan\n",
    "# Buat objek karyawan bernama Aksara\n",
    "aksara = Karyawan('Aksara', 25, 8500000)\n",
    "# Akses ke attribute class Karyawan\n",
    "print(aksara.__class__.Karyawan)\n",
    "# Akan menimbulkan error ketika di run\n",
    "print(aksara.nama)"
   ]
  },
  {
   "source": [
    "# [Inheritance pada Python – Part 1](https://academy.dqlab.id/main/livecode/161/302/1365)"
   ],
   "cell_type": "markdown",
   "metadata": {}
  },
  {
   "cell_type": "code",
   "execution_count": 7,
   "metadata": {},
   "outputs": [
    {
     "output_type": "stream",
     "name": "stdout",
     "text": [
      "8750000\n15000000\n"
     ]
    }
   ],
   "source": [
    "# Definisikan class Karyawan (sebagai base class)\n",
    "class Karyawan: \n",
    "    nama_perusahaan = 'ABC' \n",
    "    insentif_lembur = 250000\n",
    "    def __init__(self, nama, usia, pendapatan): \n",
    "        self.nama = nama\n",
    "        self.usia = usia \n",
    "        self.pendapatan = pendapatan \n",
    "        self.pendapatan_tambahan = 0\n",
    "    def lembur(self):\n",
    "        self.pendapatan_tambahan += self.insentif_lembur \n",
    "    def tambahan_proyek(self, insentif_proyek):\n",
    "        self.pendapatan_tambahan += insentif_proyek \n",
    "    def total_pendapatan(self):\n",
    "        return self.pendapatan + self.pendapatan_tambahan\n",
    "# Buat class turunan (sebagai inherit class) dari class karyawan, \n",
    "# yaitu class AnalisData\n",
    "class AnalisData(Karyawan):\n",
    "    def __init__(self, nama, usia, pendapatan):\n",
    "    # melakukan pemanggilan konstruktur class Karyawan \n",
    "        super().__init__(nama, usia, pendapatan)\n",
    "# Buat kembali class turunan (sebagai inherit class) dari class karyawan,  \n",
    "# yaitu class IlmuwanData\n",
    "class IlmuwanData(Karyawan):\n",
    "    def __init__(self, nama, usia, pendapatan):\n",
    "        # melakukan pemanggilan konstruktur class Karyawan \n",
    "        super().__init__(nama, usia, pendapatan)\n",
    "# Buat objek karyawan yang bekerja sebagai AnalisData\n",
    "aksara = AnalisData('Aksara', 25, 8500000)\n",
    "aksara.lembur()\n",
    "print(aksara.total_pendapatan())\n",
    "# Buat objek karyawan yang bekerja sebagai IlmuwanData\n",
    "senja = IlmuwanData('Senja', 28, 13000000)\n",
    "senja.tambahan_proyek(2000000)\n",
    "print(senja.total_pendapatan())"
   ]
  },
  {
   "source": [
    "# [Inheritance pada Python – Part 2](https://academy.dqlab.id/main/livecode/161/302/1370)"
   ],
   "cell_type": "markdown",
   "metadata": {}
  },
  {
   "cell_type": "code",
   "execution_count": 8,
   "metadata": {},
   "outputs": [
    {
     "output_type": "stream",
     "name": "stdout",
     "text": [
      "8750000\n13500000\n"
     ]
    }
   ],
   "source": [
    "# Definisikan class Karyawan (sebagai base class)\n",
    "class Karyawan: \n",
    "    nama_perusahaan = 'ABC' \n",
    "    insentif_lembur = 250000\n",
    "    def __init__(self, nama, usia, pendapatan): \n",
    "        self.nama = nama\n",
    "        self.usia = usia \n",
    "        self.pendapatan = pendapatan \n",
    "        self.pendapatan_tambahan = 0\n",
    "    def lembur(self):\n",
    "        self.pendapatan_tambahan += self.insentif_lembur \n",
    "    def tambahan_proyek(self, insentif_proyek):\n",
    "        self.pendapatan_tambahan += insentif_proyek \n",
    "    def total_pendapatan(self):\n",
    "        return self.pendapatan + self.pendapatan_tambahan\n",
    "# Buat class turunan (sebagai inherit class) dari class karyawan, \n",
    "# yaitu class AnalisData\n",
    "class AnalisData(Karyawan):\n",
    "    def __init__(self, nama, usia, pendapatan):\n",
    "    # melakukan pemanggilan konstruktur class Karyawan \n",
    "        super().__init__(nama, usia, pendapatan)\n",
    "# Buat kembali class turunan (sebagai inherit class) dari class karyawan,  \n",
    "# yaitu class IlmuwanData\n",
    "class IlmuwanData(Karyawan):\n",
    "    # mengubah atribut insentif_lembur yang digunakan pada fungsi lembur()\n",
    "    insentif_lembur = 500000\n",
    "    def __init__(self, nama, usia, pendapatan):\n",
    "        super().__init__(nama, usia, pendapatan)\n",
    "# Buat objek karyawan yang bekerja sebagai AnalisData\n",
    "aksara = AnalisData('Aksara', 25, 8500000)\n",
    "aksara.lembur()\n",
    "print(aksara.total_pendapatan())\n",
    "# Buat objek karyawan yang bekerja sebagai IlmuwanData\n",
    "senja = IlmuwanData('Senja', 28, 13000000)\n",
    "senja.lembur()\n",
    "print(senja.total_pendapatan())"
   ]
  },
  {
   "source": [
    "# [Polymorphism pada Python - Part 1](https://academy.dqlab.id/main/livecode/161/304/1373)"
   ],
   "cell_type": "markdown",
   "metadata": {}
  },
  {
   "cell_type": "code",
   "execution_count": 9,
   "metadata": {},
   "outputs": [
    {
     "output_type": "stream",
     "name": "stdout",
     "text": [
      "9350000\n"
     ]
    }
   ],
   "source": [
    "# Definisikan class Karyawan (sebagai base class)\n",
    "class Karyawan: \n",
    "    nama_perusahaan = 'ABC' \n",
    "    insentif_lembur = 250000\n",
    "    def __init__(self, nama, usia, pendapatan): \n",
    "        self.nama = nama\n",
    "        self.usia = usia \n",
    "        self.pendapatan = pendapatan \n",
    "        self.pendapatan_tambahan = 0\n",
    "    def lembur(self):\n",
    "        self.pendapatan_tambahan += self.insentif_lembur \n",
    "    def tambahan_proyek(self, insentif_proyek):\n",
    "        self.pendapatan_tambahan += insentif_proyek \n",
    "    def total_pendapatan(self):\n",
    "        return self.pendapatan + self.pendapatan_tambahan\n",
    "# Buat class turunan (sebagai inherit class) dari class karyawan, \n",
    "# yaitu class AnalisData\n",
    "class AnalisData(Karyawan):\n",
    "    def __init__(self, nama, usia, pendapatan):\n",
    "    # melakukan pemanggilan konstruktur class Karyawan \n",
    "        super().__init__(nama, usia, pendapatan)\n",
    "    # menerapkan polymorphism dengan mendefinisikan kembali fungsi \n",
    "    # lembur() pada class AnalisData \n",
    "    def lembur(self):\n",
    "        # pendapatan tambahan pada class AnalisData sebesar\n",
    "        # 10 % dari pendapatannya.\n",
    "        self.pendapatan_tambahan += int(self.pendapatan * 0.1)\n",
    "# Buat objek karyawan yang bekerja sebagai AnalisData\n",
    "aksara = AnalisData('Aksara', 25, 8500000)\n",
    "aksara.lembur()\n",
    "print(aksara.total_pendapatan())"
   ]
  },
  {
   "source": [
    "# [Polymorphism pada Python - Part 2](https://academy.dqlab.id/main/livecode/161/304/1374)"
   ],
   "cell_type": "markdown",
   "metadata": {}
  },
  {
   "cell_type": "code",
   "execution_count": 10,
   "metadata": {},
   "outputs": [
    {
     "output_type": "stream",
     "name": "stdout",
     "text": [
      "9175000\n"
     ]
    }
   ],
   "source": [
    "# Definisikan class Karyawan (sebagai base class)\n",
    "class Karyawan: \n",
    "    nama_perusahaan = 'ABC' \n",
    "    insentif_lembur = 250000\n",
    "    def __init__(self, nama, usia, pendapatan): \n",
    "        self.nama = nama\n",
    "        self.usia = usia \n",
    "        self.pendapatan = pendapatan \n",
    "        self.pendapatan_tambahan = 0\n",
    "    def lembur(self):\n",
    "        self.pendapatan_tambahan += self.insentif_lembur \n",
    "    def tambahan_proyek(self, insentif_proyek):\n",
    "        self.pendapatan_tambahan += insentif_proyek \n",
    "    def total_pendapatan(self):\n",
    "        return self.pendapatan + self.pendapatan_tambahan\n",
    "# Buat class turunan (sebagai inherit class) dari class karyawan, \n",
    "# yaitu class AnalisData\n",
    "class AnalisData(Karyawan):\n",
    "    def __init__(self, nama, usia, pendapatan): \n",
    "        super().__init__ (nama, usia, pendapatan)\n",
    "    # mendefinisikan kembali fungsi lembur() pada class AnalisData \n",
    "    def lembur(self):\n",
    "        # memanggil fungsi lembur pada class Karyawan \n",
    "        super().lembur()\n",
    "        # pendapatan tambahan pada class AnalisData sebesar\n",
    "        # 5 % dari pendapatannya.\n",
    "        self.pendapatan_tambahan += int(self.pendapatan * 0.05)\n",
    "# Buat objek karyawan yang bekerja sebagai AnalisData\n",
    "aksara = AnalisData('Aksara', 25, 8500000)\n",
    "aksara.lembur()\n",
    "print(aksara.total_pendapatan())"
   ]
  },
  {
   "source": [
    "# [Tugas Praktek](https://academy.dqlab.id/main/livecode/161/304/1375)"
   ],
   "cell_type": "markdown",
   "metadata": {}
  },
  {
   "cell_type": "code",
   "execution_count": 11,
   "metadata": {},
   "outputs": [],
   "source": [
    "# Definisikan class Karyawan\n",
    "class Karyawan:\n",
    "    def __init__(self, nama, usia, pendapatan, insentif_lembur): \n",
    "        self.nama = nama\n",
    "        self.usia = usia \n",
    "        self.pendapatan = pendapatan \n",
    "        self.pendapatan_tambahan = 0\n",
    "        self.insentif_lembur = insentif_lembur \n",
    "    def lembur(self):\n",
    "        self.pendapatan_tambahan += self.insentif_lembur \n",
    "    def tambahan_proyek(self,jumlah_tambahan):\n",
    "        self.pendapatan_tambahan += jumlah_tambahan \n",
    "    def total_pendapatan(self):\n",
    "        return self.pendapatan + self.pendapatan_tambahan\n",
    "# Definisikan class TenagaLepas sebagai child class dari\n",
    "# class Karyawan\n",
    "class TenagaLepas(Karyawan):\n",
    "    def __init__(self, nama, usia, pendapatan):\n",
    "        super().__init__(nama, usia, pendapatan,0)\n",
    "    def tambahan_proyek(self, nilai_proyek):\n",
    "        self.pendapatan_tambahan += nilai_proyek * 0.01"
   ]
  },
  {
   "source": [
    "# [Tugas Praktek](https://academy.dqlab.id/main/livecode/161/304/1376)"
   ],
   "cell_type": "markdown",
   "metadata": {}
  },
  {
   "cell_type": "code",
   "execution_count": 12,
   "metadata": {},
   "outputs": [],
   "source": [
    "# Definisikan class Karyawan sebagai parent class\n",
    "class Karyawan:\n",
    "    def __init__(self, nama, usia, pendapatan, insentif_lembur): \n",
    "        self.nama = nama\n",
    "        self.usia = usia \n",
    "        self.pendapatan = pendapatan \n",
    "        self.pendapatan_tambahan = 0\n",
    "        self.insentif_lembur = insentif_lembur \n",
    "    def lembur(self):\n",
    "        self.pendapatan_tambahan += self.insentif_lembur \n",
    "    def tambahan_proyek(self,jumlah_tambahan):\n",
    "        self.pendapatan_tambahan += jumlah_tambahan \n",
    "    def total_pendapatan(self):\n",
    "        return self.pendapatan + self.pendapatan_tambahan\n",
    "# Definisikan class TenagaLepas sebagai child class dari\n",
    "# class Karyawan\n",
    "class TenagaLepas(Karyawan):\n",
    "    def __init__(self, nama, usia, pendapatan):\n",
    "        super().__init__(nama, usia, pendapatan, 0)\n",
    "    def tambahan_proyek(self, nilai_proyek):\n",
    "        self.pendapatan_tambahan += nilai_proyek * 0.01\n",
    "# Definisikan class AnalisData sebagai child class dari\n",
    "# class Karyawan\n",
    "class AnalisData(Karyawan):\n",
    "\tpass\n",
    "# Definisikan class IlmuwanData sebagai child class dari\n",
    "# class Karyawan\n",
    "class IlmuwanData(Karyawan):\n",
    "    def tambahan_proyek(self, nilai_proyek): \n",
    "        self.pendapatan_tambahan += 0.1 * nilai_proyek\n",
    "# Definisikan class PembersihData sebagai child class dari\n",
    "# class TenagaLepas\n",
    "class PembersihData(TenagaLepas):\n",
    "\tpass\n",
    "# Definisikan class DokumenterTeknis sebagai child class dari\n",
    "# class TenagaLepas\n",
    "class DokumenterTeknis(TenagaLepas):\n",
    "    def tambahan_proyek(self, jumlah_tambahan): \n",
    "        return"
   ]
  },
  {
   "source": [
    "# [Tugas Praktek](https://academy.dqlab.id/main/livecode/161/304/1378)"
   ],
   "cell_type": "markdown",
   "metadata": {}
  },
  {
   "cell_type": "code",
   "execution_count": 13,
   "metadata": {},
   "outputs": [
    {
     "output_type": "stream",
     "name": "stdout",
     "text": [
      "Budi\n21\n5000000\nDidi\n25\n5000000\nHadi\n21\n8000000\n"
     ]
    }
   ],
   "source": [
    "class Karyawan: \n",
    "    nama_perusahaan = 'ABC' \n",
    "    insentif_lembur = 250000\n",
    "    # usia akan di-set nilainya menjadi 21 saat tidak\n",
    "    # dispesifikasikan dan pendapatan akan di-set nilainya\n",
    "    # menjadi 5000000 saat tidak dispesifikasikan\n",
    "    def __init__(self, nama, usia=21, pendapatan=5000000): \n",
    "        self.nama = nama\n",
    "        self.usia = usia \n",
    "        self.pendapatan = pendapatan \n",
    "        self.pendapatan_tambahan = 0\n",
    "    def lembur(self):\n",
    "        self.pendapatan_tambahan += self.insentif_lembur \n",
    "    def tambahan_proyek(self, insentif_proyek):\n",
    "        self.pendapatan_tambahan += insentif_proyek \n",
    "    def total_pendapatan(self):\n",
    "        return self.pendapatan + self.pendapatan_tambahan\n",
    "# Karyawan baru pertama yang bernama Budi\n",
    "karyawan_baru1 = Karyawan('Budi')\n",
    "print(karyawan_baru1.nama)\n",
    "print(karyawan_baru1.usia)\n",
    "print(karyawan_baru1.total_pendapatan())\n",
    "# Karyawan baru ke-2 yang bernama Didi, umur 25\n",
    "karyawan_baru2 = Karyawan('Didi', 25)\n",
    "print(karyawan_baru2.nama)\n",
    "print(karyawan_baru2.usia)\n",
    "print(karyawan_baru2.total_pendapatan())\n",
    "# Karyawan baru ke-3 yang bernama Hadi, pendapatan 8000000\n",
    "karyawan_baru3 = Karyawan('Hadi', pendapatan=8000000)\n",
    "print(karyawan_baru3.nama)\n",
    "print(karyawan_baru3.usia)\n",
    "print(karyawan_baru3.total_pendapatan())"
   ]
  },
  {
   "source": [
    "# [Studi Kasus dari Senja](https://academy.dqlab.id/main/livecode/161/305/1380)"
   ],
   "cell_type": "markdown",
   "metadata": {}
  },
  {
   "cell_type": "code",
   "execution_count": 14,
   "metadata": {},
   "outputs": [
    {
     "output_type": "stream",
     "name": "stdout",
     "text": [
      "57000000\n"
     ]
    }
   ],
   "source": [
    "# Definisikan class Karyawan sebagai parent class\n",
    "class Karyawan:\n",
    "    def __init__(self, nama, usia, pendapatan, insentif_lembur):\n",
    "        self.nama = nama\n",
    "        self.usia = usia \n",
    "        self.pendapatan = pendapatan \n",
    "        self.pendapatan_tambahan = 0\n",
    "        self.insentif_lembur = insentif_lembur \n",
    "    def lembur(self):\n",
    "        self.pendapatan_tambahan += self.insentif_lembur\n",
    "    def tambahan_proyek(self,jumlah_tambahan):\n",
    "        self.pendapatan_tambahan += jumlah_tambahan \n",
    "    def total_pendapatan(self):\n",
    "        return self.pendapatan + self.pendapatan_tambahan \n",
    "\n",
    "# Definisikan class TenagaLepas sebagai child class dari class Karyawan \n",
    "class TenagaLepas(Karyawan):\n",
    "    def __init__(self, nama, usia, pendapatan): \n",
    "        super().__init__(nama, usia, pendapatan, 0)\n",
    "    def tambahan_proyek(self, nilai_proyek): \n",
    "        self.pendapatan_tambahan += nilai_proyek  * 0.01\n",
    "\n",
    "# Definisikan class AnalisData sebagai child class dari class Karyawan \n",
    "class AnalisData(Karyawan):\n",
    "    def __init__(self, nama, usia = 21, pendapatan = 6500000,\n",
    "\t\t\t\t insentif_lembur = 100000):\n",
    "        super().__init__(nama, usia, pendapatan, insentif_lembur)\n",
    "\n",
    "# Definisikan class IlmuwanData sebagai child class dari class Karyawan\n",
    "class IlmuwanData(Karyawan):\n",
    "    def __init__(self, nama, usia = 25, pendapatan = 12000000,\n",
    "\t\t\t\t insentif_lembur = 150000):\n",
    "        super().__init__(nama, usia, pendapatan,insentif_lembur)\n",
    "    def tambahan_proyek(self, nilai_proyek):\n",
    "        self.pendapatan_tambahan += 0.1 * nilai_proyek\n",
    "\n",
    "# Definisikan class PembersihData sebagai child class dari class TenagaLepas\n",
    "class PembersihData(TenagaLepas):\n",
    "    def __init__(self, nama, usia, pendapatan = 4000000):\n",
    "        super().__init__(nama, usia, pendapatan)\n",
    "\n",
    "# Definisikan class DokumenterTeknis sebagai child class dari class TenagaLepas\n",
    "class DokumenterTeknis(TenagaLepas):\n",
    "    def __init__(self, nama, usia, pendapatan = 2500000):\n",
    "        super().__init__(nama, usia, pendapatan)\n",
    "        def tambahan_proyek(self, jumlah_tambahan):\n",
    "            return\n",
    "\n",
    "# Definisikan class Perusahaan \n",
    "class Perusahaan:\n",
    "    def __init__(self, nama, alamat, nomor_telepon):\n",
    "        self.nama = nama\n",
    "        self.alamat = alamat\n",
    "        self.nomor_telepon = nomor_telepon\n",
    "        self.list_karyawan = []\n",
    "    def aktifkan_karyawan(self, karyawan): \n",
    "        self.list_karyawan.append(karyawan)\n",
    "    def nonaktifkan_karyawan(self, nama_karyawan): \n",
    "        karyawan_nonaktif = None\n",
    "        for karyawan in self.list_karyawan:\n",
    "            if karyawan.nama == nama_karyawan: \n",
    "                karyawan_nonaktif = karyawan \n",
    "                break\n",
    "        if karyawan_nonaktif is not None: \n",
    "            self.list_karyawan.remove(karyawan_nonaktif)\n",
    "    def total_pengeluaran(self): \n",
    "        pengeluaran = 0\n",
    "        for karyawan in self.list_karyawan:\n",
    "            pengeluaran += karyawan.total_pendapatan() \n",
    "        return pengeluaran\n",
    "    def cari_karyawan(self, nama_karyawan): \n",
    "        for karyawan in self.list_karyawan:\n",
    "            if karyawan.nama == nama_karyawan: \n",
    "                return karyawan\n",
    "        return None\n",
    "\n",
    "# Create object karyawan sesuai dengan tugasnya masing-masing\n",
    "# seperti yang dinyatakan dalam tabel.\n",
    "ani = PembersihData('Ani', 25)\n",
    "budi = DokumenterTeknis('Budi', 18)\n",
    "cici = IlmuwanData('Cici')\n",
    "didi = IlmuwanData('Didi', 32, 20000000)\n",
    "efi = AnalisData('Efi')\n",
    "febi = AnalisData('Febi', 28, 12000000)\n",
    "\n",
    "# Create object perusahaan\n",
    "perusahaan = Perusahaan('ABC','Jl. Jendral Sudirman, Blok 11', '(021) 95812XX')\n",
    "\n",
    "# Aktifkan setiap karyawan yang telah didefinisikan\n",
    "perusahaan.aktifkan_karyawan(ani)\n",
    "perusahaan.aktifkan_karyawan(budi)\n",
    "perusahaan.aktifkan_karyawan(cici)\n",
    "perusahaan.aktifkan_karyawan(didi)\n",
    "perusahaan.aktifkan_karyawan(efi)\n",
    "perusahaan.aktifkan_karyawan(febi)\n",
    "\n",
    "# Cetak keseluruhan total pengeluaran perusahaan\n",
    "print(perusahaan.total_pengeluaran())"
   ]
  }
 ]
}
