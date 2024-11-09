---
layout: default
title: Writing Documentation
nav_order: 3
---

# Writing Documentation
<!-- writing-docs.md -->

## Documentation Guidelines

### File Organization

Organize your documentation files logically:
```
docs/
├── index.md          # Home page
├── guides/           # User guides
├── reference/        # API reference
└── tutorials/        # Step-by-step tutorials
```

### Markdown Best Practices

1. **Front Matter**
   ```yaml
   ---
   title: Page Title
   layout: default
   nav_order: 1
   ---
   ```

2. **Headers and Navigation**
   ```markdown
   # Main Title
   ## Section
   ### Subsection
   ```

### Including Assets

1. **Images**
   ```markdown
   ![Alt text](assets/images/screenshot.png)
   ```

2. **Code Blocks**
   ````markdown
   ```python
   def example():
       return "Hello, World!"
   ```
   ````

[← Jekyll Setup](jekyll-setup.md) | [Testing and Deployment →](testing-deployment.md)