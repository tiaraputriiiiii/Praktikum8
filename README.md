# Nama    : Tiara Putri
# NIM     : 312210064
# Kelas   : TI.22.A1

## Tugas Praktikum 8

Buat program sederhana dengan mengaplikasikan penggunaan class. Buatlah class untuk menampilkan daftar nilai mahasiswa, dengan ketentuan:

- Method tambah() untuk menambah data
- Method tampilkan() untuk menampilkan data
- Method hapus(nama) untuk menghapus data berdasarkan nama
- Method ubah(nama) untuk mengubah data berdasarkan nama
- Buat diagram class, flowchart dan penjelasan programnya pada README.md.
- Commit dan push repository ke github.

      class mahasiswa:
          def __init__(self, nim, nama, tugas, uts, uas):
              self.nim = nim
              self.nama = nama
              self.tugas = tugas
              self.uts = uts
              self.uas = uas

          def tambah(self,nim,nama,tugas,uts,uas):
              data.nim.append(nim)
              data.nama.append(nama)
              data.tugas.append(tugas)
              data.uts.append(uts)
              data.uas.append(uas)

          def lihat(self):
              for i in range(len(data.nama)):
                  print("|", i+1, "  |", end="")
                  print('{0:<25}'.format(self.nama[i]), end="")
                  print("|", self.nim[i], end="")
                  print(" |", self.tugas[i], end="")
                  print("    |", self.uts[i], end="")
                  print("  |", self.uas[i], " | ", end="")
                  print(f'{((self.tugas[i]*30/100) + (self.uts[i]*35/100) + (self.uas[i]*35/100)) :.2f}', " |")

          def ubah(self,nim,nama,tugas,uts,uas):
              self.nim[no] = nim
              self.nama[no] = nama
              self.tugas[no] = tugas
              self.uts[no] = uts
              self.uas[no] = uas

          def hapus(self):
              del self.nim[no]
              del self.nama[no]
              del self.tugas[no]
              del self.uts[no]
              del self.uas[no]

      data = mahasiswa([],[],[],[],[])

      while True:
          menu = input("\n[(L)ihat, (T)ambah, (U)bah, (H)apus, (K)eluar]:")
          if menu == "t" or menu == "T":
             print("\nTambah Data")
             data.tambah(
                 input("Masukkan NIM : "),
                 input("Masukkan Nama : "),
                 int(input("Nilai Tugas : ")),
                 int(input("Nilai UTS : ")),
                 int(input("Nilai UAS : "))
                 )
             print("\nData berhasil ditambahkan")

          elif menu == "l" or menu == "L":
              print("\nDaftar Nilai")
              print("==========================================================================")
              print("| No  |          Nama           |    NIM    | TUGAS | UTS | UAS |  AKHIR |")
              print("==========================================================================")
              if len(data.nama) != 0:
                  data.lihat()
              else:
                  print("                         TIDAK ADA DATA                               ")
              print("==========================================================================")

          elif menu == "u" or menu == "U":
              print("\nUbah Data")
              ubah = input("Masukkan Nama : ")
              if ubah in data.nama:
                 no = data.nama.index(ubah)
                 print("Masukkan Data Yang Baru : ")
                 data.ubah(
                     input("NIM : "),
                     input("Nama : "),
                     int(input("Nilai Tugas : ")),
                     int(input("Nilai UTS : ")),
                     int(input("Nilai UAS : "))
                     )
              else:
                  print(ubah, "tidak ada di dalam data")

          elif menu == "h" or menu == "H":
              print("\nHapus Data")
              hapus = input("Masukkan Nama : ")
              if hapus in data.nama:
                  no = data.nama.index(hapus)
                  data.hapus()
                  print("Data", hapus, "Berhasil dihapus")
              else:
                  print(hapus, "tidak ada di dalam data")

          elif menu == "k" or menu == "K":
              print("\nTerimakasih\n")
              break

          else:
              print("\nPerintah yang dimasukkan salah!\n")
              
## Program

