# Web Accessibility Code Patterns

Common accessible and inaccessible patterns with corrections.

## Images

### Bad
```html
<img src="chart.png">
<img src="logo.png" alt="image">
<img src="banner.jpg" alt="banner.jpg">
<div style="background-image: url(info.png)"></div>
```

### Good
```html
<img src="chart.png" alt="Sales increased 25% from Q1 to Q4 2025">
<img src="logo.png" alt="Acme Corp">
<img src="divider.png" alt="">  <!-- decorative -->
<div style="background-image: url(info.png)" role="img" aria-label="Important notice about shipping delays"></div>

<!-- Complex image with extended description -->
<figure>
  <img src="chart.png" alt="Quarterly revenue chart" aria-describedby="chart-desc">
  <figcaption id="chart-desc">Q1: $2M, Q2: $2.5M, Q3: $3.1M, Q4: $3.8M</figcaption>
</figure>
```

## Forms

### Bad
```html
<input type="text" placeholder="Email">
<input type="checkbox"> I agree
<span class="red">*</span> Required
<input type="text"> <span class="error">Invalid</span>
```

### Good
```html
<label for="email">Email</label>
<input id="email" type="email" autocomplete="email" required aria-describedby="email-help">
<span id="email-help">We'll send a confirmation to this address.</span>

<input id="agree" type="checkbox" required>
<label for="agree">I agree to the terms of service</label>

<label for="name">
  Full name <span aria-hidden="true">*</span>
  <span class="sr-only">(required)</span>
</label>
<input id="name" type="text" required autocomplete="name">

<label for="phone">Phone</label>
<input id="phone" type="tel" aria-invalid="true" aria-errormessage="phone-error">
<span id="phone-error" role="alert">Enter a valid phone number (e.g., 555-123-4567)</span>
```

## Buttons and Links

### Bad
```html
<a href="#">Click here</a>
<div onclick="submit()">Submit</div>
<a href="/report.pdf">Report</a>
<a href="https://example.com" target="_blank">Example</a>
<span class="btn" tabindex="0">Save</span>
```

### Good
```html
<a href="/pricing">View pricing details</a>
<button type="submit">Submit application</button>
<a href="/report.pdf">Download annual report (PDF, 2.3 MB)</a>
<a href="https://example.com" target="_blank" rel="noopener">
  Example <span class="sr-only">(opens in new tab)</span>
</a>
<button type="button">Save changes</button>

<!-- Icon button -->
<button type="button" aria-label="Close dialog">
  <svg aria-hidden="true">...</svg>
</button>
```

## Navigation

### Bad
```html
<div class="nav">
  <a href="/">Home</a>
  <a href="/about">About</a>
</div>
```

### Good
```html
<a href="#main" class="skip-link">Skip to main content</a>

<nav aria-label="Main">
  <ul>
    <li><a href="/" aria-current="page">Home</a></li>
    <li><a href="/about">About</a></li>
    <li><a href="/contact">Contact</a></li>
  </ul>
</nav>

<nav aria-label="Breadcrumb">
  <ol>
    <li><a href="/">Home</a></li>
    <li><a href="/products">Products</a></li>
    <li><a href="/products/widgets" aria-current="page">Widgets</a></li>
  </ol>
</nav>

<main id="main">
  <!-- page content -->
</main>
```

## Headings

### Bad
```html
<div class="title">Page Title</div>
<h1>Welcome</h1>
<h3>Section</h3>  <!-- skipped h2 -->
<h1>Another Section</h1>  <!-- duplicate h1 -->
```

### Good
```html
<h1>Product Catalog</h1>
  <h2>Electronics</h2>
    <h3>Laptops</h3>
    <h3>Phones</h3>
  <h2>Clothing</h2>
    <h3>Men's</h3>
    <h3>Women's</h3>
```

## Modal Dialog

### Bad
```html
<div class="modal" style="display:block">
  <div class="content">
    <span onclick="close()">X</span>
    <p>Are you sure?</p>
    <div onclick="confirm()">Yes</div>
  </div>
</div>
```

