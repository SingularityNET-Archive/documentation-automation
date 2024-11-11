---
title: Repository Setup
layout: default
parent: Setup Guide
nav_order: 1
---

# Repository Setup Guide

This guide will walk you through setting up your documentation automation system using our template repository.

## Creating Your Repository from Template

1. **Use the Template Repository**
   
   Click the button below to create your repository using our template:
   
   [![Use this template](https://img.shields.io/badge/Use%20this%20template-2ea44f?style=for-the-badge)](https://github.com/SingularityNET-Archive/documentation-automation/generate)

2. **Configure Repository Settings**
   - Name your repository
   - Choose public or private visibility
   - Click "Create repository from template"

The template includes the following pre-configured structure:

```
your-repository/
├── .github/
│   └── workflows/
│       └── deploy-docs.yml
├── docs/
│   ├── _config.yml
│   ├── Gemfile
│   ├── index.md
│   ├── setup-guide/
│   │   ├── index.md
│   │   ├── repository-setup.md
│   │   └── github-actions-setup.md
│   ├── writing-docs.md
│   └── troubleshooting.md
├── .gitignore
└── README.md
```

## Configuration Customization

After creating your repository from the template, you'll need to customize a few configuration files:

1. **Update `docs/_config.yml`**
   
   Modify the following values in your config file:
   ```yaml
   # Update these values to match your repository
   baseurl: "/your-repository-name"  # Replace with your repository name
   url: "https://your-username.github.io" # Replace with your GitHub pages url

   # Update auxiliary links
   aux_links:
     "GitHub":
       - "https://github.com/your-username/your-repository" # Replace with your repo url
   ```

2. **Configure GitHub Pages**
   - Go to your repository settings on GitHub
   - Navigate to the "Pages" section
   - Under "Source", select "GitHub Actions"
   - Wait for the initial deployment to complete


## Common Issues and Solutions

### Configuration Issues
- **Incorrect baseurl**: Must match your repository name exactly
- **URL format**: Should be `https://username.github.io`
- **Theme not loading**: Verify the template's `remote_theme` setting wasn't modified


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