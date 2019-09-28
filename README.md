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

Fungsi Marshal() dapat mengambil apa pun, yang didalam GO berarti antarmuka kosong dan mengembalikan sepotong byte serta  kesalahan. Jika Marshal() gagal membuat serialisasi nilai input, akan mengembalikan kesalahan non-nil. Marshal() memiliki beberapa batasan ketat, yaitu:
•	Kunci peta harus berupa string.
•	Nilai peta harus jenis yang dapat diserialkan oleh paket json.
•	Jenis berikut tidak didukung: Channel, kompleks, dan fungsi.
•	Struktur data siklik yang tidak didukung.
•	Pointer akan dikodekan (dan kemudian didekodekan) sebagai nilai-nilai yang mereka tunjuk (atau 'null' jika pointer nol).

Cara Kerja :

* Di Go, data json dituliskan sebagai string. Dengan menggunakan json.Unmarshal, json string bisa dikonversi menjadi bentuk objek, entah itu dalam bentuk map[string]interface{} ataupun objek struct.

* Program diatas adalah contoh cara decoding json ke bentuk objek. Pertama import package yang dibutuhkan, lalu siapkan struct Person. Struct Person ini nantinya digunakan untuk membuat variabel baru penampung hasil decode json string. Proses decode sendiri dilakukan lewat fungsi json.Unmarshal(). 

* Fungsi unmarshal hanya menerima data json dalam bentuk []byte, maka dari itu data json string pada kode di atas di-casting terlebih dahulu ke tipe []byte sebelum dipergunakan pada fungsi unmarshal. Juga, perlu diperhatikan, argument ke-2 fungsi unmarshal harus diisi dengan pointer dari objek yang nantinya akan menampung hasilnya. Jika kita perhatikan lagi, pada struct Person, salah satu property-nya yaitu firstName memiliki tag json:"FirstName". Tag tersebut digunakan untuk mapping informasi json ke property yang bersangkutan.

* Data json yang akan diparsing memiliki 2 property yaitu FirstName dan LastName. Dengan menambahkan tag json, maka property FirstName & LastName struct akan secara cerdas menampung data json property FirstName & LastName.

#### HASIL RUNNING NOMOR 2 ####

[![Screen-Shot-2019-09-22-at-16-33-42.png](https://i.postimg.cc/T2kY5K88/Screen-Shot-2019-09-22-at-16-33-42.png)](https://postimg.cc/MXQ8hKKt)

Fungsi Unmarshal () mengambil sepotong byte yang diharapkan mewakili JSON yang valid dan antarmuka tujuan,  biasanya merupakan pointer ke struct atau tipe dasar. Ini deserializes JSON ke antarmuka dengan cara yang umum. Jika serialisasi gagal, itu akan kembali kekesalahan.
Cara Kerja : 
* Fungsi Marshal akan digunakan untuk melakukan encode data objek ke bentuk json string.

* Fungsi json.Marshal digunakan untuk decoding data ke json string. Sumber data bisa berupa variabel objek cetakan struct, map[string]interface{}, atau slice.

* Pada contoh diatas, data slice struct dikonversi ke dalam bentuk json string. Hasil konversi berupa []byte, casting terlebih dahulu ke tipe string agar bisa ditampilkan bentuk json string-nya.

#### HASIL RUNNING NOMOR 3 ####

[![Screen-Shot-2019-09-22-at-16-32-21.png](https://i.postimg.cc/L5qd16fR/Screen-Shot-2019-09-22-at-16-32-21.png)](https://postimg.cc/p5t1Nvq1)

1. Output

2.	Cara Kerja & Diagram FSM

3.	Analisis perbedaan dari protocol buffer dan flatbuffer
-	Protocol Buffer
Protocol Buffers adalah metode untuk serialisasi data terstruktur, yang dibuat oleh Google. Protobuf cocok digunakan pada aplikasi yang berkomunikasi dengan aplikasi lain. Protobuf bisa dipakai di banyak platform, contoh: komunikasi antara aplikasi mobile iOS dan Golang Web Service, bisa menggunakan protobuf.
Protobuf hanya bertugas di bagian serialisasi data saja, untuk komunikasi antar service atau antar aplikasi sendiri menggunakan gRPC.
-	Flatbuffer
Perbedaan utama antara protobuf dan buffer datar adalah bahwa tidak perlu melakukan deserialisasi seluruh data pada yang terakhir sebelum mengakses objek. Ini membuat buffer rata bertanggung jawab atas kasus penggunaan yang memiliki banyak data. Ini juga mengkonsumsi memori jauh lebih sedikit daripada protobuf.
Kode juga merupakan urutan besarnya lebih kecil dan mendukung lebih banyak fitur skema (mis. Serikat jenis dalam XML)
Flatbuffers juga menderita kelemahan yang sama dengan protobuf karena kurangnya representasi yang dapat dibaca manusia.
