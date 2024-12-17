# Dokumentasi Bahasa Pemrograman (Aesth)
Desain syntax aest language (Procedural Compilated Language)

## 1. **Deklarasi Variabel**
Di dalam bahasa ini, deklarasi variabel mengikuti gaya deklarasi yang tradisional seperti di aesth, yaitu tipe data diletakkan di depan variabel.

### Contoh:
```aesth
// Tipe data dasar
int age = 30;                
string name = "John Doe";    
float price = 99.99;         

// Tipe data tambahan
bool isActive = true;         

// Tipe data untuk server-side
datetime createdAt = "2024-12-17T14:30:00"; 
object user = {                             
    "id": 1,
    "name": "John Doe",
    "email": "john@example.com"
};
```

## 2. **Output (Cetak Data)**
Untuk mencetak output ke layar, digunakan `print` atau `println`. `println` digunakan untuk menambahkan baris baru setelah output.

### Contoh:
```aesth
// Mencetak tanpa baris baru
print("Hello, World!");

// Mencetak dengan baris baru
println("Hello, World!");
```

## 3. **Percabangan (If-Else)**
Sintaks `if-else` digunakan untuk membuat keputusan berdasarkan kondisi.

### Contoh:
```aesth
// Percabangan
if (age > 18) {
    println("Adult");
} else {
    println("Not an Adult");
}
```

## 4. **Fungsi (Function)**
Fungsi dideklarasikan menggunakan keyword `function`. Fungsi dapat menerima parameter dan mengembalikan nilai.

### Contoh:
```aesth
// Fungsi sederhana
function greet(name) {
    println("Hello, " + name);
}

greet("John Doe");
```

## 5. **Looping (Perulangan)**
Tiga tipe perulangan yang disediakan adalah `for`, `while`, dan `do-while`.

### For Loop:
```aesth
// Perulangan for
for (int i = 0; i < 10; i++) {
    println(i);
}
```

### While Loop:
```aesth
// Perulangan while
int i = 0;
while (i < 10) {
    println(i);
    i++;
}
```

### Do-While Loop:
```aesth
// Perulangan do-while
int i = 0;
do {
    println(i);
    i++;
} while (i < 10);
```

## 6. **Array**
Untuk mendeklarasikan array, kita menggunakan tipe data diikuti dengan nama array dan elemen-elemen yang ingin dimasukkan.

### Contoh:
```aesth

// 1. Deklarasi Array
int numbers[] = {10, 20, 30, 40, 50}; // Array integer
string names[] = {"Alice", "Bob", "Charlie"}; // Array string
float prices[] = {99.99, 49.50, 19.90}; // Array float

// 2. Mengakses dan Mengubah Elemen Array
println("Elemen pertama di numbers: " + numbers[0]); // Output: 10
numbers[1] = 25; // Mengubah elemen kedua
println("Elemen kedua setelah diubah: " + numbers[1]); // Output: 25

// 3. Conditional dengan Array
if (numbers[0] > 15) {
    println("Elemen pertama lebih besar dari 15");
} else {
    println("Elemen pertama kurang dari atau sama dengan 15");
}

// 4. Looping Array
// Menggunakan for loop
println("Menampilkan isi array numbers dengan for loop:");
for (int i = 0; i < 5; i++) {
    println("numbers[" + i + "] = " + numbers[i]);
}

// Menggunakan while loop
println("Menampilkan isi array names dengan while loop:");
int i = 0;
while (i < 3) {
    println("names[" + i + "] = " + names[i]);
    i++;
}

// 5. Array dalam Function
function printArray(array, length) {
    for (int i = 0; i < length; i++) {
        println("Array[" + i + "] = " + array[i]);
    }
}

println("Menampilkan isi array prices menggunakan function:");
printArray(prices, 3);

// 6. Array Multi-Dimensional
int matrix[2][2] = {
    {1, 2},
    {3, 4}
};

// Akses elemen array multi-dimensional
println("Elemen matrix[1][1]: " + matrix[1][1]); // Output: 4

// Looping array multi-dimensional
println("Menampilkan isi array multi-dimensional:");
for (int i = 0; i < 2; i++) {
    for (int j = 0; j < 2; j++) {
        println("matrix[" + i + "][" + j + "] = " + matrix[i][j]);
    }
}

```

## 7. **CRUD HTTP**
Operasi CRUD (Create, Read, Update, Delete) dapat dilakukan melalui HTTP requests seperti `POST`, `GET`, `PUT`, dan `DELETE`.

### Create (POST):
```aesth
// POST request untuk membuat data baru
function createData() {
    http.post("/api/data", {
        name: "John Doe",
        age: 30
    }, function(response) {
        println("Data Created: " + response);
    });
}
```

