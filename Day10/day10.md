<div align="center">

# 🚀 Rudresh Srivastava — Personal Portfolio

### GenAI Builder · Full Stack Developer · Competitive Programmer

</div>

---

## ✨ Overview

A **modern, single-file personal portfolio** built with pure HTML, Tailwind CSS (CDN), and vanilla JavaScript — no build tools, no dependencies, no friction. Just open and ship.

Designed for a **GenAI Builder & Full Stack Developer** persona with a dark-first aesthetic, terminal personality touches, and recruiter-ready content layout.

---

## 🖼️ Preview

| Dark Mode | Light Mode |
|-----------|------------|
| Deep space navy + violet/cyan gradients | Clean slate with the same accent palette |

> Toggle between modes with the switch in the navbar — preference is saved to `localStorage`.

---

## 🗂️ Sections

| Section | Description |
|---------|-------------|
| **Hero** | Name, animated typing title, location, CTA buttons, social links |
| **About** | Bio, role pills, interactive terminal-style JSON card |
| **Skills** | Animated progress bars + tech stack & soft skill tags |
| **Projects** | Cards for Zenith Banking, NASA Explorer, Spotify Clone |
| **Experience** | Timeline of roles at Blockchain Research Lab & AKGEC |
| **Achievements** | Key milestones as highlight cards |
| **Contact** | Form (opens mailto) + direct email/LinkedIn/GitHub links |

---

## ⚡ Features

- 🌙 **Dark / Light mode toggle** — persists across sessions
- ✍️ **Typing animation** — cycles through 5 professional roles
- 📊 **Scroll-triggered skill bars** — animate on first viewport entry
- 🎭 **Reveal animations** — every section fades in on scroll
- 🔗 **Active nav highlighting** — tracks current section via IntersectionObserver
- 📱 **Fully responsive** — mobile menu with hamburger toggle
- 💌 **Contact form** — pre-fills a `mailto:` with name, subject, and message
- 🔍 **SEO meta tags** — Open Graph, Twitter Card, description, robots
- 🎨 **Glassmorphism UI** — cards with blur, border, and hover lift effects
- 🖋️ **Custom fonts** — Space Grotesk + Inter + JetBrains Mono (Google Fonts)

---

## 🛠️ Tech Stack

```
HTML5   ·   Tailwind CSS (CDN)   ·   Vanilla JavaScript
Google Fonts   ·   IntersectionObserver API   ·   CSS Custom Properties
```

No npm. No webpack. No React. Just one `.html` file.

---

## 🚀 Getting Started

### Option 1 — Open locally
```bash
# Clone the repo
git clone https://github.com/srivastavarudresh552-cmyk/portfolio.git

# Open directly in your browser
open index.html
```

### Option 2 — Deploy to Vercel (recommended)
```bash
# Drag & drop the HTML file at
https://vercel.com/new
```

### Option 3 — GitHub Pages
1. Push `index.html` to a repo named `yourusername.github.io`
2. Go to **Settings → Pages → Deploy from branch → main**
3. Live at `https://yourusername.github.io`

---

## 🎨 Customization

All personal info is written directly in the HTML. To make it yours:

| What to change | Where |
|----------------|-------|
| Name, title, location | `<h1>` and subtitle in the `#hero` section |
| Typing phrases | `const phrases = [...]` in the `<script>` block |
| Skills & levels | `const skills = [...]` array in the script |
| Projects | `.glass` cards in the `#projects` section |
| Experience & Achievements | `#experience` and `#achievements` sections |
| Social links | `href` attributes on anchor tags |
| Colors | CSS variables in `:root` and `.dark` blocks |

---

## 📁 File Structure

```
portfolio/
└── index.html     ← Everything lives here
```

---

---

<div align="center">

Built with ♥ by **Rudresh Srivastava** · Ghaziabad, India

⭐ Star this repo if it helped you!

</div>
