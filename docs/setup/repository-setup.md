---
layout: default
title: Repository Setup
parent: setup
nav_order: 2
---

# Repository Setup
<!-- repository-setup.md -->

## Initial Repository Setup

### Creating the Repository Structure

Create the following folder structure in your repository:

```
your-repository/
├── .github/
│   └── workflows/
│       └── deploy-docs.yml
├── docs/
│   ├── _config.yml
│   ├── Gemfile
│   └── index.md
```

### Required Files

1. Create `.github/workflows/deploy-docs.yml`:
   ```yaml
   name: Deploy Documentation
   # (full workflow file content as shown earlier)
   ```

2. Create `docs/Gemfile`:
   ```ruby
   source 'https://rubygems.org'
   # (Gemfile content as shown earlier)
   ```

3. Create `docs/_config.yml`:
   ```yaml
   title: Your Documentation Title
   # (_config.yml content as shown earlier)
   ```

### Configuration Steps

1. **Repository Settings**
   - Go to Settings → Pages
   - Configure source branch as `gh-pages`
   - Enable GitHub Actions permissions

2. **Branch Protection** (Optional)
   - Set up branch protection rules
   - Configure required status checks

[← Back to Getting Started](index.md) | [GitHub Actions Setup →](github-actions-setup.md)