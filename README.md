# 七秩晋一·寿词 | Birthday Ci

An interactive, minimalist website celebrating a father's 71st birthday with floating poetry, vintage photographs, and a traditional red seal.

## Features

- **Floating poem characters** that drift and scatter with mouse movement
- **Interactive parallax** on three images (seal, childhood photo, film strip)
- **Draggable images** — rearrange photos freely
- **Ambient blur effect** — background characters blur for readability focus
- **Dark ink aesthetic** — deep black background with paper texture
- **Responsive** — works on desktop and tablet

## Deploy to Cloudflare Pages

### Option 1: Git-based Deployment (Recommended)

1. **Create a GitHub repository** (or GitLab/Gitea)
   ```bash
   git init
   git add .
   git commit -m "initial commit"
   git branch -M main
   git remote add origin https://github.com/YOUR_USERNAME/birthday-ci.git
   git push -u origin main
   ```

2. **Connect to Cloudflare Pages**
   - Go to [dash.cloudflare.com](https://dash.cloudflare.com)
   - Pages → Create a project → Connect to Git
   - Select your repository
   - Build settings:
     - **Framework preset**: None
     - **Build command**: (leave empty)
     - **Build output directory**: `/` (or `.`)
   - Deploy!

### Option 2: Direct Upload with Wrangler

1. **Install Wrangler CLI**
   ```bash
   npm install -g wrangler
   ```

2. **Deploy**
   ```bash
   wrangler pages deploy .
   ```

3. **Follow prompts** to authenticate and select your Pages project

### Option 3: Drag & Drop in Dashboard

1. Go to [dash.cloudflare.com](https://dash.cloudflare.com) → Pages
2. Create a project → Direct upload
3. Drag all files into the upload area
4. Deploy!

## File Structure

```
.
├── index.html          # Main page (all content embedded)
├── wrangler.toml       # Cloudflare configuration
└── README.md           # This file
```

## Customization

### Edit the Poem
Open `index.html` and find the `<div id="poem-panel">` section around line 200. Replace the text within the `<span>` tags.

### Change Colors
At the top of the `<style>` section (line 10), modify the CSS variables:
```css
:root {
  --ink: #07070a;          /* Background */
  --paper: #e8e0d0;        /* Text */
  --gold: #c9a84c;         /* Accents */
  --red: #c0392b;          /* Seal color */
}
```

### Replace Images
To replace the three images, you'll need to:
1. Convert new images to base64
2. Find the `<img>` tags in the HTML (around line 190)
3. Replace the `src` data URIs

Quick conversion:
```bash
base64 your-image.png | tr -d '\n' | xclip -selection clipboard
```

## Performance Notes

- **File size**: ~1MB (all images embedded as base64)
- **Load time**: < 1 second on typical connections
- **Compatibility**: All modern browsers (Chrome, Firefox, Safari, Edge)
- **Mobile**: Fully responsive, works on tablets and large phones

## Browser Support

- Chrome/Edge 90+
- Firefox 88+
- Safari 14+
- No IE support

## License

Created for personal use.

---

**Deployment URLs**
- If using git: `https://your-project.pages.dev`
- Custom domain: Add DNS CNAME in Cloudflare dashboard after setup

For help, see [Cloudflare Pages Docs](https://developers.cloudflare.com/pages/)
