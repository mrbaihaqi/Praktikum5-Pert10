# Praktikum 5
<b>Nama : Baihaqi Asa'ari Lubis</b>

<b>NIM : 312210720</b>

<b>Prodi : Teknik Informatika</b>

<b>Mata Kuliah : Bahasa Pemrograman</b>

### Program Data Mahasiswa

Pada praktikum 5, kita akan membuat program sederhana untuk membuat data mahasiswa menggunakan Dictionary dengan python.

#### Program Praktikum 5

```python
x = {}
print("Program Input Nilai")
print("="*19)
while True:
    c = input("\n(L)ihat, (T)ambah, (U)bah, (H)apus, (C)ari, (K)eluar: ")
    if c.lower() == 't':
        print("\nTambah Data")
        nim = input("NIM            : ")
        nama = input("Nama           : ")
        uts = int(input("Nilai UTS      : "))
        uas = int(input("Nilai UAS      : "))
        tugas = int(input("Nilai Tugas    : "))
        akhir = tugas*30/100 + uts*35/100 + uas*35/100
        x[nim] = nama, tugas, uts, uas, akhir
    elif c.lower() == 'u':
        print("\nUbah Data")
        nim = input("Masukan NIM    : ")
        if nim in x.keys():
            del x[nim]
            nim = input("NIM            : ")
            nama = input("Nama           : ")
            uts = int(input("Nilai UTS      : "))
            uas = int(input("Nilai UAS      : "))
            tugas = int(input("Nilai Tugas    : "))
            akhir = tugas*30/100 + uts*35/100 + uas*35/100
            x[nim] = nama, tugas, uts, uas, akhir
        else:
            print("NIM {0} tidak ditemukan".format(nim))
    elif c.lower() == 'h':
        print("\nHapus Data")
        nim = input("Masukan NIM    : ")
        if nim in x.keys():
            del x[nim]
        else:
            print("NIM {0} Tidak Ditemukan".format(nim))
    elif c.lower() == 'c':
        print("\nCari Data")
        nim = input("Masukan NIM    : ")
        if nim in x.keys():
            print("\nDaftar Nilai")
            print("="*73)
            print("|      NIM       |       NAMA       |  TUGAS  |  UTS  |  UAS  |  AKHIR  |")
            print("="*73)
            print("| {0:15s}| {1:15s}  | {2:5d}   | {3:5d} |{4:6d} | {5:7.2f} |"
                  .format(nim, nama, tugas, uts, uas, akhir))
            print("="*73)
        else:
            print("NIM {0} Tidak Ditemukan".format(nim))
    elif c.lower() == 'l':
        if x.items():
            print("\nDaftar Nilai")
            print("="*78)
            print("|No. |      NIM       |       NAMA       |  TUGAS  |  UTS  |  UAS  |  AKHIR  |")
            print("="*78)
            i = 0
            for z in x.items():
                i += 1
                print("| {no:2d} | {0:15s}| {1:15s}  | {2:5d}   | {3:5d} |{4:6d} | {5:7.2f} |"
                      .format(z[0][:13], z[1][0], z[1][1], z[1][2], z[1][3], z[1][4], no=i))
            print("=" * 78)
        else:
            print("\nDaftar Nilai")
            print("="*78)
            print("|No. |      NIM       |       NAMA       |  TUGAS  |  UTS  |  UAS  |  AKHIR  |")
            print("="*78)
            print("|                                TIDAK ADA DATA                              |")
            print("="*78)
    elif c. lower() == 'k':
        break
    else:
        print("Pilih menu yang tersedia")
```
#### Hasil Output
![picture output](picture/hasil%201.PNG)
![picture output](picture/hasil%202.PNG)

#### Penjelasan :

1.) Pertama kita membuat sebuah dictionary kosong yang nantinya akan diinputkan data ketika program dijalankan.
```python
x = {}
```

2.) Lalu kita membuat kondisi perulangan dan sebuah keterangan untuk pilihan menu yang akan menjalankan program.
```python
while True:
    c = input("\n(T)ambah, (U)bah, (H)apus, (C)ari, (L)ihat, (K)eluar: ")
```

