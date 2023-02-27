# Praktikum-Keamanan-Informasi-kelas-A

# **`LAB 1`**
Lab 1 merupakan lanjutan dari pertemuan sebelumnya (pertemuan 1) di mana pada laporan belum ditambahkan langkah untuk mematikan VM menggunakan perintah Linux. Saat menggunakan perintah linux, ketik **sudo shutdown -h now** lalu enter kemudian pengguna dipinta untuk memasukkan password, tambahan now diletakkan agar VM langsung mati setelah pengguna memasukkan password VM-nya.

# **`LAB 2`**
1. Perintah **man nmap** digunakan untuk mengetahui informasi tentang nmap, seperti pengertian, manfaat, perintah-perintah yang terdapat di dalamnya, dan lain-lain. Tekan q untuk keluar dari halaman _Nmap Reference Guide_.
2. Perintah **nmap -A -T4 localhost** digunakan untuk mengetahui informasi tentang port dan layanan yang terbuka serta software yang digunakan pada port yang terbuka tersebut. Pada praktikum, ada dua port yang terbuka yakni 21/tcp, 22/tcp, dan 23/tcp dengan layanan masing-masing ftp, ssh, dan telnet menggunakan software vsftpd 2.0.8, OpenSSH 8.2 (protocol 2.0), dan Openwall GNU/*/Linux/ telnetd.
3. Sebelum melakukan network scanning, disarankan untuk mengetahui alamat ip host terlebih dahulu, gunakan perintah **ip address**, maka akan muncul beberapa address seperti ipv4 dan ipv6, gunakan ip inet bagian bawah untuk melakukan port scanning lalu ketik perintah **nmap -A -T4 [alamat_ip]**, pada praktikum diketahui bahwa alamat ip-nya adalah 10.0.2.0/24 maka perintah yang digunakan dalam praktikum ini adalah **nmap -A -T4 10.0.2.15/24**.
4. Kali ini melakukan remote server scanning pada alamat website www.scanme.nmap.org. Sebelum melakukannya, buka lebih dahulu website tersebut pada web browser linux lalu ketik perintah **nmap -A -T4 scanme.nmap.org** pada terminal linux. Akan muncul macam informasi seperti port, layanan, alamat ip server, sistem operasi yang digunakan server, dan lain semacamnya. Saat praktikum diketahui bahwa port yang terbuka adalah 22/tcp, 25/tcp, 53/tcp, 80/tcp, 9929/tcp, dan 31337/tcp dengan layanan secara berurut yaitu ssh, smtp, domain, http, nping-echo, dan tcpwrapped. IP address host yang diketahui dari praktikum adalah 45.33.32.156 dan menggunakan sistem operasi Linux.

# **`LAB 3`**
1. Login VM dan masukkan password. Karena sudah dilakukan sebelum mengerjakan lab 1 maka tidak perlu diulang kembali.
2. Perintah **sudo tcpdump –i enp0s3 –s 0 –w httpdump.pcap** digunakan untuk mengetahui jumlah paket yang diterima oleh filter.
3. Pada poin 3, diperintahkan untuk membuka link http://www.altoromutual.com/login.jsp melalui web browser VM. Setelah link dibuka, periksa pada file manajer dengan alamat folder /home/analyst/ apakah terdapat file bernama httpdump.pcap, klik file kemudian buka aplikasi Wireshark yang ada di dalam file. Lakukan filter http, tunggu sampai terlihat barisan informasi, cari yang memiliki keterangan info POST. Saat memilih POST akan diketahui uid dan password yang digunakan. Untuk merekam paket HTTP digunakan perintah **sudo tcpdump –i enp0s3 –s 0 –w httpdump.pcap** (pada file hasil project terjadi kesalahan pengetikan perintah).
4. Setelah selesai melakukan perekaman paket HTTP, saatnya untuk melakukannya pada paket HTTPS. Website HTTPS yang digunakan pada praktikum adalah https://www.netacad.com/ dan dibutuhkan login berpassword untuk dapat membuka website. Temukan file httpsdump.pcap pada folder /home/analyst/ kemudian buka dan lakukan filter tcp.port==443. Pilih Application Data untuk mengetahui kode enkripsinya.
