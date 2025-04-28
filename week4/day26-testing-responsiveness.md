# Hari 26: Testing Responsiveness + Interaksi

## Tujuan Pembelajaran
- Memahami cara testing responsiveness website
- Menguji interaksi user di berbagai device
- Menggunakan tools untuk testing
- Mengidentifikasi dan memperbaiki masalah responsif
- Memastikan konsistensi cross-browser

## 1. Testing Tools dan Metode

### Browser Developer Tools
```javascript
// Chrome DevTools Shortcuts
// Windows/Linux: Ctrl + Shift + I
// macOS: Cmd + Option + I

// Toggle Device Toolbar
// Windows/Linux: Ctrl + Shift + M
// macOS: Cmd + Option + M

// Common Device Dimensions
const commonDevices = {
    iPhone12: {
        width: 390,
        height: 844
    },
    iPadAir: {
        width: 820,
        height: 1180
    },
    SamsungGalaxyS20: {
        width: 360,
        height: 800
    }
};
```

### Responsive Testing Checklist
```markdown
## Visual Testing
- [ ] Layout integrity at all breakpoints
- [ ] Image scaling and aspect ratios
- [ ] Typography readability
- [ ] Navigation functionality
- [ ] Button and form element sizes
- [ ] Spacing and margins
- [ ] Content alignment

## Functional Testing
- [ ] Navigation menu (hamburger menu)
- [ ] Form submissions
- [ ] Interactive elements (buttons, links)
- [ ] Sliders and carousels
- [ ] Modal windows
- [ ] Dropdown menus
- [ ] Touch interactions

## Performance Testing
- [ ] Page load time
- [ ] Image loading
- [ ] Animation smoothness
- [ ] Scrolling performance
- [ ] Form responsiveness
```

## 2. Common Breakpoint Testing

### Breakpoint Test Template
```html
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Breakpoint Tester</title>
    <style>
        /* Breakpoint indicator */
        body::after {
            position: fixed;
            bottom: 0;
            right: 0;
            padding: 10px;
            background: #333;
            color: white;
            font-size: 14px;
            z-index: 9999;
        }

        /* Mobile */
        @media (max-width: 576px) {
            body::after {
                content: 'Mobile (<576px)';
                background: #dc3545;
            }
        }

        /* Tablet */
        @media (min-width: 577px) and (max-width: 768px) {
            body::after {
                content: 'Tablet (577px-768px)';
                background: #ffc107;
            }
        }

        /* Desktop */
        @media (min-width: 769px) and (max-width: 992px) {
            body::after {
                content: 'Desktop (769px-992px)';
                background: #28a745;
            }
        }

        /* Large Desktop */
        @media (min-width: 993px) {
            body::after {
                content: 'Large Desktop (>992px)';
                background: #007bff;
            }
        }

        /* Test grid */
        .grid-test {
            display: grid;
            gap: 20px;
            padding: 20px;
        }

        @media (min-width: 576px) {
            .grid-test {
                grid-template-columns: repeat(2, 1fr);
            }
        }

        @media (min-width: 768px) {
            .grid-test {
                grid-template-columns: repeat(3, 1fr);
            }
        }

        @media (min-width: 992px) {
            .grid-test {
                grid-template-columns: repeat(4, 1fr);
            }
        }

        .grid-item {
            background: #f0f0f0;
            padding: 20px;
            text-align: center;
            border-radius: 8px;
        }
    </style>
</head>
<body>
    <div class="grid-test">
        <div class="grid-item">Item 1</div>
        <div class="grid-item">Item 2</div>
        <div class="grid-item">Item 3</div>
        <div class="grid-item">Item 4</div>
        <div class="grid-item">Item 5</div>
        <div class="grid-item">Item 6</div>
        <div class="grid-item">Item 7</div>
        <div class="grid-item">Item 8</div>
    </div>

    <script>
        // Display current viewport size
        function showViewportSize() {
            const size = document.createElement('div');
            size.style.position = 'fixed';
            size.style.top = '0';
            size.style.left = '0';
            size.style.background = '#333';
            size.style.color = 'white';
            size.style.padding = '10px';
            size.style.fontSize = '14px';
            size.style.zIndex = '9999';
            
            function updateSize() {
                size.textContent = `Viewport: ${window.innerWidth}px × ${window.innerHeight}px`;
            }
            
            updateSize();
            window.addEventListener('resize', updateSize);
            document.body.appendChild(size);
        }

        showViewportSize();
    </script>
</body>
</html>
```

