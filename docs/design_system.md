\# DESIGN\_SYSTEM.md



```markdown

\# Design System - EPL Historical Predictor



\## Informasi Dokumen



| Atribut | Keterangan |

|---------|-------------|

| Nama Aplikasi | EPL Historical Predictor |

| Versi Design System | 1.0 |

| Tanggal | 25 Mei 2026 |

| Target Platform | Streamlit Web App |



\---



\## 1. Filosofi Desain



| Aspek | Deskripsi |

|-------|-----------|

| Kesan | Profesional, clean, data-driven |

| Referensi | The Athletic, Opta Analyst, FiveThirtyEight |

| Pendekatan | Minimalis, fungsional, mudah dibaca |

| Emoji | Minimal, hanya untuk fungsi (toggle tema) |



\---



\## 2. Color Palette



\### 2.1 Tema Terang (Light Mode)



| Peran | Hex | RGB | Penggunaan |

|-------|-----|-----|-------------|

| Primary | `#0F4C81` | 15,76,129 | Header, tombol utama, link |

| Primary Light | `#2E6DA4` | 46,109,164 | Hover state |

| Secondary | `#2C3E50` | 44,62,80 | Teks judul |

| Success | `#2E7D32` | 46,125,50 | Home Win |

| Warning | `#F57C00` | 245,124,0 | Draw |

| Danger | `#C62828` | 198,40,40 | Away Win |

| Background | `#F8FAFC` | 248,250,252 | Latar halaman |

| Surface | `#FFFFFF` | 255,255,255 | Kartu, modal |

| Border | `#E2E8F0` | 226,232,240 | Garis pemisah |

| Text Primary | `#1E293B` | 30,41,59 | Teks utama |

| Text Secondary | `#64748B` | 100,116,139 | Teks bantuan |



\### 2.2 Tema Gelap (Dark Mode)



| Peran | Hex | RGB | Penggunaan |

|-------|-----|-----|-------------|

| Primary | `#3B82F6` | 59,130,246 | Tombol utama, aksen |

| Primary Dark | `#2563EB` | 37,99,235 | Hover state |

| Secondary | `#94A3B8` | 148,163,184 | Teks sekunder |

| Success | `#22C55E` | 34,197,94 | Home Win |

| Warning | `#F59E0B` | 245,158,11 | Draw |

| Danger | `#EF4444` | 239,68,68 | Away Win |

| Background | `#0F172A` | 15,23,42 | Latar halaman |

| Surface | `#1E293B` | 30,41,59 | Kartu, modal |

| Border | `#334155` | 51,65,85 | Garis pemisah |

| Text Primary | `#F1F5F9` | 241,245,249 | Teks utama |

| Text Secondary | `#94A3B8` | 148,163,184 | Teks bantuan |



\### 2.3 Tabel Warna Hasil Pertandingan



| Hasil | Tema Terang | Tema Gelap |

|-------|-------------|------------|

| Home Win (H) | `#2E7D32` | `#22C55E` |

| Draw (D) | `#F57C00` | `#F59E0B` |

| Away Win (A) | `#C62828` | `#EF4444` |



\---



\## 3. Tipografi



\### 3.1 Font Family



| Penggunaan | Font | Fallback |

|------------|------|----------|

| Semua teks | Inter | -apple-system, BlinkMacSystemFont, Segoe UI, Helvetica, Arial, sans-serif |

| Kode | JetBrains Mono | SF Mono, Monaco, Consolas, monospace |



\### 3.2 Font Source



```html

<link href="https://fonts.googleapis.com/css2?family=Inter:opsz,wght@14..32,400;14..32,500;14..32,600;14..32,700\&family=JetBrains+Mono\&display=swap" rel="stylesheet">

```



\### 3.3 Font Scale



| Elemen | Size | Weight | Line Height | Penggunaan |

|--------|------|--------|-------------|------------|

| H1 | 32px | 700 | 1.2 | Judul halaman utama |

| H2 | 24px | 600 | 1.3 | Sub judul halaman |

| H3 | 20px | 600 | 1.4 | Judul section dalam card |

| Body | 16px | 400 | 1.5 | Teks utama, paragraf |

| Small | 14px | 400 | 1.5 | Teks bantuan, keterangan |

| Caption | 12px | 400 | 1.5 | Label kecil, footer |

