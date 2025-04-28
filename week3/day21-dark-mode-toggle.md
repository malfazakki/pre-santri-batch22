# Hari 21: Mini Project 2 - Dark Mode Toggle

## Tujuan Project
- Membuat fitur dark mode yang bisa diaktifkan/nonaktifkan
- Menerapkan perubahan tema menggunakan CSS variables
- Menyimpan preferensi tema di localStorage
- Membuat transisi yang smooth saat pergantian tema
- Menerapkan dark mode pada berbagai komponen UI

## 1. Implementasi Dasar

### Contoh 1: Simple Dark Mode Toggle
```html
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Simple Dark Mode</title>
    <style>
        /* CSS Variables untuk tema */
        :root {
            --background-color: #ffffff;
            --text-color: #333333;
            --card-background: #f0f0f0;
        }

        /* Dark theme colors */
        [data-theme="dark"] {
            --background-color: #333333;
            --text-color: #ffffff;
            --card-background: #444444;
        }

        /* Transisi smooth */
        body {
            transition: background-color 0.3s, color 0.3s;
            background-color: var(--background-color);
            color: var(--text-color);
            min-height: 100vh;
            margin: 0;
            padding: 20px;
            font-family: Arial, sans-serif;
        }

        /* Toggle button style */
        .theme-toggle {
            background-color: var(--text-color);
            color: var(--background-color);
            border: none;
            padding: 10px 20px;
            border-radius: 5px;
            cursor: pointer;
            position: fixed;
            top: 20px;
            right: 20px;
        }

        /* Content styles */
        .card {
            background-color: var(--card-background);
            padding: 20px;
            border-radius: 8px;
            margin: 20px 0;
        }
    </style>
</head>
<body>
    <button class="theme-toggle" onclick="toggleTheme()">Toggle Theme</button>

    <h1>Dark Mode Demo</h1>
    
    <div class="card">
        <h2>Card Title</h2>
        <p>This is a sample card that will change appearance in dark mode.</p>
    </div>

    <script>
        // Check for saved theme preference
        const savedTheme = localStorage.getItem('theme') || 'light';
        document.documentElement.setAttribute('data-theme', savedTheme);

        function toggleTheme() {
            const currentTheme = document.documentElement.getAttribute('data-theme');
            const newTheme = currentTheme === 'dark' ? 'light' : 'dark';
            
            document.documentElement.setAttribute('data-theme', newTheme);
            localStorage.setItem('theme', newTheme);
        }
    </script>
</body>
</html>
```

## 2. Advanced Dark Mode Implementation

