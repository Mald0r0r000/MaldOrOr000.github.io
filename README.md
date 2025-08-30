# Portfolio Antoine Bedos

This is a modern, performant portfolio website that showcases video and photo work. The site features a custom cursor, smooth animations, and lazy loading of media content.

## 🚀 Features

- Dynamic loading of portfolio items from `data/portfolio.json`
- Custom cursor and smooth animations
- Responsive design with mobile support
- Lazy loading of images and videos
- Keyboard navigation support
- Media hosted on Cloudflare R2 for optimal performance
- Custom domain support for media

## 🔧 Development

To run the website locally, you can use Python's built-in web server:

```bash
python3 -m http.server 8000
```

Then, open your browser and navigate to `http://localhost:8000`.

## 🛠️ Changelog

- **August 2025:**
  - Fixed a critical JavaScript syntax error that prevented the application from initializing correctly.
  - Resolved an issue where the initial video would not load or display due to incorrect activation logic.
  - Restructured the entire script to improve readability, maintainability, and performance.
  - Ensured all portfolio media (videos and images) load correctly on demand.
  - Fixed a race condition where the initial item activation failed because the DOM was not ready.
  - Corrected a critical CSS sizing issue that prevented media from being displayed.