| Code | 14px | 400 | 1.5 | Kode program |



\---



\## 4. Spacing



\### 4.1 Spacing Scale



| Nama | Nilai | Penggunaan |

|------|-------|-------------|

| xs | 4px | Jarak antar ikon dan teks |

| sm | 8px | Jarak dalam komponen |

| md | 16px | Jarak antar elemen dalam card |

| lg | 24px | Jarak antar card, padding container |

| xl | 32px | Jarak antar section |

| 2xl | 48px | Jarak antar halaman |



\### 4.2 Layout Container



| Properti | Nilai |

|----------|-------|

| Max width | 1200px |

| Padding container | 24px (lg) |

| Gap antar kolom | 16px (md) |



\---



\## 5. Komponen UI



\### 5.1 Tombol (Button)



| Properti | Nilai |

|----------|-------|

| Border radius | 8px |

| Padding | 8px 20px |

| Transition | 0.2s ease |

| Hover effect | opacity 0.85, transform translateY(-1px) |



\*\*Varian Tombol:\*\*



| Varian | Tema Terang | Tema Gelap |

|--------|-------------|------------|

| Primary | Background `#0F4C81`, text putih | Background `#3B82F6`, text putih |

| Secondary | Background putih, border `#0F4C81`, text `#0F4C81` | Background `#1E293B`, border `#3B82F6`, text `#3B82F6` |

| Danger | Background `#C62828`, text putih | Background `#EF4444`, text putih |



\### 5.2 Kartu (Card)



| Properti | Tema Terang | Tema Gelap |

|----------|-------------|------------|

| Background | `#FFFFFF` | `#1E293B` |

| Border | `1px solid #E2E8F0` | `1px solid #334155` |

| Border radius | 12px | 12px |

| Shadow | `0 1px 3px rgba(0,0,0,0.05)` | `0 1px 3px rgba(0,0,0,0.3)` |

| Padding | 20px | 20px |



\### 5.3 Dropdown (Select Box)



| Properti | Tema Terang | Tema Gelap |

|----------|-------------|------------|

| Padding | 8px 12px | 8px 12px |

| Border radius | 8px | 8px |

| Border | `1px solid #E2E8F0` | `1px solid #334155` |

| Background | `#FFFFFF` | `#1E293B` |

| Text color | `#1E293B` | `#F1F5F9` |



\### 5.4 Progress Bar



| Properti | Nilai |

|----------|-------|

| Height | 8px |

| Border radius | 4px |

| Background | `#E2E8F0` (light) / `#334155` (dark) |

| Fill (Primary) | `#0F4C81` (light) / `#3B82F6` (dark) |

| Fill (Success) | `#2E7D32` (light) / `#22C55E` (dark) |

| Fill (Warning) | `#F57C00` (light) / `#F59E0B` (dark) |

| Fill (Danger) | `#C62828` (light) / `#EF4444` (dark) |

| Transition | width 0.3s ease |



\### 5.5 Sidebar



| Properti | Tema Terang | Tema Gelap |

|----------|-------------|------------|

| Background | `#FFFFFF` | `#1E293B` |

| Border right | `1px solid #E2E8F0` | `1px solid #334155` |

| Width | 280px | 280px |

| Padding | 20px 16px | 20px 16px |



\### 5.6 Tabel (Data Table)



| Properti | Tema Terang | Tema Gelap |

|----------|-------------|------------|

| Header background | `#F1F5F9` | `#334155` |

| Row hover | `#F8FAFC` | `#2D3748` |

| Border | `1px solid #E2E8F0` | `1px solid #334155` |

| Padding | 12px 16px | 12px 16px |

| Border radius | 12px | 12px |



\---



\## 6. Toggle Tema



\### 6.1 Posisi

\- Sidebar bagian bawah

\- Atau top right corner (alternatif)



\### 6.2 Ikon

| Tema | Ikon |

|------|------|

| Terang (Light) | ☀️ |

| Gelap (Dark) | 🌙 |



\### 6.3 State yang Disimpan

\- Preferensi tema disimpan di session\_state

\- Disimpan di localStorage browser



\---



\## 7. Gambar Eksternal



Semua gambar diambil dari URL online (tidak disimpan lokal).



| Gambar | URL | Penggunaan |

