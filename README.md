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

## Soal 1

User melakukan berbagai aktivitas dengan menggunakan protokol FTP. Salah satunya adalah mengunggah suatu file.
- Berapakah sequence number (raw) pada packet yang menunjukkan aktivitas tersebut? 
- Berapakah acknowledge number (raw) pada packet yang menunjukkan aktivitas tersebut? 
- Berapakah sequence number (raw) pada packet yang menunjukkan response dari aktivitas tersebut?
- Berapakah acknowledge number (raw) pada packet yang menunjukkan response dari aktivitas tersebut?

### Penyelesaian soal 1
Langkah 1 : Copy `nc 10.21.78.111` 12345 pada terminal, kemudian akan menampilkan soal yang diminta

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

Setelah menjawab semua soal maka didapatkan flag untuk menjawab soal 5 seperti dibawah ini : <br />
<img width="371" alt="no 5" src="https://github.com/bilaaripa/Jarkom-Modul-1-A06-2023/assets/91377793/e521cdbf-51bf-4c95-a312-1fa9dc564e4e"><br />


## Soal 6
### Penyelesaian soal 6

## Soal 7
### Penyelesaian soal 7

## Soal 8
### Penyelesaian soal 8

## Soal 9
### Penyelesaian soal 9

## Soal 10
### Penyelesaian soal 10
