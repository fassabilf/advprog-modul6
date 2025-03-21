## Commit 1 Reflection Notes  
**Apa isi dari fungsi `handle_connection`?**

Fungsi `handle_connection` bertugas menangani koneksi yang masuk dari browser. Di dalamnya, digunakan `BufReader` untuk membaca data dari `TcpStream` secara efisien baris demi baris. Kemudian, fungsi ini mengumpulkan setiap baris dari permintaan HTTP (HTTP request) sampai menemukan baris kosong yang menandai akhir dari bagian header. Semua baris tersebut disimpan dalam sebuah vector bertipe `String`. Setelah seluruh header berhasil dikumpulkan, isi dari permintaan HTTP tersebut dicetak ke console dengan format yang rapi menggunakan `{:#?}` agar lebih mudah dibaca.

