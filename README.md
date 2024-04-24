
# Tutorial 8 - Refleksi

## a) Pengertian AMQP
AMQP, atau Advanced Message Queuing Protocol, adalah sebuah protokol yang memungkinkan aplikasi untuk saling berkomunikasi dengan aplikasi sumber yang mengirimkan informasi atau data. Dalam konteks ini, data dikirimkan melalui middleware messaging, yang memungkinkan klien untuk mengambil data yang mereka perlukan dari middleware ini.

Pada URL `amqp://guest:guest@localhost:5672`, AMQP merupakan protokol yang digunakan untuk melakukan transaksi data.

## b) Penjelasan Komponen URL: `guest:guest@localhost:5672`
- **guest:guest** adalah representasi dari username dan password yang digunakan untuk autentikasi oleh server.
- **localhost:5672**:
  - **localhost** merujuk pada hostname dari server, di mana hostnya adalah perangkat lokal.
  - **5672** adalah port yang digunakan untuk AMQP.

# MQProcessWithSleep
![image](https://github.com/rhaken/publisher/assets/39646450/85b0e574-2a08-4203-ba84-a0b45b06f133)
Dalam contoh ini, saya mendapati bahwa Penerima mengalami penundaan dalam menerima atau memproses data dari jalur pesan dengan selang waktu 1 detik (1000 ms) untuk tiap proses. Karena itu, jumlah pesan yang tertunda dalam antrian jalur pesan bertambah seiring dengan penambahan waktu jeda yang diterapkan, sebab Pengirim mengirimkan data lebih cepat daripada kecepatan Penerima dalam menerima data tersebut. Pada kasus ini, terdapat total 35 pesan yang tertunda dalam antrian jalur pesan setelah 10 kali Pengirim mengirimkan pesan.

# 3ConcoleMQProcessWithSleep
![image](https://github.com/rhaken/subscriber/assets/39646450/56f02e1d-265a-4918-ab85-5e3a12fd5a64)
![image](https://github.com/rhaken/subscriber/assets/39646450/6e848b27-a090-4ca0-bf8d-dc9f7db677fc)
Dari tangkapan layar tersebut, terlihat bahwa setiap Subscriber mendapatkan data yang berbeda saat Publisher mengirimkan data dalam jumlah besar ke dalam antrian pesan. Ini disebabkan oleh setiap Subscriber berfungsi secara mandiri layaknya aplikasi terpisah, memungkinkan mereka mengambil data dari antrian pesan secara independen. Setelah data diambil, pesan tersebut akan dihapus dari antrian dan tidak tersedia lagi untuk aplikasi lain.

Lebih lanjut, saya berpendapat bahwa untuk meningkatkan efisiensi aplikasi Subscriber, satu langkah yang bisa dilakukan adalah mengimplementasikan multithreading sehingga memungkinkan mereka untuk memproses berbagai peristiwa dari Publisher secara simultan.


