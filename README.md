# Access Shiny Apps From Local Network
Beberapa waktu terakhir ini ada orang yang bertanya tentang "Apakah ada cara lain agar orang lain, rekan kerja atau user dari web apps yang sudah dibuat menggunakan shiny tanpa memanfaatkan shinyapps.io?". Ada juga pertanyaan "Bagaimana caranya agar web apps shiny saya dapat diakses di jaringan lokal seperti melalui WiFi atau LAN di tempat kerja?".

Bagi Anda yang belum familiar dengan shiny dapat mebacanya di <http://shiny.rstudio.com/>. 

Misalkan Anda sudah membuat sebuah atau bahkan mungkin beberapa web apps menggunakan shiny, tentu Anda ingin agar orang lain dapat menggunakannya. Namun tidak ingin mengunggahnya ke shinyapps.io atau server lainnya dengan alasan hanya orang tertentu yang diizinkan mengaksesnya, aplikasi tersebut hanya boleh diakses melalui local network kerja Anda, atau karena alasan keamanan dan kerahasiaan lainnya.

Selain dapat di-deploy ke sebuah server host secara online, aplikasi shiny juga dapat digunakan/diakses melalui local network. Cara yang pertama, Anda dapat memberikan seluruh file shiny termasuk data-data yang dibutuhkan untuk dapat menjalankan aplikasi tersebut dengan baik. Cara ini mengharuskan user atau orang yang akan membuka aplikasi tersebut di komputernya harus sudah terinstal R (+RStudio), seluruh package dan seluruh file+data yang dibutuhkan untuk dapat menjalankan aplikasi tersebut. Buka aplikasi tersebut seperti Anda menjalankannya pada saat development.

Cara berikutnya adalah dengan menyediakan sebuah PC yang berfungsi sebagai sebuah server lokal. Pastikan PC tersebut dapat diakses oleh semua user yang akan mengakses aplikasi shiny tersebut. Jalankan dan pastikan aplikasi tersebut dapat berjalan dengan baik di server lokal ini. 
