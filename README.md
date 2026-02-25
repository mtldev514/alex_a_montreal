# alex_a_montreal

A retro-styled portfolio powered by [@mtldev514/retro-portfolio-maker](https://www.npmjs.com/package/@mtldev514/retro-portfolio-maker).

## 🚀 Quick Start

```bash
# 1. Install dependencies (includes Python Flask auto-install)
npm install

# 2. Configure your environment (IMPORTANT!)
# Edit .env file and add your Cloudinary credentials
# Get them at: https://cloudinary.com/console

# 3. Launch site + admin in parallel (recommended)
npm start
# → Site + Admin Interface: http://localhost:8000/admin.html
# → Admin API: http://localhost:5001/api/

# Or launch them separately:
npm run dev      # Site only (http://localhost:8000)
npm run admin    # Admin API only (http://localhost:5001/api/)
```

## 📁 Project Structure

- `config/` - Site configuration (app, languages, categories)
- `data/` - Your portfolio content (JSON files)
- `lang/` - Translations (en.json, fr.json, etc.)
- `assets/` - Your images and media files

## ⚙️ Environment Configuration

**IMPORTANT:** Before using the admin interface, you MUST configure your Cloudinary credentials:

1. Sign up at [cloudinary.com](https://cloudinary.com) (free tier available)
2. Get your credentials from the [Cloudinary Console](https://cloudinary.com/console)
3. Edit `.env` file and replace the placeholder values:
   ```
   CLOUDINARY_CLOUD_NAME=your_actual_cloud_name
   CLOUDINARY_API_KEY=your_actual_api_key
   CLOUDINARY_API_SECRET=your_actual_api_secret
   ```

**Optional:** For large audio/video files, add a GitHub token:
```
GITHUB_TOKEN=your_github_personal_access_token
```

## 🎨 Admin Interface

The admin interface allows you to:
- Upload and manage images via Cloudinary
- Edit content in all languages
- Add/edit/delete portfolio items
- Manage translations

Access it at **http://localhost:8000/admin/admin.html** after:
1. Running `npm start` (launches both site and API)
2. Or running both `npm run dev` and `npm run admin` in separate terminals

## 🏗️ Building for Production

```bash
# Build the static site
npm run build

# Output will be in dist/ folder
# Deploy dist/ to GitHub Pages, Netlify, Vercel, etc.
```

## 🌐 Deployment

### GitHub Pages (Automated)

This project includes a GitHub Action for automatic deployment.

1. Push your code to GitHub
2. Enable GitHub Pages in repository settings
3. On every push to `main`, the site will automatically build and deploy

### Manual Deployment

```bash
npm run build
# Then deploy the dist/ folder to your hosting provider
```

## 🔧 Configuration

### Cloudinary (for image uploads)

1. Create a free account at [Cloudinary](https://cloudinary.com)
2. Copy `.env.example` to `.env`
3. Add your Cloudinary credentials to `.env`

```bash
cp .env.example .env
nano .env  # Edit with your credentials
```

### Customization

- **Site name**: Edit `config/app.json`
- **Languages**: Edit `config/languages.json`
- **Categories**: Edit `config/categories.json`
- **Content**: Use the admin interface or edit JSON files in `data/`

## 📚 Available Commands

- `npm start` - Launch site + admin together
- `npm run dev` - Development server (site only)
- `npm run admin` - Admin interface
- `npm run build` - Build for production
- `npm run deploy` - Deploy to GitHub Pages

## 🆘 Troubleshooting

### Admin won't start

Make sure Flask is installed:

```bash
pip install flask flask-cors
```

### Images won't upload

Check your `.env` file has valid Cloudinary credentials.

### Site won't build

Make sure all required files exist in `config/`, `data/`, and `lang/` directories.

## 📖 Documentation

- [Engine Documentation](https://github.com/mtldev514/retro-portfolio-engine)
- [NPM Package](https://www.npmjs.com/package/@mtldev514/retro-portfolio-maker)

## 📄 License

MIT

---

**Made with 💜 using @mtldev514/retro-portfolio-maker**
