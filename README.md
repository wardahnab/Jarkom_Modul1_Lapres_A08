Lapres Praktikum Modul 1 Jaringan Komputer Kelompok A08

**A. Display Filter**

1. Sebutkan webserver yang digunakan pada "testing.mekanis.me"!

    **Revisi**
      
      - Webserver yang digunakan adalah nginx/1.14.0 (Ubuntu)

      - Wireshark filter expression :

        ```http.host == “testing.mekanis.me” && http.request```
        
         ![Nomor 1.2](https://github.com/wardahnab/Jarkom_Modul1_Lapres_A08/blob/main/Nomor%201.2.png)

          Klik kanan pada salah satu paket, Follow -> TCP
          
          ![Nomor 1](https://github.com/wardahnab/Jarkom_Modul1_Lapres_A08/blob/main/Nomor%201.png)

2. Simpan gambar "Tim_Kunjungan_Kerja_BAKN_DPR_RI_ke_Sukabumi141436.jpg"!
   
   **Jawaban**
   
      - Wireshark filter expression :

         ```http contains "Tim_Kunjungan_Kerja_BAKN_DPR_RI_ke_Sukabumi141436.jpg"```
         
         ![Nomor 2.1](https://github.com/wardahnab/Jarkom_Modul1_Lapres_A08/blob/main/Nomor%202.1.png)

         Export file dengan cara Klik File -> Export Objects -> HTTP
         
         ![Nomor 2.2](https://github.com/wardahnab/Jarkom_Modul1_Lapres_A08/blob/main/Nomor%202.2.png)

         Klik file dengan judul yang diinginkan -> save
         
         Hasil Gambar :
         
         ![Nomor 2.3](https://github.com/wardahnab/Jarkom_Modul1_Lapres_A08/blob/main/Nomor%202.3.png)
         
3. Cari username dan password ketika login di "ppid.dpr.go.id"!
   
   **Jawaban**
   
   - Wireshark filter expression :
      
      ```http.request.method == POST```
      
      ![Nomor 3 Jawaban](https://github.com/wardahnab/Jarkom_Modul1_Lapres_A08/blob/main/Nomor%203Jawaban.png)
      
      ![Nomor 3 Jawaban.2](https://github.com/wardahnab/Jarkom_Modul1_Lapres_A08/blob/main/Nomor%203.2Jawaban.png)
      
   **Revisi**
   
      - Wireshark filter expression :
            
         ```http.host == ppid.dpr.go.id && http.request.method == POST```
         
         ![Nomor 3](https://github.com/wardahnab/Jarkom_Modul1_Lapres_A08/blob/main/Nomor%203.png)
         
         Username :10pemuda

         Password :guncangdunia
         
4. Temukan paket dari web-web yang menggunakan basic authentication method!
   
   **Revisi**
   
      - Wireshark filter expression :

         ```http.authbasic```
      
         ![Nomor 4.1](https://github.com/wardahnab/Jarkom_Modul1_Lapres_A08/blob/main/Nomor%204.1.png)
      
         ![Nomor 4.2](https://github.com/wardahnab/Jarkom_Modul1_Lapres_A08/blob/main/Nomor%204.2.png)
      
         Dari filter yang dimasukkan, web yang basic authentication adalah **testing.mekanis.me** dan **aku.pengen.pw**
      
5. Ikuti perintah di aku.pengen.pw! Username dan password bisa didapatkan dari file .pcapng!
   
   **Revisi**
   
      - Wireshark filter expression :
   
         ```http.host == aku.pengen.pw```
      
         ![Nomor 5.1](https://github.com/wardahnab/Jarkom_Modul1_Lapres_A08/blob/main/Nomor%205.1.png)
      
         Username dan password dapat dilihat pada Authorization -> Credentials

         Username : kakakgamtenk
      
         Password : hartatahtabermuda

         Berikut adalah halaman aku.pengen.pw yang sudah dibuka beserta tugas yang ada di dalamnya.
      
         ![Nomor 5.2](https://github.com/wardahnab/Jarkom_Modul1_Lapres_A08/blob/main/Nomor%205.2.png)
      
6. Seseorang menyimpan file zip melalui FTP dengan nama "Answer.zip". Simpan dan Buka file "Open This.pdf" di Answer.zip. Untuk mendapatkan password zipnya, temukan dalam file zipkey.txt (passwordnya adalah isi dari file txt tersebut).
   
   **Jawaban**
   
   - Wireshark filter expression :
   
      ``` ftp contains "Answer.zip"```
   
      ![Nomor 6 Jawaban](https://github.com/wardahnab/Jarkom_Modul1_Lapres_A08/blob/main/Nomor%206Jawaban.png)
      
   **Revisi**
   
      - Wireshark filter expression :

         ```ftp-data.command contains "Answer.zip"```
      
         ![Nomor6.1](https://github.com/wardahnab/Jarkom_Modul1_Lapres_A08/blob/main/Nomor%206.1.png)
      
         Kemudian follow -> TCP stream pada paket 1775
      
         File signature untuk zip adalah 50 4B 03 04 , maka pada hasil follow, search kode tersebut dengan pilihan hex dump
      
         ![Nomor 6.2](https://github.com/wardahnab/Jarkom_Modul1_Lapres_A08/blob/main/Nomor%206.2.png)
      
         Hasil pencarian ditemukan, maka show and save file as “Answer.zip”
      
         ![Nomor 6.3](https://github.com/wardahnab/Jarkom_Modul1_Lapres_A08/blob/main/Nomor%206.3.png)
      
         ![Nomor 6.4](https://github.com/wardahnab/Jarkom_Modul1_Lapres_A08/blob/main/Nomor%206.4.png)

         Setelah memasukkan password dari zipkey.txt
      
         Password : hey997400323051
      
         ![Nomor 6.5](https://github.com/wardahnab/Jarkom_Modul1_Lapres_A08/blob/main/Nomor%206.5.png)
      
      - Mengetahui isi zipkey.txt
      
         - Wireshark filter expression :

            ```ftp-data.command contains “zipkey.txt”```
      
            ![Nomor 6.6](https://github.com/wardahnab/Jarkom_Modul1_Lapres_A08/blob/main/Nomor%206.6.png)
      
            Lakukan hal yang sama, yaitu follow -> TCP stream -> show and save data as raw -> save as “zipkey.txt”
      
            ![Nomor 6.7](https://github.com/wardahnab/Jarkom_Modul1_Lapres_A08/blob/main/Nomor%206.7.png)
      
7. Ada 500 file zip yang disimpan ke FTP Server dengan nama 1.zip, 2.zip, ..., 500.zip. Salah satunya berisi pdf yang berisi puisi. Simpan dan Buka file pdf tersebut. Your Super Mega Ultra Rare Hint = nama pdf-nya "Yes.pdf"

   **Jawaban**
   
      - Wireshark filter expression :
      
         ```ftp.request.arg == RETR```
         
         ![Nomor 7 Jawaban](https://github.com/wardahnab/Jarkom_Modul1_Lapres_A08/blob/main/Nomor%207Jawaban.png)

   **Revisi**
   
      - Wireshark filter expression :  
         
        ```ftp-data contains "Yes.pdf"```
      
         ![Nomor 7.1](https://github.com/wardahnab/Jarkom_Modul1_Lapres_A08/blob/main/Nomor%207.1.png)
      
         Kemudian pada paket pilihan, lakukan follow -> TCP stream -> show and save data as Raw -> save as “473.zip”
      
         ![Nomor 7.2](https://github.com/wardahnab/Jarkom_Modul1_Lapres_A08/blob/main/Nomor%207.2.png)
      
         Setelah file zip diambil, diekstrak isinya yaitu “Yes.pdf” dan berikut adalah isinya.
      
         ![Nomor 7.3](https://github.com/wardahnab/Jarkom_Modul1_Lapres_A08/blob/main/Nomor%207.3.png)
      
8. Cari objek apa saja yang didownload (RETR) dari koneksi FTP dengan Microsoft FTP Service!

   **Jawaban**
   
      - Wireshark filter expression : 
      
         ```ftp.request.command == "RETR"```
         
         Objek yang Didownload :
         
         - Readme
         
         - license.txt
         
         ![Nomor 8 Jawaban](https://github.com/wardahnab/Jarkom_Modul1_Lapres_A08/blob/main/Nomor%208Jawaban.png)
   
   **Revisi**
   
      - Wireshark filter expression :
      
         ```ftp contains“Microsoft” kemudian src diambil menjadi ftp.request.command == RETR && ip.dst == 198.246.117.106```

         Objek yang didownload :
      
         - Readme
         
         ![Nomor 8](https://github.com/wardahnab/Jarkom_Modul1_Lapres_A08/blob/main/Nomor%208.png)
      
9. Cari username dan password ketika login FTP pada localhost!

   **Jawaban**
   
      - Wireshark filter expression :

         ```ftp.request.command == USER || ftp.request.command == PASS```
      
         ![Nomor 9](https://github.com/wardahnab/Jarkom_Modul1_Lapres_A08/blob/main/Nomor%209.png)
      
         Username : dhana
         
         Password : dhana123
      
10. Cari file .pdf di wireshark lalu download dan buka file tersebut! clue: "25 50 44 46"

     **Jawaban**
      
      - Wireshark filter expression :
      
         ```http contains ".pdf"```
         
         ![Nomor 10 Jawaban](https://github.com/wardahnab/Jarkom_Modul1_Lapres_A08/blob/main/Nomor%2010Jawaban.png)
         
      **Revisi**
   
      - Wireshark filter expression :

         ```http contains “.pdf”```
      
         ![Nomor 10.1](https://github.com/wardahnab/Jarkom_Modul1_Lapres_A08/blob/main/Nomor%2010.1.png)
      
         Selain itu, file juga bisa diambil dengan mencari paket yang mengandung 25 50 44 46
      
         ![Nomor 10.2](https://github.com/wardahnab/Jarkom_Modul1_Lapres_A08/blob/main/Nomor%2010.2.png)
      
         Kemudian pada paket pilihan, lakukan follow -> TCP stream -> show and save data as Raw -> save as “1759.pdf”
      
         ![Nomor 10.3](https://github.com/wardahnab/Jarkom_Modul1_Lapres_A08/blob/main/Nomor%2010.3.png)
      
         Hasil file pdf yang diambil :
         
         ![Nomor 10.4](https://github.com/wardahnab/Jarkom_Modul1_Lapres_A08/blob/main/Nomor%2010.4.png)



**B. Capture Filter**

11. Filter sehingga wireshark hanya mengambil paket yang mengandung port 21!

      **Jawaban**
      
      - Wireshark filter expression :

         ```port 21```
      
         ![Nomor 11.1](https://github.com/wardahnab/Jarkom_Modul1_Lapres_A08/blob/main/Nomor%2011.1.png)
      
         Untuk destinasi port 21
      
         ![Nomor 11.2](https://github.com/wardahnab/Jarkom_Modul1_Lapres_A08/blob/main/Nomor%2011.2.png)
      
         Untuk source port 21
      
         ![Nomor 11.3](https://github.com/wardahnab/Jarkom_Modul1_Lapres_A08/blob/main/Nomor%2011.3.png)
      
12. Filter sehingga wireshark hanya mengambil paket yang berasal dari port 80!

      **Jawaban**
      
      - Wireshark filter expression :

         ```src port 80```
      
         ![Nomor 12.1](https://github.com/wardahnab/Jarkom_Modul1_Lapres_A08/blob/main/Nomor%2012.1.png)
      
         ![Nomor 12.2](https://github.com/wardahnab/Jarkom_Modul1_Lapres_A08/blob/main/Nomor%2012.2.png)
      
13. Filter sehingga wireshark hanya menampilkan paket yang menuju port 443!

      **Jawaban**
   
      - Wireshark filter expression :

         ```dst port 443```
      
         ![Nomor 13.1](https://github.com/wardahnab/Jarkom_Modul1_Lapres_A08/blob/main/Nomor%2013.1.png)
         
         ![Nomor 13.2](https://github.com/wardahnab/Jarkom_Modul1_Lapres_A08/blob/main/Nomor%2013.2.png)
      
14. Filter sehingga wireshark hanya mengambil paket yang berasal dari ip kalian!

      **Jawaban**
   
      Cmd : 
      
      ```ipconfig/all```
    
      ![Nomor 14.1](https://github.com/wardahnab/Jarkom_Modul1_Lapres_A08/blob/main/Nomor%2014.1.png)
    
      - Wireshark filter expression :

         ```src host 192.168.1.3```
      
         ![Nomor 14.2](https://github.com/wardahnab/Jarkom_Modul1_Lapres_A08/blob/main/Nomor%2014.2.png)
      
         ![Nomor 14.3](https://github.com/wardahnab/Jarkom_Modul1_Lapres_A08/blob/main/Nomor%2014.3.png)
      
15. Filter sehingga wireshark hanya mengambil paket yang tujuannya ke monta.if.its.ac.id!

    **Jawaban**
    
      ![Nomor 15.1](https://github.com/wardahnab/Jarkom_Modul1_Lapres_A08/blob/main/Nomor%2015.1.png)
   
      - Wireshark filter expression :

         ```dst host 103.94.190.11```
      
         ![Nomor 15.2](https://github.com/wardahnab/Jarkom_Modul1_Lapres_A08/blob/main/Nomor%2015.2.png)
      
         ![Nomor 15.3](https://github.com/wardahnab/Jarkom_Modul1_Lapres_A08/blob/main/Nomor%2015.3.png)
