# Praktikum Modul 4 Jarkom 2023
| Nama                           | NRP      |
|--------------------------------|-------------|
| Maria Teresia Elvara Bumbungan | 5027211042  |
| Nathania Elirica Aliyah        | 5027211057  |

## Soal
![Screenshot 2023-11-28 235649](https://github.com/nathaniaelirica/Jarkom-Modul-4-IT21-2023/assets/67095933/b2978741-2b14-4d4e-8a4d-bcfec498d868)

Soal dikerjakan pada Cisco Packet Tracer dan GNS3 menggunakan metode perhitungan CLASSLESS yang berbeda.

Maka dari itu, pada praktikum ini kami menggunakan metode **VLSM di CPT** dan **metode CIDR di GNS3.**

## Subnet dan Rute
Berikut merupakan pembagian subnet dan rute untuk tiap subnet yang telah kami tentukan:

### Pembagian Subnet
![topologi](https://github.com/nathaniaelirica/Jarkom-Modul-4-IT21-2023/assets/67095933/e3e1be19-55c8-4e86-b110-1cde668f3583)

### Penetuan Rute
![rute](https://i.ibb.co/LhhhKf8/rute-modul-4.png)

Jumlah IP ditentukan dari jumlah host yang ada untuk tiap subnet. Untuk router dengan router, jumlahnya adalah 2. Sementara itu, untuk client yang terhubung dengan router melalui switch dihitung dengan menjumlah jumlah host ditambah 1.

Sebagai contoh, untuk menghitung jumlah IP pada subnet A1 adalah 625 (AppetitRegion) ditambah 397 (LaubHills) ditambah 1 (Fern) sehingga jumlah IP-nya adalah 1023.

## VLSM
Dari penentuan length untuk tiap rute, dapat dibuat tree dari subnet besar dengan network ID **10.74.0.0** dan netmask **/19.** Setelah dibuat tree, dibuat subnetting dari jumlah IP terbesar yaitu, subnet A1. Berikut merupakan tree-nya:

![tree_vlsm](https://i.ibb.co/3Cs15sT/IT21-VLSM-Tree.png)

Selanjutnya, dapat dibuat pembagian IP untuk tiap subnet beserta range IP-nya. Berikut merupakan pembagiannya:

![ip_vlsm](https://i.ibb.co/3dJr3ML/pembagian-ip-vlsm.png)

Setelah itu, dilakukan konfigurasi untuk tiap node sesuai dengan range IP yang ada di tabel sebelumnya. Lalu, baru dilakukan routing agar tiap client bisa terhubung ke router Aura. Berikut merupakan routing yang digunakan:

![routing_vlsm](https://i.ibb.co/mvLYZmT/routing-vlsm.png)

Setelah routing telah dilakukan di tiap router, dapat dilakukan testing dengan melakukan `ping` dari client ke router Aura. Berikut merupakan hasil testingnya:

![testing_vlsm](https://i.ibb.co/DLkv2f0/ping-modul-4.png)

Dari hasil di atas, dapat dilihat bahwa routing telah berhasil dilakukan karena seluruh client dapat melakukan `ping` ke router Aura.

## CIDR
### Langkah 1 

![rute](https://i.ibb.co/LhhhKf8/rute-modul-4.png)

### Langkah 2

![rute](https://i.ibb.co/m9BjVf6/image.png)

### Langkah 3

![rute](https://i.ibb.co/0Y5vwdy/image.png)

### Langkah 4

![rute](https://i.ibb.co/vBtW8t0/image.png)

### Langkah 5

![rute](https://i.ibb.co/4PhMb0T/image.pn)

### Langkah 6

![rute](https://i.ibb.co/zPWGCdX/image.png)

### Langkah 7

![rute](https://i.ibb.co/0DkLjqF/image.png)

### Langkah 7

![rute](https://i.ibb.co/0DkLjqF/image.png)

### Langkah 8

![rute](https://i.ibb.co/pJfYNYm/image.png)
