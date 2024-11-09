---
layout: default
title: Jekyll Setup
nav_order: 4
---

# Jekyll Setup
<!-- jekyll-setup.md -->

## Jekyll Configuration Guide

### Basic Setup

1. **Install Required Gems**
   ```ruby
   source 'https://rubygems.org'
   gem "jekyll", "~> 3.9.3"
   gem "github-pages"
   gem "just-the-docs"
   ```

2. **Configure Jekyll**
   ```yaml
   # _config.yml basic settings
   title: Your Documentation
   theme: just-the-docs
   ```

### Theme Customization

1. **Color Scheme**
   ```yaml
   color_scheme: dark  # or: light, custom
   ```

2. **Navigation Structure**
   ```yaml
   # Enable navigation
   nav_external_links:
     - title: GitHub
       url: https://github.com/your-repo
   ```

### Search Configuration

```yaml
search_enabled: true
search:
  heading_level: 2
  previews: 3
```

[← GitHub Actions Setup](github-actions-setup.md) | [Writing Documentation →](writing-docs.md)