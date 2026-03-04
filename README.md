# Praktikum 1 - User Management REST API

Aplikasi REST API sederhana untuk manajemen data pengguna menggunakan Spring Boot, Spring Data JPA, MySQL, Lombok, MapStruct, dan Validation.

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
    "name": "Budi Santoso",
    "age": 20
}
```

**Response Body (Success - 201 Created):**
```json
{
    "status": "success",
    "data": {
        "id": "550e8400-e29b-41d4-a716-446655440000",
        "name": "Budi Santoso",
        "age": 20
    }
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
            "id": "550e8400-e29b-41d4-a716-446655440000",
            "name": "Budi Santoso",
            "age": 20
        },
        {
            "id": "661f9511-f30c-52e5-b827-557766551111",
            "name": "Siti Rahayu",
            "age": 22
        }
    ]
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
GET /api/users/550e8400-e29b-41d4-a716-446655440000
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
        "id": "550e8400-e29b-41d4-a716-446655440000",
        "name": "Budi Santoso",
        "age": 20
    }
}
```

**Response Body (Failed - 404):**
```json
{
    "status": "error",
    "message": "user not found"
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
PUT /api/users/550e8400-e29b-41d4-a716-446655440000
```

**Request Header:**
```
Content-Type: application/json
```

**Request Body:**
```json
{
    "name": "Budi Santoso Updated",
    "age": 21
}
```

**Response Body (Success - 200 OK):**
```json
{
    "status": "success",
    "data": {
        "id": "550e8400-e29b-41d4-a716-446655440000",
        "name": "Budi Santoso Updated",
        "age": 21
    }
}
```

**Response Body (Failed - 404):**
```json
{
    "status": "error",
    "message": "user not found"
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
DELETE /api/users/550e8400-e29b-41d4-a716-446655440000
```

**Request Body:**
```
-
```

**Response Body (Success - 200 OK):**
```json
{
    "status": "success delete user with id 550e8400-e29b-41d4-a716-446655440000"
}
```

**Response Body (Failed - 404):**
```json
{
    "status": "error",
    "message": "user not found"
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