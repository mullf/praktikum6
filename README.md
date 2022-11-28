 # Praktikum 6
 ## Latihan 1
 
 ### Buat Dictionary daftar kontak
 #### - Nama sebagai Key dan Nomor sebagai value
 ```
 telp = {}
 telp['Ari'] = '081267888'
 telp['Dina'] = '087677776'
 ```
 #### - Tampilkan kontaknya Ari
 ```
 print(telp['Ari'])
 ```
 #### - Tambah kontak baru dengan nama Riko, nomor 087654544
 ```
 telp['Riko'] = '087654544'
 ```
 #### - Ubah kontak Dina dengan nomor baru 088999776
 ```
 telp['Dina'] = '08999776'
 ```
 #### - Tampilkan semua nama
 ```
 print(telp.keys())
 ```
 #### - Tampilkan semua nomor
 ```
 print(telp.values())
 ```
 #### - Tampilkan daftar Nama dan nomornya
 ```
 print(telp.items())
 ```

![gambar1](gambar/prak6_1.png)

#### - Hapus kontak Dina
```
telp.pop('Dina')
```

![gambar1](gambar/prak6_2.png)

## Tugas Praktikum

### Buat Nilai Mahasiswa menggunakan Dictionary
#### 1. Membuat sebuah dictionary kosong yang nantinya akan diinputkan data ketika program dijalankan.
```
Data = {}
```
#### 2. Membuat perulangan dan sebuah keterangan untuk pilihan menu yang akan menjalakan program.
```
while True:
    List = input("\n(T)ambah, (U)bah, (H)apus, (C)ari, (L)ihat, (K)eluar :")
```
#### 3. Membuat syntax untuk menambahkan data.
```
if List.lower() == 't':
        print("Tambah Data")
        nama = input("Nama              : ")
        nim = int(input("NIM               : "))
        tugas = int(input("Nilai Tugas       : "))
        uts = int(input("NIlai UTS         : "))
        uas = int(input("Nilai UAS         : "))
        akhir = tugas *30/100 + uts *35/100 + uas *35/100
        Data[nama] = nim, tugas, uts, uas, akhir
```
#### Disini apabila menginputkan 't' maka akan diminta untuk menginputkan beberapa data. Data yang inputkan akan masuk ke dictionary 'Data' yang telah dibuat tadi dengan data 'nama' sebagai keys dan sisanya sebagai values.

![gambar1](gambar/prak6_3.png)

#### 4. Membuat syntax untuk mengubah data.
```
elif List.lower() == 'u':
        print ("Ubah Data")
        nama = input("Masukkan Nama  : ")
        if nama in Data.keys():
            nim = int(input("NIM            :"))
            tugas = int(input("Nilai Tugas    : "))
            uts = int(input("NIlai UTS      : "))
            uas = int(input("Nilai UAS      : "))
            akhir = tugas *30/100 + uts *35/100 + uas *35/100
            Data[nama] = nim, tugas, uts, uas, akhir
        else :
            print("Nama {0} tidak ditemukan".format(nama))
```
#### Apabila menginput 'u' maka akan ada keterangan untuk mengubah data dan akan diminta untuk menginputkan nama yang mau diubah datanya, apabila nama tidak ada maka outputnya "Nama {} tidak ditemukan". Dimana {} adalah nama/data yang mau diubah.

![gambar1](gambar/prak6_4.png)

#### 5. Membuat syntax untuk menghapus data.
```
elif List.lower() == 'h':
        print("Hapus Data")
        nama = input("Masukkan Nama :")
        if nama in Data.keys():
            del Data[nama]
        else:
            print("Nama {0} Tidak Dtemukan".format(nama))
```
#### Apabila kita menginput 'h' maka kita akan diminta menginput nama yang akan dihapus. Jika nama ada di dalam dictionary, maka system akan menghapus keys/nama tersebut beserta valuesnya pada statement del Data[nama].

![gambar1](gambar/prak6_5.png)

#### 6. Membuat sybtax untuk mencari data.
```
elif List.lower() == 'c':
        print("Cari Data")
        nama = input("Masukkan Nama : ")
        if nama in Data.keys():
            print("="*73)
            print("|                        Daftar Mahasiswa                        |")
            print("="*73)
            print("|   Nama     |      NIM      |  UTS  |  UAS  |  Tugas  |  Akhir  |")
            print("="*73)
            print("| {0:15s} | {1:15d} | {2:5d} | {3:5d} | {4:7d} | {5:7.2f} |"
                  .format(nama, nim, uts, uas, tugas, akhir))
            print("="*73)
        else:
            print("Nama {0} Tidak Ditemukan".format(nama))
```
#### Apabila menginputkan 'c' maka akan diminta untuk memasukkan nama yang akan dicari. Apabila nama yang dicari ada di dalam dictionary maka outputnya akan menampilkan data dari nama tersebut.

![gambar1](gambar/prak6_6.png)

#### 7. Membuat syntax untuk melihat atau menampilkan data.
```
elif List.lower() == 'l':
        if Data.items():
            print("="*78)
            print("|                            Daftar Mahasiswa                            |")
            print("="*78)
            print("|No. |     Nama      |      NIM      |  UTS  |  UAS  |  Tugas  |  Akhir  |")
            print("="*78)
            i = 0
            for j in Data.items():
                i += 1
                print("| {no:2d} | {0:15s} | {1:15d | {2:5d} | {3:5d} | {4:7d} | {5:7.2f} |"
                      .format(j[0][13], j[1][0], j[1][1], j[1][2], j[1][3], j[1][4], no=i))
                print("="*78)
            else:
                print("="*78)
                print("|                            Daftar Mahasiswa                            |")
                print("="*78)
                print("|No. |     Nama      |      NIM      |  UTS  |  UAS  |  Tugas  |  Akhir  |")
                print("="*78)
                print("|                           TIDAK ADA DATA                               |")
                print("="*78)
```
#### Apabila menginput 'l' maka sistem akan menampilkan data - data yang sudah dimasukkan. Jika belum memasukkan data maka outputnya menjadi "TIDAK ADA DATA".

![gambar1](gambar/prak6_7.png)

#### 8. Mmebuat sybtax untuk menghentikan perulangan.
```
elif List.lower() == 'k':
        break
```
#### Apabila menginput 'k' maka program akan langsung berhenti.

![gambar1](gambar/prak6_8.png)

#### 9. Membuat syntax untuk apabila memilih pilihan yang akan tidak ada di menu.
```
else:
        print("Pilih menu yang lainnya")
```
#### Jika menginputkan selain yang ada pada menu (t, u, h, c, l, k) maka akan diminta untuk memilih menu yang tersedia.

![gambar1](gambar/prak6_9.png)
