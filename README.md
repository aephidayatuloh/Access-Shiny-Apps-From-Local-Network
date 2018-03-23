# Access Shiny Apps From Local Network
Beberapa waktu terakhir ini ada orang yang bertanya tentang "Apakah ada cara lain agar orang lain, rekan kerja atau user dari web apps yang sudah dibuat menggunakan shiny tanpa memanfaatkan shinyapps.io?". Ada juga pertanyaan "Bagaimana caranya agar web apps shiny saya dapat diakses di jaringan lokal seperti melalui WiFi atau LAN di tempat kerja?".

Bagi Anda yang belum familiar dengan shiny dapat mebacanya di <http://shiny.rstudio.com/>. 

Misalkan Anda sudah membuat sebuah atau bahkan mungkin beberapa web apps menggunakan shiny, tentu Anda ingin agar orang lain dapat menggunakannya. Namun tidak ingin mengunggahnya ke shinyapps.io atau server lainnya dengan alasan hanya orang tertentu yang diizinkan mengaksesnya, aplikasi tersebut hanya boleh diakses melalui local network kerja Anda, atau karena alasan keamanan dan kerahasiaan lainnya.

Selain dapat di-deploy ke sebuah server host secara online, aplikasi shiny juga dapat digunakan/diakses melalui local network. Cara yang pertama, Anda dapat memberikan seluruh file shiny termasuk data-data yang dibutuhkan untuk dapat menjalankan aplikasi tersebut dengan baik. Cara ini mengharuskan user atau orang yang akan membuka aplikasi tersebut di komputernya harus sudah terinstal R (+RStudio), seluruh package dan seluruh file+data yang dibutuhkan untuk dapat menjalankan aplikasi tersebut. Buka aplikasi tersebut seperti Anda menjalankannya pada saat development.

Cara lain adalah dengan menyediakan sebuah PC yang berfungsi sebagai sebuah server lokal. Pastikan PC tersebut dapat diakses oleh semua user yang akan mengakses aplikasi shiny tersebut dan aplikasi harus aktif sebelum diakses. Jalankan dan pastikan aplikasi tersebut dapat berjalan dengan baik di server lokal ini. 

## Bagaimana cara mengaksesnya?

Agar aplikasi yang berjalan pada server dapat diakses, ikuti langkah-langkah berikut. 

### 1. Jalankan aplikasi dari RStudio.
Ada sedikit perbedaan pada saat menjalankan aplikasi ini dibandingkan dengan menjalankan saat development.

Pada saat development mungkin Anda akan menjalankan aplikasi dengan mengklik **Run App** pada RStudio Anda, atau dengan menjalankan script R di bawah ini.
``` markdown
shiny::runApp("/path/to/myapps")
```

Jika Anda membuat shiny app ini dalam sebuah project di RStudio Anda cukup dengan menggunakan script berikut.
``` markdown
shiny::runApp()
```

Cara ini dapat menjalankan aplikasi shiny Anda namun orang lain tidak akan dapat mengakses aplikasi ini dari browser PC mereka. Misalkan IP dari PC server lokal yang digunakan adalah 192.168.229.109. Pastikan PC user/client yang akan mengakses dapat mengakses IP tersebut. Agar dapat diakses jalankan script berikut.
``` markdown
shiny::runApp("/path/to/myapps", host = "0.0.0.0", port = 5050)
```

Tambahan ```host = "0.0.0.0"``` dan ```port = 5050``` agar aplikasi tersebut dapat diakses oleh user. Anda dapat menggunakan ```"0.0.0.0"``` untuk host atau nilai lain dengan format string, sedangkan untuk port Anda dapat menggunakan 4 digit angka yang lain yang belum digunakan dalam PC tersebut agar tidak terjadi konflik. Port ini harus bernilai numerik sehingga tidak boleh diapit oleh tanda kutip. 

### 2. Mengakses Aplikasi
Setelah menjalankan aplikasi dengan script di atas, user dapat mengakses melalui browser mereka.

1. Buka browser di PC user.
2. Ketik IP PC server dan port aplikasi yang dijalankan dengan dipisahan tanda titik-dua (:).
Misalkan IP PC server adalah 192.168.229.109 dan port aplikasi kita adalah 5050. Maka ketikkan di browser user 192.168.229.109:5050.

## Troubleshoot
Jika Anda masih tidak dapat mengakses aplikasi tersebut, pastikan:
1. PC server dapat diakses dari PC user.
2. Pastikan aplikasi sudah dijalankan dan dapat berjalan dengan baik di server.
3. Pastikan port yang digunakan tidak ada konflik dengan port lain atau port sudah digunakan.

Demikian cara menjalankan dan mengakses shiny apps dari server lokal ini. 
Semoga bermanfaat.
^_^

