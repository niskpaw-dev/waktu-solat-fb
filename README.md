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
- `ZONE_LABEL` — label atas grid waktu; kosongkan (`""`) untuk guna `zone_name` dari API
- `SOURCE_SHORT` — pemendek label sumber untuk footer (`source` penuh dari API terlalu panjang)
- `TIME_12H`, `HIJRI_NUMERALS` — format paparan

## Nota

- Request API sentiasa hantar `?month=MM&year=YYYY`. Tanpa `year`, API guna tahun semasa.
- Pemilih default ke **bulan depan** (waktu KL), sebab poster dijana awal.
- Deploy: Vercel, static (tiada build command, output = root).