3.) Membuat syntax untuk menambahkan data.
```python
    if c.lower() == 't':
        print("\nTambah Data")
        nim = input("NIM            : ")
        nama = input("Nama           : ")
        uts = int(input("Nilai UTS      : "))
        uas = int(input("Nilai UAS      : "))
        tugas = int(input("Nilai Tugas    : "))
        akhir = tugas*30/100 + uts*35/100 + uas*35/100
        x[nim] = nama, tugas, uts, uas, akhir
```
Disini apabila kita menginputkan 't' maka kita akan diminta untuk menginputkan beberapa data. Data yang kita inputkan akan masuk ke dictionary 'x' yang telah dibuat tadi dengan data 'nama' sebagai keys dan sisanya sebagai valuesnya.

4.) Membuat syntax untuk mengubah data.
```python
    elif c.lower() == 'u':
        print("\nUbah Data")
        nim = input("Masukan NIM    : ")
        if nim in x.keys():
            del x[nim]
            nim = input("NIM            : ")
            nama = input("Nama           : ")
            uts = int(input("Nilai UTS      : "))
            uas = int(input("Nilai UAS      : "))
            tugas = int(input("Nilai Tugas    : "))
            akhir = tugas*30/100 + uts*35/100 + uas*35/100
            x[nim] = nama, tugas, uts, uas, akhir
        else:
            print("NIM {0} tidak ditemukan".format(nim))
```
Apabila kita menginput 'u' maka akan ada keterangan untuk mengubah data dan kita akan diminta untuk menginputkan nama yang mau diubah datanya, apabila nama tidak ada maka outputnya "Nama {} tidak ditemukan". Dimana `{}` adalah nama/data yang mau kita ubah.

5.) Membuat syntax untuk menghapus data.
```python
    elif c.lower() == 'h':
        print("\nHapus Data")
        nim = input("Masukan NIM    : ")
        if nim in x.keys():
            del x[nim]
        else:
            print("NIM {0} Tidak Ditemukan".format(nim))
```
Apabila kita menginput 'h' maka kita akan diminta menginput nama yang akan dihapus. Jika nama ada di dalam dictionary, maka system akan menghapus keys/nama tersebut beserta valuesnya pada statement `del x[nama]`.

6.) Membuat syntax untuk mencari data.
```python
    elif c.lower() == 'c':
        print("\nCari Data")
        nim = input("Masukan NIM    : ")
        if nim in x.keys():
            print("\nDaftar Nilai")
            print("="*73)
            print("|      NIM       |       NAMA       |  TUGAS  |  UTS  |  UAS  |  AKHIR  |")
            print("="*73)
            print("| {0:15s}| {1:15s}  | {2:5d}   | {3:5d} |{4:6d} | {5:7.2f} |"
                  .format(nim, nama, tugas, uts, uas, akhir))
            print("="*73)
        else:
            print("NIM {0} Tidak Ditemukan".format(nim))
```
Apabila kita menginputkan 'c' maka kita akan diminta untuk memasukkan nama yang akan dicari. Apabila nama yang dicari ada di dalam dictionary maka outputnya akan menampilkan data dari nama tersebut.

7.) Membuat syntax untuk melihat atau menampilkan data.
```python
    elif c.lower() == 'l':
        if x.items():
            print("\nDaftar Nilai")
            print("="*78)
            print("|No. |      NIM       |       NAMA       |  TUGAS  |  UTS  |  UAS  |  AKHIR  |")
            print("="*78)
            i = 0
            for z in x.items():
                i += 1
                print("| {no:2d} | {0:15s}| {1:15s}  | {2:5d}   | {3:5d} |{4:6d} | {5:7.2f} |"
                      .format(z[0][:13], z[1][0], z[1][1], z[1][2], z[1][3], z[1][4], no=i))
            print("=" * 78)
        else:
            print("\nDaftar Nilai")
            print("="*78)
            print("|No. |      NIM       |       NAMA       |  TUGAS  |  UTS  |  UAS  |  AKHIR  |")
            print("="*78)
            print("|                                TIDAK ADA DATA                              |")
            print("="*78)
```
Apabila kita menginput 'l' maka sistem akan menampilkan data - data yang sudah kita masukkan. Jika kita belum memasukkan data maka outputnya menjadi "TIDAK ADA DATA".

8.) Membuat syntax untuk menghentikan perulangan.
```python
    elif c. lower() == 'k':
        break
```
Apabila kita menginput 'k' maka program akan langsung berhenti.

9.) Membuat syntax untuk apabila memilih pilihan yang tidak ada di menu.
```python
    else:
        print("Pilih menu yang tersedia")
```
Jika kita menginputkan selain yang ada pada menu (t, u, h, c, l, k) maka kita akan diminta untuk memilih menu yang tersedia.
