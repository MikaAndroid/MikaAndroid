# Halo, Saya Mikail Zamakhsyari! 👋

### 🚀 Calon Unity Programmer | Peminat Logika Game & Backend

Saya adalah mahasiswa Informatika (Semester 6) dengan fondasi kuat dalam **Pemrograman Berorientasi Objek (Java/Python)** dan **Logika Pengembangan Game**. Saat ini sedang dalam proses transisi dari Godot ke **Unity (C#)**, dengan membawa pemahaman solid mengenai fisika game, mekanik tabrakan (_collision_), dan manajemen data yang kompleks.

## 🎮 Proyek Game Unggulan: Ox's Gambit

> **Game Puzzle Platformer 2D yang dibangun dengan Godot Engine.** Fokus: _Mekanik Gameplay, Interaksi Fisika, State Machines._

### ⚙️ Sorotan Teknis

Dalam proyek ini, saya berfokus pada implementasi logika _gameplay_ inti menggunakan **GDScript** (yang memiliki kemiripan logika dengan Python/C#):

*   **Finite State Machine (FSM):** Mengimplementasikan _state_ yang berbeda untuk pemain (`Idle`, `Run`, `Jump`, `Fall`) guna memastikan transisi animasi yang halus dan penanganan input yang responsif di `player.gd`.
    
*   **Sistem Interaktif:** Merancang sistem interaksi modular di mana **Pressure Plates** (Pelat Tekan) memicu **Pintu** tertentu.
    
    *   _Logika:_ Menggunakan _signals_ untuk komunikasi antara node `pressure_plate` dan node `door` tanpa ketergantungan kode yang kaku (_tight coupling_).
        
*   **Fisika & Kolisi:** Menangani tabrakan `KinematicBody2D` untuk kotak/peti yang memungkinkan pemain memecahkan teka-teki lingkungan.
    

### 💻 Cuplikan Kode (Showcase Logika)

_Menangani logika aktivasi pelat tekan:_

```gdscript
# scripts/pressure_plate.gd

extends Area2D

signal on_plate_pressed
signal on_plate_released

func _on_body_entered(body):
    # Mengecek apakah yang menginjak adalah Player atau Kotak
    if body.is_in_group("Player") or body.is_in_group("Box"):
        emit_signal("on_plate_pressed")
        $Sprite.play("pressed")

func _on_body_exited(body):
    if body.is_in_group("Player") or body.is_in_group("Box"):
        emit_signal("on_plate_released")
        $Sprite.play("released")

```

[Lihat Repository Lengkap](https://github.com/MikaAndroid/oxs-gambit)

## 🛒 Rekayasa Backend: David Bakery System

> **Sistem Manajemen Inventaris & Pesanan dibangun dengan Laravel (MVC).** Fokus: _Logika Bisnis Kompleks, Relasi Database, CRUD._

Meskipun melamar sebagai Game Programmer, saya memiliki keahlian **Software Engineering** yang kuat yang dibuktikan melalui aplikasi web kompleks ini.

### 🔧 Konsep Rekayasa Kunci

*   **Arsitektur MVC:** Pemisahan tugas yang bersih menggunakan _Controllers_ (`OrderController`, `SlotController`) dan _Models_ (`Order`, `ProductionSlot`).
    
*   **Logika Kompleks:** Mengimplementasikan sistem **"Slot Produksi"** (`ProductionSlot.php`) untuk mengatur kuota harian toko roti, mencegah pesanan masuk saat slot penuh—logika ini memiliki paralelisasi dengan **Sistem Inventaris** dalam game RPG.
    
*   **Manajemen Database:** Merancang skema database relasional untuk Pengguna, Produk, Pesanan, dan Item Keranjang menggunakan migrasi MySQL.
    

```php
// Contoh: Logika untuk mengecek ketersediaan slot sebelum memesan
public function checkAvailability($date, $quantity) {
    $slot = ProductionSlot::where('date', $date)->first();
    
    // Jika kapasitas terpakai + jumlah pesanan melebihi batas, tolak pesanan
    if ($slot->used_capacity + $quantity > $slot->max_capacity) {
        return false; // Logika slot penuh
    }
    return true;
}

```

[Lihat Repository Lengkap](https://github.com/MikaAndroid/DavidBekery)

## 🛠 Keahlian & Alat

| **Kategori** | **Teknologi** | | **Bahasa** | Python, Java (OOP Kuat), GDScript, **C#** (Sedang Pelajari) | | **Game Dev** | Godot Engine, Unity (Transisi), Fisika 2D, Tilemaps | | **Backend/Web** | Laravel (MVC), MySQL, Konsep REST | | **Alat** | Git/GitHub, Visual Studio Code |

### 📫 Mari Terhubung!

Saya saat ini sedang mencari **Kesempatan Magang sebagai Unity Programmer**. Saya adalah pembelajar cepat yang memahami logika inti pengembangan game dan siap beradaptasi dengan _tech stack_ tim Anda.

*   📧 **Email:**
    
    23081010115@student.upnjatim.ac.id
