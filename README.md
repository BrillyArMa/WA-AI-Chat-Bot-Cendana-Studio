# 🤖 AI Booking System - Cendana Music Studio
[![License](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Status](https://img.shields.io/badge/Status-Production%20Ready-brightgreen.svg)]()

## 💡 Project Overview: Mengubah Interaksi Bisnis Menjadi Otomatisasi Cerdas
Cendana Music Studio menghadapi tantangan dalam mengelola *booking* studio, menjawab pertanyaan umum (harga, jadwal), dan menangani komplain secara efisien melalui WhatsApp. Proyek ini adalah solusi **Intelligent Automation** yang menggunakan AI Agent untuk menjadi "front-office" digital 24/7.

Kami berhasil mengubah interaksi chat pengguna yang bersifat natural menjadi proses bisnis terstruktur, menghasilkan penghematan biaya operasional sebesar Rp120.000/bulan dan peningkatan efisiensi hingga 87%.

---

## ⚙️ Technical Deep Dive: Arsitektur Sistem
Sistem ini dirancang sebagai *micro-workflow* yang sangat modular, di mana N8N bertindak sebagai orkestrator utama yang menghubungkan semua layanan.

### 🖼️ Visualisasi Workflow (The Orchestration)
*(Ganti path/to/your_n8n_image.png dengan lokasi gambar Anda)*
![Diagram Alir Otomatisasi Booking Cendana Music Studio](path/to/your_n8n_image.png)

### 🧠 How It Works: Peran AI Agent sebagai Business Logic Engine
AI Agent bukan hanya menjawab pertanyaan, tetapi bertindak sebagai **mesin logika bisnis** yang cerdas. Berikut adalah tahapan kerjanya:

1.  **Ingestion (Input):** Permintaan masuk melalui Webhook WhatsApp dalam bentuk teks natural dari pengguna.
2.  **Intelligent Routing & Categorization:** AI Agent menganalisis *intent* (maksud) dari chat tersebut. Apakah ini `[Booking Request]`, `[Price Inquiry]`, atau `[Complaint]`? Kategorisasi ini menentukan alur selanjutnya.
3.  **Decision Making & Calculation:** Jika permintaan adalah booking, Agent akan:
    *   Memeriksa ketersediaan tanggal/waktu melalui **Google Calendar**.
    *   Menghitung total biaya sewa berdasarkan durasi (misalnya, 1 jam x Rp50.000).
4.  **Data Persistence:** Semua interaksi pengguna—termasuk kategori dan detail booking—disimpan secara terstruktur di **PostgreSQL**, memungkinkan pelacakan riwayat yang akurat.
5.  **Action & Confirmation:** Setelah logika selesai, sistem mengirimkan balasan yang relevan (informasi harga, konfirmasi slot) kembali ke WhatsApp, sekaligus mencatat event di Google Calendar sebagai *reminder* resmi.

---
