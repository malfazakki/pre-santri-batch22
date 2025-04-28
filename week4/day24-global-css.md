# Hari 24: Styling CSS Global & Mobile First

## Tujuan Pembelajaran
- Memahami pendekatan mobile-first design
- Membuat CSS global yang konsisten
- Mengimplementasikan responsive design
- Membuat sistem komponen yang reusable
- Menerapkan CSS variables untuk konsistensi

## 1. CSS Global Setup

### Reset dan Variables
```css
/* reset.css */
*, *::before, *::after {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

/* variables.css */
:root {
    /* Colors */
    --primary-color: #4CAF50;
    --secondary-color: #2196F3;
    --text-color: #333333;
    --light-text: #ffffff;
    --background-color: #ffffff;
    --light-gray: #f5f5f5;
    --dark-gray: #666666;
    --border-color: #dddddd;

    /* Typography */
    --font-primary: 'Open Sans', sans-serif;
    --font-heading: 'Playfair Display', serif;
    --font-size-base: 16px;
    --line-height-base: 1.5;

    /* Spacing */
    --spacing-xs: 0.25rem;
    --spacing-sm: 0.5rem;
    --spacing-md: 1rem;
    --spacing-lg: 2rem;
    --spacing-xl: 4rem;

    /* Border Radius */
    --border-radius-sm: 4px;
    --border-radius-md: 8px;
    --border-radius-lg: 16px;

    /* Box Shadow */
    --shadow-sm: 0 2px 4px rgba(0,0,0,0.1);
    --shadow-md: 0 4px 6px rgba(0,0,0,0.1);
    --shadow-lg: 0 10px 15px rgba(0,0,0,0.1);

    /* Container */
    --container-padding: 20px;
    --container-max-width: 1200px;
}
```

### Base Styles
```css
/* base.css */
html {
    font-size: var(--font-size-base);
    line-height: var(--line-height-base);
}

body {
    font-family: var(--font-primary);
    color: var(--text-color);
    background-color: var(--background-color);
}

h1, h2, h3, h4, h5, h6 {
    font-family: var(--font-heading);
    margin-bottom: var(--spacing-md);
}

p {
    margin-bottom: var(--spacing-md);
}

a {
    color: var(--primary-color);
    text-decoration: none;
    transition: color 0.3s ease;
}

a:hover {
    color: darken(var(--primary-color), 10%);
}

img {
    max-width: 100%;
    height: auto;
}

.container {
    width: 100%;
    padding: 0 var(--container-padding);
    margin: 0 auto;
    max-width: var(--container-max-width);
}
```

## 2. Mobile-First Components

### Button Component
```css
/* components/button.css */
.btn {
    display: inline-block;
    padding: var(--spacing-sm) var(--spacing-md);
    border-radius: var(--border-radius-sm);
    font-weight: 600;
    text-align: center;
    cursor: pointer;
    transition: all 0.3s ease;
    border: none;
}

.btn-primary {
    background-color: var(--primary-color);
    color: var(--light-text);
}

.btn-secondary {
    background-color: var(--secondary-color);
    color: var(--light-text);
}

.btn-outline {
    background-color: transparent;
    border: 2px solid var(--primary-color);
    color: var(--primary-color);
}

/* Mobile-first responsive adjustments */
@media (min-width: 768px) {
    .btn {
        padding: var(--spacing-md) var(--spacing-lg);
    }
}
```

### Card Component
```css
/* components/card.css */
.card {
    background-color: var(--background-color);
    border-radius: var(--border-radius-md);
    box-shadow: var(--shadow-sm);
    padding: var(--spacing-md);
    margin-bottom: var(--spacing-md);
}

.card-image {
    width: 100%;
    border-radius: var(--border-radius-sm);
    margin-bottom: var(--spacing-md);
}

.card-title {
    font-size: 1.25rem;
    margin-bottom: var(--spacing-sm);
}

.card-text {
    color: var(--dark-gray);
    margin-bottom: var(--spacing-md);
}

/* Mobile-first grid */
.card-grid {
    display: grid;
    gap: var(--spacing-md);
    grid-template-columns: 1fr;
}

@media (min-width: 768px) {
    .card-grid {
        grid-template-columns: repeat(2, 1fr);
    }
}

@media (min-width: 992px) {
    .card-grid {
        grid-template-columns: repeat(3, 1fr);
    }
}
```

