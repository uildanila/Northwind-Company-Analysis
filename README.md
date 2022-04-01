# Module 2 Final Project Specifications
Capstone Project modul 2 ini bertujuan untuk mengimplementasikan materi yang telah dipelajari terkait data analysis dalam sebuah proyek.


# Northwind Company Analysis 

> The Northwind database contains the sales data for a fictitious company called **Northwind Traders**, which imports and exports specialty foods from around the world.
> 
> 👉 
Tugas saya dalam studi kasus ini adalah melakukan analisis kinerja perusahaan ini menggunakan **SQL**, **Manipulasi Data**, **Visualisasi Data**, dan **Statistik**. Dan yang menjadi fokus analisis adalah **customers**

<!-- omit in toc -->
## 📕  Table Of Contents
* [📂 Dataset](#-dataset)
* [🧙‍♂️ Business Question](#️-business-question)


## 📂 Dataset
#### **Context**

Sebuah perusahaan bergerak di bidang eksport dan import makanan ingin mengetahui gambaran umum tentang bisnis yang sedang mereka jalankan. Terdapat sebuah database yang menunjukkan detail data layaknya dalam suatu perusahaan eksport import seperti tabel Customers, Orders, Supplier, dan lain sebagainya. Dari database tersebut, perusahaan ingin bisa mendapatkan insight yang dapat dijalankan, sehingga nantinya mereka dapat melakukan penerapan strategi yang tepat sasaran untuk meningkatkan jumlah customers dan mengetahui berbagai kemungkinan penyebab naik/turunnya jumlah customers, meningkatkan loyalitas cutomers agar perusahaan dapat memperoleh keuntungan yang lebih dari saat ini.

#### **Database Information**

Sumber Database: https://drive.google.com/drive/folders/1fTHrwh_gcLsOFKXHnUzUGEu_APxLoD9i

<details>
<summary>
Show summary
</summary>
  
Database yang dimiliki mempunyai 13 tabel, yaitu:

| No | Nama Tabel | Deskripsi |
| --- | --- | --- |
| 1 | Categories | Informasi Kategori Produk Northwind |
| 2 | Customers | Informasi pelanggan/customers Northwind |
| 3 | Employees | Informasi pegawai/karyawan Northwind (Name, Title, dan informasi personal) |
| 4 | Employeeterritories | Informasi wilayah penjualan yang menjadi tanggung jawab dari karyawan  |
| 5 | Orderdetails | Informasi detail produk, jumlah, dan harga setiap order berdasarkan table Orders   |
| 6 | Orders | Informasi detail order setiap pelanggan, tanggal order, dan biaya pengiriman barang setiap produk yang diorder   |
| 7 | Products | Informasi detail produk yang tersedia di Northwind (nama produk, supplier, harga, dan unit stok)   |
| 8 | Region | Informasi daftar region   |
| 9 | Shippers | Informasi daftar ekspedisi pengiriman   |
| 10 | Suppliers | Informasi daftar supplier produk Northwind   |
| 11 | Territories | Informasi detail daftar wilayah teritorial penjualan   |
| 12 | customercustomerdemo | -   |
| 13 | customerdemographics | -   |
  
 </details>

Berikut ini adalah diagram hubungan entitas (*Entity Relationship Diagram*) database Northwind
<p align="center"><img width=60% height=60%" src="https://yintingchou.com/posts/2017-09-01-learning-microsoft-sql-server/ERD.png"></p>

Setiap tabel yang tertera pada database dapat terhubung, baik secara langsung maupun tidak langsung, sehingga setiap informasi dari database ini akan dapat saling berkaitan. Data pertama ini merupakan data utama yang nantinya akan dianalisa lebih lanjut. Data ini merupakan gabungan dari 6 tabel, yaitu tabel ```costumers```, ```orders```, ```orderdetails```, ```products```, ```categories```, dan ```shippers```. Masing-masing dari setiap tabel tersebut diambil beberapa kolomnya dan tidak diambil secara keseluruhan. Hanya Informasi-informasi yang dianggap penting yang akan digunakan. Berikut ini merupakan informasi yang digunakan:
* OrderDate dari tabel orders
* CustomerID dari tabel customers
* CompanyName dari tabel customers
* ContactName dari tabel customers
* ContactTitle dari tabel customers
* City dari tabel customers
* Country dari tabel customers
* ProductName dari tabel products
* CategoryName dari tabel categories
* EmployeeID dari tabel orders
* UnitPrice dari tabel products
* Quantity dari tabel orderdetails
* UnitPrice dari tabel orderdetails

Selain dari tabel, terdapat kolom juga yang dinamakan **TotalBasedPrice** yang merupakan Total Harga Beli berdasarkan harga asli produk Northwind tanpa discount; juga terdapat kolom yang bernama **TotalBuyPrice** yang merupakan Total Harga Beli produk setelah didiskon. 

Semua informasi tersebut kemudian dijadikan dalam sebuah DataFrame yang nantinya akan diolah informasinya.
                                                                                                                 
#### **Visualization Tools**
✅ **Tableau**
✅ **Plotly**
  
                                                                                                                 
## 🧙‍♂️ General Question
* Bagaimana konteks bisnis berdasarkan dengan data yang telah diberikan ?
* Ada berapa banyak tabel yang disediakan oleh database yang tersedia? Jabarkan setiap tabelnya. Jika terdapat ERD, silahkan ditampilkan.
  
## 🧙‍♂️ SQL : 
* Apakah tabel customers, orders, orderdetails, dan products, dan category dapat digabungkan menjadi 1 tabel? Jika memungkinkan, tampilkan tabel yang memuat informasi total pembelian yang melibatkan keempat tabel tersebut.
* Berapa banyak pelanggan perusahaan tersebut? Dan berapa banyak pelanggan untuk setiap wilayahnya?
* Seberapa sering pelanggan melakukan order ?

 ## 🧙‍♂️ Data Manipulation :
* Apakah terdapat anomaly berupa missing values, data duplicate, kesalahan data formatting, dan/atau inconsistency typing? Jika ada tunjukkan serta lakukan penanganan pada anomaly tersebut.
* Apakah terdapat tipe data yang berupa datetime pada data? Jika iya, apakah tipe data yang berupa datetime tersebut dapat dicari tahu selisihnya? Silahkan tampilkan hasilnya, berikan insight yang sesuai (jika memungkinkan).
* Berapa total harga pembelian produk  untuk customers berdasarkan asal negaranya? Lalu, bagaimana rata-rata dari BuyPrice untuk setiap customers? Jabarkan dan berikan insight.
* TotalBuyPrice adalah sebuah variabel baru yang merupakan hasil kali antara banyaknya Quantity produk yang diorder dan BuyPrice setiap unit produk. Apakah terdapat outlier pada variable baru yang bernama TotalBuyPrice tersebut? Jika ada, tunjukan di data keberapa. Lalu, bagaimana outlier ini akan memberikan pengaruh terhadap penjualan setiap produk? Coba jelaskan.
* GapDays adalah sebuah variabel baru yang merupakan rentang waktu dalam hari (dapat dikaitkan dengan lama proses pesanan) berdasarkan OrderDate (tanggal order) hingga ShippedDate (Tanggal Pengiriman). Apakah terdapat outlier pada variable baru yang bernama GapDays tersebut? Jika ada, tunjukan di data keberapa. Lalu, bagaimana outlier ini akan memberikan pengaruh terhadap tingkat pemesanan produk? Coba jelaskan.

 ## 🧙‍♂️ Data Visualization & Statistics :
* Bagaimana distribusi/persebaran pelanggan Northwind? 
* Apakah terdapat pelanggan yang loyal? Jika ada, bagaimana treatment dan strategi yang bisa dimanfaatkan dengan melihat adanya pelanggan setia tersebut?
* Wilayah mana yang menjadi pemesan produk makanan terbanyak? Tampilkan dan jabarkan.
* Bagaimana jumlah pelanggan berdasarkan title pelanggan yang memesan produk makanan di perusahaan impor/ekspor makanan tersebut? 
* Kategori produk dan produk apa yang paling laku dan paling banyak terjual di 5 negara asal pelanggan yang paling loyal?
* Pada tahun berapa tingkat penjualan terbesar perusahaan didapatkan? Serta pada bulan apa saja penjualan mencapai titik tertingginya?
* Pegawai mana yang mendapatkan akumulasi total harga pembelian produk tertinggi oleh pelanggan? 
* Pelanggan Northwind diasumsikan dapat memilih ekpedisi pengiriman setiap pemesanan produk, ekspedisi apa yang paling banyak digunakan oleh pelanggan Nortwind? Lalu, Berikan insight terkait hal tersebut.
* Terdapat X kategori product yang tersedia, apakah terdapat perbedaan nilai BuyPrice antar setiap product tersebut? Buktikan.
* Diketahui bahwa terdapat pelanggan yang mendapatkan discount harga sehingga harga beli (BuyPrice) jauh lebih murah. Apakah ada perbedaan yang signifikan antara BuyPrice (Harga Beli) dan UnitPrice (Harga asli produk Northwind)?
* Apakah terdapat hubungan antara 'Quantity',  BuyPrice', ‘Discount’, ‘UnitPrice’, ‘Freight’, ‘TotalBuyPrice’? Jika iya, variable mana saja yang paling mempengaruhi satu sama lain? Gambarkan bentuk hubungannya.
* Apakah terdapat hubungan antara 'TotalQuantity',  ‘TotalProduct’, ‘Freight’, ‘TotalBuyPrice’, ‘TotalBasedPrice’, ‘TotalPayment’? Jika iya, variable mana saja yang paling mempengaruhi satu sama lain? Gambarkan bentuk hubungannya.
                                                                                                                 
