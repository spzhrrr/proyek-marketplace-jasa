# Marketplace Jasa Backend

Backend ini dibuat untuk kebutuhan aplikasi marketplace jasa berbasis web. Sistem dikembangkan menggunakan Node.js, Express.js, TypeScript, dan MySQL dengan konsep REST API serta layered architecture agar struktur project lebih rapi dan lebih mudah dikembangkan ke depannya.

Project ini mendukung beberapa fitur utama seperti authentication menggunakan JWT, pengelolaan layanan jasa, booking layanan, sistem review, upload gambar, dan dashboard sederhana untuk kebutuhan analitik.

Fokus utama project ini bukan hanya membuat fitur CRUD berjalan, tetapi juga mencoba menerapkan struktur backend yang lebih terorganisir seperti penggunaan middleware, service layer, error handling terpusat, dan validasi authorization.

---

# Fitur yang Tersedia

## Authentication & Authorization

- Register dan login user
- JWT authentication
- Protected routes
- Password hashing menggunakan bcrypt
- Authorization berdasarkan ownership data

Contoh:
- User hanya bisa mengedit service miliknya sendiri
- Seller hanya bisa mengubah status booking miliknya
- User hanya bisa memberi review setelah melakukan booking

---

## Service Marketplace

Fitur layanan jasa meliputi:

- Menambahkan layanan jasa
- Mengedit layanan jasa
- Menghapus layanan jasa
- Menampilkan seluruh layanan
- Detail layanan berdasarkan ID
- Upload gambar layanan
- Search layanan
- Filter berdasarkan kategori

---

## Booking System

Sistem booking digunakan untuk menghubungkan buyer dan seller.

Fitur:
- Membuat booking layanan
- Melihat daftar booking
- Mengubah status booking
- Workflow booking sederhana

Status booking:
- pending
- accepted
- rejected
- completed

---

## Review System

User dapat memberikan review terhadap layanan yang pernah dibooking.

Fitur:
- Memberikan rating
- Memberikan komentar review
- Menampilkan review berdasarkan service
- Validasi agar review tidak bisa diberikan sembarangan

---

## User Profile

Fitur profile user:
- Edit profile
- Upload avatar
- Menambahkan bio
- Menambahkan lokasi
- Menambahkan nomor kontak

---

## Dashboard

Dashboard sederhana untuk kebutuhan statistik backend.

Data yang ditampilkan:
- Total user
- Total service
- Total booking
- Total review
- Top rated services

---

# Teknologi yang Digunakan

| Teknologi | Kegunaan |
| ---------- | ---------- |
| Node.js | Runtime backend |
| Express.js | Framework backend |
| TypeScript | Penulisan kode dengan type safety |
| MySQL | Database |
| JWT | Authentication |
| bcrypt | Hash password |
| Multer | Upload file |
| mysql2 | Koneksi database |
| dotenv | Environment variables |

---

# Struktur Backend

Project menggunakan layered architecture.

Alur request:

```text
Routes
↓
Middleware
↓
Controller
↓
Service
↓
Database
