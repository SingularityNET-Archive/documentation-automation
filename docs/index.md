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

1. [Fork or clone this repository](https://github.com/SingularityNET-Archive/documentation-automation)
2. Enable GitHub Pages in your repository settings
3. Update `docs/_config.yml` with your repository information
4. Add markdown files to the `docs` folder
5. Push to main branch and watch your documentation deploy!

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

4. [Testing and Deployment](/documentation-automation/testing-deployment)
   - Local testing
   - Deployment verification
   - Troubleshooting common issues

## File Structure

```
docs/
├── index.md (this file)
└── setup-guide/
    ├── index.md
    ├── repository-setup.md
    └── github-actions-setup.md
├── writing-docs.md
├── testing-deployment.md
└── advanced/
    ├── customization.md
    ├── navigation.md
    └── search.md
```

## Requirements

- GitHub account with repository access
- Basic understanding of Git
- Text editor for markdown files
- Ruby (for local testing only)

## Next Steps

1. Start with [Repository Setup](/documentation-automation/setup-guide/repository-setup) to create the basic structure
2. Follow each guide in sequence
3. Check [Troubleshooting](testing-deployment.md#troubleshooting) if you encounter issues

For advanced customization and features, check the [Advanced Topics](/documentation-automation/advanced/) section.