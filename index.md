Here is the complete solution for your assignment, including the design-token stylesheet (styles.css) and a sample webpage (index.html) demonstrating how the CSS variables work across buttons, headings, and cards.

1. The Design-Token Stylesheet (styles.css)
Save this file as styles.css. It defines your design tokens and variables inside the :root pseudo-class and applies them to various UI components.

CSS
/* ==========================================
   1. Design Tokens & CSS Variables (:root)
   ================================---------- */
:root {
  /* Colors */
  --color-primary: #3b82f6;       /* Vibrant Blue */
  --color-primary-hover: #2563eb; /* Darker Blue for hover states */
  --color-secondary: #10b981;     /* Emerald Green */
  --color-background: #f8fafc;    /* Light Slate background */
  --color-surface: #ffffff;       /* Card/Container background */
  --color-text: #1e293b;          /* Dark Slate text */
  --color-text-muted: #64748b;    /* Muted text */

  /* Spacing Tokens */
  --space-sm: 0.5rem;   /* 8px */
  --space-md: 1rem;     /* 16px */
  --space-lg: 2rem;     /* 32px */

  /* Font Size Tokens */
  --font-size-sm: 0.875rem; /* 14px */
  --font-size-md: 1rem;     /* 16px */
  --font-size-lg: 1.5rem;   /* 24px */
  --font-size-xl: 2.25rem;  /* 36px */

  /* Border Radius & Shadows */
  --radius-md: 8px;
  --shadow-sm: 0 4px 6px -1px rgb(0 0 0 / 0.1);
}

/* ==========================================
   2. Global Styles
   ================================---------- */
body {
  background-color: var(--color-background);
  color: var(--color-text);
  font-family: system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;
  margin: 0;
  padding: var(--space-lg);
  line-height: 1.5;
}

/* ==========================================
   3. Using Variables in Elements
   ================================---------- */

/* Headings */
h1, h2, h3 {
  color: var(--color-text);
  margin-top: 0;
}

h1 {
  font-size: var(--font-size-xl);
  margin-bottom: var(--space-sm);
}

h2 {
  font-size: var(--font-size-lg);
  margin-bottom: var(--space-md);
}

p {
  font-size: var(--font-size-md);
  color: var(--color-text-muted);
}

/* Cards */
.card-container {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: var(--space-lg);
  margin-top: var(--space-lg);
}

.card {
  background-color: var(--color-surface);
  padding: var(--space-lg);
  border-radius: var(--radius-md);
  box-shadow: var(--shadow-sm);
  border-top: 4px solid var(--color-primary);
}

.card.secondary-accent {
  border-top-color: var(--color-secondary);
}

/* Buttons */
.btn {
  background-color: var(--color-primary);
  color: var(--color-surface);
  padding: var(--space-sm) var(--space-md);
  font-size: var(--font-size-sm);
  border: none;
  border-radius: var(--radius-md);
  cursor: pointer;
  font-weight: 600;
  transition: background-color 0.2s ease;
}

.btn:hover {
  background-color: var(--color-primary-hover);
}

.btn-secondary {
  background-color: var(--color-secondary);
}

.btn-secondary:hover {
  background-color: #059669;
}
2. Sample Webpage (index.html)
Save this file as index.html in the same folder as your styles.css. It links the stylesheet and showcases headings, cards, and buttons using the design tokens.

HTML
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Assignment 5.4 — CSS Variables & Design Tokens</title>
  <link rel="stylesheet" href="styles.css">
</head>
<body>

  <header>
    <h1>Design System Dashboard</h1>
    <p>Demonstrating reusable colors, spacing, and font sizes using CSS Variables.</p>
  </header>

  <main class="card-container">
    <!-- Card 1 -->
    <section class="card">
      <h2>Primary Component</h2>
      <p>This card uses primary accent colors and spacing tokens defined globally in <code>:root</code>.</p>
      <button class="btn">Primary Action</button>
    </section>

    <!-- Card 2 -->
    <section class="card secondary-accent">
      <h2>Secondary Component</h2>
      <p>This card leverages secondary color tokens to establish hierarchy within the UI design system.</p>
      <button class="btn btn-secondary">Secondary Action</button>
    </section>
  </main>

</body>
</html>
3. Step 6 Verification Instructions
To fulfill Step 6 ("Change a variable and verify that multiple elements update"):

Open styles.css.

Locate --color-primary: #3b82f6; at the top.

Change it to a different color (e.g., #ef4444 for red or #8b5cf6 for purple).

Save the file and refresh your browser. You will instantly see both the top border of the first card and the primary button change color globally without having to edit HTML or multiple CSS rules.