### Navigation Component
```css
/* components/navigation.css */
.navbar {
    padding: var(--spacing-md) 0;
    background-color: var(--background-color);
    box-shadow: var(--shadow-sm);
}

.nav-container {
    display: flex;
    justify-content: space-between;
    align-items: center;
}

.logo {
    font-size: 1.5rem;
    font-weight: bold;
}

.nav-menu {
    display: none; /* Hidden on mobile by default */
}

.nav-toggle {
    display: block; /* Shown on mobile */
    background: none;
    border: none;
    cursor: pointer;
}

/* Mobile menu when active */
.nav-menu.active {
    display: block;
    position: absolute;
    top: 100%;
    left: 0;
    right: 0;
    background-color: var(--background-color);
    padding: var(--spacing-md);
    box-shadow: var(--shadow-sm);
}

.nav-menu.active .nav-item {
    display: block;
    margin: var(--spacing-sm) 0;
}

/* Desktop styles */
@media (min-width: 768px) {
    .nav-toggle {
        display: none;
    }

    .nav-menu {
        display: flex;
        gap: var(--spacing-md);
    }

    .nav-item {
        display: inline-block;
    }
}
```

## 3. Layout Systems

### Grid System
```css
/* layout/grid.css */
.grid {
    display: grid;
    gap: var(--spacing-md);
}

/* Mobile-first grid columns */
.col-1 { grid-template-columns: 1fr; }
.col-2 { grid-template-columns: repeat(2, 1fr); }

/* Responsive grid adjustments */
@media (min-width: 768px) {
    .md\:col-2 { grid-template-columns: repeat(2, 1fr); }
    .md\:col-3 { grid-template-columns: repeat(3, 1fr); }
    .md\:col-4 { grid-template-columns: repeat(4, 1fr); }
}

@media (min-width: 992px) {
    .lg\:col-3 { grid-template-columns: repeat(3, 1fr); }
    .lg\:col-4 { grid-template-columns: repeat(4, 1fr); }
    .lg\:col-5 { grid-template-columns: repeat(5, 1fr); }
}
```

### Flexbox Utilities
```css
/* layout/flex.css */
.flex {
    display: flex;
}

.flex-col {
    flex-direction: column;
}

.items-center {
    align-items: center;
}

.justify-between {
    justify-content: space-between;
}

.gap-sm { gap: var(--spacing-sm); }
.gap-md { gap: var(--spacing-md); }
.gap-lg { gap: var(--spacing-lg); }

/* Responsive flex direction */
@media (min-width: 768px) {
    .md\:flex-row {
        flex-direction: row;
    }
}
```

## 4. Utility Classes

### Spacing Utilities
```css
/* utilities/spacing.css */
.m-0 { margin: 0; }
.m-1 { margin: var(--spacing-sm); }
.m-2 { margin: var(--spacing-md); }
.m-3 { margin: var(--spacing-lg); }

.p-0 { padding: 0; }
.p-1 { padding: var(--spacing-sm); }
.p-2 { padding: var(--spacing-md); }
.p-3 { padding: var(--spacing-lg); }

/* Directional spacing */
.mt-1 { margin-top: var(--spacing-sm); }
.mb-1 { margin-bottom: var(--spacing-sm); }
.my-1 { 
    margin-top: var(--spacing-sm);
    margin-bottom: var(--spacing-sm);
}

/* Responsive spacing */
@media (min-width: 768px) {
    .md\:m-2 { margin: var(--spacing-md); }
    .md\:p-2 { padding: var(--spacing-md); }
}
```

### Typography Utilities
```css
/* utilities/typography.css */
.text-center { text-align: center; }
.text-left { text-align: left; }
.text-right { text-align: right; }

.text-sm { font-size: 0.875rem; }
.text-base { font-size: 1rem; }
.text-lg { font-size: 1.125rem; }
.text-xl { font-size: 1.25rem; }

.font-bold { font-weight: 700; }
.font-medium { font-weight: 500; }
.font-normal { font-weight: 400; }

/* Responsive text alignment */
@media (min-width: 768px) {
    .md\:text-left { text-align: left; }
    .md\:text-center { text-align: center; }
}
```

