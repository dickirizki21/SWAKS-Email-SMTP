# Installasi SWAKS Ubuntu
 1. Jalankan perintah ini pada terminal 
```
sudo apt update
sudo apt install swaks
```
 2. Cek apakah SWAKS sudah berhasil di install
```
swaks --help
```

# Kirim Email Menggunakan SWAKS
Jika swaks sudah ter instal dengan baik, maka kita akan melakukan pengetesan kirim email menggunakan SWAKS. yang harus disiapkan untuk dapat mengirim email menggunakan SWAKS adalah, akun RELAY SMTP, HOST, username, password.
 1. Kirim email plain text menggunakan SWAKS. 
 ##### Jalankan perintah ini di terminal, untuk host, username dan password SMTP bisa disesuaikan.
```
swaks --pipeline -tls --server server.host.co.id --port 587 --auth-user 'akun.user.co.id' --auth-pass 'passwordakunrelay' --from 'dicki@gmail.com' --to 'rizki@gmail.com' --header "To: rizki@gmail.com" --header 'Subject: Send Email With SWAKS' --body 'Test isi body kirim email dengan swaks'

```
 2. Kirim email HTML menggunakan SWAKS
##### Buat file di linux dengan format html, salin kode berikut. 
``` html
<!DOCTYPE html>
<html>
<body>

<h1>Send Mail With SWAKS</h1>

<p>THis is file HTML</p>

</body>
</html>
```
##### Jika sudah jalankan perintah berikut di terminal. untuk host, username, dan password akun relay bisa disesuaikan.
```
swaks --pipeline -tls --server server.host.co.id --port 587 --auth-user 'akun.user.co.id' --auth-pass 'passwordakunrelay' --from 'dicki@gmail.com' --to 'rizki@gmail.com' --header "To: rizki@gmail.com" --header 'Subject: Send Email With SWAKS' --attach-body '/path/to/file.html'
```
 3. Kirim email dengan attachment .TXT menggunakan SWAKS
##### Buat file dengan format txt dan salin kata-kata berikut.
```
Ini merupakan isi dari file .txt sebagai attahment dalam mengirim email menggunakan SWAKS
```
##### Jika sudah jalankan perintah berikut di terminal. untuk host, username, dan password akun relay bisa disesuaikan.
```
swaks --pipeline -tls --server server.host.co.id --port 587 --auth-user 'akun.user.co.id' --auth-pass 'passwordakunrelay' --from 'dicki@gmail.com' --to 'rizki@gmail.com' --header "To: rizki@gmail.com" --header 'Subject: Send Email With SWAKS' --body 'Isi body swaks dengan attachment file htlm' --attach '/path/to/file.html'
```
