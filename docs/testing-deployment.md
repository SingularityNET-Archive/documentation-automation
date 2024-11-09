---
layout: default
title: Testing Deployment
nav_order: 4
---

# Testing and Deployment
<!-- testing-deployment.md -->

## Local Testing

### Setup Local Environment

```bash
cd docs
bundle install
bundle exec jekyll serve
```

### Common Issues

1. **Bundle Install Failures**
   - Check Ruby version
   - Verify Gemfile content
   - Clear bundle cache

2. **Build Errors**
   - Validate YAML syntax
   - Check file permissions
   - Verify Jekyll configuration

## Deployment Verification

1. **Check Build Status**
   - Monitor GitHub Actions
   - Review build logs

2. **Verify Deployment**
   - Check GitHub Pages URL
   - Validate content updates
   - Test navigation

[← Writing Documentation](writing-docs.md)