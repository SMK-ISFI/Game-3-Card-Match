# Menambahkan Instance Variable Global Variable

Untuk memberikan nilai-nilai tersendiri pada masing-masing kartu, akan menggunakan instance variable, instance variable sangat berbeda dengan global variable maupun local variable, dimana instance variable akan selalu melekat pada objek yang diberikan instance variable, penggunaan instance variable tidak dapat berfungsi apabila tidak ada objeknya dalam layout yang dimaksud.

1. Untuk menambahkan **"instance variable"**, pilih objectnya yang akan diberikan, lalu pada bagian Object **"Properties"**, tepat di atas Behaviors, terdapat tulisan Instance variables, klik link tersebut.

   ![01](/assets/003/01.png)

2. Lalu tekan **icon tambah "+"** kemudian berikan nama variablenya dengan **warna** dan Type **Number**. lalu tekan **OK**.

   ![02](/assets/003/02.png)

3. Kemudian tambahkan **instance variable** dengan Nama **buka** dan type **Number**.

   Maka hasilnya:

   ![03](/assets/003/03.png)

4. Berikutnya tambahkan beberapa **"global variable"** di **"Event sheet 1"** yang nanti akan digunakan pada materi selanjutnya. (Klik kanan pada **Event sheet** > pilih **Add global variable)**
   - acak, Number, 0 (menyimpan nilai sementara)
   - tahap, Number, 0 (0:Pilih kartu pertama, 1: Pilih kartu kedua, 2: Bandingkan kartu)
   - score, Number, 0 (keterangan nilai)
   - bukaKartu1, Number, 0 (menyimpan id kartu pertama yang dibuka)
   - bukaKartu2, Number, 0 (menyimpan id kartu kedua yang dibuka)
   - mulaiGame, Number, 0 (0:awal permaian, 1: pemainan dimulai, 2: permainan selesai)

   **Sehingga tampilan di Event sheet 1 sebagai berikut:**

   ![04](/assets/003/04.png)
