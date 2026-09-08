# Membuat Fungsi Pengacakan

Array digunakan untuk menyimpan sekumpulan nilai. Nanti akan digunakan untuk menyimpan daftar kartu yang akan dimunculkan.

1. Tambahkan object **Array** dengan nama **"DaftarKartu"** (**Klik kanan di layout** > pilih **Add new object**)

   ![01](/assets/004/01.png)

2. Buka kembali Event sheet 1. Kemudian tambahkan event sebagai berikut:

   Condition:
   - **System** > **On start of layout**

   Action:
   - **DaftarKartu** > **Set size** > Width: **10**, Height: **1**, Depth: **1**
   - **DaftarKartu** > **Set at X** > X: **0**, Value: **1**
   - **DaftarKartu** > **Set at X** > X: **1**, Value: **1**
   - **DaftarKartu** > **Set at X** > X: **2**, Value: **2**
   - **DaftarKartu** > **Set at X** > X: **3**, Value: **2**
   - **DaftarKartu** > **Set at X** > X: **4**, Value: **3**
   - **DaftarKartu** > **Set at X** > X: **5**, Value: **3**
   - **DaftarKartu** > **Set at X** > X: **6**, Value: **4**
   - **DaftarKartu** > **Set at X** > X: **7**, Value: **4**
   - **DaftarKartu** > **Set at X** > X: **8**, Value: **5**
   - **DaftarKartu** > **Set at X** > X: **9**, Value: **5**

   Maka hasilnya:

   ![02](/assets/004/02.png)

   Karena kartu hanya berjumlah 10 dan jenis kartu ada 5. Maka setiap jenis kartu dipanggil 2 kali.

3. Untuk memberikan nilai acak pada warna kartu, maka perlu melakukan pengulangan sebanyak jumlah kartu dengan menambahkan sub-event pada baris 1 (System On start of layout) dengan ketentuan sebagai

   Sub event(dari baris 1) - Condition:
   - **System > For > Name: "SetWarnaKartu", Start: 9, End: 0**

   Maka hasilnya:

   ![03](/assets/004/03.png)

   Melakukan pengulangan dari 9 ke 0 karena nanti akan digunakan untuk pengambilan kartu dengan sistem acak dari 9 kartu, kemudian setelah didapat 1 kartu kemudian melakukan lagi dengan sisa 8 kartu, dan seterusnya sampai kartu habis. Jumlah sisa kartu didapat dari nilai **loopindex**. Pastikan event diatas merupakan sub event dari **System On start of layout**.

4. Kemudian melakukan pemberian kode warna pada kartu. Sehingga tambahkan **Sub event** pada System for **"SetWarnaKartu" from 9 to 0**.

   Sub action(2) - Condition
   - **System** > **Pick nth instance** > Object: **Kartu**, Instance: **loopindex**

   Action:
   - **System** > **Set value** > Variable: **acak**, Value: **int(random(0,loopindex+1))**
   - **Kartu** > **Set value** > Instance variable: **warna**, Value: **DaftarKartu.At(acak)**
   - **DaftarKartu** > **Delete** > Index: **acak**, Axis: **X**

   Maka hasilnya:

   ![04](/assets/004/04.png)

   Keterangan:
   - **Pick Kartu instance looping** adalah Kondisi pengambilan kartu dari kartu ke 9 sampai kartu ke 0.
   - **System Set acak to int(random(0, loopindex + 1))**, membuat nilai acak yang nantinya dijadikan nilai index pada DaftarKartu yang nanti keluar dengan mengambil nilai acak dari 0 sampai maksimal 10. Maksimal nilai 10 tersebut nanti akan didapat nilai maksimal 9,99 dan kemudian akan di bulatkan oleh fungsi int menjadi 9 sehingga didapat pengacakan kartu dari 0 sampai 9.
   - **Kartu Set warna to DaftarKartu.At(acak)**, dari nilai acak didapat maka akan digunakan untuk mengambil warna/jenis kartu dari id kartu **1** sampai **5**.
   - **DaftarKartu Delete index acak from X axis**, Setelah id warna kartu sudah didapat maka daftar kartu yang digunakan dihapus supaya tidak digunakan kembali.
