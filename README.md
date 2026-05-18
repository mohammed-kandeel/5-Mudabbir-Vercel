<div align="center">

# 🪙 Mudabbir — Smart Personal Finance Dashboard

**Manage your money intelligently**

[![Live Demo](https://img.shields.io/badge/🌐_Live_Demo-View_Project-4F9DFF?style=for-the-badge)](https://mohammed-kandeel.github.io/5-Mudabbir-Vercel/)
[![GitHub](https://img.shields.io/badge/GitHub-Source_Code-181717?style=for-the-badge&logo=github)](https://github.com/mohammed-kandeel/5-Mudabbir-Vercel)
![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)

</div>

---

## 📌 About

**Mudabbir** (Arabic for "The One Who Plans") is a personal finance dashboard built entirely with HTML and CSS. It gives users a comprehensive overview of their financial life — current balance, recent transactions, budgets, monthly bills, and payment methods — all wrapped in a clean Arabic RTL interface.

This project is **Assignment 5** of my Frontend learning journey, focused on mastering **CSS Grid** for complex, responsive layouts.

---

## ✨ Technical Highlights

### 1. CSS Grid with Named Template Areas

The most challenging part of this project was building a layout that completely reorganizes itself across screen sizes using `grid-template-areas` — no JavaScript, no layout library.

```css
/* Tablet — 2 columns */
grid-template-areas:
  'item-1 item-5'
  'item-2 item-2'
  'item-3 item-6'
  'item-4 item-7';

/* Desktop — 3 columns */
grid-template-areas:
  'item-1 item-2 item-2'
  'item-3 item-2 item-2'
  'item-4 item-5 item-7'
  'item-4 item-6 item-7';
```

Each section (Activities, Transactions, Budget...) snaps into its correct position automatically based on the viewport — zero HTML changes needed.

---

### 2. Fully Responsive — 4 Breakpoints

| Breakpoint | Size | Behavior |
|---|---|---|
| Mobile | `< 640px` | Sidebar hidden, single-column layout |
| Small | `640px+` | Topbar collapses into one row, username appears |
| Tablet | `768px+` | Icon-only sidebar, 2-column grid |
| Desktop | `1280px+` | Full sidebar with labels, 3-column grid |

---

### 3. CSS-Only 3D Card Flip

The Bonus task: credit cards flip on hover to reveal the back face (CVV, signature strip) — pure CSS, zero JavaScript.

```css
.card .card-inner {
  transform-style: preserve-3d;
  transition: transform 0.8s cubic-bezier(0.2, 0.9, 0.3, 1);
}
.card:hover .card-inner {
  transform: perspective(1200px) rotateY(180deg);
}
.front-card { backface-visibility: hidden; }
.back-card  { transform: rotateY(180deg); }
```

---

### 4. Design System via CSS Custom Properties

Instead of repeating values across the stylesheet, I built a full token system in `:root` covering colors, transitions, and typography — making the whole UI consistent and easy to maintain.

```css
:root {
  --color-blue-600:             rgb(21, 93, 251);
  --color-green-500:            rgb(0, 201, 80);
  --color-gray-900:             rgb(16, 24, 40);
  --transition-duration:        0.15s;
  --transition-timing-function: cubic-bezier(0.4, 0, 0.2, 1);
}
```

---

### 5. RTL-First Layout

The entire interface is built for Arabic with `dir="rtl"` on the `<html>` tag. All flexbox and grid directions, sidebar positioning, and logical CSS properties (`padding-inline`, `border-left` for highlights) are handled correctly without hacks.

```html
<html lang="ar" dir="rtl">
```

---

### 6. Micro-interactions with Consistent Transitions

Every interactive element uses the same easing curve pulled from the design system, creating a cohesive feel across the entire page.

```css
/* Budget card lift on hover */
.card:hover {
  transform: translateY(-1px);
  box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1);
}

/* Sidebar action button nudge */
#side-bar .actions button:hover {
  transform: translate(2px);
}
```

---

### 7. Zero JavaScript

The entire page runs on **HTML + CSS only** — no JS whatsoever. Every interaction (hover states, card flip, transitions, progress bars) is handled by the browser's CSS engine.

---

## 🧩 Components

| Component | Description |
|---|---|
| **Top Bar** | Logo, search, notification badge, user profile |
| **Summary Cards** | Current balance, income, and expenses at a glance |
| **Transactions Table** | Scrollable table with color-coded categories and status badges |
| **Budget Overview** | Progress bars per budget category with remaining percentage |
| **Monthly Bills** | Bill tracker with due-date urgency coloring |
| **Income vs Expenses** | Pure-CSS bar chart across 4 weeks |
| **Account Summary** | Bank accounts and credit card balances |
| **Payment Methods** | 3D flip cards for Visa, Mastercard, and PayPal |

---

## 🛠️ Built With

- **HTML5** — Semantic markup, RTL support
- **CSS3** — Grid · Flexbox · Custom Properties · 3D Transforms · Transitions
- **IBM Plex Sans Arabic** — Primary typeface
- **Font Awesome** — Inline SVG icons

---

## 🚀 Getting Started

```bash
git clone https://github.com/mohammed-kandeel/5-Mudabbir-Vercel.git
cd 5-Mudabbir-Vercel
# Open index.html in your browser
```

Or visit the [Live Demo](https://mohammed-kandeel.github.io/5-Mudabbir-Vercel/) directly.

---

<div align="center">
  Built with ❤️ as part of my Frontend learning journey
</div>
