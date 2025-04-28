# Hari 25: JavaScript Interaktif (Form Validation & Slider)

## Tujuan Pembelajaran
- Mengimplementasikan form validation dengan JavaScript
- Membuat image slider interaktif
- Menerapkan error handling dan feedback user
- Membuat animasi smooth untuk slider
- Mengoptimalkan performa interaksi

## 1. Form Validation

### Basic Form Validation
```html
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Form Validation</title>
    <style>
        .form-group {
            margin-bottom: 1rem;
        }

        .error {
            color: #dc3545;
            font-size: 0.875rem;
            margin-top: 0.25rem;
            display: none;
        }

        .form-control.error {
            border-color: #dc3545;
        }

        .success-message {
            color: #28a745;
            display: none;
            margin-top: 1rem;
        }
    </style>
</head>
<body>
    <form id="contactForm" novalidate>
        <div class="form-group">
            <label for="name">Name:</label>
            <input type="text" id="name" class="form-control" required>
            <div class="error" id="nameError">Name is required</div>
        </div>

        <div class="form-group">
            <label for="email">Email:</label>
            <input type="email" id="email" class="form-control" required>
            <div class="error" id="emailError">Please enter a valid email</div>
        </div>

        <div class="form-group">
            <label for="phone">Phone:</label>
            <input type="tel" id="phone" class="form-control">
            <div class="error" id="phoneError">Please enter a valid phone number</div>
        </div>

        <div class="form-group">
            <label for="message">Message:</label>
            <textarea id="message" class="form-control" required></textarea>
            <div class="error" id="messageError">Message is required</div>
        </div>

        <button type="submit">Submit</button>
        <div class="success-message" id="successMessage">Form submitted successfully!</div>
    </form>

    <script>
        const form = document.getElementById('contactForm');
        const successMessage = document.getElementById('successMessage');

        // Validation functions
        const validators = {
            name: (value) => {
                return value.length >= 2;
            },
            email: (value) => {
                const emailRegex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
                return emailRegex.test(value);
            },
            phone: (value) => {
                const phoneRegex = /^[\d\s-+()]{10,}$/;
                return value === '' || phoneRegex.test(value);
            },
            message: (value) => {
                return value.length >= 10;
            }
        };

        // Show error message
        function showError(fieldId, show) {
            const errorElement = document.getElementById(`${fieldId}Error`);
            const inputElement = document.getElementById(fieldId);
            
            errorElement.style.display = show ? 'block' : 'none';
            inputElement.classList.toggle('error', show);
        }

        // Validate single field
        function validateField(fieldId) {
            const field = document.getElementById(fieldId);
            const isValid = validators[fieldId](field.value);
            showError(fieldId, !isValid);
            return isValid;
        }

        // Real-time validation
        ['name', 'email', 'phone', 'message'].forEach(fieldId => {
            const field = document.getElementById(fieldId);
            field.addEventListener('blur', () => validateField(fieldId));
            field.addEventListener('input', () => {
                if (field.classList.contains('error')) {
                    validateField(fieldId);
                }
            });
        });

        // Form submission
        form.addEventListener('submit', (e) => {
            e.preventDefault();

            const isNameValid = validateField('name');
            const isEmailValid = validateField('email');
            const isPhoneValid = validateField('phone');
            const isMessageValid = validateField('message');

            if (isNameValid && isEmailValid && isPhoneValid && isMessageValid) {
                // Form is valid - you can submit it
                successMessage.style.display = 'block';
                form.reset();
                setTimeout(() => {
                    successMessage.style.display = 'none';
                }, 3000);
            }
        });
    </script>
</body>
</html>
```

## 2. Image Slider

