---
title: GitHub Actions Setup
layout: default
parent: Setup Guide
nav_order: 2
---

# GitHub Actions Configuration

This guide explains how to set up and configure GitHub Actions for automatic documentation deployment.

## Understanding the Workflow

The GitHub Actions workflow automates the process of building and deploying your documentation to GitHub Pages. Here's a detailed breakdown of the workflow configuration.

## Workflow File Setup

Create `.github/workflows/deploy-docs.yml` with the following configuration:

```yaml
name: Deploy Documentation

on:
  push:
    branches:
      - main
    paths:
      - 'docs/**'
      - '.github/workflows/deploy-docs.yml'

jobs:
  deploy-docs:
    runs-on: ubuntu-latest
    permissions:
      pages: write
      id-token: write
      contents: read
    environment:
      name: github-pages
      url: ${{ steps.deployment.outputs.page_url }}
    steps:
      - name: Checkout
        uses: actions/checkout@v3

      - name: Setup Pages
        uses: actions/configure-pages@v3

      - name: Setup Ruby
        uses: ruby/setup-ruby@v1
        with:
          ruby-version: '3.1'
          bundler-cache: true
          working-directory: docs

      - name: Build with Jekyll
        working-directory: docs
        run: |
          bundle install
          bundle exec jekyll build --baseurl "${{ github.event.repository.name }}"
        env:
          JEKYLL_ENV: production

      - name: Upload artifact
        uses: actions/upload-pages-artifact@v2
        with:
          path: docs/_site

      - name: Deploy to GitHub Pages
        id: deployment
        uses: actions/deploy-pages@v2
```

## Configuration Breakdown

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
- Triggers on pushes to the main branch
- Only runs when changes are made to documentation or workflow files

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
- Sets required permissions for GitHub Pages deployment
- Configures the deployment environment

## Required GitHub Settings

1. **Enable GitHub Actions**
   - Go to repository Settings → Actions → General
   - Enable "Allow all actions and reusable workflows"

2. **Configure GitHub Pages**
   - Go to Settings → Pages
   - Source: Deploy from a branch
   - Branch: gh-pages (created by the action)

3. **Repository Permissions**
   - Ensure the repository has GitHub Pages enabled
   - Check that Actions have necessary permissions

## Environment Variables

The workflow uses several environment variables:

| Variable | Description | Required |
|----------|-------------|-----------|
| `JEKYLL_ENV` | Jekyll environment (production/development) | Yes |
| `github.event.repository.name` | Repository name for baseurl | Auto-set |

## Testing the Workflow

1. **Initial Test**
   - Make a small change to any documentation file
   - Commit and push to main branch
   - Check Actions tab for workflow status

2. **Monitoring Deployment**
   - Watch the workflow execution
   - Check each step for success/failure
   - Verify the deployment URL

## Troubleshooting

### Common Issues

1. **Build Failures**
   - Check Ruby version compatibility
   - Verify Gemfile contents
   - Ensure all dependencies are listed

2. **Deployment Failures**
   - Verify GitHub Pages is enabled
   - Check repository permissions
   - Validate workflow file syntax

3. **Path Issues**
   - Confirm working-directory settings
   - Check file paths in configuration
   - Verify baseurl setting

### Debug Steps

1. Enable debug logging:
   ```yaml
   env:
     ACTIONS_RUNNER_DEBUG: true
   ```

2. Check workflow logs in GitHub Actions tab

3. Validate local build:
   ```bash
   cd docs
   bundle install
   bundle exec jekyll build
   ```

## Advanced Configuration

### Custom Build Commands
```yaml
- name: Build with Jekyll
  working-directory: docs
  run: |
    bundle install
    bundle exec jekyll build --config _config.yml,_config_prod.yml
  env:
    JEKYLL_ENV: production
```

### Cache Configuration
```yaml
- name: Setup Ruby
  uses: ruby/setup-ruby@v1
  with:
    ruby-version: '3.1'
    bundler-cache: true
    cache-version: 1
```

## Next Steps

After configuring GitHub Actions:
1. Proceed to [Test Deployment](../testing-deployment.md)
2. Test the complete deployment pipeline
3. Add your documentation content

Remember to check the workflow status after each significant change to ensure proper deployment.