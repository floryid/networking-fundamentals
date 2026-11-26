# Networking Fundamentals - Panduan Lengkap

Aplikasi edukasi interaktif untuk mempelajari konsep-konsep fundamental jaringan komputer yang penting untuk **pentesting** dan **cyber security**. Dibangun dengan HTML, CSS, dan JavaScript murni tanpa framework.

![Status](https://img.shields.io/badge/status-active-success)
![License](https://img.shields.io/badge/license-MIT-blue)
![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat&logo=javascript&logoColor=black)

## Daftar Isi

- [Tentang](#tentang)
- [Fitur](#fitur)
- [Topik yang Dibahas](#topik-yang-dibahas)
- [Cara Menjalankan](#cara-menjalankan)
- [Deploy ke GitHub Pages](#deploy-ke-github-pages)
- [Struktur Project](#struktur-project)
- [Tech Stack](#tech-stack)
- [Kontribusi](#kontribusi)
- [Lisensi](#lisensi)

## Tentang

**Networking Fundamentals** adalah aplikasi web edukatif yang dirancang untuk membantu pemula maupun profesional IT dalam memahami konsep jaringan komputer yang menjadi fondasi penting dalam dunia **network pentesting** dan **cyber security**.

Aplikasi ini mencakup penjelasan mendalam tentang:
- TCP vs UDP dan TCP handshake
- DNS records dan subdomain enumeration
- HTTP/HTTPS methods, status codes, dan headers
- Subnetting, CIDR, dan routing
- Proxy, VPN, dan pivoting techniques

Setiap topik dilengkapi dengan **visualisasi interaktif**, **contoh praktis**, dan **command line examples** yang relevan untuk pentesting.

## Fitur

- **Dark Theme Modern** - Desain gelap yang nyaman untuk mata
- **Responsive Design** - Tampil sempurna di desktop, tablet, dan mobile
- **Animasi Interaktif** - Visualisasi TCP handshake yang bisa dijalankan
- **Subnet Calculator** - Tool untuk menghitung network details secara real-time
- **Tab Navigation** - Navigasi smooth antar topik
- **Code Blocks** - Contoh command dengan syntax yang jelas
- **Comparison Tables** - Perbandingan fitur yang mudah dipahami
- **Zero Dependencies** - Tidak butuh framework atau library eksternal

## Topik yang Dibahas

### 1. TCP vs UDP
- Perbandingan lengkap TCP dan UDP
- **Visualisasi TCP Three-Way Handshake** (SYN -> SYN-ACK -> ACK)
- Hubungan dengan port scanning (SYN Scan, Connect Scan, UDP Scan)
- Contoh command Nmap

### 2. DNS (Domain Name System)
- Jenis DNS Records: A, CNAME, MX, TXT, NS
- Contoh query dengan `dig` dan `nslookup`
- Teknik subdomain enumeration
- Tools: subfinder, amass

### 3. HTTP/HTTPS
- Request Methods (GET, POST, PUT, DELETE, PATCH, HEAD, OPTIONS)
- Status Codes (2xx, 3xx, 4xx, 5xx) dengan color coding
- HTTP Headers (Request & Response)
- Cookie & Session management
- HTTPS & TLS handshake

### 4. Subnetting & Routing
- CIDR Notation (/8, /16, /24, /28, /30, /32)
- **Subnet Calculator** interaktif
- Gateway & Router configuration
- NAT (Static, Dynamic, PAT)
- Pentingnya untuk network pentesting

### 5. Proxy & VPN
- Jenis Proxy (HTTP, SOCKS, Transparent, Reverse)
- VPN Protocols (OpenVPN, WireGuard, IPSec, L2TP, SSTP)
- Traffic routing visualization
- Pivoting techniques (SSH tunneling, Chisel, proxychains)
- Perbandingan Proxy vs VPN

## Cara Menjalankan

### Metode 1: Langsung di Browser
```bash
# Clone repository
git clone https://github.com/floryid/networking-fundamentals.git

# Masuk ke directory
cd networking-fundamentals

# Buka file di browser
# Windows:
start index.html

# macOS:
open index.html

# Linux:
xdg-open index.html
```

### Metode 2: Live Server (VS Code)
1. Install extension **Live Server** di VS Code
2. Klik kanan pada `index.html`
3. Pilih **"Open with Live Server"**

### Metode 3: Python HTTP Server
```bash
# Python 3
python -m http.server 8000

# Buka browser ke http://localhost:8000
```

### Metode 4: Node.js
```bash
npx serve
```

## Deploy ke GitHub Pages

### Langkah 1: Buat Repository di GitHub
1. Login ke [GitHub](https://github.com)
2. Klik tombol **"New"** untuk membuat repository baru
3. Isi nama repository, misalnya: `networking-fundamentals`
4. Pilih **Public** (wajib untuk GitHub Pages free)
5. Klik **"Create repository"**

### Langkah 2: Push Code ke GitHub
```bash
# Inisialisasi git (jika belum)
git init

# Tambahkan semua file
git add .

# Commit perubahan
git commit -m "Initial commit: Networking Fundamentals App"

# Tambahkan remote repository
git branch -M main
git remote add origin https://github.com/floryid/networking-fundamentals.git

# Push ke GitHub
git push -u origin main
```

### Langkah 3: Aktifkan GitHub Pages
1. Buka repository di GitHub
2. Klik **Settings** -> **Pages**
3. Pada bagian **"Source"**, pilih:
   - **Branch**: `main`
   - **Folder**: `/ (root)`
4. Klik **Save**
5. Tunggu beberapa menit, aplikasi akan tersedia di:
   ```
   https://floryid.github.io/networking-fundamentals/
   ```

### Alternatif: Deploy dengan GitHub Actions

Buat file `.github/workflows/deploy.yml`:

```yaml
name: Deploy to GitHub Pages

on:
  push:
    branches: ["main"]

permissions:
  contents: read
  pages: write
  id-token: write

jobs:
  deploy:
    runs-on: ubuntu-latest
    environment:
      name: github-pages
      url: ${{ steps.deployment.outputs.page_url }}
    steps:
      - uses: actions/checkout@v4
      
      - name: Setup Pages
        uses: actions/configure-pages@v4
        
      - name: Upload artifact
        uses: actions/upload-pages-artifact@v3
        with:
          path: '.'
          
      - name: Deploy to GitHub Pages
        id: deployment
        uses: actions/deploy-pages@v4
```

## Struktur Project

```
networking-fundamentals/
|-- .github/
|   +-- workflows/
|       +-- deploy.yml          # GitHub Actions workflow
|-- index.html                   # Aplikasi utama
|-- README.md                    # Dokumentasi
|-- LICENSE                      # Lisensi MIT
+-- .gitignore                   # Git ignore rules
```

## Tech Stack

- **HTML5** - Struktur halaman
- **CSS3** - Styling dengan Flexbox, Grid, dan Animations
- **JavaScript (Vanilla)** - Interaktivitas dan logic
- **No Framework** - Pure web technologies
- **No Build Tools** - Langsung bisa dijalankan

## Kontribusi

Kontribusi sangat diterima! Jika Anda ingin berkontribusi:

1. **Fork** repository ini
2. Buat branch fitur baru: `git checkout -b feature/AmazingFeature`
3. **Commit** perubahan: `git commit -m 'Add some AmazingFeature'`
4. **Push** ke branch: `git push origin feature/AmazingFeature`
5. Buat **Pull Request**

### Ide Pengembangan

- [ ] Tambah quiz interaktif untuk menguji pemahaman
- [ ] Implementasi dark/light mode toggle
- [ ] Tambah topik: Firewall, IDS/IPS, SIEM
- [ ] Tambah simulasi packet sniffing
- [ ] Multi-language support (English, Indonesia)
- [ ] Export catatan ke PDF
- [ ] Tambah video tutorial embedded

## Lisensi

Project ini dilisensikan di bawah **MIT License** - lihat file [LICENSE](LICENSE) untuk detail.

## Acknowledgments

- [MDN Web Docs](https://developer.mozilla.org/) - Referensi web technologies
- [OWASP](https://owasp.org/) - Security guidelines
- [Nmap Documentation](https://nmap.org/book/man.html) - Network scanning reference
- [RFC Documents](https://www.rfc-editor.org/) - Internet standards

## Kontak

Jika ada pertanyaan atau saran, silakan:
- Buka **Issue** di repository ini
- Hubungi melalui email: your-email@example.com

## Disclaimer

Aplikasi ini dibuat untuk **tujuan edukasi**. Semua informasi tentang pentesting, scanning, dan security testing harus digunakan secara **legal dan etis**, hanya pada sistem yang Anda miliki atau memiliki izin tertulis untuk mengujinya.

**Selalu dapatkan izin sebelum melakukan testing pada sistem orang lain!**

---

<div align="center">

**Dibuat dengan hati untuk komunitas cyber security Indonesia**

Jika project ini bermanfaat, jangan lupa untuk memberikan star!

</div>
