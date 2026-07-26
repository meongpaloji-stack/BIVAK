# BIVAK — Barter Item & Value Antar Komunitas

Situs statis satu halaman berisi **dokumen rancangan MVP BIVAK**, marketplace barter gear outdoor untuk ekosistem Pintu Angin dan komunitas Reichas Chelebes.

Dibuat dengan HTML5 + CSS murni. Tanpa build step, tanpa dependensi, tanpa JavaScript.

---

## Struktur repo

```
.
├── index.html                  # halaman dokumen rancangan BIVAK
├── 404.html                    # halaman not found
├── favicon.svg                 # ikon situs
├── robots.txt
├── .nojekyll                   # matikan proses Jekyll di GitHub Pages
├── .gitignore
├── LICENSE
└── .github/workflows/deploy.yml  # deploy otomatis ke GitHub Pages
```

---

## Cara deploy ke GitHub Pages

### Opsi A — lewat web GitHub (paling cepat)

1. Buka <https://github.com/new>, buat repo baru, misal `bivak-docs`, set **Public**.
2. Klik **uploading an existing file**, lalu unggah seluruh isi folder ini (termasuk file `.nojekyll` dan folder `.github`).
   Jika drag-and-drop tidak menyertakan file bertitik, unggah lewat Git (Opsi B).
3. Commit ke branch `main`.
4. Masuk **Settings → Pages**.
5. Bagian **Build and deployment → Source**, pilih **GitHub Actions**.
6. Tunggu tab **Actions** selesai (ikon centang hijau).
7. Situs aktif di `https://<username>.github.io/bivak-docs/`.

### Opsi B — lewat Git di komputer sendiri

```bash
cd bivak-site

git init
git add .
git commit -m "BIVAK: dokumen rancangan MVP"
git branch -M main

# ganti <username> dan <nama-repo>
git remote add origin https://github.com/<username>/<nama-repo>.git
git push -u origin main
```

Lalu **Settings → Pages → Source: GitHub Actions**.

### Opsi C — tanpa GitHub Actions

Di **Settings → Pages**, pilih **Source: Deploy from a branch**, branch `main`, folder `/ (root)`.
File `.nojekyll` memastikan semua aset disajikan apa adanya. Workflow di `.github/workflows/deploy.yml` bisa dihapus jika memakai cara ini.

---

## Uji coba lokal

```bash
# cukup buka langsung
open index.html

# atau jalankan server statis
python3 -m http.server 8000
# lalu buka http://localhost:8000
```

---

## Catatan

- Domain kustom: tambahkan file `CNAME` berisi nama domain, lalu arahkan DNS ke GitHub Pages.
- Untuk repo privat, GitHub Pages memerlukan paket berbayar. Gunakan repo publik jika dokumen ini boleh dibaca umum.
- Dokumen ini bersifat rancangan internal; jangan menaruh kredensial Supabase, kunci API, atau data pengguna di repo ini.
