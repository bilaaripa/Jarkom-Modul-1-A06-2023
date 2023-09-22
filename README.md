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

Langkah 4 : Setelah dicek dan diketahui bahwa ada sebanyak 21 packet yang tercapture, lalu input jawaban ke terminal. Setelah jawaban diinput dan benar maka akan muncul soal yang kedua yaitu protokol layer apa yang digunakan. Jawabannya telah ada di screenshoot diatas yakni menggunakan UDP. Setelah menginputkan jawaban kedua maka akan muncul flag untuk menjawab soal tersebut.<br />
<img width="624" alt="3" src="https://github.com/bilaaripa/Jarkom-Modul-1-A06-2023/assets/91377793/7b419847-7e74-478d-91e3-b2ffa5a1b8ca">

## Soal 4
### Penyelesaian soal 4

## Soal 5
### Penyelesaian soal 5

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
