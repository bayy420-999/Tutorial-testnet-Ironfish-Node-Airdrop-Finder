# Tutorial testnet Ironfish Node Airdrop Finder

<p style="font-size:14px" align="right">
<a href="https://t.me/airdropfind" target="_blank">Join Telegram Airdrop Finder<img src="https://user-images.githubusercontent.com/50621007/183283867-56b4d69f-bc6e-4939-b00a-72aa019d1aea.png" width="30"/></a>
</p>

<p align="center">
  <img height="auto" width="auto" src="https://raw.githubusercontent.com/bayy420-999/airdropfind/main/NavIcon.png">
</p>

## Referensi

* [Dokumen resmi](https://ironfish.network/docs/onboarding/iron-fish-tutorial)
* [Explorer](https://explorer.ironfish.network/)
* [Server discord](https://discord.gg/A8uKyzjMqn)
* [Daftar leaderboard](https://testnet.ironfish.network/signup)

## Spesifikasi Software & Hardware

### Persyaratan Hardware

| Komponen | Spesifikasi minimal |
|----------|---------------------|
|CPU|4 Cores|
|RAM|8 GB DDR4 RAM|
|Penyimpanan|1 TB HDD|
|Koneksi|10Mbit/s port|

| Komponen | Spesifikasi rekomendasi |
|----------|---------------------|
|CPU|32 Cores|
|RAM|32 GB DDR4 RAM|
|Penyimpanan|2 x 1 TB NVMe SSD|
|Koneksi|1 Gbit/s port|

### Persyaratan Software/OS

| Komponen | Spesifikasi minimal |
|----------|---------------------|
|Sistem Operasi|Ubuntu 16.04|

| Komponen | Spesifikasi rekomendasi |
|----------|---------------------|
|Sistem Operasi|Ubuntu 22.04|

## Setup Node

### Registrasi leaderboard

1. Registrasi [disini](https://testnet.ironfish.network/signup)
2. Isi data sesuai yang diminta
3. Done

> Untuk bagian Graffiti isi terserah, Graffiti = MONIKER

### Install dependensi linux

```console
sudo apt-get update && upgrade
sudo apt-get install curl screen
```

### Install paket Node.js dan NPM

1. Install dan update NPM
   ```console
   curl -fsSL https://raw.githubusercontent.com/tj/n/master/bin/n | bash -s lts
   sudo npm install -g npm@latest
   ```
2. Install Node.js
   ```console
   sudo npm install -g n && n v18.13.0
   ```

Sebelum melanjutkan ke langkah berikutnya pastikan bahwa Node.js dan NPM sudah terinstall dengan menggunakan perintah dibawah

* Cek Node.js
  ```console
  node --version
  ```
* Cek NPM
  ```console
  npm --version
  ```

### Install dan jalankan Node

1. Download dan install Node menggunakan NPM
   ```console
   npm install -g ironfish
   ```
2. Setting Moniker dan blockGraffiti
   ```console
   ironfish config:set nodeName <MONIKER>
   ironfish config:set blockGraffiti <BLOCK_GRAFFITI>
   ```
3. Download snapshot
   ```console
   ironfish chain:download
   ```
4. Buka terminal baru menggunakan screen
   ```console
   screen -Rd ironfish
   ```
5. Jalankan Node
   ```console
   ironfish start
   ```

> Kalian bisa close terminal dengan menggunakan <kbd>CTRL</kbd>+<kbd>a</kbd>+<kbd>d</kbd>

### Buat dompet

1. Buat dompet
   ```console
   ironfish wallet:create
   ```

   > Nanti kalian diminta memasukan nama dompet

2. Setting dompet menjadi default
   ```console
   ironfish wallet:use <NAMA_DOMPET>
   ```

   > Ganti NAMA_DOMPET dengan nama dompet yang tadi kalian buat

### Memulai mining $IRON

1. Pastikan Node kalian sudah tersinkronisasi
```console
ironfish status -f
```

   Jika sudah sinkron maka akan muncul output seperti ini di terminal

   ```console
   Version              0.1.61 @ 009c85e
   Node                 STARTED
   Node Name            bayy420
   Block Graffiti       bayy420
   Memory               Heap: 58.67 MiB -> 92.03 MiB / 4.00 GiB
   (1.4%), RSS: 546.69 MiB (3.4%), Free: 2.94 GiB (81.1%)
   CPU                  Cores: 6, Current: 398.1%
   P2P Network          CONNECTED - In: 214 B/s, Out: 2.10 KB/s,
   peers 46
   Mining               STARTED - 1 miners, 0 mined
   Mem Pool             Count: 1 tx, Bytes: 2.70 KiB
   Syncer               IDLE - 3.41 blocks added/sec
   Blockchain           000000000015da69abfdeb77aefb601ed6049d8bf
   191ee2c6e01f60bf3aec8ca (4115), Since HEAD: 10s 284ms (SYNCED)
   Accounts             000000000015da69abfdeb77aefb601ed6049d8bf
   191ee2c6e01f60bf3aec8ca (4115)
   Telemetry            STOPPED
   Workers              STARTED - 0 -> 0 / 5 - 0.03 jobs Δ, 0.81
   jobs/s
   ```

2. Buat terminal baru untuk menjalankan miner
   ```console
   screen -Rd ironfish-mining
   ```

3. Mulai mining
   ```console
   ironfish miners:start
   ```

4. Keluar terminal dengan <kbd>CTRL</kbd>+<kbd>a</kbd>+<kbd>d</kbd>
5. Periksa status node lagi
   ```console
   ironfish status -f
   ```

### Perintah berguna

* Menjalankan Node
  ```console
  ironfish start
  ```
* Menampilkan log Node
  ```console
  ironfish logs
  ```
* Menampilkan status Node
  ```console
  ironfish status -f
  ```
* Buat dompet
  ```console
  ironfish wallet:create
  ```
* Setting dompet menjadi default
  ```console
  ironfish wallet:use <NAMA_DOMPET>
  ```
* Import dompet
  ```console
  ironfish wallet:import
  ```
* Menampilkan list dompet
  ```console
  ironfish wallet:accounts
  ```
* Menampilkan alamat dompet
  ```console
  ironfish wallet:address
  ```
* Menampilkan dompet yang menjadi default
  ```console
  ironfish wallet:which
  ```
* Menampilkan saldo dompet
  ```console
  ironfish wallet:balance
  ```
* Menampilkan semua saldo dompet
  ```console
  ironfish wallet:balances
  ```
* Menghapus dompet
  ```console
  ironfish wallet:remove <NAMA_DOMPET>
  ```
* Mengirim saldo
  ```console
  ironfish wallet:send
  ```
* Menampilkan daftar transaksi
  ```console
  ironfish wallet:transactions
  ```

## Troubleshoot

Reserved
