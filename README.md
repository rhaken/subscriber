
# Tutorial 8 - Refleksi

## a) Pengertian AMQP
AMQP, atau Advanced Message Queuing Protocol, adalah sebuah protokol yang memungkinkan aplikasi untuk saling berkomunikasi dengan aplikasi sumber yang mengirimkan informasi atau data. Dalam konteks ini, data dikirimkan melalui middleware messaging, yang memungkinkan klien untuk mengambil data yang mereka perlukan dari middleware ini.

Pada URL `amqp://guest:guest@localhost:5672`, AMQP merupakan protokol yang digunakan untuk melakukan transaksi data.

## b) Penjelasan Komponen URL: `guest:guest@localhost:5672`
- **guest:guest** adalah representasi dari username dan password yang digunakan untuk autentikasi oleh server.
- **localhost:5672**:
  - **localhost** merujuk pada hostname dari server, di mana hostnya adalah perangkat lokal.
  - **5672** adalah port yang digunakan untuk AMQP.
