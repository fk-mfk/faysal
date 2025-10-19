# TrailTrustMedia - Publicity & Review Agency Website

A modern, SEO-optimized static website built with Angular 18+ for TrailTrustMedia, a publicity and review agency specializing in travel and bus businesses.

## Features

- ✅ **Angular 18+ with Standalone Components** - Modern architecture using signals and standalone components
- ✅ **Server-Side Rendering (SSR)** - Angular Universal for optimal SEO performance
- ✅ **Mobile-First Responsive Design** - Optimized for all devices
- ✅ **SEO Optimized** - Meta tags, structured data, sitemap, and robots.txt
- ✅ **Core Web Vitals Optimized** - Fast loading times and excellent performance
- ✅ **Complete Feature Set**:
  - Homepage with hero, services, metrics, and testimonials
  - About Us page with team and company story
  - Services page with detailed offerings and pricing
  - Portfolio with case studies and success stories
  - Reviews & testimonials showcase
  - Blog with article listing and detail pages
  - Multi-step contact form

## Project Structure

```
trailtrustmedia/
├── src/
│   ├── app/
│   │   ├── core/
│   │   │   ├── components/       # Header, Footer
│   │   │   ├── models/          # Data models
│   │   │   └── services/        # Data service, SEO service
│   │   ├── features/
│   │   │   ├── home/            # Homepage
│   │   │   ├── about/           # About page
│   │   │   ├── services/        # Services page
│   │   │   ├── portfolio/       # Portfolio page
│   │   │   ├── reviews/         # Reviews page
│   │   │   ├── blog/            # Blog listing & detail
│   │   │   └── contact/         # Contact form
│   │   ├── app.component.ts
│   │   ├── app.config.ts
│   │   └── app.routes.ts
│   ├── index.html
│   ├── main.ts
│   ├── main.server.ts
│   └── styles.scss
├── public/
│   ├── robots.txt
│   ├── sitemap.xml
│   └── favicon.ico
├── angular.json
├── package.json
├── tsconfig.json
└── server.ts
```

## Prerequisites

- Node.js 18.x or higher
- npm or yarn

## Installation

1. Install dependencies:
```bash
npm install
```

## Development

Run the development server:
```bash
npm start
```

Navigate to `http://localhost:4200/`. The application will automatically reload if you change any of the source files.

## Build

Build the project for production:
```bash
npm run build:static
```

The build artifacts will be stored in the `dist/` directory.

## Build with SSR

To build with server-side rendering:
```bash
npm run build:ssr
```

## Deployment

### Netlify

1. Build command: `npm run build:static`
2. Publish directory: `dist/trailtrustmedia/browser`

### Vercel

1. Build command: `npm run build:static`
2. Output directory: `dist/trailtrustmedia/browser`

### GitHub Pages

1. Build the project: `npm run build:static`
2. Deploy the `dist/trailtrustmedia/browser` directory

## SEO Features

- ✅ Meta tags for all pages (title, description, keywords)
- ✅ Open Graph tags for social sharing
- ✅ Twitter Card tags
- ✅ Structured data (JSON-LD) for organization schema
- ✅ Sitemap.xml
- ✅ Robots.txt
- ✅ Canonical URLs
- ✅ Server-side rendering for search engines

## Performance Optimizations

- Lazy loading of routes
- Image optimization with lazy loading
- Bundle size optimization (target: <500KB)
- Core Web Vitals optimized
- Service Worker ready (can be enabled)
- Critical CSS inlining

## Browser Support

- Chrome (latest)
- Firefox (latest)
- Safari (latest)
- Edge (latest)
- Mobile browsers

## License

Copyright © 2024 TrailTrustMedia. All rights reserved.

## Contact

For questions or support:
- Email: inquiry@trailtrustmedia.com
- Phone: +91 937-3333-613
- Website: https://trailtrustmedia.com



