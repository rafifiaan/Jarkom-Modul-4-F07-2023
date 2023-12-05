# Laporan Resmi Praktikum Jaringan Komputer Modul 4 2023

**Topic :**

Subnetting & Routing

**Identity :** 

Kelompok F07 -
Jaringan Komputer (F) </br>
*Insitut Teknologi Sepuluh Nopember*

**Authors :**
| Name                              | Student ID |
| ----------------------------------|------------|
| Arfi Raushani Fikra               | 5025211084 |
| Rafi Aliefian Putra Ramadhani     | 5025211234 |

## Information
- Subnetting & Routing Classless (VLSM) menggunakan Cisco Packet Tracer (CPT)
- Subnetting & Routing Classless (CIDR) menggunakan GNS3
- Prefix IP **10.55.x.x**

## List of Contents
- [Information](#information)
- [Topology](#topology)
  - [VLSM](#vlsm---cisco-packet-tracer-cpt)
  - [CIDR](#cidr---gns3)
- [VLSM Implementation](#vlsm-implementation)
  - [Subnet Determination](#subnet-determination)
  - [IP Tree](#tree-ip)
  - [IP Determination](#ip-determination)
  - [Node Configuration](#node-configuration)
  - [Routing](#routing)
  - [Testing](#testing)
- [CIDR Implementation](#cidr-implementation)
  - [IP Merge](#ip-merge)
  - [IP Tree](#ip-tree-1)
  - [IP Determination](#ip-determination-1)
  - [Configuration & Routing](#configuration--routing)
  - [Testing](#testing-1)
- [Obstacle](#obstacle)
---

## Topology

### VLSM - Cisco Packet Tracer (CPT)
![topoVLSM](img/Topologi%20F07%20-%20VLSM.png)

### CIDR - GNS3

![topoCIDR](img/Topologi%20F07%20-%20CIDR.png)


## VLSM Implementation
<div align=justify>
VLSM, atau Variable Length Subnet Masking, adalah teknik subnetting yang memungkinkan pengelompokan alamat IP secara efisien dengan membagi jaringan besar menjadi subnet yang lebih kecil, disesuaikan dengan kebutuhan masing-masing subnet. Keunggulan utama VLSM terletak pada kemampuannya memberikan netmask yang sesuai dengan jumlah host dalam setiap subnet, menghindari pemborosan alamat IP, dan mendukung pertumbuhan jaringan secara efisien dengan penggunaan sumber daya yang optimal. </br></br>

Dengan VLSM, administrator dapat lebih fleksibel dalam mengalokasikan alamat IP, memberikan subnet dengan ukuran yang berbeda-beda sesuai kebutuhan, dan mengurangi konsumsi alamat IP secara keseluruhan di dalam jaringan.

### Subnet Determination 

![subnetVLSM](img/Subnet%20F07%20-%20VLSM.jpeg)

### IP Tree

![treeIPVLSM](img/Tree%20F07%20-%20VLSM.png)

### IP Determination
> Pembagian IP dilakukan berdasarkan subnet yang telah ditentukan pada Topologi

![IPdetermination](img/Pembagian%20IP%20-%20VLSM.png)

### Node Configuration
**Router**

Interface dapat dilihat pada file **.pkt**

- Aura 

![aura-config](img/aura-config.png)

- Frieren

![frieren-config](img/frieren-config.png)

- Flamme

![flamme-config](img/flamme-config.png)

- Fern

![fern-config](img/fern-config.png)

- Himmel 

![himmel-config](img/himmel-config.png)

- Denken

![denken-config](img/denken-config.png)

- Eisen

![eisen-config](img/eisen-config.png)

- Lugner 

![lugner-config](img/lugner-config.png)

- Linie

![linie-config](img/linie-config.png)

- Lawine

![lawine-config](img/lawine-config.png)

- Heiter

![heiter-config](img/heiter-config.png)


**Client**

- LakeKorridor (24 Host)

![lake-config](img/lakekorridor-config.png)

- LaubHills (397 Host)

![laub-config](img/laub-config.png)

- AppetitRegion (625 Host)

![appt-config](img/appt-config.png)

- RohrRoad (1000 Host)

![rr-config](img/rohroad-config.png)

- SchwerMountains (5 Host)

![schwer-config](img/schwer-config.png)

- BredtRegion (29 Host)

![bredt-config](img/bredt-config.png)

- RiegelCanyon (510 Host)

![riegel-config](img/riegel-config.png)

- GranzChannel (254 Host)

![granz-config](img/granz-config.png)

- GrobeForest (250 Host)

![grobe-config](img/grobe-config.png)

- TurkRegion (1000 Host)

![turk-config](img/turk-config.png)

- WilleRegion (63 Host)

![wille-config](img/wille-config.png)

- RoyalCapital (63 Host)

![royalcap-config](img/royalcap-config.png)

### Routing
> Titik awal routing dimulai dari router pusat dibawah Internet yang kemudian berjalan sesuai Subnet yang telah ditentukan pada Topologi

![RoutingVLSM](img/Routing%20VLSM.png)

### Testing

Untuk membuktikan routing berjalan tidak hanya dalam 1 router atau 2 router, kami membuktikan dengan pemisalan seperti berikut:

![routingTestVLSM](img/routingtest-VLSM.png)

Paket dari `RoyalCapital` akan dikirimkan kepada `RiegelCanyon`. Berlaku pula untuk sebaliknya.

Hasilnya seperti berikut:

![testVLSM](img/resultVLSM.png)


## CIDR Implementation
<div align=justify>
CIDR, atau Classless Inter-Domain Routing, merevolusi cara alamat IP dialokasikan dan dikelompokkan di Internet. Sebelumnya, penggunaan alamat IP didasarkan pada kelas-kelas dengan ukuran tetap, mengakibatkan pemborosan. CIDR memperkenalkan pendekatan baru dengan notasi yang fleksibel, memungkinkan penggunaan yang lebih efisien dari ruang alamat IP yang tersedia.</br></br>

Contohnya, misalkan kita memiliki alamat jaringan 10.55.0.0 dengan notasi CIDR "/24". Ini berarti 24 bit pertama dari alamat tersebut digunakan sebagai netmask, mengizinkan administrator jaringan untuk menyesuaikan ukuran subnet sesuai kebutuhan tanpa batasan kelas tradisional.

Keuntungan utama CIDR termasuk efisiensi dalam penggunaan alamat IP. Misalnya, jika sebuah jaringan memerlukan 300 alamat IP, administrator dapat menggunakan CIDR untuk mengalokasikan subnet yang tepat tanpa harus memilih kelas yang lebih besar dari yang dibutuhkan.

Salah satu keunggulan besar CIDR adalah kemampuannya untuk melakukan agregasi rute. Ini memungkinkan penggabungan beberapa blok alamat IP ke dalam satu entri routing, yang secara signifikan mengurangi ukuran tabel routing di Internet. Dengan demikian, CIDR membantu meningkatkan efisiensi dalam manajemen lalu lintas jaringan global dengan menyederhanakan tabel routing.

Dengan CIDR, fleksibilitas dalam alokasi alamat IP meningkat, efisiensi penggunaan alamat IP teroptimasi, dan pengelolaan tabel routing menjadi lebih sederhana.

### IP Merge
- Subnet B

![SUBNETB1](img/CIDR%20SUBNETTING1.png)
![SUBNETB2](img/CIDR%20SUBNETTING1-1.png)

- Subnet C

![SUBNETC1](img/CIDR%20SUBNETTING2.png)
![SUBNETC2](img/CIDR%20SUBNETTING2-1.png)

- Subnet D

![SUBNETD1](img/CIDR%20SUBNETTING3.png)
![SUBNETD2](img/CIDR%20SUBNETTING3-1.png)

- Subnet E

![SUBNETE1](img/CIDR%20SUBNETTING4.png)
![SUBNETE2](img/CIDR%20SUBNETTING4-1.png)

- Subnet F

![SUBNETF1](img/CIDR%20SUBNETTING5.png)
![SUBNETF2](img/CIDR%20SUBNETTING5-1.png)

- Subnet G

![SUBNETG1](img/CIDR%20SUBNETTING6.png)
![SUBNETG2](img/CIDR%20SUBNETTING6-1.png)

### IP Determination

![CIDR-TABLE](img/CIDR-TABLE.png)

### IP Tree

![treeCIDR](img/Tree%20F07%20-%20CIDR.png)

### Configuration & Routing
- Aura
```bash
auto eth0
iface eth0 inet dhcp

auto eth1
iface eth1 inet static
	address 10.55.65.1
	netmask 255.255.255.252

auto eth2
iface eth2 inet static
	address 10.55.66.34
	netmask 255.255.255.252

auto eth3
iface eth3 inet static
	address 10.55.192.9
	netmask 255.255.255.252
```
- Frieren
```bash
auto eth0
iface eth0 inet static
	address 10.55.66.33
	netmask 255.255.255.252

auto eth1
iface eth1 inet static
	address 10.55.16.2
	netmask 255.255.255.252

auto eth2
iface eth2 inet static
	address 10.55.66.1
	netmask 255.255.255.224
```
- Flamme
```bash
auto eth0
iface eth0 inet static
	address 10.55.16.1
	netmask 255.255.255.252

auto eth1
iface eth1 inet static
	address 10.55.8.2
	netmask 255.255.255.252

auto eth2
iface eth2 inet static
	address 10.55.36.9
	netmask 255.255.255.252

auto eth3
iface eth3 inet static
	address 10.55.32.1
	netmask 255.255.252.0
```
- Fern
```bash
auto eth0
iface eth0 inet static
	address 10.55.8.1
	netmask 255.255.255.252

auto eth1
iface eth1 inet static
	address 10.55.0.1
	netmask 255.255.248.0
```
- Himmel
```bash
auto eth0
iface eth0 inet static
	address 10.55.36.10
	netmask 255.255.255.252

auto eth1
iface eth1 inet static
	address 10.55.36.1
	netmask 255.255.255.248
```
- Denken
```bash
auto eth0
iface eth0 inet static
	address 10.55.65.2
	netmask 255.255.255.252

auto eth1
iface eth1 inet static
	address 10.55.64.1
	netmask 255.255.255.0
```
- Eisen
```bash
auto eth0
iface eth0 inet static
	address 10.55.192.10
	netmask 255.255.255.252

auto eth1
iface eth1 inet static
	address 10.55.146.1
	netmask 255.255.255.252

auto eth2
iface eth2 inet static
	address 10.55.168.1
	netmask 255.255.255.252

auto eth3
iface eth3 inet static
	address 10.55.176.1
	netmask 255.255.255.252

auto eth4
iface eth4 inet static
	address 10.55.192.1
	netmask 255.255.255.248
```
- Lugner
```bash
auto eth0
iface eth0 inet static
	address 10.55.168.2
	netmask 255.255.255.252

auto eth1
iface eth1 inet static
	address 10.55.160.1
	netmask 255.255.252.0

auto eth2
iface eth2 inet static
	address 10.55.164.1
	netmask 255.255.255.0
```
- Linie
```bash
auto eth0
iface eth0 inet static
	address 10.55.146.2
	netmask 255.255.255.252

auto eth1
iface eth1 inet static
	address 10.55.136.1
	netmask 255.255.252.0

auto eth2
iface eth2 inet static
	address 10.55.144.1
	netmask 255.255.254.0
```
- Lawine
```bash
auto eth0
iface eth0 inet static
	address 10.55.136.2
	netmask 255.255.255.252

auto eth1
iface eth1 inet static
	address 10.55.132.1
	netmask 255.255.255.192
```
- Heiter
```bash
auto eth0
iface eth0 inet static
	address 10.55.132.2
	netmask 255.255.255.192

auto eth1
iface eth1 inet static
	address 10.55.128.1
	netmask 255.255.252.0
```
- Stark
```bash
auto eth0
iface eth0 inet static
	address 10.55.176.2
	netmask 255.255.255.252
	gateway 10.55.176.1
```
- Richter
```bash
auto eth0
iface eth0 inet static
	address 10.55.192.2
	netmask 255.255.255.248
	gateway 10.55.192.1
```
- Revolte
```bash
auto eth0
iface eth0 inet static
	address 10.55.192.3
	netmask 255.255.255.248
	gateway 10.55.192.1
```
- Sein
```bash
auto eth0
iface eth0 inet static
	address 10.55.128.2
	netmask 255.255.252.0
	gateway 10.55.128.1
```
- LaubHills (397 host)
```bash
auto eth0
iface eth0 inet static
	address 10.55.0.2
	netmask 255.255.248.0
	gateway 10.55.0.1
```
- AppetitRegion (625 host)
```bash
auto eth0
iface eth0 inet static
	address 10.55.3.0
	netmask 255.255.248.0
	gateway 10.55.0.1
```
- LakeKorridor (24 host)
```bash
auto eth0
iface eth0 inet static
	address 10.55.66.3
	netmask 255.255.255.224
	gateway 10.55.66.1
```
- RohrRoad (1000 host)
```bash
auto eth0
iface eth0 inet static
	address 10.55.32.2
	netmask 255.255.252.0
	gateway 10.55.32.1
```
- RoyalCapital (63 host)
```bash
auto eth0
iface eth0 inet static
	address 10.55.64.64
	netmask 255.255.255.0
	gateway 10.55.64.1
```
- WilleRegion (63 host)
```bash
auto eth0
iface eth0 inet static
	address 10.55.64.65
	netmask 255.255.255.0
	gateway 10.55.64.1
```
- TurkRegion (1000 host)
```bash
auto eth0
iface eth0 inet static
	address 10.55.160.2
	netmask 255.255.252.0
	gateway 10.55.160.1
```
- GrobeForest (250 host)
```bash
auto eth0
iface eth0 inet static
	address 10.55.164.2
	netmask 255.255.252.0
	gateway 10.55.164.1
```
- GranzChannel (254 host)
```bash
auto eth0
iface eth0 inet static
	address 10.55.144.2
	netmask 255.255.254.0
	gateway 10.55.144.1
```
- BredtRegion (29 host)
```bash
auto eth0
iface eth0 inet static
	address 10.55.132.3
	netmask 255.255.255.192
	gateway 10.55.132.1
```
- RiegelCanyon (510 host)
```bash
auto eth0
iface eth0 inet static
	address 10.55.128.3
	netmask 255.255.252.0
	gateway 10.55.128.1
```
Berikut adalah konfigurasi routing pada tiap node.
- Aura
```bash
# kiri (frieren)
route add -net 10.55.0.0 netmask 255.255.248.0 gw 10.55.66.33 # subnet A1
route add -net 10.55.8.0 netmask 255.255.255.252 gw 10.55.66.33 # subnet A2
route add -net 10.55.32.0 netmask 255.255.252.0 gw 10.55.66.33 # subnet A3
route add -net 10.55.36.8 netmask 255.255.255.252 gw 10.55.66.33 # subnet A4
route add -net 10.55.36.0 netmask 255.255.255.248 gw 10.55.66.33 # subnet A5
route add -net 10.55.16.0 netmask 255.255.255.252 gw 10.55.66.33 # subnet A6
route add -net 10.55.66.0 netmask 255.255.255.224 gw 10.55.66.33 # subnet A7

# kanan (denken)
route add -net 10.55.64.0 netmask 255.255.255.0 gw 10.55.65.2 # subnet A10

# bawah (eisen)
route add -net 10.55.176.0 netmask 255.255.255.252 gw 10.55.192.10 # subnet A12
route add -net 10.55.192.0 netmask 255.255.255.248 gw 10.55.192.10 # subnet A13
route add -net 10.55.168.0 netmask 255.255.255.252 gw 10.55.192.10 # subnet A14
route add -net 10.55.160.0 netmask 255.255.252.0 gw 10.55.192.10 # subnet A15
route add -net 10.55.164.0 netmask 255.255.255.0 gw 10.55.192.10 # subnet A16
route add -net 10.55.146.0 netmask 255.255.255.252 gw 10.55.192.10 # subnet A17
route add -net 10.55.136.0 netmask 255.255.255.252 gw 10.55.192.10 # subnet A18
route add -net 10.55.132.0 netmask 255.255.255.192 gw 10.55.192.10 # subnet A19
route add -net 10.55.128.0 netmask 255.255.252.0 gw 10.55.192.10 # subnet A20
route add -net 10.55.144.0 netmask 255.255.254.0 gw 10.55.192.10 # subnet A21
```
- Frieren
```bash
# bind everywhere
route add -net 0.0.0.0 netmask 0.0.0.0 gw 10.55.66.34

route add -net 10.55.0.0 netmask 255.255.248.0 gw 10.55.16.1 # subnet A1
route add -net 10.55.8.0 netmask 255.255.255.252 gw 10.55.16.1 # subnet A2
route add -net 10.55.32.0 netmask 255.255.252.0 gw 10.55.16.1 # subnet A3
route add -net 10.55.36.8 netmask 255.255.255.252 gw 10.55.16.1 # subnet A4
route add -net 10.55.36.0 netmask 255.255.255.248 gw 10.55.16.1 # subnet A5
```
- Flamme
```bash
# bind everyhere
route add -net 0.0.0.0 netmask 0.0.0.0 gw 10.55.16.2

route add -net 10.55.0.0  netmask 255.255.248.0 gw 10.55.8.1 # subnet A1
route add -net 10.55.36.0 netmask 255.255.255.248 gw 10.55.36.10 # subnet A5
```
- Fern
```bash
# bind everywhere
route add -net 0.0.0.0 netmask 0.0.0.0 gw 10.55.8.2
```
- Himmel
```bash
# bind everywhere
route add -net 0.0.0.0 netmask 0.0.0.0 gw 10.55.36.9
```
- Denken
```bash
# bind everywhere
route add -net 0.0.0.0 netmask 0.0.0.0 gw 10.55.65.1
```
- Eisen
```bash
# bind everywhere
route add -net 0.0.0.0 netmask 0.0.0.0 gw 10.55.192.9

route add -net 10.55.160.0 netmask 255.255.252.0 gw 10.55.168.2 # subnet A15
route add -net 10.55.164.0 netmask 255.255.255.0 gw 10.55.168.2 # subnet A16
route add -net 10.55.136.0 netmask 255.255.255.252 gw 10.55.146.2 # subnet A18
route add -net 10.55.132.0 netmask 255.255.255.192 gw 10.55.146.2 # subnet A19
route add -net 10.55.128.0 netmask 255.255.252.0 gw 10.55.146.2 # subnet A20
route add -net 10.55.144.0 netmask 255.255.254.0 gw 10.55.146.2 # subnet A21
```
- Lugner
```bash
# bind everywhere
route add -net 0.0.0.0 netmask 0.0.0.0 gw 10.55.168.1
```
- Linie
```bash
# bind everywhere
route add -net 0.0.0.0 netmask 0.0.0.0 gw 10.55.146.1

route add -net 10.55.132.0 netmask 255.255.255.192 gw 10.55.136.2 # subnet A19
route add -net 10.55.128.0 netmask 255.255.252.0 gw 10.55.136.2 # subnet A20
```
- Lawine
```bash
# bind everywhere
route add -net 0.0.0.0 netmask 0.0.0.0 gw 10.55.136.1

route add -net 10.55.128.0 netmask 255.255.252.0 gw 10.55.132.2 # subnet A20
```
- Heiter
```bash
# bind everywhere
route add -net 0.0.0.0 netmask 0.0.0.0 gw 10.55.132.1
```

### Testing
Dari `RoyalCapital` menuju ke `Seins`

![routingtestCIDR](img/routingtest-CIDR.png)

![CIDRTest](img/CIDR-TEST.png)

## Obstacle
- Perlu belajar lebih lama tentang CIDR, sehingga belum dapat melakukan Implementasi
- Perlu belajar Implementasi CIDR pada platform GNS3 juga, menurut saya lebih mudah menggunakan Cisco Packet Tracer (CPT)  