## 3. Interaction Testing

### Touch Event Testing
```javascript
// Touch Event Test Script
function testTouchEvents(elementId) {
    const element = document.getElementById(elementId);
    const log = document.createElement('div');
    log.style.padding = '10px';
    document.body.appendChild(log);

    const events = ['touchstart', 'touchmove', 'touchend', 'click'];
    
    events.forEach(eventName => {
        element.addEventListener(eventName, (e) => {
            const entry = document.createElement('div');
            entry.textContent = `${eventName} detected at ${new Date().toLocaleTimeString()}`;
            log.insertBefore(entry, log.firstChild);
            
            if (log.children.length > 5) {
                log.removeChild(log.lastChild);
            }
        });
    });
}
```

### Form Interaction Test
```html
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Form Interaction Test</title>
    <style>
        .form-test {
            max-width: 500px;
            margin: 20px auto;
            padding: 20px;
        }

        .form-group {
            margin-bottom: 15px;
        }

        .form-group label {
            display: block;
            margin-bottom: 5px;
        }

        .form-group input,
        .form-group textarea {
            width: 100%;
            padding: 8px;
            border: 1px solid #ddd;
            border-radius: 4px;
        }

        .interaction-log {
            margin-top: 20px;
            padding: 10px;
            background: #f5f5f5;
            border-radius: 4px;
            max-height: 200px;
            overflow-y: auto;
        }

        .log-entry {
            padding: 5px;
            border-bottom: 1px solid #ddd;
        }

        .log-entry:last-child {
            border-bottom: none;
        }
    </style>
</head>
<body>
    <div class="form-test">
        <form id="testForm">
            <div class="form-group">
                <label for="testInput">Test Input:</label>
                <input type="text" id="testInput" name="testInput">
            </div>
            <div class="form-group">
                <label for="testTextarea">Test Textarea:</label>
                <textarea id="testTextarea" name="testTextarea"></textarea>
            </div>
            <button type="submit">Submit</button>
        </form>
        <div class="interaction-log" id="interactionLog"></div>
    </div>

    <script>
        const form = document.getElementById('testForm');
        const log = document.getElementById('interactionLog');
        const input = document.getElementById('testInput');
        const textarea = document.getElementById('testTextarea');

        function logInteraction(event, details = '') {
            const entry = document.createElement('div');
            entry.className = 'log-entry';
            entry.textContent = `${event} - ${new Date().toLocaleTimeString()} ${details}`;
            log.insertBefore(entry, log.firstChild);
        }

        // Form events
        form.addEventListener('submit', (e) => {
            e.preventDefault();
            logInteraction('Form submitted');
        });

        // Input events
        ['focus', 'blur', 'input', 'change'].forEach(eventName => {
            input.addEventListener(eventName, (e) => {
                logInteraction(`Input ${eventName}`, `Value: ${e.target.value}`);
            });
            
            textarea.addEventListener(eventName, (e) => {
                logInteraction(`Textarea ${eventName}`, `Value: ${e.target.value}`);
            });
        });

        // Touch events
        ['touchstart', 'touchend'].forEach(eventName => {
            form.addEventListener(eventName, (e) => {
                logInteraction(`Form ${eventName}`);
            });
        });
    </script>
</body>
</html>
```

## 4. Cross-Browser Testing

### Browser Compatibility Test List
```javascript
const browserTests = {
    layout: [
        'Flexbox rendering',
        'Grid layout',
        'CSS transforms',
        'CSS transitions',
        'Font rendering'
    ],
    functionality: [
        'Form validation',
        'Touch events',
        'JavaScript APIs',
        'Local storage',
        'AJAX requests'
    ],
    performance: [
        'Animation smoothness',
        'Scroll performance',
        'Image loading',
        'Form responsiveness',
        'Navigation speed'
    ]
};

// Test runner
function runBrowserTests() {
    const results = {
        browser: navigator.userAgent,
        timestamp: new Date().toISOString(),
        tests: {}
    };

    // Run tests and collect results
    Object.keys(browserTests).forEach(category => {
        results.tests[category] = browserTests[category].map(test => ({
            name: test,
            status: testFeature(test)
        }));
    });

    return results;
}

function testFeature(feature) {
    // Implement actual feature testing here
    // This is just a placeholder
    return {
        supported: true,
        notes: `Tested ${feature}`
    };
}
```

