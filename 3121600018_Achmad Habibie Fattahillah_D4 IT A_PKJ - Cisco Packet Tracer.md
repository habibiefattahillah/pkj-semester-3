# Analisis Konsep Address Resolution Protocol (ARP)
Untuk analisis ARP, digunakan Cisco Packet Tracer. Dibentuk struktur seperti berikut: 

- PC 0 dengan ip 192.168.1.1
- PC 1 dengan ip 192.168.1.2
- PC 2 dengan ip 192.168.1.3

[![1.png](https://i.postimg.cc/mgzSMJn7/1.png)](https://postimg.cc/bZPbfCpv)

Lalu disetting filter sesuai berikut:

[![3.png](https://i.postimg.cc/FKH6JNSG/3.png)](https://postimg.cc/sMbmkFwZ)

- Proses pengirim paket terjadi pada layer ke 2 (Network Layer) dan ke 3 (Data Link Layer). 
- ARP adalah protokol dalam TCP/IP Protocol Suite yang bertanggung jawab untuk melakukan resolusi alamat IP ke dalam alamat Media Access Control. 
- Broadcast adalah alamat jaringan yang digunakan untuk mengirimkan ke semua perangkat yang terhubung ke jaringan komunikasi akses jamak. Pesan yang dikirim ke alamat broadcast dapat diterima oleh semua host yang terhubung ke jaringan.

## Skenario Pertama, P0 ke P1

Cek apabila ARP memiliki cache
- arp -a

# [![5.png](https://i.postimg.cc/WzcyfrDb/5.png)](https://postimg.cc/62zz88LD)

Bisa dilihat ARP masih kosong, oleh karena itu proses enkapsulasi tidak bisa dilakukan secara langsung Untuk memenuhi proses enkapsulasi, diperlukan MAC address dari PC yang dituju. Oleh karena itu, perlu dilakukan broadcast yang akan mencari semua device yang terhubung berdasarkan MAC addres.

Dilakukan proses ping tanpa ARP cache :
- Proses Ping memulai permintaan ping berikutnya.
- Proses Ping membuat pesan ICMP Echo Request dan mengirimkannya ke layer yang lebih rendah.
- Alamat IP sumber tidak ditentukan. Perangkat menyetelnya ke alamat IP port.
- Alamat IP tujuan berada di subnet yang sama. Perangkat mengatur hop berikutnya ke tujuan.
- Proses ARP membuat permintaan untuk alamat IP target.
- Perangkat merangkum PDU ke dalam bingkai Ethernet.

[![6.png](https://i.postimg.cc/B6cqp2N4/6.png)](https://postimg.cc/ftynTt6r)

Lalu, akan didapatkan Frame Packet dari MAC Address yang di tuju dan MAC Address yang bukan dari tujuan akan di drop, yang kemudian di broadcast kembali oleh penerima MAC Address tujuan mengenai hal yang sama yang kemudian diterima oleh PC 0.

- arp -a
# [![13.png](https://i.postimg.cc/Y9qpXhPF/13.png)](https://postimg.cc/SX3FRNkQ)

Jadi, perlu dilakukan broadcast.

## Skenario Kedua, P0 ke P1 Apakah Terjadi Broadcast Lagi ?

Cek ARP Cache
- arp &ndash;a
# [![13.png](https://i.postimg.cc/Y9qpXhPF/13.png)](https://postimg.cc/SX3FRNkQ)
Bisa dilihat apabila tersimpan ARP untuk PC1

Lalu dilihat layernya
# [![16.png](https://i.postimg.cc/TYhKpy2h/16.png)](https://postimg.cc/F75r6HLQ)
Bisa dilihat pada layer 3 dest IP ICMP sudah langsung tersedia

Jadi, tidak perlu dilakukan broadcast lagi.

## Skenario Ketiga, P1 ke P0 apakah perlu broadcast (Setelah ada ARP)?
Pada proses yang pertama, dilakukan dua kali broadcast : 
- Dari PC0 ke PC1
- Dari PC1 ke PC0
Oleh karena itu, ARP juga sudah menyimpan reply dari PC1.

Cek ARP pada pc 1
- arp -a
# [![17.png](https://i.postimg.cc/SxFY3Sqs/17.png)](https://postimg.cc/8j4CrV7Q)
Bisa dilihat PC1 juga memiliki ARP Cache

Jadi, tidak perlu dilakukan broadcast.