### Basic Image Slider
```html
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Image Slider</title>
    <style>
        .slider-container {
            position: relative;
            max-width: 800px;
            margin: 0 auto;
            overflow: hidden;
        }

        .slider {
            display: flex;
            transition: transform 0.5s ease-in-out;
        }

        .slide {
            min-width: 100%;
            height: 400px;
        }

        .slide img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        .slider-controls {
            position: absolute;
            top: 50%;
            left: 0;
            right: 0;
            transform: translateY(-50%);
            display: flex;
            justify-content: space-between;
            padding: 0 20px;
        }

        .slider-button {
            background: rgba(255, 255, 255, 0.7);
            border: none;
            padding: 10px 15px;
            cursor: pointer;
            border-radius: 50%;
            transition: background-color 0.3s;
        }

        .slider-button:hover {
            background: rgba(255, 255, 255, 0.9);
        }

        .slider-dots {
            position: absolute;
            bottom: 20px;
            left: 50%;
            transform: translateX(-50%);
            display: flex;
            gap: 10px;
        }

        .dot {
            width: 10px;
            height: 10px;
            border-radius: 50%;
            background: rgba(255, 255, 255, 0.5);
            cursor: pointer;
            transition: background-color 0.3s;
        }

        .dot.active {
            background: white;
        }
    </style>
</head>
<body>
    <div class="slider-container">
        <div class="slider" id="slider">
            <div class="slide">
                <img src="image1.jpg" alt="Slide 1">
            </div>
            <div class="slide">
                <img src="image2.jpg" alt="Slide 2">
            </div>
            <div class="slide">
                <img src="image3.jpg" alt="Slide 3">
            </div>
        </div>

        <div class="slider-controls">
            <button class="slider-button prev" onclick="prevSlide()">❮</button>
            <button class="slider-button next" onclick="nextSlide()">❯</button>
        </div>

        <div class="slider-dots" id="sliderDots"></div>
    </div>

    <script>
        const slider = document.getElementById('slider');
        const slides = document.querySelectorAll('.slide');
        const dotsContainer = document.getElementById('sliderDots');
        let currentSlide = 0;
        let autoplayInterval;

        // Create dots
        slides.forEach((_, index) => {
            const dot = document.createElement('div');
            dot.classList.add('dot');
            dot.addEventListener('click', () => goToSlide(index));
            dotsContainer.appendChild(dot);
        });

        const dots = document.querySelectorAll('.dot');

        // Initialize
        updateSlider();
        startAutoplay();

        function updateSlider() {
            slider.style.transform = `translateX(-${currentSlide * 100}%)`;
            
            // Update dots
            dots.forEach((dot, index) => {
                dot.classList.toggle('active', index === currentSlide);
            });
        }

        function nextSlide() {
            currentSlide = (currentSlide + 1) % slides.length;
            updateSlider();
            resetAutoplay();
        }

        function prevSlide() {
            currentSlide = (currentSlide - 1 + slides.length) % slides.length;
            updateSlider();
            resetAutoplay();
        }

        function goToSlide(index) {
            currentSlide = index;
            updateSlider();
            resetAutoplay();
        }

        function startAutoplay() {
            autoplayInterval = setInterval(nextSlide, 5000);
        }

        function resetAutoplay() {
            clearInterval(autoplayInterval);
            startAutoplay();
        }

        // Touch events for mobile
        let touchStartX = 0;
        let touchEndX = 0;

        slider.addEventListener('touchstart', e => {
            touchStartX = e.changedTouches[0].screenX;
        });

        slider.addEventListener('touchend', e => {
            touchEndX = e.changedTouches[0].screenX;
            handleSwipe();
        });

        function handleSwipe() {
            const swipeThreshold = 50;
            const diff = touchStartX - touchEndX;

            if (Math.abs(diff) > swipeThreshold) {
                if (diff > 0) {
                    nextSlide();
                } else {
                    prevSlide();
                }
            }
        }
    </script>
</body>
</html>
```

## 3. Advanced Form Features

