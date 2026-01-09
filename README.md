# Docsify v4 to v5 Upgrade Notes

These notes walk you through upgrading your Docsify site from v4 to v5.

## Overview

The main changes involve updating CDN URLs and theme files. Your configuration settings remain mostly the same, so the upgrade is fairly straightforward.

## Before You Begin

Some older Docsify sites may use non-version-locked URLs like:
```html
<script src="//cdn.jsdelivr.net/npm/docsify/lib/docsify.min.js"></script>
```

If your site uses URLs without `@4` or a specific version number, follow the same steps below. You'll need to update both the version specifier and the path structure.

## Step-by-Step Instructions

### 1. Update the Theme CSS

**Replace the theme (v4):**
```html
<link rel="stylesheet" href="//cdn.jsdelivr.net/npm/docsify@4/lib/themes/vue.css">
<!-- OR if you have non-versioned URL: -->
<link rel="stylesheet" href="//cdn.jsdelivr.net/npm/docsify/lib/themes/vue.css">
```

**With this (v5):**
```html
<!-- Core Theme -->
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/docsify@5/dist/themes/core.min.css">
<!-- Optional: Dark Mode Support -->
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/docsify@5/dist/themes/addons/core-dark.min.css" media="(prefers-color-scheme: dark)" />
```

Learn more at:  
https://preview.docsifyjs.org/#/quickstart

### 2. Add Optional Body Class (for styling)

**Update your opening body tag:**
```html
<body class="sidebar-chevron-right">
```

This adds a chevron indicator to the sidebar. You can omit this if you prefer.

Learn more at:  
https://preview.docsifyjs.org/#/themes

### 3. Update the Main Docsify Script

**Change:**
```html
<script src="https://cdn.jsdelivr.net/npm/docsify@4/lib/docsify.min.js"></script>
<!-- OR if you have non-versioned URL: -->
<script src="//cdn.jsdelivr.net/npm/docsify/lib/docsify.min.js"></script>
```

**To:**
```html
<script src="https://cdn.jsdelivr.net/npm/docsify@5/dist/docsify.min.js"></script>
```

### 4. Update Plugin URLs

**Search Plugin:**
```html
<!-- v4 -->
<script src="https://cdn.jsdelivr.net/npm/docsify@4/lib/plugins/search.js"></script>
<!-- OR non-versioned: -->
<script src="//cdn.jsdelivr.net/npm/docsify/lib/plugins/search.js"></script>

<!-- v5 -->
<script src="https://cdn.jsdelivr.net/npm/docsify@5/dist/plugins/search.min.js"></script>
```

**Zoom Plugin:**
```html
<!-- v4 -->
<script src="https://cdn.jsdelivr.net/npm/docsify@4/lib/plugins/zoom-image.min.js"></script>
<!-- OR non-versioned: -->
<script src="//cdn.jsdelivr.net/npm/docsify/lib/plugins/zoom-image.min.js"></script>

<!-- v5 -->
<script src="https://cdn.jsdelivr.net/npm/docsify@5/dist/plugins/zoom.min.js"></script>
```

**Note:** If you're using additional Docsify plugins (such as emoji, external-script, front-matter, etc.), you'll need to update those URLs as well following the same pattern:
- Change `/lib/plugins/` to `/dist/plugins/`
- Update version from `@4` (or non-versioned) to `@5`
- Example: `//cdn.jsdelivr.net/npm/docsify/lib/plugins/emoji.min.js` becomes `https://cdn.jsdelivr.net/npm/docsify@5/dist/plugins/emoji.min.js`

## Key Differences Summary

- **CDN Path**: Changed from `/lib/` to `/dist/`
- **Version**: Updated from `@4` to `@5`
- **Theme**: Vue theme → Core theme (with optional dark mode)
- **Plugin Names**: `zoom-image` → `zoom`

## Notes

- Your configuration in `window.$docsify` stays the same
- All your markdown content remains unchanged
- Dark mode support is now built-in (optional)
- The upgrade is non-breaking for most sites

That's it! Your Docsify site should now be running on v5.
