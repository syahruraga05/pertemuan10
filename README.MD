## Tugas Melengkapi Pertemuan ke 10
Nama	: Syahru Raga Ramdhani <br>
Kelas	: TI.20.A.2 <br>
Nim	: 312010354 <br>
## Daftar Isi
| No | Isi |
| -- | --- |
| 1. | Latihan 1 | 
| 2. | Tugas Praktikum | 

## Latihan 1

 **Soal**
	Ubahlah kode dibawah ini menjadi fungsi menggunakan lambda.

![gambar](/gambar/Capture1.PNG)<br>

# Syntax Sebagai Berikut

![gambar](/gambar/Capture3.PNG)<br>

# Maka ketika dijalankan Hasil Output nya seperti ini

![gambar](/gambar/Capture2.PNG)<br>

Berikut *source code* nya
```python
	# mengubah function menggunakan lambda
	import math as m

	def a(x):
		return x ** 2


	lambda x: x ** 2

	print("1. Mengubah function menggunakan Lambda \n   def a(x): \n \t   return x ** 2")
	print("   Hasil : lambda x: x ** 2")


	def b(x, y):
		return math.sqrt(x ** 2 + y ** 2)


	lambda x, y: m.sqrt(x ** 2 + y ** 2)

	print(35*"=")
	print("2. Mengubah function menggunakan Lambda \n   def b(x, y): \n \t   return math.sqrt(x ** 2 + y ** 2)")
	print("   Hasil : lambda x, y: math.sqrt(x ** 2 + y ** 2))")


	def c(*args):
    		return sum(args) / len(args)


	lambda *args: sum(args) / len(args)

	print(35*"=")
	print("3. Mengubah function menggunakan Lambda \n   def c(*args): \n \t   return sum(args) / len(args)")
	print("   Hasil : lambda *args: sum(args) / len(args))")


	def d(s):
	   	return "".join(set(s))


	lambda s: "".join(set(s))

	print(35*"=")
	print("4. Mengubah function menggunakan Lambda \n   def d(s): \n \t   return "".join(set(s))")
	print("   Hasil : lambda s: "".join(set(s)))")
```



## Tugas Praktikum

![gambar](/gambar/Capture4.PNG)<br>

# Syntax Sebagai Berikut

![gambar](/gambar/Capture5.PNG)<br>

# Lanjutan Syntax Diatas

![gambar](/gambar/Capture6.PNG)<br>

# Lanjutan Syntax Diatas

![gambar](/gambar/Capture7.PNG)<br>

# Maka hasil output ketika dijalankan sebagai berikut
* Ketika anda memilih menu 1 maka hasilnya anda akan disuruh untuk mengetik data anda

![gambar](/gambar/Capture8.PNG)<br>

* Ketika anda memilih menu 2 maka hasilnya akan menampilkan data yg sudah anda isi

![gambar](/gambar/Capture9.PNG)<br>

* Ketika anda memilih menu 4 maka hasilnya anda disuruh untuk mengetikan nama data yg ingin diubah

![gambar](/gambar/Capture10.PNG)<br>

* Ketika anda memilih menu 3 maka hasilnya data yg sudah anda isi otomatis akan terhapus

![gambar](/gambar/Capture11.PNG)<br>

Berikut *source code* nya
```python
data = {}

def tambah():
    print("Tambah Data")
    nama    = input("Nama\t\t: ")
    nim     = int(input("NIM\t\t: "))
    tugas   = int(input("Nilai Tugas\t: "))
    uts     = int(input("Nilai UTS\t: "))
    uas     = int(input("Nilai UAS\t: "))
    nilaiakhir = (tugas * 0.3 + uts * 0.35 + uas * 0.35)
    data[nama] = nim, tugas, uts, uas, nilaiakhir


def tampilkan():
    if data.items():
        print("~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~| Daftar Nilai |~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~")
        print("_______________________________________________________________________________________")
        print("|  No  |      NAMA     |        NIM        |    TUGAS   |   UTS   |   UAS   | AKHIR   |")
        print("|______|_______________|___________________|____________|_________|_________|_________|")
        i = 0
        for a in data.items():
            i += 1
            print(f"| {i:4} | {a[0]:13s} | {a[1][0]:17} | {a[1][1]:10d} |  {a[1][2]:6d} | {a[1][2]:7d} | {a[1][4]:6.2f} | ")
    else:
        print("~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~| Daftar Nilai |~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~")
        print("________________________________________________________________________________________")
        print("|  No  |      Nama     |      NIM      |   TUGAS  |   UTS   |   UAS   | Nilai Akhir    |")
        print("________________________________________________________________________________________")
        print("|      |               |             Tidak Ada Data         |         |                |")
        print("________________________________________________________________________________________")


def hapus():
    print("Hapus Data Nilai Mahasiswa")
    nama = input(" Masukan Nama\t:")
    if nama in data.keys():
        del data[nama]
        print()
        print("~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~")
        print("===| BERHASIL MENGHAPUS DATA |===")
        print("~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~")
    else:
        print("Data {0} tidak ada".format(nama))


def ubah():
    print("~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~")
    print("===| Edit Data Nilai Mahasiswa |===")
    print("~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~")
    nama = input("Masukan Nama\t\t: ")
    print("___________________________________")
    if nama in data.keys():
        nim = input("NIM baru\t\t: ")
        tugas = int(input("Nilai Tugas Baru\t: "))
        uts = int(input("Nilai UTS Baru\t\t: "))
        uas = int(input("Nilai UAS Baru\t\t: "))
        nilaiakhir = (tugas * 30 / 100 + uts * 35 / 100 + uas * 35 / 100)
        data[nama] = nim, tugas, uts, uas, nilaiakhir
        print()
        print("<><><><><><><><><><><><><><><><>")
        print("====| BERHASIL MENGUBAH DATA |====")
        print("<><><><><><><><><><><><><><><><>")
    else:
        print("Data nilai {0} tidak ada ".format(nama))


while True:
    print("")
    print("|_<><><><><><><><><><><><><><><><><>_|")
    print("|~~~~~~~~| DATA MAHASISWA |~~~~~~~~~~|")
    print("|_<><><><><><><><><><><><><><><><><>_|")
    x = input("1.| Tambah Data \n2.| Tampilkan Data \n3.| Hapus Data \n4.| Ubah Data \n0.| Keluar Aplikasi \nPilih menu : ")
    if x.lower() == "1":
        tambah()
    elif x.lower() == "2":
        tampilkan()
    elif x.lower() == "3":
        hapus()
    elif x.lower() == "4":
        ubah()
    elif x.lower() == "0":
        print()
        print("<><><><><><><><><><><><><><><><>")
        print("====== KELUAR DARI PROGRAM ======")
        print("<><><><><><><><><><><><><><><><>")
        break

    else:
        print()
        print("<><><><><><><><><><><><><><><><>")
        print("== Pilihan Anda Tidak Tersedia ==")
        print("== Pilihlah Menu Yang Tersedia ==")
        print("<><><><><><><><><><><><><><><><>")