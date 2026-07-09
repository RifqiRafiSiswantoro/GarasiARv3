# Toyota Avanza — 3D Preview

Preview 3D interaktif mobil Toyota Avanza (Three.js + FBX), lengkap dengan tekstur PBR bawaan (basecolor, metallic, roughness, normal, RM).

## Struktur folder
```
index.html
model.fbx
textures/
  avanza_basecolor.JPEG
  avanza_metallic.JPEG
  avanza_roughness.JPEG
  avanza_normal.JPEG
  avanza_rm.JPEG
```

Model dan tekstur otomatis termuat begitu halaman dibuka — **tidak perlu upload file manual** — selama struktur folder di atas dijaga tetap sama persis dan halaman diakses lewat web server (bukan dibuka langsung sebagai `file://`). Ini otomatis terpenuhi kalau kamu host lewat GitHub Pages (lihat di bawah).

## Cara upload ke GitHub

Dari folder ini (lewat terminal):

```bash
git init
git add .
git commit -m "Toyota Avanza 3D preview"
git branch -M main
git remote add origin https://github.com/USERNAME/NAMA-REPO.git
git push -u origin main
```

Ganti `USERNAME` dan `NAMA-REPO` dengan punyamu. Kalau repo belum ada, buat dulu repo kosong (tanpa README) di github.com, baru jalankan perintah di atas.

> Catatan: `model.fbx` berukuran ~55 MB. GitHub masih mengizinkan file sampai 100 MB per file tanpa Git LFS, jadi push biasa di atas akan berhasil — tapi kalau kamu dapat peringatan ukuran file besar, bisa pakai [Git LFS](https://git-lfs.com) sebagai opsi:
> ```bash
> git lfs install
> git lfs track "*.fbx"
> git add .gitattributes
> ```
> lalu ulangi `git add`, `commit`, `push` seperti biasa.

## Cara mengaktifkan GitHub Pages (agar bisa dibuka lewat link, auto-load semua file)

1. Buka repo di GitHub → tab **Settings** → **Pages**.
2. Di bagian **Source**, pilih branch `main` dan folder `/ (root)`.
3. Simpan. Tunggu 1–2 menit, lalu buka link yang muncul (biasanya `https://USERNAME.github.io/NAMA-REPO/`).
4. Halaman akan langsung menampilkan mobil beserta teksturnya secara otomatis, tanpa perlu upload file apa pun — karena file dilayani lewat HTTP oleh GitHub Pages.

## Menjalankan secara lokal (opsional, untuk testing sebelum push)

Karena browser modern memblokir `fetch()` file lokal lewat `file://`, jalankan server lokal sederhana di folder ini:

```bash
python3 -m http.server 8000
```

Lalu buka `http://localhost:8000` di browser.