## 5. Performance Testing

### Performance Monitor
```javascript
class PerformanceMonitor {
    constructor() {
        this.metrics = {
            loadTime: 0,
            firstPaint: 0,
            firstContentfulPaint: 0,
            domInteractive: 0,
            domComplete: 0
        };
    }

    start() {
        // Record navigation timing
        window.addEventListener('load', () => {
            const timing = performance.getEntriesByType('navigation')[0];
            this.metrics.loadTime = timing.loadEventEnd - timing.navigationStart;
            this.metrics.domInteractive = timing.domInteractive - timing.navigationStart;
            this.metrics.domComplete = timing.domComplete - timing.navigationStart;
        });

        // Record paint timing
        const paintObserver = new PerformanceObserver((list) => {
            for (const entry of list.getEntries()) {
                if (entry.name === 'first-paint') {
                    this.metrics.firstPaint = entry.startTime;
                }
                if (entry.name === 'first-contentful-paint') {
                    this.metrics.firstContentfulPaint = entry.startTime;
                }
            }
        });

        paintObserver.observe({ entryTypes: ['paint'] });
    }

    getMetrics() {
        return this.metrics;
    }

    logMetrics() {
        console.table(this.metrics);
    }
}

// Usage
const monitor = new PerformanceMonitor();
monitor.start();
```

## 6. Accessibility Testing

### Accessibility Checker
```javascript
class AccessibilityChecker {
    constructor() {
        this.issues = [];
    }

    checkPage() {
        this.checkImages();
        this.checkForms();
        this.checkHeadings();
        this.checkContrast();
        return this.issues;
    }

    checkImages() {
        const images = document.getElementsByTagName('img');
        for (const img of images) {
            if (!img.alt) {
                this.addIssue('image', 'Missing alt text', img);
            }
        }
    }

    checkForms() {
        const forms = document.getElementsByTagName('form');
        for (const form of forms) {
            const inputs = form.getElementsByTagName('input');
            for (const input of inputs) {
                if (!input.getAttribute('aria-label') && !input.getAttribute('aria-labelledby')) {
                    this.addIssue('form', 'Input missing label', input);
                }
            }
        }
    }

    checkHeadings() {
        const headings = document.querySelectorAll('h1, h2, h3, h4, h5, h6');
        let lastLevel = 0;
        
        headings.forEach(heading => {
            const level = parseInt(heading.tagName[1]);
            if (level - lastLevel > 1) {
                this.addIssue('heading', 'Skipped heading level', heading);
            }
            lastLevel = level;
        });
    }

    checkContrast() {
        // Basic contrast check - would need a color contrast library for accurate results
        const elements = document.getElementsByTagName('*');
        for (const element of elements) {
            const style = window.getComputedStyle(element);
            const backgroundColor = style.backgroundColor;
            const color = style.color;
            
            // Add contrast checking logic here
        }
    }

    addIssue(type, message, element) {
        this.issues.push({
            type,
            message,
            element: element.outerHTML
        });
    }
}

// Usage
const checker = new AccessibilityChecker();
const issues = checker.checkPage();
console.table(issues);
```

## 7. Latihan

### Latihan 1: Viewport Testing
Buat halaman test yang menampilkan:
- Current viewport size
- Breakpoint indicator
- Grid system test

### Latihan 2: Interaction Logger
Buat tool untuk mencatat:
- User clicks
- Form interactions
- Touch events
- Scroll behavior

### Latihan 3: Cross-Browser Test Suite
Buat test suite untuk:
- CSS compatibility
- JavaScript functionality
- Form validation
- Touch interactions

## Kesimpulan
- Testing responsiveness penting untuk UX
- Gunakan berbagai device dan browser untuk testing
- Monitor performance dan accessibility
- Dokumentasikan hasil testing
- Perbaiki masalah yang ditemukan

## Referensi Tambahan
- [MDN - Responsive Design Testing](https://developer.mozilla.org/en-US/docs/Tools/Responsive_Design_Mode)
- [Google Chrome DevTools](https://developers.google.com/web/tools/chrome-devtools)
- [Browser Stack](https://www.browserstack.com/)
- [Web.dev - Testing](https://web.dev/testing-web-apps/)