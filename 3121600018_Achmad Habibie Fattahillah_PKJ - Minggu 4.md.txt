# Praktikum Komputer Jaringan



## Percobaan Menghubungkan Dua Perangkat Dengan Router



### 1. Topologi Jaringan

![Gambar 1](asset/1.png)
Terdapat dua PC yang terhubung melalui dua router

Kita buat topologi jaringan seperti gambar di atas.


### 2. Setting IP

- IP pada PC0

![Gambar 2](asset/2.png)

- IP pada PC1

![Gambar 3](asset/3.png)

- IP pada Router0 port0

![Gambar 4](asset/4.png)

- IP pada Router0 port1

![Gambar 5](asset/5.png)

- IP pada Router1 port0

![Gambar 6](asset/6.png)

- IP pada Router1 port1

![Gambar 7](asset/7.png)


### Tabel Routing Static

- Tabel routing static pada router0

![Gambar 8](asset/8.png)
Menghubungkan router0 pada jaringan 1 melalui router1 port1

- Tabel routing static pada router1

![Gambar 9](asset/9.png)
Menghubungkan router1 pada jaringa 3 melalui router0 port0


### 3. Percobaan PING

- Cek ARP cache

![Gambar 10](asset/10.png)
ARP belum menyimpan MAC Address PC1

- Dari PC0, ping PC1

![Gambar 11](asset/11.png)
Terjadi RTO dua kali, yang kemudian koneksi terhubung dan berhasil melakukan ping.

- Dari PC1, ping PC0 (Setelah ping pertama)

![Gambar 12](asset/12.png)
ARP telah disimpan, dan ketika ping tidak ada RTO sama sekali.
