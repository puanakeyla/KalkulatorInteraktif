# KalkulatorInteraktif by Puan Akeyla

## Spesifikasi

### Interface Kalkulator
- **Display angka & hasil**: Elemen `.display` menampilkan ekspresi berjalan dan hasil akhir.
- **Tombol angka 0–9**: Tersedia pada grid utama tombol.
- **Tombol operasi (+, −, ×, ÷)**: Diberi kelas `.btn-operator` dengan ikon operator matematika.
- **Tombol C & CE**: Tombol aksi (`data-action="clear"` dan `clear-entry`).
- **Tombol =**: `data-action="equals"` mengeksekusi evaluasi ekspresi.
- **Tombol titik desimal**: `data-action="decimal"` menambahkan `.` ke input.

### Functionality
- **Operasi dasar ( + − × ÷ )**: Ditangani oleh engine token + shunting-yard pada bagian `<script>`.
- **Perhitungan berantai**: Dukungan input berurutan seperti `5 + 3 × 2` karena evaluasi menghormati prioritas operator.
- **Penanganan error (÷0)**: Fungsi `evaluateTokensWithPrecedence` memblokir pembagian dengan nol dan menampilkan pesan.
- **Keyboard support**: Event `keydown` menangani angka, operator, Enter/=`=`, Escape, Backspace, dan titik.

### Advanced Features
- **History 5 terakhir**: Array `history` dan elemen `.history-panel` menyimpan/menampilkan lima hasil terbaru.
- **Memory functions**: Tombol `MC`, `MR`, `M+`, `M-` bekerja melalui variabel `memoryValue` di script.
- **Responsive design**: Media query di bagian CSS memastikan tata letak nyaman di layar mobile dan desktop.

## Cara Menjalankan
1. Buka folder repo ini di VS Code atau file explorer.
2. Klik dua kali atau jalankan menggunakan ekstensi Live Server.
3. Interaksi dapat dilakukan lewat mouse atau keyboard (angka, operator, Enter, Escape, Backspace, titik).

## Pengujian yang Disarankan
- **Operasi dasar**: `12 + 8 = 20`, `9 − 5 = 4`, `6 × 7 = 42`, `8 ÷ 4 = 2`.
- **Prioritas operator**: `6 + 0 × 3` menghasilkan `6`, `5 − 12 × 0` menghasilkan `5`.
- **Error handling**: `9 ÷ 0` memunculkan pesan "Tidak bisa membagi dengan 0" tanpa menghentikan aplikasi.
- **History & memori**: Jalankan beberapa perhitungan, cek panel riwayat, gunakan M+, M-, MR, MC.
- **Keyboard**: Ketik `7`, `+`, `8`, `Enter`; gunakan `Escape` untuk C dan `Backspace` untuk koreksi angka.
- **Responsif**: Gunakan DevTools atau ubah ukuran jendela untuk memastikan tata letak tetap rapi <600px.
