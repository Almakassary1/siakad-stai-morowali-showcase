<div align="center">

# SIAKAD STAI Morowali

**Sistem Informasi Akademik · Academic Information System**

Studi kasus oleh **Almakassary** · Full-stack & UI/UX · 2026

[**Lihat portofolio lengkap · View full case study →**](https://almakassary1.github.io/siakad-stai-morowali-showcase/)

![Next.js](https://img.shields.io/badge/Next.js_16-000?logo=nextdotjs&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?logo=typescript&logoColor=white)
![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-06B6D4?logo=tailwindcss&logoColor=white)
![Prisma](https://img.shields.io/badge/Prisma_7-2D3748?logo=prisma&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL_16-4169E1?logo=postgresql&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?logo=docker&logoColor=white)

<img src="assets/eksekutif.webp" alt="Command Center — Dashboard Eksekutif" width="100%">

</div>

## Tentang proyek

Sistem informasi akademik berbasis web untuk Sekolah Tinggi Agama Islam (STAI) Morowali dengan 4 program studi: PAI, HKI, PGMI, dan PIAUD. Cakupannya mulai dari KRS mahasiswa dan penilaian dosen sampai Command Center pimpinan dengan peringatan dini akademik. Struktur datanya mengikuti kode referensi PDDikti / Neo Feeder sejak awal.

*A web-based academic information system for STAI Morowali (Central Sulawesi, Indonesia). It covers student course registration, lecturer grading, and an executive Command Center with an academic early-warning system. The data model follows Indonesia's national higher-education reporting codes (PDDikti / Neo Feeder).*

| | |
|---|---|
| **4** program studi | **7** peran pengguna dengan hak akses berbeda |
| **21** halaman aplikasi | **151** tes otomatis lulus |

## Dibangun dalam lima fase

1. **Fondasi data**: skema Prisma/PostgreSQL berkode Feeder, aturan beban SKS, prasyarat, dan skala nilai.
2. **Design system**: tema *midnight glassmorphism*, sidebar per peran, palet perintah (Ctrl K), dan tabel data.
3. **Panel admin**: data master, kurikulum, plotting jadwal dengan deteksi bentrok, moderasi KRS, dan validasi keuangan.
4. **Portal mahasiswa & dosen**: KRS builder, KHS & transkrip, bimbingan akademik, dan lembar nilai.
5. **Eksekutif & rilis**: Command Center, *Early Warning System*, login aman, dan Docker siap produksi.

## Cuplikan layar

| Peringatan dini (Early Warning) | Status pembayaran per prodi |
|---|---|
| <img src="assets/ews.webp" alt="Early warning"> | <img src="assets/bayar.webp" alt="Pembayaran"> |

| KRS builder | Lembar nilai dosen |
|---|---|
| <img src="assets/krs.webp" alt="KRS builder"> | <img src="assets/nilai.webp" alt="Lembar nilai"> |

| Deteksi bentrok jadwal | Papan kurikulum |
|---|---|
| <img src="assets/konflik.webp" alt="Bentrok jadwal"> | <img src="assets/kurikulum.webp" alt="Kurikulum"> |

<div align="center">
<img src="assets/m_eks.webp" alt="Mobile — Command Center" width="30%">&nbsp;
<img src="assets/m_krs.webp" alt="Mobile — KRS" width="30%">&nbsp;
<img src="assets/m_drawer.webp" alt="Mobile — Navigasi" width="30%">
</div>

## Sorotan teknis

- **Early Warning System** dengan tiga tingkat. *Kritis*: IPK < 2,00, atau IPS < 2,00 dua semester berturut-turut. *Tinggi*: IPS < 2,00 dan turun ≥ 0,75. *Waspada*: IPS < 2,00. Notifikasi ke dosen PA dikirim dengan satu klik dan tercatat di audit log.
- **Keamanan**: password di-hash dengan scrypt, sesi bertanda tangan HMAC (httpOnly) yang gugur saat password diganti, pembatasan percobaan login, dan hak akses per peran serta per prodi.
- **Siap PDDikti**: status mahasiswa memakai kode resmi Feeder, ada kolom `feeder_id` untuk sinkronisasi, dan rasio dosen : mahasiswa diukur terhadap acuan Ditjen Dikti.
- **Deployment**: Docker multi-stage dengan Next.js standalone, kontainer non-root dan read-only, PostgreSQL 16 di jaringan internal, HTTPS otomatis, serta backup harian.

## Catatan

Repositori ini hanya berisi **halaman portofolio dan tangkapan layar**. Kode sumber aplikasi bersifat privat. Semua data pada tangkapan layar adalah **data demo**.

*This repository contains only the portfolio page and screenshots. The application source code is private. All screenshots show demo data.*

---

© 2026 Almakassary. Hak cipta dilindungi. Lihat [LICENSE](LICENSE).
