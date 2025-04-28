# Hari 22: Perencanaan Project - Tema & Ide

## Tujuan Pembelajaran
- Memahami proses perencanaan project website
- Mengembangkan ide dan konsep website
- Menentukan fitur dan fungsionalitas
- Membuat wireframe dasar
- Merencanakan struktur project

## 1. Brainstorming Project

### Jenis Project Website yang Bisa Dibuat
1. **Portfolio Personal**
   - Showcase karya
   - About me
   - Skills & Experience
   - Contact form

2. **Blog Personal**
   - Artikel posts
   - Kategori
   - Search function
   - Comment section

3. **Landing Page Produk/Jasa**
   - Product showcase
   - Features list
   - Pricing
   - Testimonials
   - Call to action

4. **Company Profile**
   - About company
   - Services
   - Team members
   - Client list
   - Contact info

5. **E-commerce Sederhana**
   - Product catalog
   - Shopping cart
   - Product details
   - Order form

## 2. Template Perencanaan Project

### Project Brief
```markdown
# Project Brief

## 1. Informasi Dasar
- Nama Project:
- Tipe Website:
- Target Audience:
- Tujuan Website:

## 2. Fitur Utama
- Fitur 1:
- Fitur 2:
- Fitur 3:
- Fitur 4:

## 3. Halaman yang Dibutuhkan
- Halaman 1:
- Halaman 2:
- Halaman 3:
- Halaman 4:

## 4. Teknologi yang Digunakan
- HTML5
- CSS3
- JavaScript
- [Tools lain]

## 5. Timeline
- Hari 1-2: Setup & struktur
- Hari 3-4: Styling
- Hari 5-6: Interaktivitas
- Hari 7: Testing & finishing
```

### Contoh Project Brief (Portfolio)
```markdown
# Project Brief: Portfolio Website

## 1. Informasi Dasar
- Nama Project: MyPortfolio
- Tipe Website: Personal Portfolio
- Target Audience: Potential employers & clients
- Tujuan Website: Showcase skills & projects

## 2. Fitur Utama
- Responsive design
- Project showcase with filters
- Interactive contact form
- Dark mode toggle
- Smooth scroll navigation

## 3. Halaman yang Dibutuhkan
- Home (Hero section)
- About Me
- Projects
- Skills
- Contact

## 4. Teknologi yang Digunakan
- HTML5
- CSS3 (Flexbox/Grid)
- JavaScript (Vanilla)
- Font Awesome icons
- Google Fonts

## 5. Timeline
- Hari 1: Setup & HTML structure
- Hari 2: Basic CSS styling
- Hari 3: Responsive design
- Hari 4: JavaScript functionality
- Hari 5: Content & testing
- Hari 6: Bug fixes & optimization
- Hari 7: Final testing & deployment
```

## 3. Wireframing

### Basic Wireframe Template
```html
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Wireframe Template</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }

        .wireframe-box {
            background-color: #f0f0f0;
            border: 2px dashed #999;
            padding: 20px;
            margin: 10px 0;
            min-height: 100px;
            display: flex;
            justify-content: center;
            align-items: center;
            font-family: Arial, sans-serif;
            color: #666;
        }

        .header {
            height: 80px;
        }

        .nav {
            height: 60px;
        }

        .hero {
            height: 400px;
        }

        .content {
            min-height: 300px;
        }

        .footer {
            height: 200px;
        }

        .grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="wireframe-box header">Header</div>
        <div class="wireframe-box nav">Navigation</div>
        <div class="wireframe-box hero">Hero Section</div>
        
        <div class="grid">
            <div class="wireframe-box">Content Box 1</div>
            <div class="wireframe-box">Content Box 2</div>
            <div class="wireframe-box">Content Box 3</div>
        </div>
        
        <div class="wireframe-box content">Main Content</div>
        <div class="wireframe-box footer">Footer</div>
    </div>
</body>
</html>
```

## 4. Struktur Project

### Recommended Project Structure
```plaintext
project-name/
├── index.html
├── about.html
├── contact.html
├── css/
│   ├── style.css
│   ├── responsive.css
│   └── components/
│       ├── header.css
│       ├── footer.css
│       └── forms.css
├── js/
│   ├── main.js
│   └── components/
│       ├── slider.js
│       └── form-validation.js
├── images/
│   ├── logo.png
│   └── assets/
└── fonts/
```

### Project Checklist
```markdown
# Project Checklist

## Setup
- [ ] Create project directory
- [ ] Initialize Git repository
- [ ] Create basic file structure
- [ ] Setup CSS reset/normalize

## Design
- [ ] Create wireframes
- [ ] Choose color palette
- [ ] Select typography
- [ ] Design logo/branding

## Development
- [ ] Create HTML structure
- [ ] Implement responsive design
- [ ] Add JavaScript functionality
- [ ] Optimize images

## Testing
- [ ] Cross-browser testing
- [ ] Mobile responsiveness
- [ ] Form validation
- [ ] Performance optimization

## Launch
- [ ] Final review
- [ ] Documentation
- [ ] Deployment
```

## 5. Tools dan Resources

### Design Tools
- Figma (UI Design)
- Adobe XD (UI Design)
- Balsamiq (Wireframing)
- Coolors.co (Color Palette)
- Google Fonts (Typography)

### Development Tools
- Visual Studio Code
- Git
- Chrome DevTools
- Live Server
- W3C Validator

### Resources
- Unsplash (Free Images)
- Font Awesome (Icons)
- MDN Web Docs (Documentation)
- CSS-Tricks (Tutorials)
- GitHub (Version Control)

## 6. Contoh Project Ideas

### 1. Portfolio Photographer
```markdown
## Features
- Image gallery with filter
- Lightbox view
- Contact booking form
- Instagram feed integration
- Client testimonials
```

### 2. Restaurant Website
```markdown
## Features
- Menu display
- Table reservation
- Location map
- Opening hours
- Special offers slider
```

### 3. Fitness Trainer Portfolio
```markdown
## Features
- Training programs
- Transformation gallery
- Booking system
- Nutrition tips blog
- Newsletter signup
```

## 7. Latihan Perencanaan

### Latihan 1: Project Brief
Buat project brief lengkap untuk website yang akan Anda buat, termasuk:
- Deskripsi project
- Target audience
- Fitur-fitur
- Timeline

### Latihan 2: Wireframe
Buat wireframe untuk minimal 3 halaman utama website Anda:
- Homepage
- About/Services
- Contact

### Latihan 3: Content Planning
Buat daftar konten yang dibutuhkan:
- Teks
- Gambar
- Video
- Icons

## Kesimpulan
- Perencanaan yang baik adalah kunci kesuksesan project
- Wireframing membantu visualisasi sebelum coding
- Struktur project yang terorganisir memudahkan development
- Dokumentasi penting untuk tracking progress
- Testing harus direncanakan dari awal

## Referensi Tambahan
- [Smashing Magazine - Project Planning](https://www.smashingmagazine.com/2018/02/comprehensive-website-planning-guide/)
- [Web.dev - Planning Guide](https://web.dev/planning-for-performance/)
- [UX Pin - Wireframing Guide](https://www.uxpin.com/studio/blog/website-wireframe-design-guide/)
- [Dribbble - Design Inspiration](https://dribbble.com/)