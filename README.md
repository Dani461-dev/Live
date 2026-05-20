# ⚽ LiveScore — Data Engine Service

Backend Data Engine untuk aplikasi **Football Live Score & Match Statistics** berbasis **Laravel Monolith**.

Service ini bertanggung jawab untuk:

* mengambil data dari API-Football
* memproses dan menormalisasi data
* menyimpan data ke database
* memperbarui data pertandingan secara berkala

Project ini difokuskan pada implementasi:

* backend data pipeline
* scheduled data fetching
* live match synchronization
* cloud database integration

---

# 🚀 Tech Stack

## Backend

* Laravel
* PHP 8.4+

## Database

* PostgreSQL (Supabase)

## External API

* API-Football

## Real-Time Strategy

* Laravel Scheduler
* Polling System

---

# 🧠 Data Engine Architecture

```text id="o9i0b0"
API-Football
      ↓
Laravel Service
      ↓
Data Normalization
      ↓
PostgreSQL (Supabase)
      ↓
Controller / API Layer
```

---

# 🎯 Main Responsibilities

## ✅ API Integration

Menghubungkan backend dengan API-Football.

## ✅ Data Fetching

Mengambil:

* live matches
* today matches
* match statistics

## ✅ Data Normalization

Mengubah struktur raw API menjadi format internal aplikasi.

## ✅ Database Management

Menyimpan:

* teams
* fixtures
* match statistics

## ✅ Scheduler System

Menjalankan update data otomatis tiap 1 menit.

---

# 📁 Project Structure

```text id="8s44oq"
app/
├── Console/
│   └── Commands/
├── Models/
├── Services/

database/
├── migrations/
├── seeders/
```

---

# ⚙️ Setup Project

## 1. Clone Repository

```bash id="1o98nl"
git clone https://github.com/USERNAME/LiveScore.git
cd LiveScore
```

---

## 2. Install Dependency

```bash id="mjlwmq"
composer install
```

---

## 3. Copy Environment

```bash id="nnhq0n"
cp .env.example .env
```

---

## 4. Generate App Key

```bash id="0ch02s"
php artisan key:generate
```

---

# 🗄️ Database Configuration

Menggunakan PostgreSQL dari Supabase.

Isi `.env`

```env id="6lb6fe"
DB_CONNECTION=pgsql
DB_HOST=YOUR_SUPABASE_HOST
DB_PORT=5432
DB_DATABASE=postgres
DB_USERNAME=postgres
DB_PASSWORD=YOUR_PASSWORD
DB_SSLMODE=require
```

---

# 🔑 API Configuration

Tambahkan API-Football key di `.env`

```env id="rj8d5u"
API_FOOTBALL_KEY=YOUR_API_KEY
API_FOOTBALL_BASE_URL=https://v3.football.api-sports.io
```

---

# 🧱 Database Schema

## teams

Menyimpan data tim sepak bola.

## fixtures

Menyimpan data pertandingan.

## match_stats

Menyimpan statistik pertandingan.

---

# ▶️ Migration

Menjalankan migration database:

```bash id="ubm5yb"
php artisan migrate
```

---

# 🔄 Scheduler System

Scheduler digunakan untuk:

* fetch live score otomatis
* update pertandingan
* sinkronisasi data

Menjalankan scheduler:

```bash id="p7h2yi"
php artisan schedule:work
```

---

# ⚡ Fetch Live Match

Command digunakan untuk mengambil pertandingan live dari API-Football dan menyimpannya ke database.

Contoh command:

```bash id="7v7xx1"
php artisan fetch:livescore
```

---

# 📡 Data Flow

```text id="7o1i0t"
API-Football
    ↓
Laravel Command
    ↓
Service Layer
    ↓
Data Processing
    ↓
PostgreSQL
```

---

# 📌 Features

## ✅ Live Match Fetching

Mengambil data pertandingan live.

## ✅ Match Statistics Fetching

Mengambil statistik pertandingan.

## ✅ Automatic Update

Update data otomatis menggunakan scheduler.

## ✅ Database Synchronization

Sinkronisasi data pertandingan ke database.

---

# 🎯 Development Goals

* Membangun backend data pipeline
* Implementasi scheduled data processing
* Integrasi cloud database
* Sinkronisasi data pertandingan secara otomatis
* Menjaga struktur backend tetap sederhana dan stabil

---

# ⚠️ Development Notes

Project ini menggunakan arsitektur sederhana:

* tanpa Redis
* tanpa WebSocket
* tanpa microservice

Tujuannya:

* mempermudah development
* fokus pada backend data flow
* menjaga stabilitas project untuk tim kecil

---

# 👨‍💻 Role

## Data Engine Developer

Tanggung jawab:

* API integration
* data fetching
* database synchronization
* scheduler system
* data normalization

Framework pembagian tugas backend disusun agar sinkronisasi kerja tim tetap terjaga. 

---

# 📄 License

MIT License
