# Wireshark
Wireshark adalah network analyzer untuk menganalisa paket bebas dan sumber terbuka. Digunakan untuk pemecahan masalah jaringan, analisis, software dan pengembangan protokol komulikasi, dan pendidikan.

## Color rule di Wireshark
Color rule digunakan untuk memudahkan analisa. Klasifikasi kode warna antara lain sebagai berikut:

| Warna      | Jenis Paket |
| ----------- | ----------- |
| Light Purple      | TCP       |
| Light Blue   | UDP        |
| Black   | Paket dengan kesalahan        |
| Light Green   | Trafic HTTP        |
| Light Yellow   | Lalu lintas khusus Windows, termasuk Server Message Blocks (SMB) dan NetBIOS       |
| Dark Yellow   | Rute        |
| Red   | Display Filter Invalid    |
| Dark Gray   | TCP SYN, FIN dan ACK lalu lintas        |
| Black   |   |

![](https://www.wireshark.org/docs/wsug_html_chunked/wsug_graphics/ws-coloring-rules-dialog.png)

## Tracking Jalur ICMP pada Packet Analyzer
### - Cek IP Address dan Default Gateway
![](https://cdn.discordapp.com/attachments/589417117544218629/1019082297481371689/Screenshot_169.png)
### - Ping Default Gateway
![](https://cdn.discordapp.com/attachments/589417117544218629/1019082297829511219/Screenshot_170.png)
Default Gateway (192.168.100.1) di ping dari komputer (192.168.100.49). Proses ping berhasil dan ping mendapat balasan. 
### - Cek Wireshark dengan filter icmp
![](https://cdn.discordapp.com/attachments/589417117544218629/1019082298269892608/Screenshot_167.png)
Ping dilakukan sebanyak 4 kali, dan terekam ping request juga sebanyak 4 kali di Wireshark.
### - Cek Header ICMP
![](https://cdn.discordapp.com/attachments/589417117544218629/1019082298609643580/Screenshot_166.png)
Version : Lalu lintas melalui IPv4
Header Length: Panjang header IP 20 bytes
Protocol ICMP: Protokol yang digunakan adalah ICMP
Src: 192.168.100.49, Dst: 192.168.100.1: Dilakukan request ping dari IP address local computer ke default gateway.

## Kesimpulan
Internet Control Message Protocol / ICMP adalah merupakan salah satu protokol inti dari protokol jaringan internet yang digunakan terutama untuk sistem operasi komputer jaringan untuk mengirim pesar error.

ICMP berbeda dengan TCP dan UDP karena ICMP tidak secara langsung digunakan oleh aplikasi jaringan pengguna, kecuali pada aplikasi ping yang mengirim ICMP Echo Request untuk menentukan apabila komputer tujuan available dan jangka waktu balasan dari komputer tujuan