### Dynamic Form Validation
```javascript
class FormValidator {
    constructor(formId, validations) {
        this.form = document.getElementById(formId);
        this.validations = validations;
        this.init();
    }

    init() {
        this.form.addEventListener('submit', (e) => this.handleSubmit(e));
        
        // Real-time validation
        Object.keys(this.validations).forEach(fieldId => {
            const field = document.getElementById(fieldId);
            if (field) {
                field.addEventListener('input', () => this.validateField(fieldId));
                field.addEventListener('blur', () => this.validateField(fieldId));
            }
        });
    }

    validateField(fieldId) {
        const field = document.getElementById(fieldId);
        const value = field.value;
        const validation = this.validations[fieldId];
        
        let isValid = true;
        let errorMessage = '';

        // Run all validations
        for (let rule of validation.rules) {
            if (!rule.test(value)) {
                isValid = false;
                errorMessage = rule.message;
                break;
            }
        }

        this.showFieldError(fieldId, !isValid, errorMessage);
        return isValid;
    }

    showFieldError(fieldId, show, message = '') {
        const field = document.getElementById(fieldId);
        const errorElement = document.getElementById(`${fieldId}Error`);
        
        if (errorElement) {
            errorElement.textContent = message;
            errorElement.style.display = show ? 'block' : 'none';
        }
        
        field.classList.toggle('error', show);
    }

    handleSubmit(e) {
        e.preventDefault();
        
        let isFormValid = true;
        
        // Validate all fields
        Object.keys(this.validations).forEach(fieldId => {
            if (!this.validateField(fieldId)) {
                isFormValid = false;
            }
        });

        if (isFormValid) {
            // Form is valid - submit data
            this.submitForm();
        }
    }

    async submitForm() {
        try {
            const formData = new FormData(this.form);
            const response = await fetch(this.form.action, {
                method: 'POST',
                body: formData
            });

            if (response.ok) {
                this.showSuccess();
            } else {
                throw new Error('Submission failed');
            }
        } catch (error) {
            this.showError(error.message);
        }
    }

    showSuccess() {
        // Show success message
        const successMessage = document.createElement('div');
        successMessage.className = 'success-message';
        successMessage.textContent = 'Form submitted successfully!';
        this.form.appendChild(successMessage);

        // Reset form
        this.form.reset();

        // Remove success message after delay
        setTimeout(() => {
            successMessage.remove();
        }, 3000);
    }

    showError(message) {
        // Show error message
        const errorMessage = document.createElement('div');
        errorMessage.className = 'error-message';
        errorMessage.textContent = message;
        this.form.appendChild(errorMessage);

        // Remove error message after delay
        setTimeout(() => {
            errorMessage.remove();
        }, 3000);
    }
}

// Usage example
const validations = {
    name: {
        rules: [
            {
                test: value => value.length >= 2,
                message: 'Name must be at least 2 characters'
            }
        ]
    },
    email: {
        rules: [
            {
                test: value => /^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(value),
                message: 'Please enter a valid email address'
            }
        ]
    },
    // Add more field validations as needed
};

const formValidator = new FormValidator('contactForm', validations);
```

## 4. Advanced Slider Features

