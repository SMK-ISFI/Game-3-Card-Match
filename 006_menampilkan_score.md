# Menampilkan Score

Score untuk menampilkan Nilai sedang diperoleh sedangkan Highscore untuk menampilkan nilai tertinggi setelah beberapa kali bermain. Untuk menambahkan sistem **highscore**, yang diperlukan hanya **perbandingan** antara **Highscore** dan **Score**. Jika nilai Score lebih tinggi dari pada nilai Highscore maka sistem akan langsung menerapkan nilai Highscore berdasarkan nilai yang ada pada Score. Jika tidak maka sistem tidak akan menggantikan nilai Highscore tersebut.

1. Buka Layout 1, masukkan Object **Text** dengan nama **TextScore** (klik kanan pada layout > Pilih **Insert new object** > Pilih **Text** > Beri nama **TextScore** > Klik **Insert**)

   ![01](/assets/006/01.png)

2. Kemudian atur posisi object text tersebut pada layout dan atur properties object **TextScore** sebagai berikut:

   ![02](/assets/006/02.png)

3. Buka kembali Event sheet, kemudian tambahkan action untuk menampilkan score ketika melakukan penambahan atau pengurangan score.

   Action:
   - **TextScore** > **Set text** > Text: **score**

   Maka hasilnya:
   ![03](/assets/006/03.png)
   - **TextScore** -> **Set text to score**, menampilkan nilai score sebagai text dan pastikan setelah penambahan /pengurangan nilai variable **score**

   Ketika dijalankan hasilnya sebagai berikut:
   ![04](/assets/006/04.gif)
