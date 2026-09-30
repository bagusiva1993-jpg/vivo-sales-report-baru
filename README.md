# VIVO Sales Report — Firebase Baru

Paket ini adalah website laporan penjualan promotor Vivo yang dapat dipasang di repository GitHub baru.

## Penting: database benar-benar baru

Website ini **tidak menggunakan database lama** selama konfigurasi Firebase di `index.html` diganti dengan konfigurasi dari Firebase Project baru.

Jangan memasukkan konfigurasi Firebase lama.

## 1. Buat Firebase Project Baru

1. Buka Firebase Console.
2. Pilih **Add project / Tambah project**.
3. Buat project baru, misalnya:
   `vivo-sales-report-baru`
4. Masuk ke **Realtime Database**.
5. Buat database baru.
6. Pilih lokasi database sesuai kebutuhan.
7. Untuk pengujian awal, ikuti aturan keamanan Firebase yang sesuai. Jangan menggunakan aturan terbuka untuk penggunaan produksi.

## 2. Tambahkan Web App

Di Firebase Project baru:

1. Project settings.
2. Add app → Web `</>`.
3. Beri nama misalnya `Vivo Sales Web`.
4. Firebase akan memberikan konfigurasi seperti:

```js
const firebaseConfig = {
  apiKey: "...",
  authDomain: "...",
  databaseURL: "...",
  projectId: "...",
  storageBucket: "...",
  messagingSenderId: "...",
  appId: "..."
};
```

## 3. Masukkan konfigurasi ke website

Buka `index.html`.

Cari bagian:

```js
const firebaseConfig = {
  apiKey: "GANTI_API_KEY",
  ...
};
```

Ganti dengan konfigurasi Firebase **PROJECT BARU**.

Pastikan `databaseURL` juga berasal dari database baru.

## 4. Upload ke GitHub

Buat repository baru, misalnya:

`vivo-sales-report-baru`

Upload:

- `index.html`
- `README.md`

Tidak perlu upload database Firebase ke GitHub. Database berada di Firebase.

## 5. Aktifkan GitHub Pages

Di repository GitHub:

**Settings → Pages**

Pilih:

- Source: Deploy from a branch
- Branch: `main`
- Folder: `/ (root)`

Simpan.

Setelah proses selesai, GitHub akan memberikan alamat website.

## Data yang disimpan

Website menggunakan Firebase Realtime Database dengan node:

- `promotors`
- `reports`

Karena memakai Firebase Project baru, data ini terpisah dari project/database lama.

## Catatan keamanan

Versi ini dibuat sederhana agar mudah dipasang. Password admin di HTML/client-side bukan sistem keamanan produksi.

Untuk penggunaan serius, sebaiknya gunakan Firebase Authentication dan Firebase Security Rules.
