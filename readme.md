# Hugo Blog Development and Deployment

This document outlines the steps for developing and deploying the blog hosted on GitHub Pages.

---

## Development Workflow

### 1. Switch to the `hugo` Branch
All development work, including writing blog posts, is done on the `hugo` branch.

### 2. Writing Blog Posts
- Blog posts are created in the `content/` directory.
- Follow Hugo's guidelines for content organization and front matter.

### 3. Local Testing
To test the site locally:

```bash
hugo server --baseURL="http://localhost:1313/zarxstar.github.io/" --cleanDestinationDir
```
- This starts a local server for previewing the blog at `http://localhost:1313/zarxstar.github.io/`.
- Changes are automatically reflected during development.

---

## Deployment Workflow

### 1. Generate Static Files for Deployment
Switch to the `hugo` branch and regenerate the `public/` directory with the correct base URL for production:

```bash
hugo --baseURL="https://zarxstar.github.io/" --cleanDestinationDir
```

### 2. Deploy to GitHub Pages
1. Switch to the deployment branch (`github-pages`):
   ```bash
   git checkout github-pages
   ```
2. Copy all files from the `public/` directory to the root:
   ```bash
   cp -r public/* .
   ```
3. Commit and push the changes:
   ```bash
   git add .
   git commit -m "Deploy updated site"
   git push origin github-pages
   ```

---

## Summary of Commands

### Development
```bash
git checkout hugo
hugo server --baseURL="http://localhost:1313/zarxstar.github.io/" --cleanDestinationDir
```

### Deployment
```bash
hugo --baseURL="https://zarxstar.github.io/" --cleanDestinationDir
git checkout github-pages
cp -r public/* .
git add .
git commit -m "Deploy updated site"
git push origin github-pages
```

---

## Notes
- Always ensure the `baseURL` is set correctly for development (`http://localhost:1313/zarxstar.github.io/`) and production (`https://zarxstar.github.io/`).
- Verify the site locally before deploying by testing with the correct production `baseURL`.
