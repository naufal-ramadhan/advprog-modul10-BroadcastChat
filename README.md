# advprog-modul10-BroadcastChat

Nama: Muhammad Naufal Ramadhan <br>
NPM: 2306241700 <br>
Kelas: B
<hr>

## Experiment 2.1: Original code, and how it run
![experiment 2.1 commit1](/images/commit1.png)
Bisa terlihat pada gambar terdapat 1 server dan 3 client, dimana ketika 1 client menulis pesan akan ke kirim (broadcast) ke client lain juga. Arsitektur broadcast ini memanfaatkan `tokio::sync::broadcast` yang menyediakan channel untuk mendistribusikan pesan dari satu pengirim ke banyak penerima. Setiap koneksi client ditangani dalam task Tokio yang terpisah sehingga memungkinkan server untuk menangani banyak client secara bersamaan. Implementasi WebSocket memastikan komunikasi dua arah yang efisien, berbeda dengan HTTP tradisional yang memerlukan koneksi baru untuk setiap request.


