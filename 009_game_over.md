# Menambahkan Kondisi Game Over

Sebelumnya sudah membuat Text untuk Game Over. Sekarang kita akan membuat fungsi kondisi pengecekan apakah permainannya memang benar sudah selesai karena waktu habis atau permainannya selesai karena semua kartunya benar sudah tidak ada lagi.

1. Pada event sheet, tambahkan action baru pada **System** > **On start of layout** seperti berikut:

   Tambahkan action:
   - **System** > **Set layer visible** > Layer: **1**, Visibility: **Invisible**
   - **System** > **Set layer opacity** > Layer: **0**, Opacity: **100**

   Maka hasilnya:
   ![01](/assets/009/01.png)

   Keterangan: Layer 1 merupakan layer gameover, sehingga pertama kali harus Invisible (tidak ditampilkan) dan pada layer 0 pastikan jelas dengan memberi nilai opacity 100.

2. Kemudian pada bagian kondisi waktu permainan habis pada event **mulaiGame = 1** dan **Timer width <= 0**, maka sebelum action **Wait 2 seconds** tambahkan action sebagai berikut:

   Action:
   - **TextGameover** > **Set text** > Text: **“YOU LOSE!”**
   - **Syste**m > **Set layer visible** > Layer: **1**, Visibility: **Visible**
   - **System** > **Set layer opacity** > Layer: **0**, Opacity: **40**

   Maka hasilnya:
   ![02](/assets/009/02.png)

   Keterangan:
   - **TextGameover Set text to “YOU LOSE!”**, menampilkan text “YOU LOSE!” pada object TextGameover.
   - **System Set layer 1 Visible**, Memunculkan layer yang terdapat Font Gameover
   - **System Set layer 0 opacity to 40**, membuat layer pada gameplay menjadi gelap sebanyak 60% (semakin kecil nilainya semakin gelap).

3. Selanjutnya pada bagian kondisi permainan selesai pada event **mulaiGame = 1** dan **Kartu.Count = 0**, maka sebelum action **Wait 2 seconds** tambahkan action sebagai berikut:

   Action:
   - **TextGameover** > **Set tex**t > Text: **“YOU WIN!”**
   - **System** > **Set layer visible** > Layer: **1**, Visibility: **Visible**
   - **System** > **Set layer opacity** > Layer: **0**, Opacity: **40**

   Maka hasilnya:
   ![03](/assets/009/03.png)

   Ketika dijalankan hasilnya sebagai berikut:
   ![04](/assets/009/04.gif)

4. Tambahkan background Select **Layer 0** pada Kolom **Layer** dan pastikan Anda sudah membuka gembok, agar dapat mengedit Sprite yang akan ditambahkan.

   ![05](/assets/009/05.png)

5. Buka **Layout 1**, kemudian menambahkan **Sprite** baru dan beri Nama **Background**. (Klik kanan pada **Layout** > Pilih **Insert new object**)

   ![06](/assets/009/06.png)

6. Masukkan gambar dengan klik **icon Folder tebuka** dan cari file **Background.png** dari berkas yang sudah diunduh.

   ![07](/assets/009/07.png)

7. Kemudian atur posisi object Background dengan mengatur nilai **Position** menjadi **640,360**

   ![08](/assets/009/08.png)

8. Atur kedalaman object Background dengan **klik Kanan pada object Background** > Pilih **Z Order** > Pilih **Send to buttom of layer**.

   ![09](/assets/009/09.png)

Sehingga tampilannya sebagai berikut:

![010](/assets/009/010.png)

Ketika dijalankan hasilnya sebagai berikut:

![011](/assets/009/011.gif)
