## TUGAS 5 NETPRO ##

<p align="center"
  <a><strong>  NAMA KELOMPOK :  </strong></a> 
</p>
<p align="center">
  <a>  I Putu Surya Baratha (1301188566)  </a> 
</p> 

<p align="center">
  <a>  Muhammad Risdham Nur A.P (1301188603)  </a> 
</p>

<p align="center">
  <a>  Sella Tresnasari  (1301188565)  </a> 
</p> 

#### HASIL RUNNING NOMOR 1 ####

[![Screen-Shot-2019-09-22-at-16-33-24.png](https://i.postimg.cc/44FsNjts/Screen-Shot-2019-09-22-at-16-33-24.png)](https://postimg.cc/CdDWcPmQ)

Di Go, data json dituliskan sebagai string. Dengan menggunakan json.Unmarshal, json string bisa dikonversi menjadi bentuk objek, entah itu dalam bentuk map[string]interface{} ataupun objek struct.

Program diatas adalah contoh cara decoding json ke bentuk objek. Pertama import package yang dibutuhkan, lalu siapkan struct User. Struct User ini nantinya digunakan untuk membuat variabel baru penampung hasil decode json string. Proses decode sendiri dilakukan lewat fungsi json.Unmarshal(). Fungsi unmarshal hanya menerima data json dalam bentuk []byte, maka dari itu data json string pada kode di atas di-casting terlebih dahulu ke tipe []byte sebelum dipergunakan pada fungsi unmarshal. Juga, perlu diperhatikan, argument ke-2 fungsi unmarshal harus diisi dengan pointer dari objek yang nantinya akan menampung hasilnya. Jika kita perhatikan lagi, pada struct User, salah satu property-nya yaitu FullName memiliki tag json:"Name". Tag tersebut digunakan untuk mapping informasi json ke property yang bersangkutan.

Data json yang akan diparsing memiliki 2 property yaitu Name dan Age. Kebetulan penulisan Age pada data json dan pada struktur struct adalah sama, berbeda dengan Name yang tidak ada pada struct. Dengan menambahkan tag json, maka property FullName struct akan secara cerdas menampung data json property Name.

#### HASIL RUNNING NOMOR 2 ####

[![Screen-Shot-2019-09-22-at-16-33-42.png](https://i.postimg.cc/T2kY5K88/Screen-Shot-2019-09-22-at-16-33-42.png)](https://postimg.cc/MXQ8hKKt)

#### HASIL RUNNING NOMOR 3 ####

[![Screen-Shot-2019-09-22-at-16-32-21.png](https://i.postimg.cc/L5qd16fR/Screen-Shot-2019-09-22-at-16-32-21.png)](https://postimg.cc/p5t1Nvq1)