### Complete Website with Dark Mode
```html
<!DOCTYPE html>
<html lang="id" data-theme="light">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Advanced Dark Mode</title>
    <style>
        /* CSS Variables */
        :root {
            /* Light theme */
            --primary-color: #4CAF50;
            --background-color: #ffffff;
            --text-color: #333333;
            --card-background: #f0f0f0;
            --border-color: #dddddd;
            --shadow-color: rgba(0, 0, 0, 0.1);
            --header-background: #f8f8f8;
        }

        [data-theme="dark"] {
            /* Dark theme */
            --primary-color: #66bb6a;
            --background-color: #1a1a1a;
            --text-color: #ffffff;
            --card-background: #2d2d2d;
            --border-color: #404040;
            --shadow-color: rgba(0, 0, 0, 0.3);
            --header-background: #2d2d2d;
        }

        /* Global styles */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            transition: background-color 0.3s, color 0.3s, border-color 0.3s;
        }

        body {
            background-color: var(--background-color);
            color: var(--text-color);
            font-family: Arial, sans-serif;
            line-height: 1.6;
        }

        /* Header styles */
        header {
            background-color: var(--header-background);
            padding: 1rem;
            box-shadow: 0 2px 5px var(--shadow-color);
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
        }

        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
            max-width: 1200px;
            margin: 0 auto;
        }

        .logo {
            font-size: 1.5rem;
            font-weight: bold;
            color: var(--primary-color);
        }

        /* Theme toggle button */
        .theme-toggle {
            background-color: var(--primary-color);
            color: white;
            border: none;
            padding: 8px 16px;
            border-radius: 20px;
            cursor: pointer;
            display: flex;
            align-items: center;
            gap: 8px;
        }

        .theme-toggle:hover {
            opacity: 0.9;
        }

        /* Main content */
        main {
            max-width: 1200px;
            margin: 80px auto 0;
            padding: 20px;
        }

        /* Card styles */
        .card {
            background-color: var(--card-background);
            border-radius: 8px;
            padding: 20px;
            margin: 20px 0;
            box-shadow: 0 2px 5px var(--shadow-color);
        }

        .card h2 {
            color: var(--primary-color);
            margin-bottom: 10px;
        }

        /* Form styles */
        .form-group {
            margin-bottom: 15px;
        }

        label {
            display: block;
            margin-bottom: 5px;
        }

        input, textarea {
            width: 100%;
            padding: 8px;
            border: 1px solid var(--border-color);
            border-radius: 4px;
            background-color: var(--background-color);
            color: var(--text-color);
        }

        /* Button styles */
        .btn {
            background-color: var(--primary-color);
            color: white;
            padding: 10px 20px;
            border: none;
            border-radius: 4px;
            cursor: pointer;
        }

        .btn:hover {
            opacity: 0.9;
        }

        /* Footer styles */
        footer {
            background-color: var(--header-background);
            color: var(--text-color);
            text-align: center;
            padding: 20px;
            margin-top: 40px;
        }
    </style>
</head>
<body>
    <header>
        <nav>
            <div class="logo">MyWebsite</div>
            <button class="theme-toggle" onclick="toggleTheme()">
                <span id="theme-icon">🌞</span>
                <span id="theme-text">Toggle Theme</span>
            </button>
        </nav>
    </header>

    <main>
        <div class="card">
            <h2>Welcome</h2>
            <p>This is a complete website example with dark mode support.</p>
        </div>

        <div class="card">
            <h2>Features</h2>
            <ul>
                <li>Smooth theme transition</li>
                <li>Persistent theme preference</li>
                <li>Responsive design</li>
                <li>Consistent styling across components</li>
            </ul>
        </div>

        <div class="card">
            <h2>Contact Form</h2>
            <form>
                <div class="form-group">
                    <label for="name">Name:</label>
                    <input type="text" id="name" name="name">
                </div>
                <div class="form-group">
                    <label for="email">Email:</label>
                    <input type="email" id="email" name="email">
                </div>
                <div class="form-group">
                    <label for="message">Message:</label>
                    <textarea id="message" name="message" rows="4"></textarea>
                </div>
                <button type="submit" class="btn">Send Message</button>
            </form>
        </div>
    </main>

    <footer>
        <p>&copy; 2023 MyWebsite. All rights reserved.</p>
    </footer>

    <script>
        // Theme management
        function loadTheme() {
            const savedTheme = localStorage.getItem('theme') || 'light';
            document.documentElement.setAttribute('data-theme', savedTheme);
            updateThemeIcon(savedTheme);
        }

        function toggleTheme() {
            const currentTheme = document.documentElement.getAttribute('data-theme');
            const newTheme = currentTheme === 'dark' ? 'light' : 'dark';
            
            document.documentElement.setAttribute('data-theme', newTheme);
            localStorage.setItem('theme', newTheme);
            updateThemeIcon(newTheme);
        }

        function updateThemeIcon(theme) {
            const icon = document.getElementById('theme-icon');
            const text = document.getElementById('theme-text');
            
            if (theme === 'dark') {
                icon.textContent = '🌜';
                text.textContent = 'Light Mode';
            } else {
                icon.textContent = '🌞';
                text.textContent = 'Dark Mode';
            }
        }

        // Check system preference
        function checkSystemThemePreference() {
            if (window.matchMedia && window.matchMedia('(prefers-color-scheme: dark)').matches) {
                return 'dark';
            }
            return 'light';
        }

        // Initialize theme
        if (!localStorage.getItem('theme')) {
            localStorage.setItem('theme', checkSystemThemePreference());
        }
        loadTheme();

        // Listen for system theme changes
        window.matchMedia('(prefers-color-scheme: dark)').addEventListener('change', e => {
            if (!localStorage.getItem('theme')) {
                document.documentElement.setAttribute('data-theme', e.matches ? 'dark' : 'light');
                updateThemeIcon(e.matches ? 'dark' : 'light');
            }
        });
    </script>
</body>
</html>
```

