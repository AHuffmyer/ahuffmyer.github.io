# Deployment Guide

## GitHub Pages Setup

After pushing this code to the `main` branch, follow these steps to enable GitHub Pages:

### 1. Enable GitHub Pages

1. Go to your repository on GitHub
2. Click **Settings** (top navigation)
3. Click **Pages** (left sidebar)
4. Under **Source**, select **GitHub Actions**
5. The site will automatically deploy when you push to `main`

### 2. Verify Deployment

1. Go to the **Actions** tab in your repository
2. You should see a workflow run called "Deploy Quarto Website to GitHub Pages"
3. Wait for it to complete (usually 2-3 minutes)
4. Once complete, your site will be live at: `https://ahuffmyer.github.io/website/`

### 3. Custom Domain (Optional)

If you want to use a custom domain:

1. In repository **Settings** → **Pages**
2. Add your custom domain in the "Custom domain" field
3. Update `_quarto.yml` with your custom domain URL:
   ```yaml
   website:
     site-url: "https://yourdomain.com"
   ```

## Workflow Details

The GitHub Actions workflow (`.github/workflows/publish.yml`) automatically:

1. Checks out your code
2. Installs Quarto
3. Renders all `.qmd` files to HTML
4. Deploys the `docs/` folder to GitHub Pages

## Troubleshooting

### Workflow Fails

If the deployment fails:

1. Check the **Actions** tab for error messages
2. Ensure all `.qmd` files render locally: `quarto render`
3. Check that code blocks with executable code have `eval: false` or that required packages are installed

### Site Not Updating

If changes don't appear:

1. Verify the workflow completed successfully in **Actions**
2. Clear your browser cache
3. Wait a few minutes for CDN to update

### 404 Error

If you get a 404:

1. Ensure GitHub Pages is set to "GitHub Actions" source
2. Verify the workflow completed successfully
3. Check that the repository is public (or you have GitHub Pro for private repos)

## Local Development

### Preview Changes Locally

Before pushing, preview your changes:

```bash
# Start live preview server (auto-refreshes on save)
quarto preview

# Or build once
quarto render
```

The preview will be available at `http://localhost:4200` (or another port if specified).

### Building for Production

The workflow builds automatically, but you can test the build locally:

```bash
quarto render
```

This creates the `docs/` folder with all HTML files.

## Updating the Site

### Quick Update Workflow

1. **Edit files locally** (or directly on GitHub)
2. **Commit changes**: `git commit -am "Update content"`
3. **Push to main**: `git push origin main`
4. **Wait 2-3 minutes** for automatic deployment
5. **View changes** at your site URL

### Adding New Pages

1. Create a new `.qmd` file (e.g., `new-page.qmd`)
2. Add it to the navbar in `_quarto.yml`:
   ```yaml
   website:
     navbar:
       left:
         - text: "New Page"
           href: new-page.qmd
   ```
3. Commit and push

## Dependencies

The workflow automatically handles:

- Installing Quarto (v1.4.549)
- Rendering all Quarto documents
- Deploying to GitHub Pages

No additional setup required!

## Security Notes

- The workflow uses GitHub's `GITHUB_TOKEN` automatically
- No secrets or API keys need to be configured
- The workflow has minimal permissions (contents: read, pages: write)

## Performance

- Initial build: ~2-3 minutes
- Subsequent builds: ~1-2 minutes
- Site is served via GitHub's CDN for fast global access

## Monitoring

Check deployment status:

1. **Actions tab**: See workflow runs and logs
2. **Environments**: See deployment history and status
3. **Pages settings**: See current deployment URL

Your site is now ready to use! 🎉
