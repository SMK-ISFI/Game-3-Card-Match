# Membuat Timer

Setelah menampilkan score, sekarang Anda akan membuat kondisi Timer, dimana timer ini akan menentukan apakah permainannya telah usai atau masih berjalan.

![01](/assets/007/01.gif)

1. Buka kembali **Layout**, lalu tambahkan objek **"Tiled Background"** dan beri nama **"Timer"**.

   ![02](/assets/007/02.png)

2. Selanjutnya ubah posisi object **"Timer"** itu hingga tepat di atas **Score**. Agar score dapat terlihat maka klik kanan pada objek **Timer** > pilih **Z Order** > klik **Send to bottom of layer**.

   ![03](/assets/007/03.png)

3. Tambahkan condition baru pada **Tahap 0**, **Tahap 1** dan **Tahap 2.** Dengan condition sebagai berikut:

   Condition:
   - **System** > **Compare variable** > Variable: **mulaiGame**, Comparison: **Equal to**, Value: **2**

   (Kemudian di Invertkan dengan cara, **Klik kanan** > **Pilih Invert**)

   Maka hasilnya:
   ![04](/assets/007/04.png)

   Keterangan:
   - **mulaiGame = 0**, ketika diam
   - **mulaiGame = 1**, ketika game berjalan
   - **mulaiGame = 2**, ketika game berakhir

4. Kemudian ketika klik pertama kali kartu dibuka maka timer akan berjalan yang menandakan permainan dimulai, maka tambahkan action pada membuka kartu pada saat tahap = 0.

   Action:
   - **System** > **Set value** > Variable: **mulaiGame**, Value: **1**

   Maka hasilnya:
   ![05](/assets/007/05.png)

   **System Set mulaiGame to 1**, Ketika kartu dipilih maka game dimulai.

5. Kemudian selanjutnya memberikan event untuk memastikan permainan masih sedang berlangsung sehingga tambahkan event sebagai berikut:

   Condition:
   - **System** > **Compare variable** > Variable: **mulaiGame**, Comparison: **Equal to**, Value: **1**

   Maka hasilnya:
   ![06](/assets/007/06.png)

6. Membuat waktu berjalan setiap 0.3 detik sekali untuk Tambahkan **sub-event dari baris no. 13**. Eventnya sebagai berikut:

   Sub event(13) - Condition:
   - **System** > **Every X seconds** > Interval: **0.3**

   Action:
   - **Timer** > **Set width** > Width: **Self.Width - 18**

   Maka hasilnya:
   ![07](/assets/007/07.png)

7. Tambahkan **sub-event pada baris 13** untuk menangkap kondisi ketika waktu permainan habis. Eventnya sebagai berikut:

   Sub event(13) - Condition:
   - **Timer** > **Compare width** > Comparison: **Less or equal**, Width: **0**

   Action:
   - **System** > **Set variable** > variable: **mulaiGame**, value: **2**
   - **System** > **Wait** > Seconds: **2**
   - **System** > **Restart layout**

Maka hasilnya:
![08](/assets/007/08.png)

Keterangan:

- **Timer Width <= 0**, Ketika panjang object Timer sama dengan 0 (Waktu habis)
- **System Set mulaiGame to 2**, Permainan berhenti atau selesai
- **System Wait 2 seconds**, tunggu selama 2 detik untuk melanjutkan langkah selanjutnya.
- **Restart layout**, mengatur ulang layout termasuk object-object didalam game tetapi tidak termasuk variable.

8. Tambakan **sub-event pada baris 13** untuk memberikan kondisi ketika permainan selesai sebelum waktu habis, maka tambahkan event seperti berikut:

   Sub event(13) - Condition:
   - **System** > **Compare two values** > First value: **Kartu.Count**, Comparison: **Equal to**, Second value: **0**

   Action:
   - **System** > **Set value** > variable: **mulaiGame**, value: **2**
   - **System** > **Wait** > Seconds: **2**
   - **System** > **Restart layout**

   Maka hasilnya:
   ![09](/assets/007/09.png)

   **Count** berfungsi sebagai expression untuk mengecek berapa total objek dimaksud yang masih ada di dalam layout.

   Sehingga ketika condition Kartu.Count = 0 digunakan, maka artinya sistem mengecek apakah benar bahwa objek Kartu yang ada di dalam layout sudah 0 / tidak ada lagi, bila iya, maka sistem akan melanjutkan pada aksi/tujuan berikutnya.

   Note : Expression Count hanya dapat digunakan pada objek yang menggunakan action Destroy, dan tidak dapat digunakan pada objek yang menggunakan action Visible/Invisible,Transparent/Opaque.

9. Kemudian supaya kondisi seperti semula ketika mengulang permainan, maka perlu ditambahkan action sebagai berikut:

   Cari Condition:
   - **System** > **On start of layout**

   Tambahkan Action paling atas:
   - **System** > **Set value** > Variable: **mulaiGame**, Value: **0**
   - **System** > **Set value** > Variable: **score**, Value: **0**
   - **System** > **Set value** > Variable: **tahap**, Value: **0**

   Maka hasilnya:
   ![010](/assets/007/010.png)

   Keterangan:
   - **System Set mulaiGame to 0**, dimana kondisi timer belum berjalan
   - **System Set score to 0**, mengatur score kembali 0 karena permainan baru
   - **System Set tahap to 0**, memulai lagi untuk membuka kartu pertama

Ketika dijalankan hasilnya sebagai berikut:

![012](/assets/007/012.gif)
