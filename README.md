# Trakking Website

GPS tracking solution for field teams.

## 🚀 Project Structure

Inside of your Astro project, you'll see the following folders and files:

```text
/
├── public/
├── src/
│   ├── components/
│   ├── layouts/
│   ├── i18n/
│   └── pages/
└── package.json
```

Astro looks for `.astro` or `.md` files in the `src/pages/` directory. Each page is exposed as a route based on its file name.

## 🧞 Commands

All commands are run from the root of the project, from a terminal:

| Command                   | Action                                           |
| :------------------------ | :----------------------------------------------- |
| `npm install`             | Installs dependencies                            |
| `npm run dev`             | Starts local dev server at `localhost:4321`      |
| `npm run build`           | Build your production site to `./dist/`          |
| `npm run preview`         | Preview your build locally, before deploying     |
| `npm run astro ...`       | Run CLI commands like `astro add`, `astro check` |
| `npm run astro -- --help` | Get help using the Astro CLI                     |

## 🚀 Deployment to GitHub Pages

### Initial Setup

1. **Push your code to GitHub:**
   ```bash
   git add .
   git commit -m "Configure GitHub Pages deployment"
   git remote add origin git@github.com:f1lander/trakking-website.git
   git branch -M main
   git push -u origin main
   ```

2. **Enable GitHub Pages in your repository:**
   - Go to your repository on GitHub: https://github.com/f1lander/trakking-website
   - Click on "Settings"
   - Scroll down to "Pages" in the left sidebar
   - Under "Source", select "GitHub Actions"
   - Save your changes

3. **The workflow will automatically deploy after you push to main**

### Custom Domain Setup (Namecheap)

1. **In Namecheap:**
   - Go to your domain's DNS settings
   - Add a CNAME record:
     - Type: `CNAME`
     - Host: `@` or `www` (depending on what you want)
     - Value: `f1lander.github.io`
     - TTL: Automatic

2. **In GitHub:**
   - Create a file named `CNAME` in the `public/` directory with your domain:
     ```bash
     echo "yourdomain.com" > public/CNAME
     ```
   - Commit and push:
     ```bash
     git add public/CNAME
     git commit -m "Add custom domain"
     git push
     ```

3. **Once deployed, go back to repository Settings > Pages**
   - Under "Custom domain", enter your domain
   - GitHub will verify the domain

### After Custom Domain is Set Up

Update `astro.config.mjs` to remove the base path:

```javascript
export default defineConfig({
  site: 'https://yourdomain.com',
});
```

Then commit and push the changes.
