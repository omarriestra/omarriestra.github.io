# GitHub Pages Setup Guide

## 📋 Configuration Steps

To enable GitHub Pages for this repository, follow these steps:

### 1. Go to Repository Settings
Navigate to: `https://github.com/omarriestra/omarriestra.github.io/settings/pages`

### 2. Configure Source
Under "Build and deployment":
- **Source**: Select "GitHub Actions"
- The workflow file `.github/workflows/hugo-deploy.yml` will handle the build

### 3. Verify Workflow
- Go to the "Actions" tab in your repository
- You should see a workflow run after pushing to `main`
- Wait for it to complete (usually 1-2 minutes)

### 4. Access Your Site
Once the deployment completes, your site will be available at:
```
https://omarriestra.github.io/
```

## 🔧 Workflow Details

The GitHub Actions workflow (`hugo-deploy.yml`):
1. Installs Hugo Extended v0.128.0
2. Checks out the repository with submodules (for the Congo theme)
3. Builds the site with Hugo
4. Deploys to GitHub Pages

## 🚀 Publishing New Content

Every time you push to the `main` branch:
1. The workflow automatically triggers
2. Hugo rebuilds the entire site
3. Changes are deployed to GitHub Pages
4. Your site updates within 1-2 minutes

## 📝 Manual Deployment

You can also trigger deployment manually:
1. Go to Actions tab
2. Select "Deploy Hugo site to GitHub Pages"
3. Click "Run workflow"
4. Select branch and run

## 🔍 Troubleshooting

### Build Fails
- Check the Actions tab for error logs
- Verify `hugo.toml` configuration
- Ensure theme submodule is properly initialized

### Site Not Updating
- Verify the workflow completed successfully
- Clear browser cache
- Check that you're pushing to the correct branch

### 404 Errors
- Ensure `baseURL` in `hugo.toml` matches your GitHub Pages URL
- Verify all internal links are correct

## 🛠️ Local Development

To preview locally before pushing:

```bash
# Start Hugo development server
hugo server --buildDrafts

# Visit http://localhost:1313
```

To build locally (same as GitHub Actions):

```bash
# Build site
hugo --gc --minify

# Output will be in ./public/
```

## 📚 Resources

- [Hugo Documentation](https://gohugo.io/documentation/)
- [GitHub Pages Documentation](https://docs.github.com/en/pages)
- [Congo Theme Documentation](https://jpanther.github.io/congo/)

## ✅ Checklist

After merging to `main`, verify:
- [ ] GitHub Actions workflow completes successfully
- [ ] Site is accessible at https://omarriestra.github.io/
- [ ] All pages render correctly
- [ ] Navigation works properly
- [ ] Images load correctly
- [ ] Theme styling is applied

---

*This setup uses GitHub Actions for continuous deployment. Every push to main automatically updates your live site.*
