# Membuat Fungsi Kartu Dibuka

Kemudian logika permainan pencocokan kartu ada 3 tahap. Yang pertama, membuka salah satu kartu. Kemudian yang kedua, membuka kartu yang kedua. Lalu yang tahap yang ketiga mencocokan kedua kartu yang telah dibuka. Jika kartunya sama maka akan hilang, jika kartunya berbeda maka akan menutup kembali. Setelah itu kembali ke tahap pertama lagi.

1. Sebelumnya Anda sudah menambahkan Instance variable buka pada kartu seperti di bawah ini:

   ![01](/assets/005/01.png)

   Instance Variable buka tersebut berfungsi untuk memberi indentitas jika bernilai 0 maka kartu dalam keadaan tertutup dan jika buka bernilai 1 maka kartu dalam keadaan terbuka.

2. Karena untuk membuka kartu memerlukan object **Touch**, maka buka **Layout 1** kemudian tambahkan Object Touch dengan klik kanan pada **layout** > pilih **Insert new object** > Pilih Touch > Klik **Insert**.

   ![02](/assets/005/02.png)

3. Kemudian buka **event sheet 1**, lalu tambahkan event sheet sebagai berikut:

   Condition:
   - **System** > **Compare variable** > Variable: **tahap**, Comparison: **Equal to**, Value: **0**

   Hasilnya sebagai berikut:

   ![03](/assets/005/03.png)

   Keterangan:
   - **Tahap = 0**, kondisi pada saat akan membuka kartu yang pertama.

4. Tambahkan **sub event pada baris ke 4**, yaitu pada kondisi **System tahap = 0**. Maka eventnya sebagai berikut:

   Sub event(4) - Condition:
   - **Touch** > **On touched object** > Object: **Kartu**

   Maka hasilnya:
   ![04](/assets/005/04.png)

   Keterangan:
   - **Touch On touched Kartu**, Merupakan sub event dari System tahap = 0, yang berfungsi ketika salah satu kartu dibuka dengan di sentuh/di klik akan menjalankan actionnya.

5. Tambahkan **sub event pada baris event ke 5**, yaitu pada kondisi **Touch On touch Kartu**, maka eventnya sebagai berikut:

   Sub event(5) - Condition:
   - **Kartu** > **Compare instance variable** > Instance variable: **buka**, Comparison: **Equal to**, Value: **0**

   Event:
   - **System** > **et value > Variable: **bukaKartu1**, Value: **Kartu.warna\*\*
   - **Kartu** > **Set value** > Instance variable: **buka**, Value: **1**
   - **Kartu** > **Set frame** > Frame number: **Kartu.warna**
   - **System** > **Set value** > Variable: **tahap**, Value: **1**

   Maka hasilnya:
   ![05](/assets/005/05.png)

   Keterangan:
   - **Kartu buka=0**, memastikan kartu yang akan dibuka itu dalam keadaan tertutup (0=tertutup)
   - **Set bukaKartu1 to Kartu.warna**, menyimpan warna yang terpilih pada kartu pertama
   - **Set buka to 1**, memberi tanda pada kartu jika kartu tersebut sudah dibuka (1=buka)
   - **Set animation frame to Kartu.warna**, mengganti gambar kartu yang sesuai dengan id warnanya
   - **Set tahap to 1**, melanjutkan tahap selanjutnya yaitu memilih kartu ke dua

6. Salinlah pada **event 4,5 dan 6 menjadi event baru** dengan **copy paste (Ctrl+C dan Ctrl+V)** kemudian ubahlah event tersebut sebagai berikut:
   - ( Pada baris no. 7) **System tahap = 0** menjadi **System tahap = 1**
   - ( Pada baris no. 9) **System Set bukaKartu1 to Kartu.warna** menjadi **System Set bukaKartu2 to Kartu.warna**
   - ( Pada baris no. 9) **System Set tahap to 1** menjadi **System Set tahap to 2**

   Maka hasilnya:
   ![06](/assets/005/06.png)

   Event di atas kondisi ketika memilih kartu yang kedua.

7. Tambahkan event baru untuk membandingkan kedua kartu, sebagai berikut:

   Condition:
   - **System** > **Compare variable** > Variable: **tahap**, Comparison: **Equal to**, Value: **2**

   Maka hasilnya:

   ![07](/assets/005/07.png)

   Ketarangan:
   - **System tahap = 2** adalah kondisi untuk mencocokkan kedua kartu yang telah terpilih

8. Tambahkan **sub-event pada bari ke 10**. Event tersebut sebagai berikut:

   Sub event(10) - Condition:
   - **System** > **Compare variable** > Variable: **bukaKartu1**, Comparison: **Equal to**, Value: **bukaKartu2**
   - **Kartu** > **Compare instance variable** > Instance variable: **buka**, Comparison: **Equal to**, Value: **1**
   - **System** > **Trigger once while true**

   Action:
   - **System** > **Wait** > Seconds: **0.5**
   - **Kartu** > **Destroy**
   - **System** > **Add to** > Variable: **score**, Value: **25**
   - **System** > **Set value** > Variable: **tahap**, Value: **0**

   Maka hasilnya:
   ![08](/assets/005/08.png)

   Keterangan:
   - **System bukaKartu = bukaKartu2**, Memastikan id warna kedua kartu adalah sama
   - **Kartu buka = 1**, Memastikan kartu yang akan diproses adalah kartu yang telah terbuka.
   - **System Trigger once**, Memastikan kondisi ini dijalankan cukup sekali
   - **System Wait 0.5 seconds**, memberi waktu untuk kartu tetap terbuka selama 0.5 detik
   - **Kartu Destroy**, Kedua kartu yang sedang dibuka kemudian dihapus/di-destroy
   - **System Add 25 to score**, memberi nilai 25 point karena kartu yang dipilih benar
   - **System Set tahap to 0**, kembali ke tahap awal yaitu untuk mengambil/membuka kartu baru

9. Salinlah baris no. 11 menjadi sub event baru dari System **tahap = 2**. Maka sub eventnya sebagai berikut:
   - (Pada baris event ke 12) ubah dari **System bukaKartu1 = bukaKartu2** menjadi **System bukaKartu1 != bukaKartu2**
   - (Pada baris event ke 12) Hilangkan action **Kartu Destroy**
   - (Pada baris event ke 12) **System Add 25 to score** menjadi **System Subtract 5 from score**

   Maka hasilnya:
   ![09](/assets/005/09.png)

10. Kemudian tambahkan action baru untuk mengembalikan kondisi kartu kembali tertutup. Dengan Menambahkan action baru pada baris no. 12 sebagai berikut:

    Action:
    - **Kartu** > **Set value** > Instance variable: **buka**, Value: 0
    - **Kartu** > **Set frame** > **Frame Number** > **0**

    Maka hasilnya:
    ![010](/assets/005/010.png)

    Keterangan:
    - **Kartu Set buka to 0**, mengembalikan nilai status kartu menjadi tertutup kembali (0: tertutup, 1: terbuka)
    - **Kartu Set animation frame to 0**, Mengembalikan tampilkan kartu yang semua terbuka kemudian menjadi tampilan tertutup kembali.

Seluruh Event Sheet 1 sebagai berikut:

![011](/assets/005/011.png)

![012](/assets/005/012.png)

Ketika dijalankan hasilnya sebagai berikut:

![013](/assets/005/013.gif)
