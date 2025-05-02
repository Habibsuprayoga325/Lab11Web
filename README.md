## PHP FRAMEWORK (Codeigneter4)
| Praktikum 4-6  |  Pemrograman Web 2   |
|-------|--------- |
| Nama   | Habib Suprayoga |
| Nim  | 312310608 |
| Kelas | TI.23.A6 |
| **Mata Kuliah**    |     Pemrograman Web 2    |
| **Dosen Pengampu** |Agung Nugroho, S.Kom., M.Kom  |

## Praktikum 4

### Langkah-langkah Praktikum
- Membuat Table User
```
CREATE TABLE user (
 id INT(11) auto_increment,
 username VARCHAR(200) NOT NULL,
 useremail VARCHAR(200),
 userpassword VARCHAR(200),
 PRIMARY KEY(id)
);
```
- Membuat Model User
![image](https://github.com/user-attachments/assets/2773bb58-b14a-4016-b8ac-2c22dcdb2ee1)


- Membuat Database Seeder

Database seeder digunakan untuk membuat data dummy. Untuk keperluan ujicoba modul
login, kita perlu memasukkan data user dan password kedalam database. Untuk itu buat
database seeder untuk tabel user. Buka CLI, kemudian tulis perintah berikut:
![image](https://github.com/user-attachments/assets/9e0925cb-17c5-459d-ad8d-043ee5f386c3)


Selanjutnya, buka file UserSeeder.php yang berada di lokasi direktori
/app/Database/Seeds/UserSeeder.php kemudian isi dengan kode berikut:
![image](https://github.com/user-attachments/assets/92ff2310-feec-47dd-afea-9a3d489e38ee)


Selanjutnya buka kembali CLI dan ketik perintah berikut:
![image](https://github.com/user-attachments/assets/78784d2b-0202-432e-bdbe-95a17982c745)

- Uji Coba Login

Selanjutnya buka url http://localhost:8080/user/login seperti berikut:
![image](https://github.com/user-attachments/assets/20cd869b-bca2-4968-a617-84fa464df561)


- Menambahkan Auth Filter

Selanjutnya membuat filer untuk halaman admin. Buat file baru dengan nama Auth.php pada
direktori app/Filters. 
![image](https://github.com/user-attachments/assets/e92e6e67-3019-4e55-aa59-ae3c56a59d3b)


Selanjutnya buka file app/Config/Filters.php tambahkan kode berikut:
```
'auth' => App\Filters\Auth::class
```
![image](https://github.com/user-attachments/assets/558adc7b-da8c-4b9e-908c-0f2c2893636f)


Selanjutnya buka file app/Config/Routes.php dan sesuaikan kodenya.
![image](https://github.com/user-attachments/assets/19a33b93-cdd4-4fe5-ac6a-77becad31d70)


Percobaan Akses Menu Admin

Buka url dengan alamat http://localhost:8080/admin/artikel ketika alamat tersebut diakses
maka, akan dimuculkan halaman login. 
![image](https://github.com/user-attachments/assets/c7a40fc4-154e-442f-875e-38e16906ea8a)


## Praktikum 5
- Membuat Pagination

Pagination adalah teknik yang digunakan untuk membatasi jumlah besar data yang ditampilkan pada sebuah situs web menjadi beberapa halaman, tergantung pada jumlah data yang akan ditampilkan pada setiap halaman.

Untuk membuat pagination, buka Kembali App/Controller/Artikel, kemudian modifikasi kode
pada method public function admin_index seperti berikut.

![image](https://github.com/user-attachments/assets/b2583a72-0388-43d0-b578-122a1152f0aa)





Dan pada link pager ubah seperti berikut.
App/Views/artikel/admin_index.php bagian paling bawah diatas footer
![image](https://github.com/user-attachments/assets/574f5ea0-d710-4608-9336-33ee93b9c826)


Hasilnya akan seperti ini:

![image](https://github.com/user-attachments/assets/786f354e-8e1e-4a17-955e-638278d9928b)


### Praktikum 6
- Menambahkan fungsi unggah gambar pada tambah artikel.

Buka kembali Controller Artikel pada project sebelumnya, sesuaikan kode pada method
add seperti berikut:

![image](https://github.com/user-attachments/assets/5bebc004-de00-4a97-8a26-f70ecb400882)

Kemudian pada file views/artikel/form_add.php tambahkan field input file seperti
berikut:

![image](https://github.com/user-attachments/assets/9aed5a31-0f68-4764-b2fe-33b7867f4f80)


Ujicoba file upload dengan mengakses menu tambah artikel.

![image](https://github.com/user-attachments/assets/4f61f5fb-73b2-4f21-8275-c9e41f52fefb)
