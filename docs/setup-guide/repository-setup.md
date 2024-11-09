---
title: Repository Setup
layout: default
parent: Setup Guide
nav_order: 1
---

# Repository Setup Guide

This guide will walk you through setting up the initial repository structure for your documentation automation system.

## Initial Repository Structure

First, you'll need to create the following folder structure in your repository:

```
your-repository/
├── docs/
│   ├── _config.yml
│   ├── Gemfile
│   ├── index.md
│   ├── setup-guide/
│   ├── writing-docs.md
│   ├── testing-deployment.md
│   └── advanced/
├── .github/
│   └── workflows/
│       └── deploy-docs.yml
└── .gitignore
```

## Step-by-Step Setup

1. **Create a New Repository**
   - Go to GitHub and create a new repository
   - Clone it to your local machine:
     ```bash
     git clone https://github.com/your-username/your-repository.git
     cd your-repository
     ```

2. **Create Required Directories**
   ```bash
   mkdir -p docs/.github/workflows
   mkdir -p docs/setup-guide
   mkdir -p docs/advanced
   ```

3. **Configure GitHub Pages**
   - Go to your repository settings on GitHub
   - Navigate to the "Pages" section
   - Under "Source", select "GitHub Actions"

4. **Create Configuration Files**

   a. Create `docs/_config.yml`:
   ```yaml
   title: Documentation Automation
   description: Automate the deployment of your documentation to GitHub Pages using GitHub Actions.
   theme: just-the-docs

   # Build settings
   markdown: kramdown
   remote_theme: just-the-docs/just-the-docs

   # Set the base URL to match your GitHub Pages URL
   baseurl: "/documentation-automation"  # Replace with your repository name
   url: "https://SingularityNET-Archive.github.io" #Replace with your GitHub pages url

   # Enable or disable the site search
   search_enabled: true

   # Aux links for the upper right navigation
   aux_links:
     "GitHub":
       - "https://github.com/SingularityNET-Archive/documentation-automation" #Replace with your repo url

   # Color scheme
   color_scheme: light

   # Enable collect for search functionality
   search:
     heading_level: 2
     previews: 3
     preview_words_before: 5
     preview_words_after: 10
   ```

   b. Create `docs/Gemfile`:
   ```ruby
   source 'https://rubygems.org'

   gem "jekyll", "~> 3.9.3"
   gem "github-pages", group: :jekyll_plugins
   gem "just-the-docs"
   ```

   c. Create `.gitignore` in the root directory:
   ```
   docs/_site
   docs/.sass-cache
   docs/.jekyll-cache
   docs/.jekyll-metadata
   docs/vendor
   docs/Gemfile.lock
   ```

5. **Create Initial Index File**
   
   Create `docs/index.md` with basic content:
   ```markdown
   ---
   title: Home
   layout: home
   nav_order: 1
   ---

   # Welcome to Your Documentation
   
   Initial setup successful! Start adding your documentation content.
   ```

## Configuration Breakdown

### _config.yml Settings
1. **Basic Site Settings**
   - `title`: Your documentation site's name
   - `description`: Brief description of your documentation
   - `theme`: Specifies the Just the Docs theme

2. **Build Configuration**
   - `markdown`: Sets Kramdown as the Markdown processor
   - `remote_theme`: Uses the Just the Docs theme from GitHub

3. **URL Settings**
   - `baseurl`: Your repository name (e.g., "/documentation-automation")
   - `url`: Your GitHub Pages URL

4. **Navigation and Search**
   - `aux_links`: Configure upper right navigation links
   - `search_enabled`: Enables site-wide search
   - `search`: Configures search functionality parameters

### Gemfile Components
- `source 'https://rubygems.org'`: Specifies gem source
- `gem "jekyll"`: The static site generator
- `gem "github-pages"`: GitHub Pages compatibility package
- `gem "just-the-docs"`: The documentation theme

### .gitignore Purpose
Excludes the following from version control:
- Built site files (`_site`)
- Cache directories (`.sass-cache`, `.jekyll-cache`)
- Local environment files (`.jekyll-metadata`, `vendor`)
- Dependency lock file (`Gemfile.lock`)

## Verification Steps

1. **Install Dependencies**
   ```bash
   cd docs
   bundle install
   ```

2. **Test Local Build**
   ```bash
   bundle exec jekyll build --safe
   ```

3. **Check Repository Structure**
   ```bash
   git status
   ```
   Verify that generated files are properly ignored

4. **Initial Commit**
   ```bash
   git add .
   git commit -m "Initial documentation setup"
   git push origin main
   ```

## Common Issues and Solutions

### Configuration Issues
- **Incorrect baseurl**: Must match your repository name exactly
- **URL format**: Should be `https://username.github.io`
- **Theme not loading**: Verify `remote_theme` setting

### Dependency Issues
- **Bundle install errors**: Run `bundle update`
- **Jekyll build failures**: Verify Jekyll version compatibility
- **Theme conflicts**: Check gem versions in Gemfile

### Permission Issues
1. Check repository settings
2. Ensure you have write access
3. Verify GitHub Pages is enabled

## Next Steps

Once you've completed the repository setup:
1. Continue to [GitHub Actions Configuration](github-actions-setup.md)
2. Test the basic structure locally using Jekyll
3. Begin adding your documentation content

Remember to commit and push changes regularly to trigger the automated deployment process.