# Module 10 Tutorial: Asynchronous Programming

Advanced Programming (Even Semester 2024/2025) Tutorial Module 10

Khansa Khairunisa - 2306152462

## Reflection

### Experiment 2.1: Original code, and how it run

![broadcast1](images/broadcast1.png)

Berdasarkan gambar di atas, server dijalankan terlebih dahulu dengan perintah `cargo run --bin server` di direktori `broadcast`. Server akan mulai mendengarkan koneksi pada port 2000 dan akan mencatat setiap koneksi baru yang masuk dari client. Untuk menjalankan tiga client, perintah `cargo run --bin client` dijalankan secara terpisah di tiga terminal berbeda. Setiap client yang berhasil terhubung akan menerima pesan sambutan dari server berupa "Welcome to chat! Type a message", lalu dapat langsung mengetik pesan.

Saat salah satu client mengirimkan pesan, server akan menerima pesan tersebut dan mencatatnya bersamaan dengan informasi koneksi client yang mengirimkannya. Selanjutnya, server akan membroadcast pesan tersebut ke seluruh client yang sedang aktif, termasuk client pengirimnya sendiri. Dengan cara ini, seluruh client dapat saling melihat pesan yang dikirimkan oleh client lain. Hal ini dimungkinkan karena server menyimpan semua koneksi aktif dan mengelola pengiriman pesan ke setiap koneksi secara paralel.