|--------|-----|-------------|

| Logo Premier League | `https://resources.premierleague.com/premierleague/badges/50/t1.png` | Sidebar, Header |

| Icon Home Win | `https://cdn-icons-png.flaticon.com/512/25/25694.png` | Hasil prediksi |

| Icon Draw | `https://cdn-icons-png.flaticon.com/512/190/190411.png` | Hasil prediksi |

| Icon Away Win | `https://cdn-icons-png.flaticon.com/512/25/25693.png` | Hasil prediksi |



\---



\## 8. Layout Halaman



\### 8.1 Struktur Umum



```

┌─────────────────────────────────────────────────────────────┐

│                         HEADER                              │

│  Judul Halaman + Deskripsi                                  │

├───────────────┬─────────────────────────────────────────────┤

│               │                                             │

│   SIDEBAR     │                 MAIN CONTENT                │

│   (280px)     │                                             │

│               │   - Kartu (Card)                            │

│               │   - Tabel (Table)                           │

│               │   - Form (Dropdown + Button)                │

│               │   - Grafik (Plotly)                         │

│               │                                             │

├───────────────┴─────────────────────────────────────────────┤

│                         FOOTER                              │

│  Copyright, sumber data, informasi proyek                   │

└─────────────────────────────────────────────────────────────┘

```



\### 8.2 Layout per Halaman



\*\*Home:\*\*

\- Header → H1 judul proyek + deskripsi

\- Main → 2 card (deskripsi proyek, identitas anggota)



\*\*Dataset Overview:\*\*

\- Header → H1 + deskripsi

\- Main → Metric cards (3-4 buah) + tabel preview + visualisasi



\*\*Prediction:\*\*

\- Header → H1 + deskripsi

\- Main → Form (2 dropdown) + tombol predict + hasil prediksi (3 progress bar)



\*\*Visualization:\*\*

\- Header → H1 + deskripsi

\- Main → Dropdown pilih grafik + plot area



\*\*About:\*\*

\- Header → H1 + deskripsi

\- Main → 2-3 card (penjelasan metode, dataset, informasi proyek)



\---



\## 9. Responsiveness



| Breakpoint | Lebar Layar | Perilaku |

|------------|-------------|----------|

| Desktop | > 992px | Layout normal (sidebar kiri, konten kanan) |

| Tablet | 768px - 992px | Sidebar bisa di-collapse |

| Mobile | < 768px | Sidebar full width, konten full width |



\---



\## 10. Aksesibilitas



| Aspek | Standar |

|-------|---------|

| Contrast ratio | Minimal 4.5:1 untuk teks normal |

| Font size | Minimal 14px untuk teks body |

| Focus indicator | Outline visible untuk keyboard navigation |

| Alt text | Semua gambar memiliki alt text |



\---



\## 11. File Implementasi



| File | Lokasi | Isi |

|------|--------|-----|

| base.css | `app/assets/base.css` | Style dasar, reset CSS |

| theme\_light.css | `app/assets/theme\_light.css` | Tema terang |

| theme\_dark.css | `app/assets/theme\_dark.css` | Tema gelap |

| theme\_manager.py | `app/utils/theme\_manager.py` | Manajemen toggle tema |



\---



\## 12. Contoh Penggunaan dalam Kode



\### CSS Class yang Tersedia



```css

/\* Kartu \*/

.card { ... }

.card-header { ... }

.card-body { ... }



/\* Tombol \*/

.btn-primary { ... }

.btn-secondary { ... }

.btn-danger { ... }



/\* Tabel \*/

.data-table { ... }

.data-table th { ... }

.data-table td { ... }



/\* Progress Bar \*/

.progress-bar { ... }

.progress-fill { ... }



/\* Hasil Prediksi \*/

.result-home { ... }

.result-draw { ... }

.result-away { ... }



/\* Toggle Tema \*/

.theme-toggle { ... }

```



\---



\## 13. Riwayat Revisi Design System



| Versi | Tanggal | Perubahan |

|-------|---------|-----------|

| 1.0 | 25/05/2026 | Initial design system (2 tema: terang \& gelap) |

```



\---



\*\*Design system sudah selesai.\*\* File ini sebaiknya disimpan di `docs/design\_system.md` dalam struktur folder proyek Anda. 🚀

