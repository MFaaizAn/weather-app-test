# weather-app-test

# 🌤️ Weather App - Real-Time Meteorological Dashboard

![HTML5](https://img.shields.io/badge/html5-%23E34F26.svg?style=for-the-badge&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/css3-%231572B6.svg?style=for-the-badge&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/javascript-%23323330.svg?style=for-the-badge&logo=javascript&logoColor=%23F7DF1E)

## 📖 Deskripsi Proyek
Weather App adalah aplikasi pencarian informasi cuaca *real-time* di seluruh dunia yang dibangun menggunakan **Vanilla JavaScript (ES6+)**, HTML5, dan CSS3. Proyek ini mengintegrasikan data eksternal dari **OpenWeatherMap API** untuk menyajikan data meteorologi yang akurat kepada pengguna secara instan dan interaktif.

Proyek ini dibuat untuk memperdalam pemahaman mengenai manipulasi siklus hidup DOM (*DOM Lifecycle*), integrasi API pihak ketiga, penanganan *asynchronous JavaScript*, serta implementasi animasi transisi CSS yang kompleks.

## ✨ Fitur Utama
* **Real-Time API Integration:** Menarik data kondisi cuaca terkini (suhu, kelembapan, dan kecepatan angin) secara *asynchronous* menggunakan `Fetch API`.
* **Dynamic Weather Theming:** Otomatis mengubah ikon dan visual utama berdasarkan kondisi cuaca yang dikembalikan oleh server (Clear, Rain, Clouds, Snow, Mist, Haze).
* **Advanced Slot-Machine Animation:** Mengimplementasikan teknik penggandaan node (`cloneNode`) untuk menciptakan efek transisi angka cuaca yang berputar ke atas saat pencarian baru dilakukan.
* **Error 404 Handling:** Sistem mitigasi *error* yang UI-responsif untuk menangani kasus di mana pengguna memasukkan nama kota yang tidak valid atau tidak ditemukan di database.
* **Modern UI/UX:** Desain antarmuka minimalis dengan efek *glassmorphism* (backdrop-filter) yang sepenuhnya responsif.

## 🧠 Tantangan & Pembelajaran ("The Aha! Moment")
Tantangan terbesar dalam proyek ini terletak pada pengelolaan animasi *cloning* elemen saat pencarian kota dilakukan berturut-turut. Pada fase awal, angka kelembapan (*humidity*) dan angin (*wind*) yang lama sempat tersangkut (*stuck*) dan mengintip terpotong di bagian atas komponen.

**Solusi:**
Melalui proses analisis *debugging*, saya menemukan dua akar masalah:
1. **JavaScript Selector Typo:** Terdapat ketidaksesuaian penulisan huruf kapital (*case-sensitive*) saat menargetkan class hasil kloning (`.info-Wind` vs `.info-wind`), yang menyebabkan eksekusi fungsi `.remove()` berhenti di tengah jalan.
2. **CSS Layout Boundary:** Wadah teks belum memiliki batas pemotongan visual yang ketat. Saya menyelesaikannya dengan menerapkan properti `overflow: hidden;` dan `position: relative;` pada selector `.weather-details .text` untuk menyembunyikan "elemen hantu" dengan sempurna saat transisi geser ke atas terjadi.

## 👨‍💻 Penulis
**Muhammad Faaiz Anugrah**
* special thanks to **Codehal**
