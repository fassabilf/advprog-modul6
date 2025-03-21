## Commit 1 Reflection Notes  
**Apa isi dari fungsi `handle_connection`?**

Fungsi `handle_connection` bertugas menangani koneksi yang masuk dari browser. Di dalamnya, digunakan `BufReader` untuk membaca data dari `TcpStream` secara efisien baris demi baris. Kemudian, fungsi ini mengumpulkan setiap baris dari permintaan HTTP (HTTP request) sampai menemukan baris kosong yang menandai akhir dari bagian header. Semua baris tersebut disimpan dalam sebuah vector bertipe `String`. Setelah seluruh header berhasil dikumpulkan, isi dari permintaan HTTP tersebut dicetak ke console dengan format yang rapi menggunakan `{:#?}` agar lebih mudah dibaca.

## Commit 2 Reflection Notes  
**Apa yang dilakukan fungsi `handle_connection` setelah update?**

![Commit 2 screen capture](assets/images/commit2.png)

Pada tahap ini, fungsi `handle_connection` diperbarui agar tidak hanya membaca permintaan dari browser, tetapi juga memberikan respons berupa halaman HTML sederhana. File HTML dibaca menggunakan fungsi `fs::read_to_string`, lalu isinya dikemas dalam format HTTP response lengkap dengan status line (`HTTP/1.1 200 OK`) dan `Content-Length` yang sesuai. Respons ini kemudian dikirim kembali ke browser melalui koneksi TCP. Dengan perubahan ini, server sudah mampu menampilkan halaman web statis secara langsung, tanpa menggunakan framework tambahan.

Saya juga memodifikasi file `hello.html` untuk menampilkan pesan pribadi, dan saat mengakses server di browser, halaman tersebut berhasil ditampilkan. Ini membuktikan bahwa server merespons permintaan HTTP dengan benar.