![2022-12-13 (3)](https://user-images.githubusercontent.com/115775237/207317789-e7eed327-faf7-4a98-b935-a4ea86d1b9f5.png)

![2022-12-13 (4)](https://user-images.githubusercontent.com/115775237/207317841-76c0d36c-955e-4fc2-a03f-8ac141024946.png)

![2022-12-13 (5)](https://user-images.githubusercontent.com/115775237/207317877-ee6e3451-8cfe-45ea-a8dc-5d40528cf6f1.png)

![2022-12-13 (6)](https://user-images.githubusercontent.com/115775237/207317917-d8542e9f-8d99-4815-ac21-e7b74c46b314.png)

## Hasil Run & Penjelasan Program :

- Pertama kita mendeklarasikan sebuah class mahasiswa yang didalamnya terdapat atribut NIM, Nama, nilai tugas, nilai UTS dan nilai UAS. Jangan lupa, untuk mendeklarasikan sebuah class didalam OOP kita harus menggunakan **def__init__ dan juga self.**

    class mahasiswa:
        def __init__(self, nim, nama, tugas, uts, uas):
            self.nim = nim
            self.nama = nama
            self.tugas = tugas
            self.uts = uts
            self.uas = uas

- Seperti biasa, deklarasikan satu dictionary kosong sebagai tempat menyimpan data-data yang sudah kita input. Ada 5 list kosong yang nantinya berisi NIM, Nama, nilai tugas, nilai UTS dan nilai UAS.

data = mahasiswa([],[],[],[],[])  

- Kita akan buat beberapa method untuk menambahkan, menampilkan, menghapus, mengubah data mahasiswa. Pertama membuat method tambah(), method ini berfungsi untuk menambahkan data. Dalam method ini kita menggunakan append() supaya data yang terakhir ditambahkan ada di urutan list paling akhir.

      def tambah(self,nim,nama,tugas,uts,uas):
              data.nim.append(nim)
              data.nama.append(nama)
              data.tugas.append(tugas)
              data.uts.append(uts)
              data.uas.append(uas)
              
- Ini tampilan jika kita menginput method : `Tambah()`

![2022-12-13](https://user-images.githubusercontent.com/115775237/207318389-c6ebbd86-44dd-4312-ba27-cd10b76cc2d0.png)

- Fungsi membuat method lihat() yaitu untuk menampilkan seluruh data yang sudah kita tambahkan tadi. Jika tidak ada data sama sekali, maka akan muncul tulisan **TIDAK ADA DATA.**

      def lihat(self):
              for i in range(len(data.nama)):
                  print("|", i+1, "  |", end="")
                  print('{0:<25}'.format(self.nama[i]), end="")
                  print("|", self.nim[i], end="")
                  print(" |", self.tugas[i], end="")
                  print("    |", self.uts[i], end="")
                  print("  |", self.uas[i], " | ", end="")
                  print(f'{((self.tugas[i]*30/100) + (self.uts[i]*35/100) + (self.uas[i]*35/100)) :.2f}', " |")

- Ini tampilan jika kita menginput method : `Lihat()`

![2022-12-13 (1)](https://user-images.githubusercontent.com/115775237/207318604-49733514-5413-4906-9512-5d4d597c8b18.png)

- Fungsi membuat method ubah() yaitu untuk mengubah data. jika method ini diinput, maka data Nama, NIM, nilai tugas, nilai UTS, nilai UAS index nomor - (no) akan diubah sesuai dengan inputan dari user. Index ke - (no) akan dicari secara otomatis sesuai dengan nama yang ingin diubah oleh user.

      def ubah(self,nim,nama,tugas,uts,uas):
              self.nim[no] = nim
              self.nama[no] = nama
              self.tugas[no] = tugas
              self.uts[no] = uts
              self.uas[no] = uas

- Ini tampilan jika kita menginput method : `Ubah()`

![2022-12-13 (7)](https://user-images.githubusercontent.com/115775237/207318776-bdd4e706-7b72-4317-bf44-684f7ca52a02.png)

![2022-12-13 (2)](https://user-images.githubusercontent.com/115775237/207318899-849b3d73-d152-480e-995e-6e11a4cdbf36.png)

- Terakhir kita membuat method hapus(), yang berfungsi untuk menghapus data berdasarkan nama. Kita bisa menggunakan del untuk menghapus datanya. Seperti sebelumnya, nomor index list yang akan dihapus disesuaikan dengan inputan dari user. Yaitu index nomor ke - (no).

      def hapus(self):
              del self.nim[no]
              del self.nama[no]
              del self.tugas[no]
              del self.uts[no]
              del self.uas[no]

- Ini tampilan jika kita menginput method : `Hapus()`

![2022-12-13 (0)](https://user-images.githubusercontent.com/115775237/207319174-02205b38-7000-42b1-895e-1f275c6313af.png)

## Diagram Class 

![2022-12-13 (8)](https://user-images.githubusercontent.com/115775237/207319506-5bf0895a-d995-461c-b308-9c37de340da1.jpeg)

## Flowchat

![2022-12-13 (9)](https://user-images.githubusercontent.com/115775237/207319763-51d94963-83f2-4228-9578-ad176f0b937d.png)

