Panduan Perintah Dasar Ollama CLI

Dokumen ini berisi daftar perintah internal (slash commands) dan pintasan yang tersedia saat menjalankan model AI secara lokal melalui antarmuka interaktif Ollama di terminal (seperti ollama run qwen2.5-coder:7b).

1. Daftar Perintah Utama

Perintah

Deskripsi & Fungsi

/set

Mengatur variabel sesi, parameter teknis, dan system prompt.

/show

Menampilkan informasi dan konfigurasi detail dari model yang sedang aktif.

/load <model>

Memuat model lain atau sesi tersimpan tanpa perlu keluar dari terminal.

/save <model>

Menyimpan sesi saat ini (riwayat chat & pengaturan) sebagai varian model baru.

/clear

Menghapus seluruh riwayat percakapan (konteks) pada sesi saat ini.

/bye

Mengakhiri sesi interaktif dan keluar kembali ke terminal/PowerShell.

/? atau /help

Menampilkan daftar bantuan perintah yang tersedia.

/? shortcuts

Menampilkan daftar pintasan keyboard untuk navigasi cepat di terminal.

2. Detail Penggunaan Perintah

A. Mengatur Sesi (/set)

Gunakan perintah ini untuk menyesuaikan perilaku model sesuai kebutuhan:

Mengatur peran (System Prompt):

/set system Kamu adalah senior software engineer yang menjawab dengan ringkas dan akurat.


Mengatur parameter teknis (contoh: kreativitas & panjang memori):

/set parameter temperature 0.2
/set parameter num_ctx 8192


Menampilkan statistik kecepatan token (tokens/sec):

/set verbose


(Gunakan /set quiet untuk menyembunyikannya kembali).

B. Melihat Informasi Model (/show)

Gunakan untuk memeriksa spesifikasi teknis model yang sedang berjalan:

/show info — Melihat arsitektur model, jumlah parameter, dan tingkat kuantisasi.

/show modelfile — Melihat isi Modelfile bawaan, template prompt, dan parameter default.

/show system — Mengecek system prompt yang sedang aktif di sesi ini.

/show parameters — Melihat daftar parameter yang sedang diterapkan.

C. Menyimpan & Memuat Sesi (/save & /load)

Jika Anda sudah mengatur system prompt atau parameter khusus, simpan sebagai model baru agar tidak perlu mengatur ulang:

Menyimpan sesi:

/save asisten-koding


Memuat sesi atau pindah ke model lain:

/load asisten-koding


D. Manajemen Konteks & Keluar (/clear & /bye)

/clear — Gunakan saat ingin memulai topik baru agar jawaban model tidak tercampur dengan obrolan sebelumnya serta menghemat penggunaan RAM/VRAM.

/bye — Keluar dari antarmuka >>> kembali ke baris perintah sistem operasi.

3. Input Multi-Baris (Multi-line)

Untuk menempelkan (paste) potongan kode yang panjang atau menulis prompt lebih dari satu baris, gunakan tanda kutip tiga kali ("""):

>>> """
Tolong perbaiki bug pada kode Python berikut:

def hitung_total(harga, jumlah):
    return harga * jumlh
"""


4. Pintasan Keyboard (Shortcuts)

Ketik /? shortcuts di terminal untuk melihat daftar lengkapnya. Beberapa pintasan yang paling sering digunakan:

Ctrl + C — Menghentikan proses generasi jawaban model yang sedang berjalan.

Ctrl + D — Keluar dari sesi Ollama (sama seperti /bye).

Ctrl + U — Menghapus seluruh teks pada baris kursor ke arah kiri.

Ctrl + W — Menghapus satu kata sebelum kursor.

Ctrl + L — Membersihkan tampilan layar terminal.
