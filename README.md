# Documentation Automation Template

A template for automatically deploying documentation to GitHub Pages using GitHub Actions. This template uses Just the Docs theme and GitHub Actions for automated builds and deployments.

Deployed docs folder [here](https://singularitynet-archive.github.io/documentation-automation/)

## Quick Start

If you already created a new repo with this template, skip to [Setup Steps](#setup-steps)

[![Use this template](https://img.shields.io/badge/Use%20this%20template-2ea44f?style=for-the-badge)](https://github.com/SingularityNET-Archive/documentation-automation/generate)

Click the "Use this template" button above or use the badge to create a new repository from this template.

## Features

- 🚀 Automatic deployment to GitHub Pages
- 📖 Modern documentation theme using Just the Docs
- 🔍 Built-in search functionality
- 📱 Mobile-responsive design
- 🔄 CI/CD pipeline using GitHub Actions
- 📝 Markdown-based content
- 🎨 Customizable theme and styling

## Setup Steps

1. **Configure GitHub Pages**
   - Go to your repository's Settings
   - Navigate to "Pages" section
   - Under "Build and deployment", select "GitHub Actions" as the source

2. **Update Configuration**
   
   Edit `docs/_config.yml` and update these key settings:
   ```yaml
   # Replace with your repository name
   baseurl: "/your-repository-name"  
   
   # Replace with your GitHub Pages URL
   url: "https://your-username.github.io"
   
   # Update repository link
   aux_links:
     "GitHub":
       - "https://github.com/your-username/your-repository"
   ```

3. **Verify Deployment**
   - Make a small change to any file in the `docs` folder
   - Commit and push to the main branch
   - Go to Actions tab to watch the deployment
   - Once complete, your documentation will be available at:
     `https://your-username.github.io/your-repository-name/`


## Documentation

Start adding your documentation in the `docs` folder using markdown files. Any push to the main branch will automatically trigger a new build and deployment.

---
⭐️ If you find this template helpful, don't forget to star it!