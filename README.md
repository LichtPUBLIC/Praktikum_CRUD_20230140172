# Praktikum 1 - User Management REST API

Aplikasi REST API sederhana untuk manajemen data pengguna menggunakan Spring Boot, Spring Data JPA, MySQL, Lombok, MapStruct, dan Validation.
---
## Tampilan Web
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/15d378bd-02b6-4188-adec-db34efff9c26" />
---
## Endpoint API

### Base URL
```
http://localhost:8080/api/users
```

---

### 1. Create User (Tambah User)

**Endpoint:**
```
POST /api/users
```

**Request Header:**
```
Content-Type: application/json
```

**Request Body:**
```json
{
    "name": "Daffa",
    "age": 17
}
```

**Response Body (Success - 201 Created):**
```json
{
    "status": "success",
    "data": {
        "id": "edcc1087-ab56-4288-bdef-356f3605beba",
        "name": "Daffa",
        "age": 17
    }
}
```

**Response Body (Failed - 400 Bad Request - Field kosong):**
```json
{
    "status": "error",
    "message": "name: must not be blank, age: must be greater than 0"
}
```

**Response Body (Failed - 400 Bad Request - Tipe data salah):**
```json
{
    "status": "error",
    "message": "age: must be a number"
}
```

---

### 2. Get All Users (Ambil Semua User)

**Endpoint:**
```
GET /api/users
```

**Request Body:**
```
-
```

**Response Body (Success - 200 OK):**
```json
{
    "status": "success",
    "data": [
        {
            "id": "edcc1087-ab56-4288-bdef-356f3605beba",
            "name": "Daffa",
            "age": 17
        }
    ]
}
```

**Response Body (Failed - 200 OK - Data kosong):**
```json
{
    "status": "success",
    "data": []
}
```

---

### 3. Get User By ID (Ambil User Berdasarkan ID)

**Endpoint:**
```
GET /api/users/{id}
```

**Contoh:**
```
GET /api/users/edcc1087-ab56-4288-bdef-356f3605beba
```

**Request Body:**
```
-
```

**Response Body (Success - 200 OK):**
```json
{
    "status": "success",
    "data": {
        "id": "edcc1087-ab56-4288-bdef-356f3605beba",
        "name": "Daffa",
        "age": 17
    }
}
```

**Response Body (Failed - 404 Not Found - ID tidak ditemukan):**
```json
{
    "status": "error",
    "message": "user not found"
}
```

**Response Body (Failed - 400 Bad Request - ID tidak valid):**
```json
{
    "status": "error",
    "message": "invalid id format"
}
```

---

### 4. Update User (Perbarui Data User)

**Endpoint:**
```
PUT /api/users/{id}
```

**Contoh:**
```
PUT /api/users/edcc1087-ab56-4288-bdef-356f3605beba
```

**Request Header:**
```
Content-Type: application/json
```

**Request Body:**
```json
{
    "name": "Daffa Updated",
    "age": 18
}
```

**Response Body (Success - 200 OK):**
```json
{
    "status": "success",
    "data": {
        "id": "edcc1087-ab56-4288-bdef-356f3605beba",
        "name": "Daffa Updated",
        "age": 18
    }
}
```

**Response Body (Failed - 404 Not Found - ID tidak ditemukan):**
```json
{
    "status": "error",
    "message": "user not found"
}
```

**Response Body (Failed - 400 Bad Request - Field kosong):**
```json
{
    "status": "error",
    "message": "name: must not be blank, age: must be greater than 0"
}
```

**Response Body (Failed - 400 Bad Request - Tipe data salah):**
```json
{
    "status": "error",
    "message": "age: must be a number"
}
```

---

### 5. Delete User (Hapus User)

**Endpoint:**
```
DELETE /api/users/{id}
```

**Contoh:**
```
DELETE /api/users/edcc1087-ab56-4288-bdef-356f3605beba
```

**Request Body:**
```
-
```

**Response Body (Success - 200 OK):**
```json
{
    "status": "success delete user with id edcc1087-ab56-4288-bdef-356f3605beba"
}
```

**Response Body (Failed - 404 Not Found - ID tidak ditemukan):**
```json
{
    "status": "error",
    "message": "user not found"
}
```

**Response Body (Failed - 400 Bad Request - ID tidak valid):**
```json
{
    "status": "error",
    "message": "invalid id format"
}
```

---
## Ringkasan Endpoint
| Method | Endpoint | Deskripsi |
|--------|----------|-----------|
| POST | /api/users | Tambah user baru |
| GET | /api/users | Ambil semua user |
| GET | /api/users/{id} | Ambil user by ID |
| PUT | /api/users/{id} | Update user by ID |
| DELETE | /api/users/{id} | Hapus user by ID |
---




User management REST API documentation - Claude
