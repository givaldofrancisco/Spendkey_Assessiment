---
name: CTW Presentation Style
description: Instructions for creating presentation slides following the "CTW 7 Years" design aesthetic.
---

# CTW 7 Years Presentation Style Guide

This skill guides the creation of presentation slides that match the CriticalTechWorks "7 Years" branding.

## 1. Asset Preparation

Ensure the following assets are available in your `images/` directory:
- **Background Image**: `images/ctw-7years-bg.png` (Deep blue/purple textured background).
- **Header Logo**: `images/ctw-header-logo.png` (CTW | BMW logo, white text).

## 2. Design Specifications

### Colors
- **Primary Teal**: `#2aeecf` (Highlights, Badges, Subtitles)
- **Text White**: `#FFFFFF` (Main Headings, Body Text)
- **Card Background**: `rgba(255, 255, 255, 0.1)` (Glassmorphism effect)
- **Overlay**: `rgba(0, 40, 80, 0.4)` (For badges/contrast)

### Typography
- **Font Family**: 'Inter', system-ui, sans-serif
- **H1 (Title)**: Large (3rem+), Light/Thin weight (300), White.
- **H2 (Slide Title)**: Medium-Large (2.5rem), Bold weight (700), White. Styled with a teal vertical bar on the left.
- **Subtitle**: Medium size, Regular weight (400), Teal.
- **Badge**: Small, Uppercase, Tracking wide, Teal text on dark overlay.

## 3. CSS Implementation

Use the following CSS variables and classes.

```css
:root {
    --ctw-teal: #2aeecf;
    --ctw-white: #ffffff;
    --ctw-bg-overlay: rgba(0, 40, 80, 0.4);
    --ctw-card-bg: rgba(255, 255, 255, 0.1);
    --ctw-card-border: rgba(42, 238, 207, 0.3);
}

body {
    font-family: 'Inter', sans-serif;
    background-image: url('images/ctw-7years-bg.png');
    background-size: cover;
    background-attachment: fixed;
    background-position: center;
    color: var(--ctw-white);
    margin: 0;
}

/* Slide Section */
section {
    min-height: 100vh;
    display: flex;
    flex-direction: column;
    justify-content: center;
    padding: 4rem 5rem;
    border-bottom: 1px solid rgba(255, 255, 255, 0.05);
}

/* Navigation Header */
nav {
    position: fixed;
    top: 0; left: 0; right: 0;
    padding: 1.5rem 3rem;
    display: flex;
    justify-content: space-between;
    align-items: center;
    z-index: 1000;
}

.nav-brand img {
    height: 60px;
    width: auto;
}

/* Typography & Components */
h2 {
    font-size: 3rem;
    margin-bottom: 2rem;
    display: flex;
    align-items: center;
    gap: 1rem;
}

h2::before {
    content: '';
    display: block; width: 8px; height: 48px;
    background: var(--ctw-teal);
    border-radius: 4px;
}

.ctw-badge {
    display: inline-block;
    border: 2px solid var(--ctw-teal);
    border-radius: 12px;
    padding: 0.5rem 1.5rem;
    color: var(--ctw-teal);
    font-weight: 600;
    text-transform: uppercase;
    letter-spacing: 0.1em;
    background: var(--ctw-bg-overlay);
    backdrop-filter: blur(4px);
    margin-bottom: 1.5rem;
}

.card {
    background: var(--ctw-card-bg);
    border-radius: 16px;
    padding: 2rem;
    border: 1px solid var(--ctw-card-border);
    backdrop-filter: blur(10px);
}
```

## 4. HTML Template Structure

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600;700&display=swap" rel="stylesheet">
    <style>/* CSS from Section 3 */</style>
</head>
<body>

    <nav>
        <a href="#" class="nav-brand">
            <img src="images/ctw-header-logo.png" alt="CTW | BMW">
        </a>
    </nav>

    <!-- Title Slide -->
    <section id="hero">
        <div class="ctw-badge">Event / Date</div>
        <h1>Presentation Title</h1>
        <h2 class="ctw-subtitle">Subtitle in Teal</h2>
    </section>

    <!-- Content Slide -->
    <section id="content">
        <h2>Slide Title</h2>
        <div class="grid-2">
            <div class="card">
                <h3>Card Title</h3>
                <p>Content goes here.</p>
            </div>
            <!-- Additional content -->
        </div>
    </section>

</body>
</html>
```

## 5. Diagrams (Mermaid/Charts)

When using Mermaid diagrams or charts on the dark background:
*   Use transparent or semi-transparent backgrounds for containers if possible, OR explicit white containers for contrast.
*   **Preferred**: Invert colors (White/Teal text/strokes on transparent background).
*   **Scale**: Ensure diagrams are large enough (scale 1.5x - 2.0x) for legibility.

```css
.visual-container.dark-mode-diagram {
     background: rgba(0, 0, 0, 0.3);
     border: 1px solid var(--ctw-teal);
     color: white; /* Ensure text is visible */
}
```