## 3. Additional Features

### System Theme Detection
```javascript
// Check system theme preference
function getSystemTheme() {
    if (window.matchMedia && window.matchMedia('(prefers-color-scheme: dark)').matches) {
        return 'dark';
    }
    return 'light';
}

// Listen for system theme changes
window.matchMedia('(prefers-color-scheme: dark)').addEventListener('change', e => {
    const newTheme = e.matches ? 'dark' : 'light';
    // Update theme if user hasn't set a preference
    if (!localStorage.getItem('theme')) {
        document.documentElement.setAttribute('data-theme', newTheme);
    }
});
```

### Theme Toggle with Animation
```css
/* Add to your CSS */
.theme-transition {
    transition: all 0.3s ease-in-out;
}

.theme-toggle-icon {
    display: inline-block;
    transition: transform 0.3s ease;
}

.theme-toggle-icon.rotate {
    transform: rotate(360deg);
}
```

```javascript
function toggleThemeWithAnimation() {
    const icon = document.querySelector('.theme-toggle-icon');
    icon.classList.add('rotate');
    
    setTimeout(() => {
        toggleTheme();
        icon.classList.remove('rotate');
    }, 300);
}
```

### Theme Switcher with Multiple Themes
```javascript
const themes = {
    light: {
        '--background-color': '#ffffff',
        '--text-color': '#333333',
        '--primary-color': '#4CAF50'
    },
    dark: {
        '--background-color': '#333333',
        '--text-color': '#ffffff',
        '--primary-color': '#66bb6a'
    },
    sepia: {
        '--background-color': '#f4ecd8',
        '--text-color': '#5c4b37',
        '--primary-color': '#8b7355'
    }
};

function applyTheme(themeName) {
    const theme = themes[themeName];
    Object.keys(theme).forEach(property => {
        document.documentElement.style.setProperty(property, theme[property]);
    });
    localStorage.setItem('theme', themeName);
}
```

## 4. Best Practices

1. **Use CSS Variables**
```css
:root {
    /* Define all theme variables here */
    --primary-color: #4CAF50;
    --background-color: #ffffff;
    /* etc... */
}
```

2. **Smooth Transitions**
```css
* {
    transition: background-color 0.3s, color 0.3s;
}
```

3. **Persist User Preferences**
```javascript
// Save theme preference
localStorage.setItem('theme', theme);

// Load theme preference
const savedTheme = localStorage.getItem('theme');
```

4. **Respect System Preferences**
```css
@media (prefers-color-scheme: dark) {
    :root {
        /* Dark theme variables */
    }
}
```

5. **Accessible Toggle Button**
```html
<button 
    class="theme-toggle" 
    onclick="toggleTheme()"
    aria-label="Toggle dark mode"
    title="Toggle dark mode">
    <span class="theme-toggle-icon">🌓</span>
</button>
```

## 5. Latihan Mandiri

### Latihan 1: Custom Theme Builder
Buat sistem yang memungkinkan user membuat dan menyimpan tema kustom mereka sendiri.

### Latihan 2: Theme Scheduler
Buat fitur yang mengubah tema secara otomatis berdasarkan waktu (light di siang hari, dark di malam hari).

### Latihan 3: Theme Transitions
Buat berbagai efek transisi saat pergantian tema (fade, slide, rotate, etc.).

## Kesimpulan
- Dark mode adalah fitur penting untuk aksesibilitas dan kenyamanan user
- CSS variables memudahkan implementasi multiple themes
- Penting untuk menyimpan preferensi user
- Transisi smooth membuat pengalaman user lebih baik
- Perhatikan aksesibilitas dalam implementasi

## Referensi Tambahan
- [MDN Web Docs - Prefers Color Scheme](https://developer.mozilla.org/en-US/docs/Web/CSS/@media/prefers-color-scheme)
- [CSS-Tricks - A Complete Guide to Dark Mode](https://css-tricks.com/a-complete-guide-to-dark-mode-on-the-web/)
- [Web.dev - Dark Mode](https://web.dev/prefers-color-scheme/)
- [Smashing Magazine - Dark Mode Implementation](https://www.smashingmagazine.com/2020/10/dark-mode-css-js/)