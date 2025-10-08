# Ariana Huffmyer's Website

This is a Quarto-based academic website hosted on GitHub Pages. It includes a portfolio of research work and a fully functional lab notebook.

## Website Features

- **Home**: Landing page with quick links
- **CV/About**: Biographical information and curriculum vitae
- **Research**: Description of current and past research projects
- **Outreach & Education**: Teaching, mentoring, and outreach activities
- **Lab Notebook**: Searchable, categorized daily research notes
- **Gallery**: Image gallery for research photos

## Lab Notebook Features

The lab notebook is a key feature of this website, providing:

- **Searchable entries**: Full-text search across all notebook entries
- **Category filtering**: Filter by project, keyword, or topic
- **Date sorting**: Chronological organization with flexible sorting
- **RSS feed**: Subscribe to notebook updates
- **Quarto formatting**: Rich formatting with code, figures, and equations

## Quick Start

### Creating a New Notebook Entry

1. Copy the template file:
   ```bash
   cp posts/_template.qmd posts/YYYY-MM-DD-entry-name.qmd
   ```

2. Edit the YAML frontmatter with your entry details:
   ```yaml
   ---
   title: "Your Entry Title"
   author: "Ariana Huffmyer"
   date: "2024-01-15"
   categories: [project-name, keyword1, keyword2]
   description: "Brief description of this entry"
   ---
   ```

3. Write your content using Markdown and Quarto syntax

4. Preview locally (optional):
   ```bash
   quarto preview
   ```

5. Commit and push to GitHub - the site will automatically deploy!

### Customizing Pages

All pages are customizable by editing the `.qmd` files:

- `index.qmd` - Home page
- `about.qmd` - CV/About page
- `research.qmd` - Research page
- `outreach.qmd` - Outreach & Education page
- `gallery.qmd` - Image Gallery page
- `notebook.qmd` - Lab Notebook listing page

### Adding Images

1. Create an `images/` folder in the repository
2. Add your image files
3. Reference them in your `.qmd` files:
   ```markdown
   ![Caption](images/your-image.jpg)
   ```

## Local Development

### Prerequisites

- [Quarto](https://quarto.org/docs/get-started/) installed

### Build and Preview Locally

```bash
# Preview the site (auto-refreshes on changes)
quarto preview

# Build the site
quarto render
```

The built site will be in the `docs/` folder.

## Deployment

This site automatically deploys to GitHub Pages when you push to the `main` branch.

### Initial GitHub Pages Setup

1. Go to your repository Settings > Pages
2. Set Source to "GitHub Actions"
3. The workflow will automatically build and deploy your site

Your site will be available at: `https://ahuffmyer.github.io/website/`

## File Structure

```
website/
├── .github/
│   └── workflows/
│       └── publish.yml          # GitHub Actions deployment workflow
├── posts/                        # Lab notebook entries
│   ├── _template.qmd            # Template for new entries
│   └── 2024-01-15-welcome.qmd   # Sample entry
├── _quarto.yml                   # Quarto configuration
├── index.qmd                     # Home page
├── about.qmd                     # CV/About page
├── research.qmd                  # Research page
├── outreach.qmd                  # Outreach & Education page
├── notebook.qmd                  # Lab Notebook listing page
├── gallery.qmd                   # Image Gallery page
├── styles.css                    # Custom CSS styles
└── .gitignore                    # Git ignore file
```

## Technologies Used

- **Quarto**: Scientific and technical publishing system
- **GitHub Pages**: Free web hosting
- **GitHub Actions**: Automated deployment
- **Markdown**: Content formatting
- **YAML**: Configuration and metadata

## Customization

### Changing the Theme

Edit `_quarto.yml` to change the theme:

```yaml
format:
  html:
    theme: cosmo  # Options: cosmo, flatly, darkly, etc.
```

See [Quarto themes](https://quarto.org/docs/output-formats/html-themes.html) for more options.

### Customizing Styles

Edit `styles.css` to customize the appearance of your site.

### Modifying the Navigation

Edit the navbar section in `_quarto.yml`:

```yaml
website:
  navbar:
    left:
      - text: "Page Name"
        href: page.qmd
```

## Support

For Quarto help, see the [Quarto documentation](https://quarto.org/docs/guide/).

## License

Content © 2024 Ariana Huffmyer
