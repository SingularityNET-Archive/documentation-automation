---
title: Home
layout: home
nav_order: 1
---

# Getting Started with Documentation Automation

Welcome to the Documentation Automation guide. This documentation will help you set up automatic deployment of your documentation to GitHub Pages using GitHub Actions. When you update markdown files in your `docs` folder, your documentation will automatically rebuild and deploy.

## Overview

This automation system allows you to:
- Write documentation in Markdown
- Automatically deploy to GitHub Pages
- Use a modern documentation theme
- Include search functionality
- Maintain versioning through Git

## Quick Start

1. [Template repo](https://github.com/new?template_name=documentation-automation&template_owner=SingularityNET-Archive)
2. Enter Repo name, description and create repo
3. Enable GitHub Pages in your repository settings
   - Go to your repository settings on GitHub
   - Navigate to the "Pages" section
   - Under "Source", select "GitHub Actions"
4. Update `docs/_config.yml` with your repository information
5. Add markdown files to the `docs` folder
6. Push to main branch and watch your documentation deploy!

## Detailed Setup Guides

Follow these guides in order for a complete setup:

1. [Repository Setup](/documentation-automation/setup-guide/repository-setup)
   - Creating the required folder structure
   - Initial repository configuration
   - Required files overview

2. [GitHub Actions Configuration](/documentation-automation/setup-guide/github-actions-setup)
   - Understanding the workflow file
   - Configuring deployment triggers
   - Setting up required permissions

3. [Writing Documentation](/documentation-automation/writing-docs)
   - Markdown file structure
   - Adding navigation
   - Including assets
   - Best practices

## File Structure

```
docs/
├── index.md (this file)
└── setup-guide/
    ├── index.md
    ├── repository-setup.md
    └── github-actions-setup.md
└── writing-docs.md
```

## Requirements

- GitHub account with repository access
- Basic understanding of Git
- Text editor for markdown files
- Ruby (for local testing only)

## Next Steps

1. Start with [Repository Setup](/documentation-automation/setup-guide/repository-setup) to create the basic structure
2. Follow each guide in sequence
3. Check [Troubleshooting](troubleshooting.md#common-issues) if you encounter issues

For advanced customization and features, check the [just-the-docs documentation](https://just-the-docs.github.io/just-the-docs/)