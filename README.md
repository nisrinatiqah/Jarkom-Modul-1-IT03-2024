# Laporan Resmi Praktikum Jarkom 2024 Modul-1

---

### Anggota Kelompok IT 03 :

- Nicholas Arya Krisnugroho Rerangin (5027231058)
- Nisrina Atiqah Dwiputri Ridzki (5027231075)

# Daftar Isi

- [Advance Sanity Check](#advance-sanity-check)
- [Illegal Breakthrough](#illegal-breakthrough)
- [FTP Login](#ftp-login)
- [Suprise](#surprise)
- [Corporate Breach](#corporate-breach)
- [EZ](#ez)
- [Rizzset](#rizzset)



---
## Advance Sanity Check
---
### Flag 
JarkomIT{8uK4n_S4n1ty_b1a5A_bdn4Detuf541FMl1x30hSjSRCSu5ADKKZvHn0ZOZ3x1O2HzLW5SftIKK}

### Penjelasan
1. Buka Statistic > Protocol Hierarchy. Cari yang percentage bytes nya paling tinggi, ditemukan bahwa yang Hypertext Transfer Protocol (http) yang paling tinggi
2. Filter http dan buka follow > http stream
3. Untuk username ditemukan di stream slide ketiga yaitu JaneD03
4. Lalu diminta mencari namefile.extension, langsung terlihat di slide keempat stream nya yaitu Clue3.txt
5. Di stream keempat itu juga terdapat pesan rahasia yang diarahkan ke ppt peraturan praktikum jarkom di slide bagian soal shift.
6. Terdapat code cGVud29yZA==
7. Terjemahkan dari code Base64 dan hasilnya "penword". Flag telah ditemukan!

### Dokumentasi Pengerjaaan
- Username
  ![WhatsApp Image 2024-09-22 at 14 08 16_620136c9](https://github.com/user-attachments/assets/2a588614-b1e9-48c2-adc6-dd1bf83f29e4)

- File
  ![WhatsApp Image 2024-09-22 at 13 51 05_a2049ba5](https://github.com/user-attachments/assets/458e7dca-275c-4286-8454-fd51d027b262)

- Pesan Rahasia
  ![WhatsApp Image 2024-09-22 at 13 51 05_1263534e](https://github.com/user-attachments/assets/6011be20-77b5-4e11-9153-f5824eb93258)
  
  ![Screenshot 2024-09-22 132326](https://github.com/user-attachments/assets/ef3ce2ec-25a1-41b1-9500-8b76e11add7c)
  
  ![WhatsApp Image 2024-09-22 at 14 08 16_8b9b04e0](https://github.com/user-attachments/assets/2163fa2d-2ed6-4ef8-a78c-e0e28fa00cf5)



---
## Illegal Breakthrough
---
### Deskripsi
Seorang full-stack developer bernama kevin sedang membuat sebuah web yang memiliki login page. Tetapi karena ia hanya digaji rendah, ia lupa untuk mengamankan web yang ia buat. Bantulah kevin untuk tracing dari jejak yang ditinggalkan oleh attacker.

### Flag
JarkomIT{d34th_fr0m_th3_sky_ujnhBlSSgFrizPCi7uDFWxfHNH1ykEKkXxSvbZpjeAVKenC4XRnsWW1}

### Penjelasan 
1. Buka Analyze > Follow > TCP Stream
2. IP Address Korban: Setelah beberapa kali mencoba, ditemukan bahwa IP korban adalah 172.21.88.207.
3. Port Webserver: Port yang digunakan oleh webserver korban adalah 1917.
4. Tools yang Digunakan Attacker: Setelah mencoba beberapa tool, penyerang menggunakan Fuzz Faster U Fool (ffuf) versi v2.1.0-dev.
5. Setelah itu ditemukannya bahwa Username: admin,  Password: fMyqjdC43

### Dokumentasi Pengerjaan

- ![WhatsApp Image 2024-09-19 at 00 47 47_e86ec266](https://github.com/user-attachments/assets/f5afde85-bc2a-4cc4-a256-aed50fb930d1)

- ![WhatsApp Image 2024-09-18 at 23 05 48_1fde54df](https://github.com/user-attachments/assets/e8b770ac-4cb6-4aa1-a82e-50b57ef17f54)

- ![WhatsApp Image 2024-09-19 at 00 47 47_e865c3de](https://github.com/user-attachments/assets/73a20309-c305-4da3-8667-748af405672c)



---
## Packets Barrage
---
Setelah membantu kevin untuk tracing attacker, sekarang bantu lagi kevin untuk mencari apa yang dilakukan oleh attacker.
File sama seperti Illegal Breakthrough.

### Flag
### Penjelasan
### Dokumentasi Pengerjaan



---
## FTP Login
---
Seseorang menemukan sebuah celah dalam sebuah server. Ia mencoba untuk melakukan brute force login dan ia berhasil masuk. Lakukan pemeriksaan untuk melihat apa yang dilakukan oleh orang tersebut!

### Flag
JarkomIT{n0t_s0_s3cur3_ftp_Ga1QFVuduiIMivZHvHaruQtsEL0VuCqOCWISuOAehGh0ttrovDrxG1N}

### Penjelasan 
1. Buka file PCAP dan gunakan filter ftp untuk melihat percobaan login FTP.
2. Gunakan filter ftp.request.command == "USER" dan ftp.request.command == "PASS".
3. Setelah beberapa kali mencoba, username yang benar adalah sn4k3y dan password supersn1ff3r.
4. Setelah login berhasil, flag yang ditemukan adalah JarkomIT{n0t_s0_s3cur3_ftp_Ga1QFuviudiMizVHyHaruQtSEl0VuCqOCWISuoAehGHottr0vDrxG1N}

### Dokumentasi Pengerjaan

- ![ftploginn](https://github.com/user-attachments/assets/4b0a3ce0-78ac-4615-8b91-9a6a271a800e)



---
## Surprise
---
### Deskripsi
Setelah mengetahui apa yang diketahui pada challenge sebelumnya, sekarang lakukan analisis untuk mengetahui apa yang sebenarnya terjadi.
File sama seperti FTP Login.

### Flag
JarkomIT{l1ttl3_m0us3_1n_th3_h0us3_GZukOIsxbZXnTC6nybWtwpa6PG0EwV7Fr4KVPdR6Foky9fCZVTIJTCHU}

### Penjelasan 
1. Buka file PCAP dan gunakan filter ftp untuk menganalisis percakapan FTP.
2. Identifikasi data yang dikirim melalui protokol FTP.
3. Dengan menganalisis traffic, kita bisa mengetahui service yang digunakan oleh server FTP. Dari data yang ada, service tersebut adalah vsFTPd 3.0.3.
4. Gunakan filter untuk melihat file transfer yang terjadi. Berdasarkan hasil filter, file yang dikirim adalah h4lo_world.txt.

### Dokumentasi Pengerjaan

- ![surprise](https://github.com/user-attachments/assets/d26bafde-0411-4783-a917-91255a658e8b)




---
## Corporate Breach
---
### Deskripsi
Sebuah perusahaan IT support mendapatkan serangan oleh orang tidak dikenal. Bantulah perusahaan tersebut untuk melacak jejak yang ditinggalkan oleh attacker.

### Flag
JarkomIT{supp0rt_k0k_l3m4h_bg_v8CT00tWiKLnufX5HNXFOOMsvG6RTEzIuFa4BhPXImZ68pDXjnGvG6}

### Penjelasan 
1. Buka Analyze > Follow > TCP Stream = Langsung terlihat di stream pertama terdapat text "Hello, my name is Nakhimov and I'm here trying to get in to your system. I'm sorry, but your system is too weak for me. I'm in." Bisa terlihat bahwa nama attacker adalah Nakhimov.
2. Buka slide stream selanjutnya dan coba coba email yang muncul
3. Setelah di slide stream 207 terdapat tulisan "email=jarkomsupport%40gmail.com&password=j4rk0mg4c0rbg". Sehingga didapat emailnya jarkomsupport@gmail.com (hilangkan %40) dan passwordnya j4rk0mg4c0rbg. Flag langsung muncul!

### Dokumentasi Pengerjaan

- ![WhatsApp Image 2024-09-18 at 23 59 30_962951cc](https://github.com/user-attachments/assets/c184343f-b818-4d91-b326-903f7521a989)

- ![WhatsApp Image 2024-09-19 at 00 00 14_34beb25b](https://github.com/user-attachments/assets/ad651566-d340-4e1e-a234-37fab471d9e7)

- ![WhatsApp Image 2024-09-18 at 23 05 47_4efe54c7](https://github.com/user-attachments/assets/0e628c05-2ded-42dd-9b00-7b89fd713368)



---
## Pegawai Negeri Sebelah
---
Kamu seorang data analisis diminta untuk memastikan ulang data-data dari beberapa pegawai.

### Flag
JarkomIT(TumdeN_p455nYa_Kust BlaS4Nya_DGYEneWuK6ZLfbfTapMERPNAOL35hBROAG La1Mp0XZ6sZWCTSRKKM4H

### Penjelasan
1.  Buka Analyze > Follow > TCP Stream. Terlihat bahwa banyak nama, password, dan jabatan dari masing-masing orang.
2.  Cara saya untuk mencari semua jawaban dari pertanyaan saya menggunakan fitur Find yang ada dibawah.
3.  Siapa yang memiliki password nNnM%coQuF? = Vero Tampubolon
4.  Apa jabatan dari Taufan Kuswandari? = Analis Kebijakan
5.  Siapa yang paling awal di list? = Cici Mustofa
6.  Apa password paling akhir di list? = RyxaJPv^yF

### Dokumentasi Pengerjaan
- ![WhatsApp Image 2024-09-22 at 13 51 05_a0f71734](https://github.com/user-attachments/assets/d9137646-c410-4ac0-acbc-ddcb4a508492)
  
- ![WhatsApp Image 2024-09-22 at 13 51 05_04cac21d](https://github.com/user-attachments/assets/fcfabf91-3456-45c9-aff6-127c7ce1e022)

- ![WhatsApp Image 2024-09-22 at 13 51 05_b0fe3023](https://github.com/user-attachments/assets/55546610-9559-4bcd-ae35-0867b0ef2346)

- ![WhatsApp Image 2024-09-22 at 13 51 05_2a7c09d8](https://github.com/user-attachments/assets/8848e357-3fc6-453f-bde1-b4139ba62310)



---
## EZ
---
Aku sedang mencoba bikin chat service tapi kayanya pesannya bisa di sniffing deh? coba temukan pesannya.

### Flag
JarkomIT{supp0rt_k0k_l3m4h_bg_v8CT00tWiKLnufX5HNXFOOMsvG6RTEzIuFa4BhPXImZ68pDXjnGvG6}

### Penjelasan 
1. Untuk mencari jawaban dari log, buka Analyze > Follow > TCP Stream = Langsung terlihat di stream pertama terdapat 2 string yaitu "jawabannya jawaban"
2. Untuk mencari port yang digunakan, lihat di sebelah kiri bawah terdapat tulisan port : 1234. Flag langsung muncul!

### Dokumentasi Pengerjaan

- ![WhatsApp Image 2024-09-19 at 00 25 05_9ee459b0](https://github.com/user-attachments/assets/ac7b2f2d-dd9b-4de4-aa43-56b99a80f54e)



---
## Rizzset
---
Aku sedang bereksperimen dengan suatu tools, kamu juga bisa menggunakannya untuk menjawab soal ini

### Flag
JarkomIT{Dn5_C0rR34t10n_RM4ATQf7sTjZniTS1HjR3LZxwr1zZzbYYVgAX8I5Hu9PkDFFkUzhCv1T5}

### Penjelasan 
1. Gunakan filter dns untuk menampilkan query DNS yang terjadi selama komunikasi.
2. Dari hasil analisis DNS, domain yang muncul adalah www.its.ac.id.
3. Setelah melakukan analisis lebih lanjut, kita dapat menemukan bahwa IP address dari domain tersebut adalah 103.94.189.5.
4. Pada bagian ini, tantangan meminta kita untuk melakukan fingerprinting JARM (TLS Fingerprinting). Hasil fingerprint dari domain yang dianalisis adalah abcdef0123456789abcdef0123456789abcdef0123456789abcdef0123456789
5. Setelah itu muncullah flag nya

### Dokumentasi Pengerjaan
- Jarm :
  ![WhatsApp Image 2024-09-21 at 14 42 10_a8b1aede](https://github.com/user-attachments/assets/dc51b87c-2a88-42a3-880d-d54222669136)

  ![WhatsApp Image 2024-09-21 at 14 42 10_e391d221](https://github.com/user-attachments/assets/aa394f75-ed36-48b5-9c36-93618616ec1b)

- ![WhatsApp Image 2024-09-18 at 23 05 47_6add4547](https://github.com/user-attachments/assets/2acd389a-1509-40e1-84fe-f1f4dec86f3f)

