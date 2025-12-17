# Laravel Auth API – Technical Test

Project ini adalah **REST API Authentication** menggunakan **Laravel 11** dengan pendekatan **Clean Code**, **Service Layer**, **Request Validation**, dan **Laravel Sanctum**.

---

## 🔧 Tech Stack

- PHP >= 8.2
- Laravel 11
- Laravel Sanctum (Token Authentication)
- MySQL / MariaDB
- Postman (API Testing)

---

## 📂 Project Structure (Clean Code)

```
app/
├── Http/
│   ├── Controllers/Api/AuthController.php
│   └── Requests/
│       ├── RegisterRequest.php
│       └── LoginRequest.php
├── Services/
│   └── AuthService.php
├── Models/User.php

database/
├── migrations/
│   └── xxxx_xx_xx_create_users_table.php
├── seeders/
│   └── UserSeeder.php

routes/
└── api.php
```

---

## 🚀 Installation & Setup

### 1. Clone Repository

```bash
git clone <repository-url>
cd laravel-auth-api
```

### 2. Install Dependency

```bash
composer install
```

### 3. Environment Setup

```bash
cp .env.example .env
php artisan key:generate
```

Konfigurasi database di `.env`

```env
DB_DATABASE=laravel_auth_api
DB_USERNAME=root
DB_PASSWORD=
```

---

## 🗄️ Database Migration & Seeder

### Run Migration & Seeder

```bash
php artisan migrate --seed
```

### Seeder Default User

```
Email    : zein@gmail.com
Password : password123
```

---

## 📡 API Endpoints

### Register

**POST** `/api/register`

Body:
```json
{
  "name": "Zein",
  "email": "zein@gmail.com",
  "password": "password123",
  "password_confirmation": "password123"
}
```

Success Response:
```json
{
  "status": true,
  "message": "Register berhasil",
  "data": {
    "id": 1,
    "name": "Zein",
    "email": "zein@gmail.com"
  }
}
```

---

### Login

**POST** `/api/login`

Body:
```json
{
  "email": "zein@gmail.com",
  "password": "password123"
}
```

Success Response:
```json
{
  "status": true,
  "access_token": "token_here",
  "token_type": "Bearer"
}
```

---

### Get Authenticated User

**GET** `/api/me`

Header:
```
Authorization: Bearer {token}
```

Response:
```json
{
  "status": true,
  "data": {
    "id": 1,
    "name": "Zein",
    "email": "zein@gmail.com"
  }
}
```

---

## 📮 Postman Collection

Project ini dilengkapi dengan **Postman Collection** untuk memudahkan proses testing API.

**File:**  
```
laravel_auth_api.postman_collection.json
```

---

## 👤 Author

Nama: **Zein Habsin Aziz**  
Role: Laravel Programmer (Middle) di PT Sakti Kinerja Kolaborasindo
