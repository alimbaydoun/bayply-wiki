---
title: Wiki Contribution Guide
description: How to create and edit wiki pages using Git
published: true
tags: guide, documentation, git
editor: markdown
---

# Wiki Contribution Guide

This guide explains how to create and edit pages on the BayPly Wiki using Git.

## Overview

The wiki is synced with a GitHub repository. You can edit pages directly in Wiki.js, or write markdown files locally and push them to GitHub. Changes sync automatically every 5 minutes.

## Method 1: Edit Directly in Wiki.js

1. Navigate to the page you want to edit
2. Click the pencil icon in the bottom-right corner
3. Make your changes using the markdown editor
4. Click **Save** when done

## Method 2: Edit via Git

### Initial Setup

Clone the repository:

```bash
git clone https://github.com/alimbaydoun/bayply-wiki.git
cd bayply-wiki
```

### Creating a New Page

1. Create a new `.md` file in the repository root
2. Add the required frontmatter at the top
3. Write your content in markdown
4. Commit and push

### Frontmatter Template

Every page needs this header:

```yaml
---
title: Your Page Title
description: A brief description of the page
published: true
tags: tag1, tag2, tag3
editor: markdown
---
```

| Field | Required | Description |
|-------|----------|-------------|
| title | Yes | The page title displayed in the wiki |
| description | Yes | Short summary shown in search results |
| published | Yes | Set to `true` to make the page visible |
| tags | No | Comma-separated list of tags |
| editor | Yes | Always use `markdown` |

### Example Page

Create a file called `my-new-page.md`:

```markdown
---
title: My New Page
description: This is an example page
published: true
tags: example
editor: markdown
---

# My New Page

Write your content here using standard markdown.

## Subheading

- Bullet points work
- As do **bold** and *italic* text

### Code Blocks

Use triple backticks for code:

\`\`\`javascript
console.log('Hello Wiki!');
\`\`\`
```

### Publishing Your Changes

```bash
git add .
git commit -m "Add new page: my-new-page"
git push
```

The page will appear on the wiki within 5 minutes.

## File Naming

- Use lowercase with hyphens: `my-page-name.md`
- The filename becomes the URL path: `my-page-name.md` → `/en/my-page-name`
- Avoid spaces and special characters

## Folder Structure

| Location | URL Path |
|----------|----------|
| `page.md` | `/en/page` |
| `docs/setup.md` | `/en/docs/setup` |
| `guides/intro.md` | `/en/guides/intro` |

## Supported Markdown Features

- Headings (`#`, `##`, `###`)
- Bold (`**text**`) and italic (`*text*`)
- Links (`[text](url)`)
- Images (`![alt](url)`)
- Code blocks (fenced with triple backticks)
- Tables
- Blockquotes (`>`)
- Horizontal rules (`---`)
- Task lists (`- [ ]` and `- [x]`)

## Tips

- Preview your markdown locally before pushing
- Use descriptive commit messages
- Keep page titles concise
- Add relevant tags for better searchability
- Break long pages into multiple smaller pages

## Need Help?

Contact the wiki administrator if you have questions or run into issues.
