---
layout: default
title: Writing Documentation
nav_order: 3
---

# Writing Documentation
<!-- writing-docs.md -->

## Documentation Guidelines

### Front Matter

Front matter is a section of YAML code at the beginning of each Markdown file that defines metadata and configuration settings for that page. It's placed at the very top of the file between triple-dashed lines (`---`). Jekyll uses this metadata to:
- Control page layout and appearance
- Set navigation structure and order
- Define relationships between pages
- Configure page-specific settings

For example:
```yaml
---
title: Page Title      # Sets the page title in navigation and browser tab
layout: default       # Defines which layout template to use
parent: Parent Page   # Creates hierarchical navigation structure
nav_order: 1         # Controls the order in navigation menus
---
```

### File Organization

Organize your documentation files logically:
```
docs/
├── index.md          # Home page
├── guides/           # User guides
├── reference/        # Reference
└── tutorials/        # Step-by-step tutorials
```

### Markdown Best Practices

1. **Front Matter Template**
   ```yaml
   ---
   title: Page Title
   layout: default
   parent: Parent Folder Name # Only use if page has parent folder
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

[← Jekyll Setup](/documentation-automation/setup-guide/jekyll-setup) | [Testing and Deployment →](testing-deployment.md)