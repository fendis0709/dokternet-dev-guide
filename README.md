**Edit a file, create a new file, and clone from Bitbucket in under 2 minutes**

When you're done, you can delete the content in this README and update the file with details for others getting started with your repository.

*We recommend that you open this README in another tab as you perform the tasks below. You can [watch our video](https://youtu.be/0ocf7u76WSo) for a full demo of all the steps in this tutorial. Open the video in a new tab to avoid leaving Bitbucket.*

---

## Laravel

Laravel is a web application framework with expressive, elegant syntax. We believe development must be an enjoyable and creative experience to be truly fulfilling. Laravel attempts to take the pain out of development by easing common tasks used in the majority of web projects.

Laravel is accessible, yet powerful, providing tools needed for large, robust applications.

Laravel has the most extensive and thorough [documentation](https://laravel.com/docs) and video tutorial library of any modern web application framework, making it a breeze to get started learning the framework.

If you're not in the mood to read, [Laracasts](https://laracasts.com) contains over 1100 video tutorials on a range of topics including Laravel, modern PHP, unit testing, JavaScript, and more. Boost the skill level of yourself and your entire team by digging into our comprehensive video library.

---

## Controllers

### Apa itu *Controller*?

*Controller* adalah serangkaian code yang bertugas untuk menjalankan logika aplikasi, penghubung antara database, serta mengembalikan hasil dari sebuah proses. Terdapat beberapa hal yang perlu diperharikan dalam penggunaan *Controller*, yakni :

- **Do** :

	- Memberi akhiran '*...Controller*' pada tiap *controller* yang dibuat. Misal, *AboutController*
	- Memberi nama *controller* dengan kapitalisasi ditiap kata. Misal, *AppointmentController*
	- Membuat / meletakkan *controller* sesuai dengan penggunaan / fungsionalitas yang dimiliki. 
		
		Misal, membuat *controller* autentikasi Android pada folder **Android**

- **Don't** :

	- Membuat variabel khusus yang hanya coder & tuhan yang tahu. 
	
		Misal, untuk membedakan apakah akun sudah aktif atau belum, digunakan angka 1 atau 0. 
	
		Sehingga pada code yang dibuat akan terbentuk seperti ini, `$userStatus->status == 1 ? 'Aktif' : 'Tidak aktif'`
	
		Untuk menghindari penggunaan tersebut, dapat menggunakan **const** dan diletakkan sesuai sumber data / *model*.
	
		Contoh : 
	
		Pada **Models/User.php**, ditambahkan `const USER_ACTIVE = 1;`. Sehingga pada pemanggilan variabel akan lebih mudah dibaca, *code* pemanggilan akan seperti ini `$userStatus->status == User::USER_ACTIVE ? 'Aktif' : 'Tidak aktif'`
	
	- Memanggil data dari database dengan kueri langsung melalui *Controller*. 
	
		Baik itu menggunakan *Model* ataupun *Query Builder*. 
	
		Contoh : 
	
		`User::where('email', 'admin@dokternet.com')->first()` atau 
	
		`DB::table('users')->where('email', 'admin@dokternet.com')->first()`.
	
		Akan lebih baik mendefinisikan kueri tersebut didalam *model*, kemudian *model* dipanggil pada *controller*.

### Bagaimana cara membuat *controller*?

Untuk membuat *controller*, Anda dapat menjalankan perintah `php artisan make:controller [nama-controller]`.

Perlu diketahui bahwa terdapat beberapa direktori yang telah disusun untuk mengelompokkan *controller*, sehingga pada saat membuat *controller* perlu menerapkan susunan direktori tersebut.

Misal, untuk membuat *controller* yang berfungsi untuk melihat profil pengguna melalui aplikasi Android, dapat dibuatkan *controller* dengan nama **ProfileController** dan diletakkan pada folder **app/Http/Controllers/API/Mobile/Android**. 

Berikut contoh perintahnya,

`php artisan make:controller API\Mobile\Android\ProfileController`