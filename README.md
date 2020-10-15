######Lapres Praktikum Modul 1 Jaringan Komputer Kelompok A08#

**A. Display Filter**
1. Sebutkan webserver yang digunakan pada "testing.mekanis.me"!

    **Revisi**
      - Webserver yang digunakan adalah nginx/1.14.0 (Ubuntu)

      - Wireshark filter expression :

        ```http.host == “testing.mekanis.me” && http.request```

          Klik kanan, Follow -> TCP
          
          ![Nomor1]

2. Simpan gambar "Tim_Kunjungan_Kerja_BAKN_DPR_RI_ke_Sukabumi141436.jpg"!
      
      - Wireshark filter expression :

         ```http contains "Tim_Kunjungan_Kerja_BAKN_DPR_RI_ke_Sukabumi141436.jpg"```
(gambar)

         Klik File -> EXPORT OBJECT -> HTTP
(gambar)

         lalu save file dengan nama "Tim_Kunjungan_Kerja_BAKN_DPR_RI_ke_Sukabumi141436.jpg"
         
         gambar akan tersimpan

gambar yang didownload :
(gambar)

3. Cari username dan password ketika login di "ppid.dpr.go.id"!

      - Wireshark filter expression
            
         ```http.host == ppid.dpr.go.id && http.request.method == POST```

(gambar)

         Username :10pemuda

         Password : guncangdunia

4. Temukan paket dari web-web yang menggunakan basic authentication method!

   - Wireshark filter expression :

      ```http.authbasic```

      Dari filter yang dimasukkan, web yang basic authentication adalah testing.mekanis.me dan aku.pengen.pw

(gambar)
(gambar)

5. Ikuti perintah di aku.pengen.pw! Username dan password bisa didapatkan dari file .pcapng!

   - Wireshark filter expression :
   
      ```http.host == aku.pengen.pw```

(gambar)

      Username dan password dapat dilihat pada authorization -> credentials

      Username : kakakgamtenk
      
      Password : hartatahtabermuda

      Berikut adalah halaman aku.pengen.pw yang sudah dibuka beserta tugas yang ada di dalamnya.
(gambar)


6. Seseorang menyimpan file zip melalui FTP dengan nama "Answer.zip". Simpan dan Buka file "Open This.pdf" di Answer.zip. Untuk mendapatkan password zipnya, temukan dalam file zipkey.txt (passwordnya adalah isi dari file txt tersebut).

   - Wireshark filter expression :

      ```ftp-data.command contains "Answer.zip"```

(gambar)

      Kemudian follow > TCP stream pada paket 1775
      
      File signature untuk zip adalah 50 4B 03 04 , maka pada hasil follow, search kode tersebut dengan pilihan hex dump

(gambar)

      Hasil pencarian ditemukan, maka show and save file as “Answer.zip”
(gambar)

      Setelah memasukkan password dari zipkey.txt
      
      Password : hey997400323051

(gambar)

   - Wireshark filter expression :

      ```ftp-data.command contains “zipkey.txt”```

      Lakukan hal yang sama, yaitu follow -> TCP stream -> show and save data as raw -> save as “zipkey.txt”

(gambar)

7. Ada 500 file zip yang disimpan ke FTP Server dengan nama 1.zip, 2.zip, ..., 500.zip. Salah satunya berisi pdf yang berisi puisi. Simpan dan Buka file pdf tersebut.
Your Super Mega Ultra Rare Hint = nama pdf-nya "Yes.pdf"

   - Wireshark filter expression :  ftp-data contains "Yes.pdf"

(gambar)

      Kemudian pada paket pilihan, lakukan follow > TCP stream > show and save data as Raw > save as “473.zip”

(gambar)

      Setelah file zip diambil, diekstrak isinya yaitu “Yes.pdf” dan ini isinya.

(gambar)

8. Cari objek apa saja yang didownload (RETR) dari koneksi FTP dengan Microsoft FTP Service!

   - Wireshark filter expression :
      ```ftp contains“Microsoft” kemudian src diambil menjadi ftp.request.command == RETR && ip.dst == 198.246.117.106```

      Objek yang didownload :
      
      Readme

(gambar)

9. Cari username dan password ketika login FTP pada localhost!

   - Wireshark filter expression :

      ```ftp.request.command == USER || ftp.request.command == PASS```

(gambar)

      Username : dhana
      Password : dhana123

10. Cari file .pdf di wireshark lalu download dan buka file tersebut!
clue: "25 50 44 46"

   - Wireshark filter expression :

      ```http contains “.pdf”```

(gambar)

      Selain itu, file juga bisa diambil dengan mencari paket yang mengandung 25 50 44 46

(gambar)

      Kemudian pada paket pilihan, lakukan follow > TCP stream > show and save data as Raw > save as “1759.pdf”

(gambar)

      Hasil file pdf yang diambil

(gambar)

**B. Capture Filter**

11. Filter sehingga wireshark hanya mengambil paket yang mengandung port 21!

   - Wireshark filter expression :

      ```port 21```

(gambar)

      Untuk destinasi port 21

(gambar)

      Untuk source port 21

(gambar)

12. Filter sehingga wireshark hanya mengambil paket yang berasal dari port 80!

   - Wireshark filter expression :

      ```src port 80```

(gambar)

(gambar)

13. Filter sehingga wireshark hanya menampilkan paket yang menuju port 443!

    - Wireshark filter expression :

      ```dst port 443```

(gambar)

(gambar)

14. Filter sehingga wireshark hanya mengambil paket yang berasal dari ip kalian!

    Cmd : ipconfig/all

(gambar)

   - Wireshark filter expression :

      ```src host 192.168.1.3```

(gambar)

(gambar)

15. Filter sehingga wireshark hanya mengambil paket yang tujuannya ke monta.if.its.ac.id!

(gambar)

   - Wireshark filter expression :

      ```dst host 103.94.190.11```

(gambar)

(gambar)
