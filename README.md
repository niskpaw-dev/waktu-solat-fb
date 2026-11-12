# Waktu Solat FB · MKSLB

Penjana poster waktu solat harian untuk Facebook Page Masjid Kampung Sungai Lang Baru.
Pilih bulan + tahun → tarik data dari API waktu solat → jana sebulan poster (PNG 2160×2700) → muat turun ZIP → jadualkan di Meta Business Suite.

## Fail

| Fail | Fungsi |
|---|---|
| `index.html` | Keseluruhan tool (vanilla HTML/CSS/JS, tiada build) |
| `bg.jpg` | Gambar latar (drone shot, 4:5). Tukar fail ini untuk tukar latar — kekalkan nama & nisbah 4:5 |
| `logo.png` | Logo masjid (latar telus) |

## Tetapan

Semua dalam blok `CONFIG` di atas `<script>` dalam `index.html`:

- `API_BASE` — endpoint API waktu solat
- `YEARS` — tahun dalam pemilih (turut dikemas kini auto dari `years_available` API)
- `ZONE_LABEL_OVERRIDE` — label kawasan ganti ikut tahun (`{2026: "Daerah Kuala Langat"}`); tahun lain terus guna `zone_name` dari API

Footer sumber guna terus `source_short` dari API (fallback ke `source`, dengan auto-fit font).
- `TIME_12H`, `HIJRI_NUMERALS` — format paparan

## Nota

- Request API sentiasa hantar `?month=MM&year=YYYY`. Tanpa `year`, API guna tahun semasa.
- Pemilih default ke **bulan depan** (waktu KL), sebab poster dijana awal.
- Deploy: Vercel, static (tiada build command, output = root).