### Good
```html
<div role="dialog" aria-modal="true" aria-labelledby="modal-title">
  <h2 id="modal-title">Confirm deletion</h2>
  <p>This action cannot be undone. Delete this item?</p>
  <div>
    <button type="button" autofocus>Cancel</button>
    <button type="button">Delete</button>
  </div>
</div>
```
```js
// Focus management
function openModal(modal) {
  const prevFocus = document.activeElement;
  modal.hidden = false;
  modal.querySelector('[autofocus]')?.focus();

  modal.addEventListener('keydown', (e) => {
    if (e.key === 'Escape') closeModal(modal, prevFocus);
    if (e.key === 'Tab') trapFocus(e, modal);
  });
}

function closeModal(modal, returnFocus) {
  modal.hidden = true;
  returnFocus?.focus();
}

function trapFocus(e, container) {
  const focusable = container.querySelectorAll(
    'button, [href], input, select, textarea, [tabindex]:not([tabindex="-1"])'
  );
  const first = focusable[0];
  const last = focusable[focusable.length - 1];

  if (e.shiftKey && document.activeElement === first) {
    e.preventDefault();
    last.focus();
  } else if (!e.shiftKey && document.activeElement === last) {
    e.preventDefault();
    first.focus();
  }
}
```

## Tables

### Bad
```html
<table>
  <tr><td><b>Name</b></td><td><b>Price</b></td></tr>
  <tr><td>Widget</td><td>$5</td></tr>
</table>
```

### Good
```html
<table>
  <caption>Product pricing as of March 2026</caption>
  <thead>
    <tr>
      <th scope="col">Product</th>
      <th scope="col">Price</th>
      <th scope="col">Availability</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th scope="row">Widget</th>
      <td>$5.00</td>
      <td>In stock</td>
    </tr>
  </tbody>
</table>
```

## Live Regions and Notifications

### Bad
```js
// Silently update count with no AT announcement
document.getElementById('count').textContent = '5 items';

// Alert for non-urgent info
<div role="alert">Search complete</div>
```

### Good
```html
<!-- Status update (polite) -->
<div role="status" aria-live="polite">5 results found</div>

<!-- Error alert (assertive) -->
<div role="alert">Payment failed. Please check your card details.</div>

<!-- Loading state -->
<div aria-busy="true" aria-live="polite">
  <span class="sr-only">Loading results...</span>
</div>

<!-- Cart update -->
<div aria-live="polite" aria-atomic="true">
  Cart: <span>3 items</span>, <span>$45.00</span>
</div>
```

## Motion and Animation

### Good
```css
/* Respect user preference */
@media (prefers-reduced-motion: reduce) {
  *,
  *::before,
  *::after {
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
    transition-duration: 0.01ms !important;
    scroll-behavior: auto !important;
  }
}
```

## Focus Styles

### Bad
```css
*:focus { outline: none; }
button:focus { outline: 0; }
```

### Good
```css
/* Visible focus for keyboard users, hidden for mouse */
:focus-visible {
  outline: 3px solid #4A90D9;
  outline-offset: 2px;
}

/* Remove outline only for mouse clicks */
:focus:not(:focus-visible) {
  outline: none;
}

/* Skip link */
.skip-link {
  position: absolute;
  left: -9999px;
  top: auto;
  padding: 8px 16px;
  background: #000;
  color: #fff;
  z-index: 9999;
}
.skip-link:focus {
  left: 8px;
  top: 8px;
}
```

## Responsive and Touch

### Good
```css
/* Minimum touch target */
button, a, input, select {
  min-height: 44px;  /* ideally 44px, minimum 24px per WCAG */
  min-width: 44px;
}

/* Adequate spacing for small targets */
.icon-btn {
  min-height: 24px;
  min-width: 24px;
  padding: 10px;  /* padding counts toward target size */
}
```

## Page Template

### Minimal Accessible Page
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Page Title - Site Name</title>
</head>
<body>
  <a href="#main" class="skip-link">Skip to main content</a>

  <header>
    <nav aria-label="Main">
      <ul>
        <li><a href="/" aria-current="page">Home</a></li>
        <li><a href="/about">About</a></li>
      </ul>
    </nav>
  </header>

  <main id="main">
    <h1>Page Title</h1>
    <!-- content -->
  </main>

  <footer>
    <nav aria-label="Footer">
      <ul>
        <li><a href="/privacy">Privacy policy</a></li>
        <li><a href="/terms">Terms of service</a></li>
      </ul>
    </nav>
    <p>&copy; 2026 Company Name</p>
  </footer>
</body>
</html>
```
