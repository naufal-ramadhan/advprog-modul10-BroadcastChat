# advprog-modul10-BroadcastChat

Nama: Muhammad Naufal Ramadhan <br>
NPM: 2306241700 <br>
Kelas: B
<hr>

## Experiment 2.1: Original code, and how it run
![experiment 2.1 commit1](/images/commit1.png)
Bisa terlihat pada gambar terdapat 1 server dan 3 client, dimana ketika 1 client menulis pesan akan ke kirim (broadcast) ke client lain juga. Arsitektur broadcast ini memanfaatkan `tokio::sync::broadcast` yang menyediakan channel untuk mendistribusikan pesan dari satu pengirim ke banyak penerima. Setiap koneksi client ditangani dalam task Tokio yang terpisah sehingga memungkinkan server untuk menangani banyak client secara bersamaan. Implementasi WebSocket memastikan komunikasi dua arah yang efisien, berbeda dengan HTTP tradisional yang memerlukan koneksi baru untuk setiap request.

## Experiment 2.2: Modifying port
![experiment 2.2 commit2](/images/commit2.png)
Bisa dilihat kedua aplikasi (server dan client) dapat tetap berjalan dengan baik ketika dilakukan pergantian port, dari port 2000 menjadi port 8080 pada kedua sisi, dengan mengganti pada server.rs di baris let listener = TcpListener::bind("127.0.0.1:8080").await?; dan pada client.rs di baris ClientBuilder::from_uri(Uri::from_static("ws://127.0.0.1:8080")). Perubahan port ini menunjukkan fleksibilitas aplikasi dalam berkomunikasi melalui endpoint jaringan yang berbeda. Port pada dasarnya hanyalah sebuah endpoint komunikasi yang berfungsi sebagai "pintu" tempat aplikasi dapat berkomunikasi melalui jaringan. Selama perubahan dilakukan secara konsisten di kedua sisi (client dan server), komunikasi akan tetap berjalan dengan baik tanpa masalah.