### Read (GET):
```aesth
// GET request untuk mengambil data
function getData() {
    http.get("/api/data", function(response) {
        println("Data Retrieved: " + response);
    });
}
```

### Update (PUT):
```aesth
// PUT request untuk memperbarui data
function updateData() {
    http.put("/api/data/1", {
        name: "John Updated",
        age: 31
    }, function(response) {
        println("Data Updated: " + response);
    });
}
```

### Delete (DELETE):
```aesth
// DELETE request untuk menghapus data
function deleteData() {
    http.delete("/api/data/1", function(response) {
        println("Data Deleted: " + response);
    });
}
```

## 8. **Contoh Penggunaan di Server**
Untuk menangani request di sisi server, kita bisa menggunakan sintaks seperti berikut:

```aesth
// Contoh sederhana server yang menangani CRUD dengan Go
function handleRequest(request) {
    if (request.method == "POST") {
        // Tangani create
        createData();
    } else if (request.method == "GET") {
        // Tangani read
        getData();
    } else if (request.method == "PUT") {
        // Tangani update
        updateData();
    } else if (request.method == "DELETE") {
        // Tangani delete
        deleteData();
    }
}
```

Berikut adalah perbaikan untuk point 9 di dokumentasi:

---

## 9. **Fungsi Bawaan**
Aesth menyediakan beberapa fungsi bawaan untuk memudahkan operasi dengan database, seperti menghubungkan ke database MySQL/MariaDB dan menjalankan query.

### Fungsi:
- **`mysqlConnect()`**  
  Digunakan untuk menghubungkan aplikasi ke database MySQL/MariaDB.

- **`mysqlQuery()`**  
  Digunakan untuk menjalankan query pada database yang sudah terhubung.

### Sintaks:

```aesth
// Menghubungkan ke database MySQL/MariaDB
mysqlConnect(host, username, password, database);

// Menjalankan query untuk mengambil data
mysqlQuery(query);
```

**Parameter:**
- **host** (string): Alamat server database (misalnya, "localhost").
- **username** (string): Nama pengguna untuk login ke database.
- **password** (string): Kata sandi untuk akun pengguna.
- **database** (string): Nama database yang akan digunakan.
- **query** (string): Query SQL yang ingin dijalankan.

### Contoh Penggunaan:

1. **Menghubungkan ke Database:**
```aesth
// Menghubungkan ke database MySQL/MariaDB
mysqlConnect("localhost", "root", "password", "mydatabase");
```

2. **Menjalankan Query:**
```aesth
// Menjalankan query untuk mengambil data pengguna
mysqlQuery("SELECT * FROM users WHERE id = 1");
```


### 10. **Modularisasi: `require`**

Fitur **modularisasi** memungkinkan untuk memanggil dan menjalankan file eksternal dalam Aesth. Konsepnya mirip dengan `require` di PHP, di mana kamu dapat memecah kode program menjadi beberapa file dan memanggilnya saat dibutuhkan.

#### Sintaks:
```aesth
require("file_name");
```

**Parameter:**
- **file_name** (string): Nama file yang ingin dipanggil. File yang dipanggil harus ada dalam direktori yang sama atau sesuai path yang diberikan.

#### Contoh Penggunaan:

1. **File Utama (`main.aesth`)**
```aesth
// Memanggil file modul
require("utils.aesth");

println(formatDate("2024-12-17T14:30:00"));
```

2. **File Modul (`utils.aesth`)**
```aesth
// Fungsi untuk memformat tanggal
function formatDate(date) {
    return date.split("T")[0];  // Mengambil bagian tanggal dari string
}
```

Dengan menggunakan `require("utils.aesth")`, file `utils.aesth` akan dipanggil dan fungsi `formatDate` dapat digunakan di file utama (`main.aesth`).
---

### Ringkasan Fitur dan Sintaks:
- **Variabel:** Tipe data diletakkan di depan nama variabel.
- **Output:** Menggunakan `print` dan `println`.
- **Percabangan:** `if-else` digunakan untuk kontrol alur program.
- **Fungsi:** Fungsi dideklarasikan menggunakan keyword `function`.
- **Perulangan:** Tiga tipe perulangan yang disediakan: `for`, `while`, dan `do-while`.
- **Array:** Deklarasi array dengan tipe data dan elemen.
- **CRUD HTTP:** Melakukan operasi CRUD dengan HTTP menggunakan method `POST`, `GET`, `PUT`, dan `DELETE`.
- **Fungsi Bawaan:** Sementara ada dua fungsi bawaan yang fungsinya untuk terhubung ke database MySQL/MariaDB.
- **Require:** Aesth juga mendukung modularisasi dengan fitur `require`, yang memungkinkan kamu untuk menyertakan file eksternal ke dalam program.

---
