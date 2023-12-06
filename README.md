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

Selain itu, antar client yang berjauhan juga bisa melakukan `ping` satu sama lain. Berikut merupakan hasil testingnya:

![testing_vlsm_client](https://i.ibb.co/ZHLzb9w/Screenshot-2023-12-06-202420.png)

## CIDR
### Langkah 1 

![topologi](https://github.com/nathaniaelirica/Jarkom-Modul-4-IT21-2023/assets/67095933/e3e1be19-55c8-4e86-b110-1cde668f3583)

### Langkah 2

![rute](https://i.ibb.co/m9BjVf6/image.png)

### Langkah 3

![rute](https://i.ibb.co/0Y5vwdy/image.png)

### Langkah 4

![rute](https://i.ibb.co/vBtW8t0/image.png)

### Langkah 5

![rute](https://i.ibb.co/4PhMb0T/image.png)

### Langkah 6

![rute](https://i.ibb.co/zPWGCdX/image.png)

### Langkah 7

![rute](https://i.ibb.co/0DkLjqF/image.png)

### Langkah 7

![rute](https://i.ibb.co/0DkLjqF/image.png)

### Langkah 8

![rute](https://i.ibb.co/pJfYNYm/image.png)

### Langkah 9

![rute](https://i.ibb.co/njqsHFf/image.png)

### Hasil Tabel Gabungan A

![rute](https://i.ibb.co/CM6qJBL/image.png) 

### Hasil Tabel Gabungan B

![rute](https://i.ibb.co/jb2yPDK/image.png) 

### Hasil Tabel Gabungan C

![rute](https://i.ibb.co/NVLnZNS/image.png) 

### Hasil Tabel Gabungan D

![rute](https://i.ibb.co/jh51Zn0/image.png) 

### Hasil Tabel Gabungan E

![rute](https://i.ibb.co/vQmPRhq/image.png) 

### Hasil Tabel Gabungan F

![rute](https://i.ibb.co/WHCb4GP/image.png) 

### Hasil Tabel Gabungan G

![rute](https://i.ibb.co/kS1bsht/image.png) 

### Hasil Tabel Gabungan H

![rute](https://i.ibb.co/kS1bsht/image.png) 

### Hasil Tabel Gabungan I

![rute](https://i.ibb.co/XXbs4sQ/image.png) 

### Pembagian IP

![rute](https://i.ibb.co/DMyzHnp/image.png) 

### Konfigurasi di topologi
#### Aura
```
auto eth0
iface eth0 inet dhcp

#Aura-Denken
auto eth2
iface eth2 inet static
	address 10.75.0.129
	netmask 255.255.255.252

#Aura-Eisen
auto eth1
iface eth1 inet static
	address 10.76.128.1
	netmask 255.255.255.252

#Aura-Frieren
auto eth3
iface eth3 inet static
	address 10.74.128.1
	netmask 255.255.255.252
 ```

#### Aura
```
auto eth0
iface eth0 inet dhcp

#Aura-Denken
auto eth2
iface eth2 inet static
	address 10.75.0.129
	netmask 255.255.255.252

#Aura-Eisen
auto eth1
iface eth1 inet static
	address 10.76.128.1
	netmask 255.255.255.252

#Aura-Frieren
auto eth3
iface eth3 inet static
	address 10.74.128.1
	netmask 255.255.255.252
 ```
#### Aura
```
auto eth0
iface eth0 inet dhcp

#Aura-Denken
auto eth2
iface eth2 inet static
	address 10.75.0.129
	netmask 255.255.255.252

#Aura-Eisen
auto eth1
iface eth1 inet static
	address 10.76.128.1
	netmask 255.255.255.252

#Aura-Frieren
auto eth3
iface eth3 inet static
	address 10.74.128.1
	netmask 255.255.255.252
 ```

#### Denken

```
#Denken-Aura
auto eth0
iface eth0 inet static
	address 10.75.0.130
	netmask 255.255.255.252

#Denken-Switch-RoyalCapital-Switch-WileRegion
auto eth1
iface eth1 inet static
	address 10.75.0.1
	netmask 255.255.255.128
 ```

#### Royal Capital

```
auto eth0
iface eth0 inet static
	address 10.75.0.2
	netmask 255.255.255.128
    gateway 10.75.0.1
 ```
#### Wille Region

```
#WilleRegion
auto eth0
iface eth0 inet static
	address 10.75.0.3
	netmask 255.255.255.128
    gateway 10.75.0.1
 ```

#### Eisen

```
#A11 Aura-Eisen
auto eth0
iface eth0 inet static
	address 10.76.128.1
	netmask 255.255.255.252

#Eisen-Linie
auto eth1
iface eth1 inet static
	address 10.74.80.1
	netmask 255.255.255.252

#Eisen-Switch0-Stark
auto eth2
iface eth2 inet static
	address 10.76.16.1
	netmask 255.255.255.252

#Eisen-Switch1-Richter-Switch1-Revolte
auto eth3
iface eth3 inet static
	address 10.76.32.1
	netmask 255.255.255.248

#Eisen-Lugner
auto eth4
iface eth4 inet static
	address 10.76.8.1
	netmask 255.255.255.252
 ```
#### Stark

```
#Stark 
auto eth0
iface eth0 inet static
	address 10.76.16.1
	netmask 255.255.255.252
 ```
#### Lugner 

```
#Eisien-Lugner
auto eth0
iface eth0 inet static
	address 10.76.8.1
	netmask 255.255.255.252

#Lugner-Switch10-TurkRegion
auto eth1
iface eth1 inet static
	address 10.76.0.1
	netmask 255.255.252.0

#A16 Lugner-Switch9-GrobeForest
auto eth2
iface eth2 inet static
	address 10.76.4.1
	netmask 255.255.255.0
 ```
#### Turk Region

```
auto eth0
iface eth0 inet static
	address 10.76.0.2
	netmask 255.255.252.0
    gateway 10.76.0.1
 ```

#### Grobe Forest

```
auto eth0
iface eth0 inet static
	address 10.76.4.2
	netmask 255.255.255.0
    gateway 10.76.4.1
 ```
#### Ritcher 

```
auto eth0
iface eth0 inet static
	address 10.76.32.2
	netmask 255.255.255.248
 ```
#### Revolte

```
auto eth0
iface eth0 inet static
	address 10.76.32.2
	netmask 255.255.255.248
 ```
#### Frieren 

```
auto eth0
iface eth0 inet static
	address 10.76.32.2
	netmask 255.255.255.248
 ```
#### Frieren 

```
#Frieren-Aura
auto eth0
iface eth0 inet static
	address 10.74.128.1
	netmask 255.255.255.252

#Flamme-Frieren
auto eth1
iface eth1 inet static
	address 10.74.32.1
	netmask 255.255.255.252

#Frieren-Switch3-LakeKorridor
auto eth2
iface eth2 inet static
	address 10.74.64.1
	netmask 255.255.255.224
 ```

#### LaubHills
```
auto eth0
iface eth0 inet static
	address 10.74.0.1
	netmask 255.255.255.0
```

#### Routing
#### Eisen
```route add -net 10.76.0.0 netmask 255.255.252.0 gw 10.76.0.1```
#### Frieren
```route add -net 0.0.0.0 netmask 0.0.0.0 gw 10.74.128.1```
#### Lugner
```route add -net 0.0.0.0 netmask 0.0.0.0 gw 10.76.8.1```

### Hasil Ping

![rute](https://i.ibb.co/fnZDxXc/image.png) 

