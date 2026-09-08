## Spritefont+

Jika Anda menggunakan Contrcut 3, Anda dapat melewati sub modul ini dengan klik tombol selanjutnya.

Plugin spritefont+ dan plugin text memiliki fungsi yang sama yaitu untuk menampilkan teks dalam permainan, tapi font yang digunakan pada plugin text tidak akan dapat digunakan apabila komputer atau smartphone milik pengguna lain tidak memiliki font tersebut.

![01](/assets/008/01.png)

Sedangkan plugin spritefont menggunakan hasil font yang sudah diubah menjadi file gambar .png, contohnya seperti gambar di atas ini. Anda bisa menemukan plugin spritefont pada software Construct 2, tapi dalam menerapkan plugin Spritefont bawaan Construct 2 ini sedikit sulit, karena kita memerlukan array untuk menata setiap huruf posisi spritefont. Untuk itulah kami sarankan untuk menggunakan plugin Spritefont+ yang dapat diunduh di bawah ini, dengan menggunakan plugin ini Anda tidak perlu menggunakan array.

Sebagai contoh, kita akan menggunakan Spritefont+ yang sudah diunduh sebelumnya. Di dalam Folder Font terdapat 4 item, sebelum menggunakan Spritefont, tambahkan terlebih dahulu plugin ke Construct 2 dan pastikan **Construct 2 Anda dalam keadaan tidak aktif atau keadaan close**.

![02](/assets/008/02.png)

Langkah langkah memasukkan Sprite font sebagai berikut:

1. Copy folder spritefont+ yang telah diunduh dengan klik Ctrl+C.

   ![03](/assets/008/03.png)

2. Buka folder tempat dimana Construct 2 install, biasanya akan terinstall di **Program Files**. Cari folder dengan nama **Construct 2**.

   ![04](/assets/008/04.png)

3. Lalu buka folder **C:\Program Files\Construct 2\exporters\html5\plugins** paste folder **Spritefont+** yang sudah Anda copy sebelumnya.

   ![05](/assets/008/05.png)

4. Buka kembali Aplikasi Construct 2 dan kemudian tambahkan layer baru untuk tempat text **Game Over** dengan klik tanda **Plus "+"** pada kolom Layers. Jangan lupa untuk mengaktifkan **Layer 1**.

   ![06](/assets/008/06.png)

5. Jika sudah, buka kembali project Construct 2 Anda, lalu tambahkan objek plugin **Spritefont+**, dan beri nama TextGameover.

   ![07](/assets/008/07.png)

   (Jika tidak muncul icon SpriteFont+ maka cek kembali berkas plugin yg telah dimasukkan apakah sudah benar atau belum)

6. Selanjutnya akan muncul kotak image editor, klik tombol open lalu pilih file Spritefont.png yang telah diunduh.

   ![08](/assets/008/08.png)

7. Font yang telah dipasang memiliki konfigurasi sendiri di properties. Anda dapat membuka file **SpriteFont*ErasITC_Medium*(48)\_[0,0,0,0]\_53x54.txt**

   ![09](/assets/008/09.png)

   Jika dibuka seperti berikut:

   ![010](/assets/008/010.png)

8. Aturlah properties pada Object **TextGameover** sebagai berikut:
   - Character width: **53**
   - Character height: **54**
   - Character set: ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789.,;:?!-\_~#"'&()[]|`\/@°+=\*$£€<>%
   - Text: **Game Over**
   - Scale: **3**
   - Char width JSON: {""c2array"":true,""size"":[2,30,1],""data"":[[[8],[10],[11],[12],[13],[14],[15],[16],[19],[20],[21],[23],[24],[25],[26],[27],[28],[29],[30],[31],[32],[34],[35],[37],[38],[39],[40],[41],[45],[51]],[[""'|""],[""I.""],[""il:!""],[""()`""],[""1,;\""""],[""°""],[""[]""],[""-""],[""rt""],[""fs""],[""j*""],[""Jcz$""],[""S?""],[""Lk""],[""Fa57\\<>""],[""EPRe236""],[""Bdqux0489~#+=£""],[""KTbghnopv_/""],[""Z""],[""CYy""],[""€""],[""HUX""],[""DGN&""],[""V""],[""A""],[""OQ@""],[""M""],[""m%""],[""w""],[""W""]]]}
   - Space char width: 10

Sehingga seperti berikut:

![011](/assets/008/011.png)