### Slider with Thumbnails
```javascript
class ImageSlider {
    constructor(containerId, options = {}) {
        this.container = document.getElementById(containerId);
        this.options = {
            autoplay: true,
            interval: 5000,
            showThumbnails: true,
            showDots: true,
            ...options
        };
        
        this.currentSlide = 0;
        this.slides = this.container.querySelectorAll('.slide');
        this.init();
    }

    init() {
        this.createControls();
        if (this.options.showThumbnails) this.createThumbnails();
        if (this.options.showDots) this.createDots();
        if (this.options.autoplay) this.startAutoplay();
        this.addTouchEvents();
        this.updateSlider();
    }

    createControls() {
        const controls = document.createElement('div');
        controls.className = 'slider-controls';
        
        const prevButton = document.createElement('button');
        prevButton.className = 'slider-button prev';
        prevButton.innerHTML = '❮';
        prevButton.onclick = () => this.prevSlide();

        const nextButton = document.createElement('button');
        nextButton.className = 'slider-button next';
        nextButton.innerHTML = '❯';
        nextButton.onclick = () => this.nextSlide();

        controls.appendChild(prevButton);
        controls.appendChild(nextButton);
        this.container.appendChild(controls);
    }

    createThumbnails() {
        const thumbnailsContainer = document.createElement('div');
        thumbnailsContainer.className = 'thumbnails';

        this.slides.forEach((slide, index) => {
            const thumb = document.createElement('div');
            thumb.className = 'thumbnail';
            const img = slide.querySelector('img').cloneNode();
            thumb.appendChild(img);
            thumb.onclick = () => this.goToSlide(index);
            thumbnailsContainer.appendChild(thumb);
        });

        this.container.appendChild(thumbnailsContainer);
    }

    createDots() {
        const dotsContainer = document.createElement('div');
        dotsContainer.className = 'slider-dots';

        this.slides.forEach((_, index) => {
            const dot = document.createElement('div');
            dot.className = 'dot';
            dot.onclick = () => this.goToSlide(index);
            dotsContainer.appendChild(dot);
        });

        this.container.appendChild(dotsContainer);
    }

    updateSlider() {
        const slider = this.container.querySelector('.slider');
        slider.style.transform = `translateX(-${this.currentSlide * 100}%)`;

        // Update thumbnails
        const thumbnails = this.container.querySelectorAll('.thumbnail');
        thumbnails.forEach((thumb, index) => {
            thumb.classList.toggle('active', index === this.currentSlide);
        });

        // Update dots
        const dots = this.container.querySelectorAll('.dot');
        dots.forEach((dot, index) => {
            dot.classList.toggle('active', index === this.currentSlide);
        });
    }

    nextSlide() {
        this.currentSlide = (this.currentSlide + 1) % this.slides.length;
        this.updateSlider();
        this.resetAutoplay();
    }

    prevSlide() {
        this.currentSlide = (this.currentSlide - 1 + this.slides.length) % this.slides.length;
        this.updateSlider();
        this.resetAutoplay();
    }

    goToSlide(index) {
        this.currentSlide = index;
        this.updateSlider();
        this.resetAutoplay();
    }

    startAutoplay() {
        this.autoplayInterval = setInterval(() => this.nextSlide(), this.options.interval);
    }

    resetAutoplay() {
        if (this.options.autoplay) {
            clearInterval(this.autoplayInterval);
            this.startAutoplay();
        }
    }

    addTouchEvents() {
        let touchStartX = 0;
        let touchEndX = 0;

        this.container.addEventListener('touchstart', e => {
            touchStartX = e.changedTouches[0].screenX;
        });

        this.container.addEventListener('touchend', e => {
            touchEndX = e.changedTouches[0].screenX;
            this.handleSwipe(touchStartX - touchEndX);
        });
    }

    handleSwipe(diff) {
        const swipeThreshold = 50;
        if (Math.abs(diff) > swipeThreshold) {
            if (diff > 0) {
                this.nextSlide();
            } else {
                this.prevSlide();
            }
        }
    }
}

// Usage example
const slider = new ImageSlider('sliderContainer', {
    autoplay: true,
    interval: 5000,
    showThumbnails: true,
    showDots: true
});
```

## 5. Latihan

### Latihan 1: Custom Form Validation
Buat form dengan validasi khusus untuk:
- Password strength
- Phone number format
- File upload size and type

### Latihan 2: Enhanced Slider
Buat slider dengan fitur tambahan:
- Lazy loading images
- Multiple slide view
- Transition effects

### Latihan 3: Combined Features
Buat gallery dengan form:
- Image upload preview
- Form validation
- Image slider for uploaded images

## Kesimpulan
- Form validation penting untuk UX dan data integrity
- Slider interaktif meningkatkan engagement
- Kombinasi CSS dan JavaScript membuat UI lebih dinamis
- Mobile-friendly interactions sangat penting

## Referensi Tambahan
- [MDN - Form Validation](https://developer.mozilla.org/en-US/docs/Learn/Forms/Form_validation)
- [Web.dev - Image Sliders](https://web.dev/image-gallery/)
- [CSS-Tricks - Form Validation UX](https://css-tricks.com/form-validation-ux-in-html-and-css/)
- [JavaScript.info - Forms](https://javascript.info/forms-controls)