## 5. Responsive Images

```css
/* components/images.css */
.img-responsive {
    max-width: 100%;
    height: auto;
}

.img-cover {
    width: 100%;
    height: 100%;
    object-fit: cover;
}

.img-contain {
    width: 100%;
    height: 100%;
    object-fit: contain;
}

/* Image aspect ratios */
.aspect-square {
    aspect-ratio: 1/1;
}

.aspect-video {
    aspect-ratio: 16/9;
}

/* Responsive image containers */
.img-container {
    position: relative;
    width: 100%;
    overflow: hidden;
}

@media (min-width: 768px) {
    .img-container {
        border-radius: var(--border-radius-md);
    }
}
```

## 6. Forms

```css
/* components/forms.css */
.form-group {
    margin-bottom: var(--spacing-md);
}

.form-label {
    display: block;
    margin-bottom: var(--spacing-sm);
    font-weight: 500;
}

.form-input {
    width: 100%;
    padding: var(--spacing-sm);
    border: 1px solid var(--border-color);
    border-radius: var(--border-radius-sm);
    font-size: 1rem;
    transition: border-color 0.3s ease;
}

.form-input:focus {
    outline: none;
    border-color: var(--primary-color);
}

.form-error {
    color: #dc3545;
    font-size: 0.875rem;
    margin-top: var(--spacing-xs);
}

/* Responsive form layout */
@media (min-width: 768px) {
    .form-grid {
        display: grid;
        grid-template-columns: repeat(2, 1fr);
        gap: var(--spacing-md);
    }
}
```

## 7. Animation Utilities

```css
/* utilities/animations.css */
.fade-in {
    opacity: 0;
    animation: fadeIn 0.3s ease forwards;
}

.slide-up {
    transform: translateY(20px);
    opacity: 0;
    animation: slideUp 0.3s ease forwards;
}

@keyframes fadeIn {
    to {
        opacity: 1;
    }
}

@keyframes slideUp {
    to {
        transform: translateY(0);
        opacity: 1;
    }
}

/* Responsive animations */
@media (prefers-reduced-motion: reduce) {
    .fade-in,
    .slide-up {
        animation: none;
        opacity: 1;
        transform: none;
    }
}
```

## 8. Best Practices

1. **Mobile-First Approach**
```css
/* Start with mobile styles */
.element {
    width: 100%;
}

/* Then add desktop styles */
@media (min-width: 768px) {
    .element {
        width: 50%;
    }
}
```

2. **CSS Organization**
```css
/* Follow a consistent structure */
@import 'reset.css';
@import 'variables.css';
@import 'base.css';
@import 'components/*.css';
@import 'layout/*.css';
@import 'utilities/*.css';
```

3. **Performance Optimization**
```css
/* Use efficient selectors */
.specific-class { } /* Good */
div > p > span { } /* Avoid deep nesting */

/* Minimize repaints */
.element {
    transform: translateZ(0); /* Hardware acceleration */
}
```

## 9. Latihan

### Latihan 1: Component Library
Buat library komponen dasar yang mencakup:
- Buttons
- Cards
- Forms
- Navigation

### Latihan 2: Responsive Layout
Implementasikan layout responsif untuk:
- Header
- Hero section
- Feature grid
- Footer

### Latihan 3: Custom Utilities
Buat utility classes untuk:
- Spacing
- Typography
- Colors
- Flexbox/Grid

## Kesimpulan
- Mobile-first adalah pendekatan yang efektif untuk responsive design
- CSS variables membantu konsistensi styling
- Komponen yang reusable meningkatkan efisiensi development
- Utility classes mempercepat styling

## Referensi Tambahan
- [CSS-Tricks - A Complete Guide to Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)
- [MDN - Using CSS custom properties](https://developer.mozilla.org/en-US/docs/Web/CSS/Using_CSS_custom_properties)
- [Smashing Magazine - Mobile First CSS](https://www.smashingmagazine.com/2018/12/responsive-design-patterns/)
- [Web.dev - CSS Architecture](https://web.dev/learn/css/architecture/)