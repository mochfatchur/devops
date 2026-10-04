# Ringkasan Diskusi: Manajemen Disk & Perintah Linux

Dokumen ini berisi rangkuman topik dan solusi teknis yang telah dibahas dalam sesi diskusi.

---

## 📌 Ringkasan Topik & Penjelasan

### 1. Konsep *Least Privilege* & Integritas Sistem
* **Pertanyaan:** Penjelasan dari *"This ensures users can perform tasks without compromising system integrity"*.
* **Penjelasan:** Memberikan hak akses secukupnya kepada pengguna agar tetap bisa menyelesaikan tugas tanpa risiko merusak, mengubah, atau membahayakan keamanan/integritas sistem.

---

### 2. Hubungan `apt` dan `dpkg` di Debian/Ubuntu
* **Pertanyaan:** Apakah `apt` bergantung pada `dpkg` untuk menginstal paket setelah *dependencies* terurai?
* **Penjelasan:** **Ya.** 
  * `apt` bertugas mengunduh paket dan menyelesaikan *dependencies* (tingkat tinggi).
  * `apt` kemudian menyerahkan file `.deb` ke `dpkg` (tingkat rendah) untuk melakukan ekstraksi, instalasi, dan konfigurasi.

---

### 3. Memeriksa Deteksi Disk Baru di CentOS / RHEL
* **Pertanyaan:** Perintah untuk mengecek apakah disk baru sudah terdeteksi sistem?
* **Perintah Utama:**
  ```bash
  lsblk         # Menampilkan daftar block devices (Direkomendasikan)
  sudo fdisk -l # Menampilkan detail partisi dan kapasitas disk
  lsscsi        # Menampilkan perangkat SCSI/SATA