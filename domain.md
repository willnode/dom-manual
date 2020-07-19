---
title: Domain
nav_order: 3
---

# Seputar Tentang Domain

### Apa itu Domain?

Domain adalah alamat internet yang mudah diingat. Seperti yang kita tahu, alamat IP hosting ialah melalui format angka 32 bit `xxx.xxx.xxx.xxx` , dan itu susah diingat. Dengan domain, kita hanya perlu mengingat `google.co.id` dan komputer akan menerjemahkannya menjadi salah satu alamat IP server Google:  `172.217.194.94`; Sistem ini dinamakan sebagai **DNS lookup**. 

### Bagaimana DNS Lookup Bekerja?

DNS Lookup membutuhkan DNS *(Domain Name Server)* yang tersebar di seluruh dunia. Saat komputer anda mulai terkoneksi dengan internet, ISP anda memberikan alamat *default* DNS. Komputer anda dapat menggunakan alamat tersebut sebagai DNS awal atau menggunakan alamat DNS lain (seperti `8.8.8.8` ) tergantung pengaturan DNS di komputer anda. 

Setelah mendapatkan alamat DNS awal, kapanpun komputer anda menjumpai domain baru, komputer akan melakukan *request* domain pada alamat tersebut. Contoh untuk `tokoku.id`, DNS tersebut melakukan lookup terhadap top-level domain (TLD), yakni `.id` dan melakukan request domain pada *registrar* `.id` untuk mencari tujuan IP dari domain yang dicari, `tokoku.id`. Setelah IP ditemukan registrar tersebut akan melakukan lookup terhadap IP tersebut, yang berisi tentang *Name Server* pemilik domain. Name Server inilah yang menjadi acuan bagaimana hasil dari DNS di respon, melalui banyak jenis record domain seperti `A`, `AAAA`, `CNAME`, dsb.

### Bagaimana Cara Mendaftarkan Domain?

Jika anda mendaftarkan hosting paket Free (gratis), anda tidak perlu mendaftarkan domain apapun, karena menggunakan fasilitas subdomain dari domain induk `dom.my.id`.

Saat mendaftarkan hosting paket berbayar, anda dapat membeli domain dengan paket TLD yang tersedia, yakni `.com`, `.xyz` dan 9 varian domain `.id`.  Jika anda ingin opsi TLD yang lain, anda dapat membeli domain di provider domain lain dan mengarahkan domain tersebut pada hosting ini.

### Bagaimana Cara Mengarahkan Domain?

Untuk pengaturan paling dasar, anda dapat memberikan record A, yakni record yang tertuju langsung pada alamat IP. Misal jika anda mempunyai domain `tokoku.id` dan server pada alamat IP `52.231.195.213` maka pengaturan domain sebagai berikut:

Record|Type|Value
---|---|---
tokoku.id|A|52.231.195.213

Anda juga dapat menambahkan beberapa A record agar dapat menangkap subdomain 

Record|Type|Value
---|---|---
www\.tokoku.id|A|52.231.195.213
app.tokoku.id|A|52.231.195.213

Jika anda ingin mengarahkan domain ke website yang sudah ada, anda dapat menambahkan record CNAME. Record CNAME diisi dengan nama domain aktif. Contoh kegunaan record CNAME ialah jika anda ingin menggunakan domain untuk Halaman Github Statis. 

| Record        | Type  | Value            |
| ------------- | ----- | ---------------- |
| app.tokoku.id | CNAME | tokoku.github.io |

 ## BIND DNS Server

Jika anda menggunakan hosting paket berbayar, anda dapat menggunakan DNS server yang tersedia dalam hosting. 
