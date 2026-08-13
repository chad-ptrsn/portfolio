# Chad Petersen Portfolio - Vue 3 Edition

A modern, responsive portfolio built with **Vue 3** and **Vite**, deployed on Cloudflare Pages.

## Tech Stack

- **Vue 3** - Progressive JavaScript framework
- **Vite** - Next-generation frontend build tool
- **Bootstrap 5** - CSS framework for responsive design
- **Font Awesome 6** - Icon library
- **Magnific Popup** - Responsive lightbox plugin
- **ScrollReveal** - Scroll animations

## Development

### Prerequisites
- Node.js 18+ and npm

### Installation

```bash
npm install
```

### Local Development Server

```bash
npm run dev
```

This starts a local dev server at `http://localhost:3000` with hot module replacement (HMR).

### Build for Production

```bash
npm run build
```

This creates an optimized production build in the `dist/` directory.

### Preview Production Build

```bash
npm run preview
```

## Project Structure

```
src/
├── components/
│   ├── NavBar.vue        # Navigation bar with scroll effects
│   ├── Masthead.vue      # Hero section
│   ├── About.vue         # About section
│   ├── Services.vue      # Skills section
│   ├── Portfolio.vue     # Projects showcase
│   └── Contact.vue       # Contact section
├── styles/
│   └── creative.css      # Global styles
├── App.vue               # Root component
└── main.js               # Application entry point

public/
├── img/                  # Portfolio images
└── resume/              # Resume PDF

index.html               # HTML template
vite.config.js          # Vite configuration
```

## Deployment to Cloudflare Pages

### Prerequisites
- GitHub repository connected to Cloudflare Pages
- Cloudflare Pages project created

### Configuration

Cloudflare Pages will automatically detect the build settings:

- **Framework**: None (using Vite)
- **Build command**: `npm run build`
- **Build output directory**: `dist/`

### Deploy

Simply push to your connected GitHub branch. Cloudflare Pages will:
1. Run `npm install`
2. Run `npm run build`
3. Deploy the contents of `dist/` to Cloudflare's CDN

## Features

- ✨ Smooth scroll navigation
- 📱 Fully responsive design
- ♿ Accessible HTML and components
- 🎨 Modern gradient design
- 🚀 Fast performance with Vite
- 📦 Optimized production builds
- 🔄 Hot module replacement in development

## License

MIT

## Author

Chad Petersen
