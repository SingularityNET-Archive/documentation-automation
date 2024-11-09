---
layout: default
title: GitHub Actions Setup
parent: Setup Guide
nav_order: 3
---

# GitHub Actions Setup
<!-- github-actions-setup.md -->

## Understanding the Workflow

The GitHub Actions workflow automates the documentation deployment process. Here's a detailed breakdown of each component:

### Trigger Configuration

```yaml
on:
  push:
    branches:
      - main
    paths:
      - 'docs/**'
      - '.github/workflows/deploy-docs.yml'
```

This configuration:
- Triggers on pushes to the main branch
- Only runs when documentation or workflow files change

### Permissions and Environment

```yaml
permissions:
  pages: write
  id-token: write
  contents: read
environment:
  name: github-pages
  url: ${{ steps.deployment.outputs.page_url }}
```

### Step-by-Step Process

1. **Checkout**
   - Pulls repository content
   - Prepares workspace

2. **Setup**
   - Configures Ruby environment
   - Installs dependencies

3. **Build**
   - Generates static site
   - Prepares for deployment

4. **Deploy**
   - Uploads to GitHub Pages
   - Updates documentation site

[← Repository Setup](repository-setup.md) | [Jekyll Setup →](jekyll-setup.md)
