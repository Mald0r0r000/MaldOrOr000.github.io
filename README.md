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

## 🏗️ Project Structure

```
.
├── admin/                  # Admin interface configuration
│   ├── config.yml          # CMS configuration
│   └── index.html          # Admin interface
├── data/
│   └── portfolio.json      # Portfolio content (videos & photos)
├── .env                    # Environment variables (not versioned)
├── .gitignore              # Git ignore rules
├── CNAME                   # Custom domain configuration
└── index.html              # Main website entry point
```

## ⚙️ Environment Setup

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/ANTOINEBEDOS_WEBSITE.git
   cd ANTOINEBEDOS_WEBSITE
   ```

2. Copy the example environment file:
   ```bash
   cp .env.example .env
   ```

3. Edit the `.env` file with your Cloudflare R2 credentials and site configuration.

## 🖥️ Local Development

1. Start a local development server:
   ```bash
   # Using Python (built-in)
   python3 -m http.server 8000
   
   # Or using Node.js with live-reload
   npx live-server
   ```

2. Open `http://localhost:8000` in your browser.

## ☁️ Cloudflare R2 Setup

1. Create an R2 bucket in your Cloudflare dashboard
2. Generate API credentials with read/write permissions
3. Update the `.env` file with your R2 credentials
4. Configure CORS settings in your R2 bucket to allow requests from your domain

## 🚀 Deployment

### GitHub Pages
1. Push your code to the `main` branch
2. Enable GitHub Pages in your repository settings
3. Set the source to `main` branch and `/` root directory

### Custom Domain
1. Update the `CNAME` file with your domain
2. Configure DNS settings to point to GitHub Pages
3. Enable HTTPS in your GitHub Pages settings

## 🔧 Managing Media

### Uploading Media to R2

1. Install `rclone` if not already installed:
   ```bash
   # macOS
   brew install rclone
   ```

2. Configure rclone with your R2 credentials:
   ```bash
   rclone config create r2 s3 \
     provider=Cloudflare \
     access_key_id=YOUR_ACCESS_KEY \
     secret_access_key=YOUR_SECRET_KEY \
     endpoint=https://${R2_ACCOUNT_ID}.r2.cloudflarestorage.com
   ```

3. Upload media files:
   ```bash
   rclone sync ./content/ r2:antoine-bedos-media --progress
   ```

### Updating Media URLs

1. Edit `data/portfolio.json` to update media URLs to use your R2 bucket URL
2. Example format: `https://media.antoine-bedos.com/path/to/media.jpg`

## 📝 Content Management

- Edit `data/portfolio.json` to manage portfolio items
- Each item supports:
  - `active`: Boolean to show/hide item
  - `order`: Display order (ascending)
  - `media`: URL to the media file
  - `type`: Media type ('video' or 'image')
  - `title`: Item title
  - `description`: Item description

## 📱 Responsive Design

The site is fully responsive and works on:
- Desktop (1920px+)
- Laptops (1024px+)
- Tablets (768px+)
- Mobile devices (320px+)

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- [Cloudflare R2](https://developers.cloudflare.com/r2/) for media storage
- [GitHub Pages](https://pages.github.com/) for hosting
