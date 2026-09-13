# Panduan Menulis Artikel Blog Manual

Sistem blog portofolio Anda menggunakan struktur static HTML modern yang sangat ringan, tanpa database, dan langsung ter-deploy di GitHub Pages.

Folder proyek blog Anda berada di:
`D:\PROJECT\Website\Movlution\blog\`

---

## Langkah 1: Buat File Artikel Baru
1. Buka folder `blog/posts/`.
2. Duplikat file template yang sudah disediakan: `blog/posts/template-artikel.html`.
3. Ganti nama filenya menggunakan huruf kecil dan tanda hubung, contoh:
   `blog/posts/tips-optimasi-unity-mobile.html`
4. Buka file tersebut dengan editor teks (VS Code / Notepad / dll).
5. Edit bagian:
   - `<title>`: Judul artikel Anda.
   - Tag kategori: `Tech Art & Tooling` / `Game Dev & Studio` / `Architecture`.
   - Tanggal & estimasi waktu baca (`5 min read`).
   - Isi teks di dalam `<div class="article-content">`:
     - Paragraf: `<p>teks anda</p>`
     - Sub-judul: `<h2>judul bagian</h2>`
     - Daftar poin: `<ul><li>poin</li></ul>`
     - Potongan kode: `<pre><code>// kode anda</code></pre>`

---

## Langkah 2: Daftarkan Artikel ke Halaman Indeks Blog
Buka file `blog/index.html`, cari bagian `<div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6" id="articles-container">`, lalu tambahkan satu kartu baru di paling atas:

```html
<!-- Artikel Baru -->
<article class="raycast-card flex flex-col justify-between" data-category="tech-art">
  <div>
    <div class="px-5 py-3 border-b border-white/[0.06] bg-white/[0.02] flex items-center justify-between text-xs font-mono">
      <span class="text-indigo-400">Tech Art & Tooling</span>
      <span class="text-slate-500">5 min read</span>
    </div>
    <div class="p-6">
      <span class="text-xs font-mono text-slate-500">15 September 2026</span>
      <h2 class="text-lg font-bold text-white mt-1 hover:text-indigo-400 transition">
        <a href="posts/tips-optimasi-unity-mobile.html">
          Tips Optimasi Performa Game Unity di Mobile
        </a>
      </h2>
      <p class="text-xs sm:text-sm text-slate-400 mt-2.5 leading-relaxed">
        Ringkasan singkat isi artikel Anda agar menarik perhatian pembaca.
      </p>
    </div>
  </div>
  <div class="p-6 pt-0">
    <div class="flex flex-wrap gap-1.5 mb-4">
      <span class="text-[10px] font-mono px-2 py-0.5 rounded bg-white/[0.04] text-slate-300">Unity</span>
      <span class="text-[10px] font-mono px-2 py-0.5 rounded bg-white/[0.04] text-slate-300">Android</span>
    </div>
    <a href="posts/tips-optimasi-unity-mobile.html" class="inline-flex items-center gap-1 text-xs font-semibold text-indigo-400 hover:text-indigo-300 transition">
      <span>Baca Artikel Lengkap</span>
      <i data-lucide="arrow-right" class="w-3.5 h-3.5"></i>
    </a>
  </div>
</article>
```

---

## Langkah 3: Publikasikan (Git Push)
Buka terminal di folder `D:\PROJECT\Website\Movlution\` dan jalankan:

```bash
git add .
git commit -m "feat(blog): publish new article tips optimasi unity mobile"
git push origin main
```

Dalam waktu ~30 detik, artikel baru Anda akan langsung tayang di `https://movlution.github.io/blog/`.
Atau jika Anda sedang bersama saya, cukup beri tahu judul dan draft isinya, saya yang akan merapikan dan menerbitkannya secara otomatis!
