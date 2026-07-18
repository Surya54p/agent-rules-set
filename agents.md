# ATURAN PALING PENTING UNTUK AGEN (SANGAT WAJIB)
1. Patuhi aturan agents.md sebelum kalian bertindak.
2. Lakukan tindakan sesuai dengan peran masing-masing.
3. Jika ada sesuatu yang tidak dipahami, tanyakan kepada user. 
4. setiap agent bekerja sesuai dengan tuga masing-masing.
5. setiap agent tidak boleh melakukan tindakan yang bukan merupakan tugasnya.
6. setiap agent harus melaporkan setiap perubahan atau penambahan yang dilakukannya.

# Base Behavior:
1. Jika saya tidak mengucapkan kata "implementasikan" atau "implement", maka jangan lakukan tindakan implementasi apa pun, cukup baca saja!
2. Jangan pernah menulis kode tanpa izin dari saya.
3. Selalu mulai dengan memberikan respons terlebih dahulu, jangan melakukan tindakan lain jika saya tidak mengatakannya secara spesifik.
4. Ketika saya memberikan perintah tanpa mengucapkan kata "implementasikan" atau "implement", itu artinya Anda perlu membuat rencana implementasi dan memberikan umpan balik (*feedback*) tentang apa yang sedang coba saya bangun.
5. BACA BERKAS `COORDINATION.MD` terlebih dahulu.
6. Setiap kali Anda selesai menulis kode, tulis di berkas `coordination.md` mengenai apa saja yang telah Anda selesaikan dan apa yang harus dilakukan oleh agen berikutnya.
7. Jika Anda memiliki tugas di dalam `coordination.md` yang belum diimplementasikan, tanyakan kepada saya terlebih dahulu. Sangat wajib untuk meminta izin saya sebelum melakukan tindakan.
8. Setelah Anda melakukan perubahan pada kode, laporkan setiap berkas mengenai apa saja yang telah Anda lakukan dan apa tujuannya.

# Aturan ROOT:
1. jika terdapat function yang dimanfaatkan pada tempat yang beragam, maka pindahkan function itu ke file utilities yang dapat dimanfaatkan untuk komponen lain.
2. pembatasan input yang ketat, setiap input user harus di validasi baik dari frontend maupun backend, jangan sampai ada input aneh masuk ke dalam database. 
3. env first, dilarang keras menulis konten penting atau mengisi nilai parameter API key secara langsung hardcoded, semuanya harus berdasarkan .env.

# Aturan styling UI&Frontend:
1. Gunakan proporsi warna 6:3:1 (60% warna primer, 30% warna sekunder, 10% warna aksen)
2. Gunakan tipografi yang konsisten dengan proposisi 4:3:1 (40% ukuran font primer, 30% ukuran font sekunder, 10% ukuran font aksen), secara default font size text biasa menggunakan ukuran text-base dan warna normal, judul dengan text-3xl, font semibold dan menggunakan warna primer untuk subjudul gunakan text biasa namun semibold aja dan menggunakan warna yang sama pada text base. dilarang keras membuat style dengan font selain dari itu atau membuat style secara sembarangan. dilarang menggunakan aksesoris font yang diluar dari aturan ini seperti leading wide dan lainnya. 
3. Gunakan padding dan margin yang konsisten yaitu bernilai ganjil kelipatan 3 (cth: 3, 9, 15, 21, 27) namun secara default padding atau margin bernilai 3 pada sumbu x dan y.
4. Gunakan border yang konsisten dengan aturan berikut: menggunakan border radius hanya dengan tingkat md saja tidak boleh selain dari itu, gunakan border color border-1 dengan warna border adalah warna aksen dari proporsi utama pada rule no 1. 
5. Gunakan layout yang konsisten
6. Gunakan spacing yang konsisten antar element dengan proporsi genap (cth: 2, 8, 14, 20, 26) namun secara default spacing bernilai 6 pada sumbu x dan y.
7. dilarang memuat style style lebay seperti shadow border radius gede dan lainnya, utamakan kerapihan, sharpness, dan tata letak yang simetris.
8. setiap ada field input wajib melakukan pengecekan dan pembatasan input misal max file 2mb dan upload file dibatasin hanya png, jpg, dan jpeg.
9. component first, jika di dalam page ada kebutuhan elemen seperti table, search field, filter, button, modal dan elemen lainnya, maka lakukan pencarian komponen yang dibutuhkan  tersebut ke folder components. jika tidak ditemukan laporkan ke pengguna dan sarankan apakah perlu dibuat komponen tersebut reusable.
10. jika terdapat komponen yang bisa digunakan kembali pada halaman atau komponen lain, maka pisahkan elemen tersebut ke file components masing-masing.
11. setiap komponen reusable memiliki parameter parameter yang relevan yang dapat digunakan untuk mengatur bagaimana dia terlihat dan berperilaku. sebagai contoh komponen button wajib memiliki parameter untuk size (sm, md, lg dengan default md) dan type (primary, secondary, ternary, destructive, outline dan link). untuk penggunaan warna pada komponen mengikuti proporsi warna pada rule no 1. namum untuk komponen yang dapat mempengaruhi ux dan kepahaman pengguna terhadap komponen itu maka komponen itu bisa menggunakan warna atau style tambahan yang relevan sesuai fungsinya.
12. setiap komponen reusable memiliki file story yang digunakan untuk mendokumentasikan komponen tersebut.

# Aturan Backend&Database
1. setiap entitas wajib memiliki modelnya masing-masing.
2. setiap logika bisnis dicatat pada schemanya masing-masing.
3. jika terdapat function yang dimanfaatkan pada tempat yang beragam, maka pindahkan function itu ke file utilities yang dapat dimanfaatkan untuk komponen lain.
4. setiap data yang data dari POST, PUT atau cara lainnya yang bersinggungan ke database, pastikan divalidasi ketat, jangan sampai ada inputan yang aneh masuk ke dalam database.
5. selalu gunakan ORM yang tersedia. dilarang mengakses database secara langsung. manfaatkan penggunaan migrasi dan seeding.
6. setiap melakukan debugging yang bersinggungan dengan logic atau database, laporkan ke user terlebih dahulu. dan pastikan file yang sudah di tulis untuk debugging saja itu di hapus.

# Aturan Pengelolaan Docker & Environment (.env)

1. **DILARANG KERAS** mengubah konfigurasi Docker (`docker-compose.yml`, `docker.yml`, `backend/Dockerfile`, `frontend/Dockerfile`).
2. **DILARANG KERAS** mengedit/memodifikasi berkas `.env` secara langsung. Jika ingin menambah, mengubah, atau menghapus variabel lingkungan, modifikasi hanya boleh dilakukan pada berkas `.env.local`.