# Petualangan di Kulawi — Statistika & Peluang

Game edukasi berbasis browser untuk materi statistika dan peluang, berlatar budaya Kulawi.

## Status proyek

Repositori ini sedang disiapkan untuk merapikan kode dari versi HTML tunggal menjadi struktur yang lebih mudah dipelihara. Sebelum pemisahan modul, simpan versi HTML yang saat ini berfungsi sebagai cadangan dan uji agar perilaku game tidak berubah.

## Struktur yang dituju

```text
petualangan-di-kulawi/
├── index.html                 # halaman utama game
├── README.md
├── css/
│   └── game.css               # seluruh CSS game
├── src/
│   ├── main.js                # titik masuk dan inisialisasi
│   ├── config.js              # konfigurasi dan konstanta
│   ├── ui.js                  # menu, dialog, HUD, dan panel
│   ├── world.js               # scene, renderer, kamera, pencahayaan
│   ├── village-map.js         # enam desa dan jalur eksplorasi
│   ├── river-bridge.js        # sungai, jembatan, dan kondisi menyeberang
│   ├── player.js              # karakter, kontrol, dan animasi
│   ├── animals.js             # babirusa dan perilakunya
│   ├── durian.js              # pohon, buah, dan pengumpulan durian
│   ├── questions.js            # soal, jawaban, dan pembahasan
│   ├── progress.js             # skor, progres, dan penyimpanan
│   └── reports.js              # ekspor CSV dan laporan cetak
├── assets/
│   ├── characters/
│   ├── animals/
│   ├── environment/
│   ├── textures/
│   ├── audio/
│   └── animations/
└── tests/
    └── smoke-test.md           # daftar pemeriksaan manual
```

## Aturan refaktor

1. Pertahankan salinan versi lama sebelum mengubah kode.
2. Pindahkan satu bagian kode pada satu waktu; hindari mengubah mekanika permainan bersamaan dengan pemindahan file.
3. Pastikan setiap modul memiliki tanggung jawab jelas dan gunakan `export`/`import` secara konsisten.
4. Jangan menghapus nama fungsi atau variabel lama sebelum semua pemanggilnya diperbarui.
5. Uji pemuatan Three.js, menu awal, gerakan pemain, enam stage, jembatan, pengumpulan durian, soal, progres, dan ekspor laporan setelah setiap tahap.
6. Untuk pengujian lokal, gunakan server lokal sederhana karena JavaScript module dan aset dapat bermasalah jika halaman dibuka langsung melalui `file://`.

## Urutan pengerjaan

- [ ] Unggah versi HTML tunggal yang terakhir berfungsi ke `legacy/` sebagai cadangan.
- [ ] Pisahkan CSS ke `css/game.css`.
- [ ] Pisahkan data soal dan konfigurasi ke `src/questions.js` dan `src/config.js`.
- [ ] Pisahkan sistem laporan dan progres.
- [ ] Pisahkan dunia 3D, peta desa, karakter, hewan, serta objek lingkungan secara bertahap.
- [ ] Jalankan pengujian manual dan catat hasilnya di `tests/smoke-test.md`.

## Teknologi

- HTML, CSS, JavaScript ES Modules
- Three.js untuk grafis 3D
- GLTF/GLB dapat digunakan untuk aset 3D rigged pada tahap optimasi berikutnya
