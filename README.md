# Jarkom-Modul-1-A06-2023

## Group Member

| NRP        | Name                        |
| ---------- | --------------------------- |
| 5025211057 | Salsabila Fatma Aripa       |
| 5025211254 | Yusna Millaturrosyidah      |


## Daftar Isi
- [Soal 1](#soal-1)
	- [Penyelesaian soal 1](#penyelesaian-soal-1)
- [Soal 2](#soal-2)
	- [Penyelesaian soal 2](#penyelesaian-soal-2)
- [Soal 3](#soal-3)
	- [Penyelesaian soal 3](#penyelesaian-soal-3)
- [Soal 4](#soal-4)
	- [Penyelesaian soal 4](#penyelesaian-soal-4)
- [Soal 5](#soal-5)
	- [Penyelesaian soal 5](#penyelesaian-soal-5)
- [Soal 6](#soal-6)
	- [Penyelesaian soal 6](#penyelesaian-soal-6)
- [Soal 7](#soal-7)
	- [Penyelesaian soal 7](#penyelesaian-soal-7)
- [Soal 8](#soal-8)
	- [Penyelesaian soal 8](#penyelesaian-soal-8)
- [Soal 9](#soal-9)
	- [Penyelesaian soal 9](#penyelesaian-soal-9)
- [Soal 10](#soal-10)
	- [Penyelesaian soal 10](#penyelesaian-soal-10)
- [Kendala](#Kendala)
   

## Soal 1

User melakukan berbagai aktivitas dengan menggunakan protokol FTP. Salah satunya adalah mengunggah suatu file.
- Berapakah sequence number (raw) pada packet yang menunjukkan aktivitas tersebut? 
- Berapakah acknowledge number (raw) pada packet yang menunjukkan aktivitas tersebut? 
- Berapakah sequence number (raw) pada packet yang menunjukkan response dari aktivitas tersebut?
- Berapakah acknowledge number (raw) pada packet yang menunjukkan response dari aktivitas tersebut?

### Penyelesaian soal 1
Langkah 1 : Copy `nc 10.21.78.111 12345` pada terminal, kemudian akan menampilkan soal yang diminta

Langkah 2 : Kemudian download juga `soal1.pcapng`, lalu buka pada wireshark

Langkah 3 : Melakuakan query pada wiresharknya dengan mengunakan command `ftp.request.command == "STOR"`. FTP "File Transfer Protocol." Ini adalah protokol yang digunakan untuk mentransfer file antara dua komputer melalui jaringan, seperti internet. `“STOR”` adalah perintah yang digunakan dalam FTP untuk mengirimkan file dari klien (pengirim) ke server (penerima).

Untuk Request terdapat pada packet 147
![Screenshot 2023-09-18 212314](https://github.com/bilaaripa/Jarkom-Modul-1-A06-2023/assets/114417418/9f462104-f4b3-4af1-8a41-19fd83c75f6b)

Untuk Response terdapat pada packet 149
![Screenshot (2726)](https://github.com/bilaaripa/Jarkom-Modul-1-A06-2023/assets/114417418/ab6798c1-a8fc-4d81-8f91-474c3eb619f3)

Langkah 4 : Pilih pada transmission control protocol, maka akan terlihat informasi sequence number (raw) dan acknowledge number (raw) pada layar.

Hasil : Hasil lalu dapat diketahui 
- 1a --> 258040667
- 1b --> 1044861039
- 1c --> 1044861039
- 1d --> 258040696

![Screenshot 2023-09-18 213014](https://github.com/bilaaripa/Jarkom-Modul-1-A06-2023/assets/114417418/2c7a47ed-148c-4afe-803e-08a2c13d17ac)

## Soal 2
Sebutkan web server yang digunakan pada portal praktikum Jaringan Komputer!

### Penyelesaian soal 2

Langkah 1 : Copy `nc 10.21.78.111 13579` pada terminal, kemudian akan menampilkan soal yang diminta

Langkah 2 : Kemudian download juga `soal2.pcapng`, lalu buka di wireshark 

Langkah 3 : Karena portal web adalah `http://10.21.78.111:8000/` maka dilakukan filtering `http` pada wireshark.
![Screenshot 2023-09-18 210102](https://github.com/bilaaripa/Jarkom-Modul-1-A06-2023/assets/114417418/620408ef-e1e8-42bb-90a8-178089832a97)

Langkah 3 : Selanjutkan klik kanan lalu memilih button follow lalu memilih follow HTTP Stream
![Screenshot 2023-09-18 210129](https://github.com/bilaaripa/Jarkom-Modul-1-A06-2023/assets/114417418/be06e80f-37d7-48bc-ac62-623bd24fc50b)

Hasil : Lalu dapat diketahui bahwa servernya menggunakan gunicorn
![Screenshot 2023-09-18 193017](https://github.com/bilaaripa/Jarkom-Modul-1-A06-2023/assets/114417418/8605ada9-1369-45b6-836a-39fe77865f3e)

## Soal 3
Dapin sedang belajar analisis jaringan. Bantulah Dapin untuk mengerjakan soal berikut:<br />
a. Berapa banyak paket yang tercapture dengan IP source maupun destination address adalah 239.255.255.250 dengan port 3702?<br />
b. Protokol layer transport apa yang digunakan?
### Penyelesaian soal 3
Langkah 1 : Copy `nc 10.21.78.111 13590` pada terminal, setelah itu akan muncul soal yang ditanyakan.<br />

Langkah 2 : Download file soal3.pcap, kemudian buka file tersebut di Wireshark. Kemudian lakukan filtering dengan `ip.addr == 239.255.255.250 && udp.port == 3702` seperti dibawah ini. 239.255.255.250 dengan port 3702.<br />
![no 3](https://github.com/bilaaripa/Jarkom-Modul-1-A06-2023/assets/91377793/6aee698f-2b12-41ba-a8ef-3c9c90f3d9cd)

Langkah 3 : Kemudian masuk ke statistic lalu ke endpoint untuk melakukan cek jumlah packet yang tercapture sehingga dapat diketahui terdapat 21 packet.<br />
<img width="951" alt="3 endpoints" src="https://github.com/bilaaripa/Jarkom-Modul-1-A06-2023/assets/91377793/7024f3e7-af36-401a-aef3-18c9c06cfc2e">

Langkah 4 : Setelah dicek dan diketahui bahwa ada sebanyak 21 packet yang tercapture, lalu input jawaban ke terminal. Setelah jawaban diinput dan benar maka akan muncul soal yang kedua yaitu protokol layer apa yang digunakan. Jawabannya telah ada di screenshoot diatas yakni menggunakan `UDP`. Setelah menginputkan jawaban kedua maka akan muncul flag untuk menjawab soal tersebut.<br />
<img width="624" alt="3" src="https://github.com/bilaaripa/Jarkom-Modul-1-A06-2023/assets/91377793/7b419847-7e74-478d-91e3-b2ffa5a1b8ca">

## Soal 4
Berapa nilai checksum yang didapat dari header pada paket nomor 130?
### Penyelesaian soal 4
Langkah 1 : Copy `nc 10.21.78.111 13591 pada terminal`. Lalu menjawab pertanyaan yang tertera dengan mendownload soal4.pcapng dan membukanya di wireshark<br />

Langkah 2 : Kemudian cari packet dengan nomor 130 dan mencari checksum pada bagian User Datagram Protocol.<br />
<img width="954" alt="line 130" src="https://github.com/bilaaripa/Jarkom-Modul-1-A06-2023/assets/91377793/3101c65a-fd8d-42df-b441-18fe1bf93d4f">
<br />
<img width="469" alt="datagram protocol" src="https://github.com/bilaaripa/Jarkom-Modul-1-A06-2023/assets/91377793/8a875961-2d5a-4fe1-848f-44dcc2cef4e2">

Langkah 3 : Kemudian masukkan nilai Checkcum yaitu `0x18e5` untuk mendapatkan flag soal tersebut.<br />
<img width="370" alt="no 4 flag" src="https://github.com/bilaaripa/Jarkom-Modul-1-A06-2023/assets/91377793/2d966980-a675-45fa-9087-136e9dc7a864">


## Soal 5
Elshe menemukan suatu file packet capture yang menarik. Bantulah Elshe untuk menganalisis file packet capture tersebut.<br />
a. Berapa banyak packet yang berhasil di capture dari file pcap tersebut?<br />
b. Port berapakah pada server yang digunakan untuk service SMTP?<br />
c. Dari semua alamat IP yang tercapture, IP berapakah yang merupakan public IP?<br />

### Penyelesaian soal 5
Pada soal no 5 belum terdapat netcat, netcat tersebut berada didalam file zip yang tertera pada soal. Maka, kita harus mencari netcat terlebih dahulu.<br />
<img width="437" alt="ziplock" src="https://github.com/bilaaripa/Jarkom-Modul-1-A06-2023/assets/91377793/493ff780-a277-4d95-9957-9c64351328a0">
<br />

Karena file zip tersebut masih terkunci dengan password, jadi kita juga harus mencari password supaya dapat unlock file zip tersebut dan mendapatkan netcat. Untuk mendapatkan password file zip tersebut, pertama yang harus dilakukan adalah mencari paket dengan protocol smtp pada file `soal5.pcap`<br />
<img width="957" alt="smtp" src="https://github.com/bilaaripa/Jarkom-Modul-1-A06-2023/assets/91377793/1ae980a5-31d4-4806-b88e-c756d606db08"><br />

Kemudian kita dapat memilih salah satu paket dan membuka TCP streamnya, setelah itu akan muncul tampilan password seperti dibawah ini : <br />
<img width="642" alt="pw" src="https://github.com/bilaaripa/Jarkom-Modul-1-A06-2023/assets/91377793/29d8f32b-07c2-479a-8810-53ecef70d960"><br />

Lalu password yang telah didapatkan di-decode dan mendapatkan hasil `5implePas5word`. Password tersebut diinputkan ke dalam file zip yang masih terkunci tadi dan didapatkan nc untuk dipakai mengerjakan soal 5.<br />
<img width="442" alt="nc 5" src="https://github.com/bilaaripa/Jarkom-Modul-1-A06-2023/assets/91377793/f501ce30-1062-4d7b-bc7d-f544e0e62489"><br />

- a. Berapa banyak packet yang berhasil di capture dari file pcap tersebut?<br />
Untuk menjawab soal ini dapat langsung membuka file `soal5.pcap` dan bisa langsung terlihat bahwa ada sebanyak 60 paket yang tercapture.<br />
<img width="959" alt="60" src="https://github.com/bilaaripa/Jarkom-Modul-1-A06-2023/assets/91377793/a11dfcb0-086d-4c28-97a2-5e1a28cf0e10"><br />

- b. Port berapakah pada server yang digunakan untuk service SMTP?<br />
Untuk Service SMTP Port yang digunakan adalah `Port 25`.<br />

- c. Dari semua alamat IP yang tercapture, IP berapakah yang merupakan public IP?<br />
Pada paket yang diberikan terdapat IP Src dan Dst. Dari kedua IP diatas yang merupakan IP Public adalah `74.53.140.153`. Karena untuk IP Private ada range tertentu seperti pada gambar dibawah ini : <br />
<img width="804" alt="ip pub" src="https://github.com/bilaaripa/Jarkom-Modul-1-A06-2023/assets/91377793/9d6d3897-f62c-4eba-8576-870df08371e0"><br />
<img width="538" alt="ip priv" src="https://github.com/bilaaripa/Jarkom-Modul-1-A06-2023/assets/91377793/1ed3b496-5584-456b-9956-0300b60da0a9"><br />

Setelah menjawab semua soal maka didapatkan flag untuk menjawab soal 5 seperti dibawah ini : <br />
<img width="371" alt="no 5" src="https://github.com/bilaaripa/Jarkom-Modul-1-A06-2023/assets/91377793/e521cdbf-51bf-4c95-a312-1fa9dc564e4e"><br />


## Soal 6
Seorang anak bernama Udin Berteman dengan SlameT yang merupakan seorang penggemar film detektif. sebagai teman yang baik, Ia selalu mengajak slamet untuk bermain valoranT bersama. suatu malam, terjadi sebuah hal yang tak terdUga. ketika udin mereka membuka game tersebut, laptop udin menunjukkan sebuah field text dan Sebuah kode Invalid bertuliskan "server SOURCE ADDRESS 7812 is invalid". ketika ditelusuri di google, hasil pencarian hanya menampilkan a1 e5 u21. jiwa detektif slamet pun bergejolak. bantulah udin dan slamet untuk menemukan solusi kode error tersebut.

### Penyelesaian soal 6
Langkah 1 : Copy `nc 10.21.78.111 13579` pada terminal, kemudian akan menampilkan soal yang diminta. Sebelumnya kita perlu melihat hint yang telah diberikan:
![Screenshot (2724)](https://github.com/bilaaripa/Jarkom-Modul-1-A06-2023/assets/114417418/c2e92659-e9e3-4a08-9f3d-f68dc5da8ba3)

Langkah 2 : Kemudian download juga `soal6-9.pcap`, lalu buka di wireshark 

Langkah 3 : Mencari packet`7812` lalu didapatakan Source Address `104.18.14.101`
![Screenshot (2727)](https://github.com/bilaaripa/Jarkom-Modul-1-A06-2023/assets/114417418/9ddea719-36d4-45d6-8fd8-6660fa96ee29)

Langkah 4 : Mari kita melihat hint yang diberikan pada soal
- Clue 1: Sepertinya ada yang salah dengan penulisan tersebut secara KBBI. Ada sesuatu yang Besar di depan mata.
- Jenis cipher merupakan substitusi a1z26 Cipher
- Rentang Huruf yang digunakan Huruf A-R, 1-18 dengan Jawaban 6 Huruf.
- SOURCE ADDRESS ADALAH KUNCI SEMUANYA.

Langkah 5
- Hint 1 kita asumsikan bahwa solusi error yang diminta menggunakan huruf kapital
- Hint 2 kita asumsikan jika angka-angka yang kita dapat nantinya akan kita conversikan kedalam sebuah huruf
- Hint 3 kita mencoba membandingan dan mengurutkan huruf dan angka sebagai berikut
-  - A = 1
-  - B = 2
-  - C = 3
-  - D = 4
-  - E = 5
-  - F = 6
-  - G = 7
-  - H = 8
-  - I = 9
-  - J = 10
-  - K = 11
-  - L = 12
-  - M = 13
-  - N = 14
-  - O = 15
-  - P = 16
-  - Q = 17
-  - R = 18
- Hint 4 kita asumsikan dengan pencocokan hint3 dengan source address sebelumnya `104.18.14.101`. 
- Caranya adalah dengan mengelompokkan source address (angka angka) tersebut sesuai dengan Hint 3 yaitu maksimal pengelompokannya pada angka 18. Maka didapatkan `10. 4. 18. 14. 10. 1`. Mengapa demikian?, Dimulai dari angka dari awal
- - `104.18.14.101` --> angka 1 terdapat pada rentang 1-18. selanjutnya angka 0 tidak, maka akan kita kelompokkan angka tersebut menjadi 10. `10.`
- - angka 4 dan 1 terdapat pada rentang 1-18. namun jika kita kelompokkan hal tersebut tidak memenuhi rentang 1-18. maka angka 4 akan berdidi sendiri. `10.4`
- - selanjutnya angka 1 dan 8 terdapat pada rentang 1-18. Angka ini dapat kita kelompokkan karena masih terdapat pada rentang 1-18, maka mennjadi 18. `10.4.18`
- - selanjutnya angka 1 dan 4 terdapat pada rentang 1-18. Angka ini dapat kita kelompokkan karena masih terdapat pada rentang 1-18, maka menjadi 18. `10.4.18.14`
- - selanjutnya angka 1 terdapat pada rentang 1-18. Selanjutnya angka 0 tidak, maka akan kita kelompokkan angka tersebut menjadi 10. `10.4.18.14.10`
- - selanjutnya angka 1 terdapat pada rentang 1-18. Karena angka 1 sisa maka langsing kita tambahkan saja. `10.4.18.14.10.1`
- Nah kita telah menemukan sebuah petunjuk `10.4.18.14.10.1`. Selanjutnya kita konversikan angka tersebut menjadi huruf kapital pada rentang 1-18 tersebut.
- Maka didapatkan **"JDRNJA"**. Jumlah hurufnya telah memenuhi yakni 6.

Hasil : Maka didapatkan kode solusi error yaitu **"JDRNJA"**
![Screenshot 2023-09-22 105313](https://github.com/bilaaripa/Jarkom-Modul-1-A06-2023/assets/114417418/3ec7ed78-ce47-4551-837c-62c3d48b326d)

## Soal 7
Berapa jumlah packet yang menuju IP 184.87.193.88?<br />

### Penyelesaian soal 7
Langkah 1 : Copy nc 10.21.78.111 6565 pada terminal, setelah itu akan muncul soal yang ditanyakan.<br />

Langkah 2 : Download file soal6-9.pcap, kemudian buka file tersebut di Wireshark. Kemudian lakukan filtering dengan `ip.dst == 184.87.193.88`. Sesuai dengan gambar dibawah ini maka didapatkan ada sebanyak `6 paket` yang menuju IP 184.87.193.88.<br />
<img width="953" alt="7" src="https://github.com/bilaaripa/Jarkom-Modul-1-A06-2023/assets/91377793/0001377a-a9f3-4676-91e7-252f44551403"><br />

Kemudian akan muncul flag untuk menjawab soal 7 seperti dibawah ini : <br />
<img width="371" alt="no 7" src="https://github.com/bilaaripa/Jarkom-Modul-1-A06-2023/assets/91377793/d715ebf2-4855-4fa6-8d53-41309e3cf7d1"><br />


## Soal 8
Berikan kueri filter sehingga wireshark hanya mengambil semua protokol paket yang menuju port 80! (Jika terdapat lebih dari 1 port, maka urutkan sesuai dengan abjad)

### Penyelesaian soal 8
Langkah 1 : Copy `nc 10.21.78.111 7171` pada terminal, setelah itu akan muncul soal yang ditanyakan. Lalu akan muncul tampilan seperti dibawah ini.

Langkah 2 : Download file soal6-9.pcap, kemudian buka file tersebut di Wireshark. Kemudian lakukan filtering dengan `tcp.dstport == 80 || udp.dstport == 80` Pernyataan ini digunakan untuk mengidentifikasi paket-paket jaringan yang memiliki port tujuan (destination port) 80 dalam protokol TCP atau UDP. Port 80 adalah port yang umumnya digunakan untuk protokol HTTP, sehingga aturan ini digunakan untuk menangkap lalu lintas jaringan yang terkait dengan komunikasi web, seperti permintaan dan respons halaman web.
![Screenshot 2023-09-18 213514](https://github.com/bilaaripa/Jarkom-Modul-1-A06-2023/assets/114417418/9a93bff1-3688-4119-bf76-584cfdab8987)

Langkah 3 : Kemudian input jawaban pada terminal dan akan muncul flag untuk menjawab pertanyaan, seperti dibawah ini.
![Screenshot 2023-09-18 194152](https://github.com/bilaaripa/Jarkom-Modul-1-A06-2023/assets/114417418/3b36ac92-ba2f-4dca-b162-3925b003f49f)

## Soal 9
Berikan kueri filter sehingga wireshark hanya mengambil paket yang berasal dari alamat `10.51.40.1` tetapi tidak menuju ke alamat `10.39.55.34`!

### Penyelesaian soal 9
Langkah 1 : Copy `nc 10.21.78.111 7272` pada terminal, setelah itu akan muncul soal yang ditanyakan. Lalu akan muncul tampilan seperti dibawah ini.

Langkah 2 : Download file soal6-9.pcap, kemudian buka file tersebut di Wireshark. Kemudian lakukan filtering dengan `ip.src == 10.51.40.1 && ip.dst != 10.39.55.34`. Ini  adalah aturan filter dalam analisis jaringan yang digunakan untuk mengidentifikasi paket-paket jaringan dengan alamat sumber (source) `10.51.40.1` dan alamat tujuan (destination) bukan `10.39.55.34`. Aturan ini digunakan untuk menangkap lalu lintas yang berasal dari alamat IP tertentu (10.51.40.1) yang tidak ditujukan ke alamat IP lainnya (10.39.55.34) dalam analisis jaringan.
![Screenshot 2023-09-18 214243](https://github.com/bilaaripa/Jarkom-Modul-1-A06-2023/assets/114417418/7a7cbf1e-e22a-4e33-8e5c-b1697e278254)

Langkah 3 : Kemudian input jawaban pada terminal dan akan muncul flag untuk menjawab pertanyaan, seperti dibawah ini.
![Screenshot 2023-09-18 200733](https://github.com/bilaaripa/Jarkom-Modul-1-A06-2023/assets/114417418/d9770a4f-a8d5-48a9-bfed-2fabc8902838)

## Soal 10
Sebutkan kredensial yang benar ketika user mencoba login menggunakan Telnet. <br />
### Penyelesaian soal 10
Langkah 1 : Copy `nc 10.21.78.111 7373` pada terminal, setelah itu akan muncul soal yang ditanyakan.<br />
Langkah 2 : Download file soal10.pcap, kemudian buka file tersebut di Wireshark. Kemudian lakukan filtering dengan telnet seperti dibawah ini.<br />
<img width="960" alt="10" src="https://github.com/bilaaripa/Jarkom-Modul-1-A06-2023/assets/91377793/0cf14def-44e2-4fd0-bb7f-7dfd28a70c66"><br />

Langkah 3 : Setelah itu untuk melihat kredensial yang benar klik kanan salah satu file lalu Follow dan pilih TCP Stream. <br />
<img width="539" alt="telnet 2" src="https://github.com/bilaaripa/Jarkom-Modul-1-A06-2023/assets/91377793/34c775d3-6075-453a-98e1-aeb0485ec364"><br />
Kemudian kredensial yang benar adalah `dhafin:kesayangannyak0k0` seperti gambar dibawah ini : <br />
![no 10](https://github.com/bilaaripa/Jarkom-Modul-1-A06-2023/assets/91377793/0d2a1a59-96ce-42df-88d0-449d848c2647)<br />


Kemudian akan muncul flag untuk menjawab soal 10.<br />
<img width="368" alt="flag 10" src="https://github.com/bilaaripa/Jarkom-Modul-1-A06-2023/assets/91377793/30c11665-4a2c-41bb-9287-7d7675c86b0c"><br />


## Kendala
1. Kami memiliki kendala pada nomor 6. Karena kami membutuhkan hint yang lebih untuk memecahkan masalah tersebut. Akan tetapi untuk mengtahui hintnya kita harus membelinya dengan point. Maka dari itu kami memilih tidak mengerjakannya terlebih dahulu
2. Pada waktu pengerjaan soal 5, ada sedikit kesulitan untuk mencari IP yang merupakan IP Public.
