# Quick Start Guide

## Adding Your First Notebook Entry

1. **Copy the template:**
   ```bash
   cp posts/_template.qmd posts/2024-01-16-my-first-entry.qmd
   ```

2. **Edit the file** and update the YAML frontmatter:
   ```yaml
   ---
   title: "My First Lab Entry"
   author: "Ariana Huffmyer"
   date: "2024-01-16"
   categories: [project-coral, methods, fieldwork]
   description: "Description of today's work"
   draft: false
   ---
   ```

3. **Write your content** using Markdown

4. **Preview locally** (optional):
   ```bash
   quarto preview
   ```

5. **Commit and push** to GitHub:
   ```bash
   git add posts/2024-01-16-my-first-entry.qmd
   git commit -m "Add lab entry for 2024-01-16"
   git push
   ```

The site will automatically rebuild and deploy!

## Customizing Your Pages

### Update Your CV/About Page

Edit `about.qmd` to add your:
- Education history
- Publications
- Professional experience
- Contact information

### Add Research Projects

Edit `research.qmd` to describe your research projects, methods, and findings.

### Share Your Outreach Work

Edit `outreach.qmd` to highlight your teaching, mentoring, and community engagement.

### Build an Image Gallery

1. Create an `images/` folder
2. Add your photos
3. Edit `gallery.qmd` to reference them:
   ```markdown
   ![Photo caption](images/photo.jpg)
   ```

## Organizing Notebook Entries

### Use Meaningful Categories

Good category examples:
- Project names: `coral-bleaching`, `RNA-seq-analysis`
- Methods: `fieldwork`, `lab-work`, `data-analysis`
- Topics: `molecular-biology`, `statistics`, `microscopy`

### Consistent Naming

Use a consistent file naming pattern:
- `YYYY-MM-DD-descriptive-name.qmd`
- Example: `2024-01-16-coral-sampling-reef-site-a.qmd`

### Link Related Entries

Reference previous entries in your notes:
```markdown
See my previous entry on [coral sampling](2024-01-10-coral-sampling.qmd).
```

## GitHub Pages Setup

After you push your code to GitHub:

1. Go to repository **Settings** → **Pages**
2. Under "Source", select **GitHub Actions**
3. Wait for the workflow to complete (check the Actions tab)
4. Your site will be live at: `https://ahuffmyer.github.io/website/`

## Tips

- **Preview locally** before pushing to see how your changes look
- **Use categories consistently** for better searchability
- **Add images** to make your notebook more visual
- **Write regularly** - the notebook is most useful when updated frequently
- **Back up important data** - commit raw data files to a separate repository

## Getting Help

- Quarto Documentation: https://quarto.org/docs/guide/
- Markdown Guide: https://www.markdownguide.org/
- Quarto Community: https://github.com/quarto-dev/quarto-cli/discussions

## Next Steps

1. Customize all pages with your information
2. Create your first real notebook entry
3. Add images to the gallery
4. Set up GitHub Pages
5. Share your website URL!
