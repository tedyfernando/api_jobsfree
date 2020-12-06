# api_jobsfree
API aplikasi Jobsfree

######## CodeIgniter4 ##########

basic configuration
1.  import database dengan file sql pada folder sql/api_jobsfree.sql
2.  pergi ke file .env
3.  sesuaikan baseurl pada baris app.baseURL = 'http://localhost:8080/'
4.  sesuaikan user dan password database

    database.default.hostname = localhost
    database.default.database = jobsfree
    database.default.username = root
    database.default.password = 123
    database.default.DBDriver = MySQLi
    database.default.DSN = 'mysql:dbname=jobsfree;host=localhost

## HTTP REQUEST

## REGISTRASI DAN LOGIN 

- Login
1. url : http://localhost:8080/login/
2. method: POST
3. body/params: email, password

- signup
1. url : http://localhost:8080/signup
2. method : POST
3. body/params: role_id, name, email, password, phone_no, idcard_no


## LAPAK

- lapak (dapatkan semua data lapak)
1. url : http://localhost:8080/lapak/
2. method : GET
3. body/params: -

- detail lapak
1. url : http://localhost:8080/lapak/$id
2. method : GET
3. body/params: -

- get lapak berdasarkan category
1. url : http://localhost:8080/category/$idcategory 
2. method : GET
3. body/params: -

- buat lapak baru
1. url : http://localhost:8080/lapak
2. method : POST
3. body/params: user_id, category_id, title, description, requirement, price_tag, working_hours, status

- update lapak
1. url : http://localhost:8080/lapak/$id
2. method : PUT
3. body/params: user_id, category_id, title, description, requirement, price_tag, working_hours, status

- hapus lapak
1. url : http://localhot:8080/lapak/$id
2. method : DELETE
3. body/params: -

## USER

- show user
1. url : http://localhost:8080/user/$id
2. method : GET
3. body/params: -

- Update user
1. url : http://localhost:8080/user/$id
2. method : PUT
3. body/params: role_id, name, email,  phone_no, idcard_no

- Update Password
1. url : http://localhost:8080/user/update_password/$id
2. method : POST
3. body/params : password, new_password
4. catatan : $id diisi dengan email

## TRANSAKSI

- buat transaksi 
1. url : http://localhost:8080/transaction
2. method : POST
3. body/params: lapak_id, freelance_id, client_id, payment_date, payment_via

- get detail transaksi
1. url : http://localhost:8080/transaction/$id
2. method : GET
3. body/params: -
4. catatan : $id adalah id transaksi

- get ongoing transaksi yang kolom status nya masih null
1. url : http://localhost:8080/transaction/ongoing/$id
2. method : GET
3. body/params: -
4. catatan: $id adalah id user, id client atau id freelancer. 

- terima proses transaksi (jasa)
1. url : http://localhost:8080/transaction/confirm/$id 
2. method : POST
3. body/params: accept, isi value jadi 1 (yang penting ga null aja)
4. catatan : $id adalah id transaksi

- menyelesaikan transaksi (jasa)
1. url : http://localhost:8080/transaction/done/$id
2. method : POST
3. body/params: message
4. catatan: $id adalah id transaksi
