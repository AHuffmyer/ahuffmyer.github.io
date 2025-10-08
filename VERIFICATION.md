# Website Verification Checklist

Use this checklist to verify that everything is working correctly.

## ✅ Pre-Deployment Checks

### Files Present
- [ ] `_quarto.yml` - Configuration file
- [ ] `index.qmd` - Home page
- [ ] `about.qmd` - CV/About page
- [ ] `research.qmd` - Research page
- [ ] `outreach.qmd` - Outreach page
- [ ] `notebook.qmd` - Lab notebook listing
- [ ] `gallery.qmd` - Image gallery
- [ ] `posts/_template.qmd` - Template file
- [ ] `posts/2024-01-15-welcome.qmd` - Sample entry
- [ ] `.github/workflows/publish.yml` - Deployment workflow
- [ ] `README.md` - Documentation
- [ ] `QUICKSTART.md` - Quick guide
- [ ] `DEPLOYMENT.md` - Deployment guide

### Build Test
```bash
cd /home/runner/work/website/website
quarto render
```

Expected output:
- ✅ No errors
- ✅ `docs/` folder created
- ✅ All HTML files generated
- ✅ `notebook.xml` RSS feed created

## ✅ Deployment Checks

### GitHub Pages Setup
1. [ ] Repository pushed to GitHub
2. [ ] Go to repository Settings
3. [ ] Navigate to Pages section
4. [ ] Source set to "GitHub Actions"
5. [ ] No errors in Actions tab

### First Deployment
1. [ ] Push to `main` branch triggered
2. [ ] Workflow "Deploy Quarto Website to GitHub Pages" started
3. [ ] Build job completed successfully
4. [ ] Deploy job completed successfully
5. [ ] Site accessible at `https://ahuffmyer.github.io/website/`

## ✅ Website Functionality Checks

### Navigation
- [ ] Home page loads
- [ ] All menu items work (CV/About, Research, Outreach, Notebook, Gallery)
- [ ] Navigation bar appears on all pages
- [ ] GitHub icon links to profile
- [ ] Footer displays correctly

### Home Page
- [ ] Title displays correctly
- [ ] Quick links work
- [ ] Content renders properly

### CV/About Page
- [ ] Page loads
- [ ] Template content visible
- [ ] Table of contents works

### Research Page
- [ ] Page loads
- [ ] Template sections visible

### Outreach & Education Page
- [ ] Page loads
- [ ] Template sections visible

### Lab Notebook Page
- [ ] Page loads
- [ ] Sample entry appears in listing
- [ ] Categories shown (getting-started, tutorial, setup)
- [ ] "Order By" dropdown works
- [ ] "Filter" search box present
- [ ] Click on entry opens detail page

### Sample Notebook Entry
- [ ] Entry page loads (`posts/2024-01-15-welcome.html`)
- [ ] Title and metadata display
- [ ] Categories are clickable links
- [ ] Table of contents appears
- [ ] All sections render correctly
- [ ] Code examples display properly

### Gallery Page
- [ ] Page loads
- [ ] Template instructions visible

### Search Functionality
- [ ] Search icon appears in navigation
- [ ] Search box opens when clicked
- [ ] Can search across site content

### RSS Feed
- [ ] `notebook.xml` accessible at `/notebook.xml`
- [ ] Contains sample entry
- [ ] Valid XML format

## ✅ Customization Checks

### After Editing Content
1. [ ] Edit a `.qmd` file locally
2. [ ] Run `quarto render` (optional - test locally)
3. [ ] Commit and push to main
4. [ ] Workflow runs automatically
5. [ ] Changes appear on live site

### Creating New Notebook Entry
1. [ ] Copy template: `cp posts/_template.qmd posts/test-entry.qmd`
2. [ ] Edit metadata (title, date, categories)
3. [ ] Add some content
4. [ ] Commit and push
5. [ ] Entry appears in notebook listing
6. [ ] Entry is searchable
7. [ ] Categories work

## ✅ Performance Checks

### Build Time
- [ ] Local build completes in < 30 seconds
- [ ] GitHub Actions build completes in < 5 minutes
- [ ] No timeout errors

### Page Load
- [ ] Pages load quickly
- [ ] No 404 errors
- [ ] Images load (if added)
- [ ] CSS styles apply correctly

## 🐛 Troubleshooting

### Build Fails Locally
- Check that Quarto is installed: `quarto --version`
- Look for errors in `.qmd` files
- Ensure YAML frontmatter is valid
- Check that code blocks with executable code have `eval: false`

### GitHub Actions Fails
- Check Actions tab for error messages
- Verify workflow file syntax
- Ensure repository is public or has GitHub Pages enabled
- Check that `.qmd` files render locally

### Site Not Updating
- Verify workflow completed successfully
- Clear browser cache
- Wait a few minutes for CDN update
- Check that changes were pushed to `main` branch

### 404 Error on Site
- Verify GitHub Pages source is set to "GitHub Actions"
- Check that workflow deployed successfully
- Ensure repository is public (or you have GitHub Pro)

### Search Not Working
- Verify `search.json` was generated
- Check browser console for errors
- Try refreshing the page

### Categories Not Filtering
- Ensure categories are specified in entry frontmatter
- Check that categories are in array format: `[cat1, cat2]`
- Verify `listings.json` contains category data

## ✅ Success Indicators

All of these should be true for a successful deployment:

1. ✅ Quarto builds locally without errors
2. ✅ GitHub Actions workflow completes successfully
3. ✅ Site is accessible at the GitHub Pages URL
4. ✅ All navigation links work
5. ✅ Lab notebook listing displays entries
6. ✅ Search and filter functionality works
7. ✅ Individual notebook entries display correctly
8. ✅ Categories are clickable and filter entries
9. ✅ RSS feed is accessible
10. ✅ Pages are customizable by editing `.qmd` files

## 📝 Notes

- Build artifacts (`docs/` folder) are excluded by `.gitignore`
- GitHub Actions handles the build and deployment
- Local builds are optional but useful for testing
- All content is version controlled in Git

---

**Last Updated**: 2024
**Status**: Ready for deployment ✅
