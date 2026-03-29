# Project Overview

This is a static business landing page / website. The site is a single `index.html` file (with inline or linked CSS/JS) served by Nginx on an AWS EC2 Ubuntu instance.

## Tech Stack

- **Frontend:** HTML, CSS, JavaScript (static — no framework, no build step)
- **Hosting:** AWS EC2 (Ubuntu)
- **Web Server:** Nginx
- **Version Control:** GitHub
- **Dev Environment:** macOS (local) → push to GitHub → pull on EC2

## Project Structure

```
/
├── index.html          # Main (and currently only) page
├── CLAUDE.md           # This file — project instructions for Claude Code
└── README.md           # Repo readme (if present)
```

## Development Workflow

1. Make changes locally on Mac
2. Test in browser (open `index.html` directly or use a local server)
3. Commit and push to GitHub
4. Deploy by pulling on the EC2 instance

## Deployment

The live site is served from the Nginx web root on the EC2 instance. To deploy after pushing:

```bash
ssh -i <key.pem> ubuntu@<ec2-ip> "cd /var/www/html && git pull"
```

Nginx config points to `/var/www/html` (confirm and update this path if different).

## Coding Conventions

- Keep it simple — plain HTML/CSS/JS, no build tools or frameworks unless explicitly discussed
- Use semantic HTML elements (`<header>`, `<main>`, `<section>`, `<footer>`, etc.)
- Mobile-first responsive design
- Keep all assets (images, icons) in an `assets/` folder if added
- Use clean, readable code with comments where logic is non-obvious

## Important Rules

- **Do not** create or suggest a build pipeline (Webpack, Vite, etc.) unless asked
- **Do not** convert to a framework (React, Next.js, etc.) unless asked
- **Always** ensure the site works as a static file served by Nginx — no server-side rendering
- **Always** make sure the site is mobile responsive
- **Test locally** before committing — open in browser and check
- When making visual changes, describe what changed so it's easy to review

## Git Conventions

- Write clear, concise commit messages
- Use present tense ("Add hero section" not "Added hero section")
- Keep commits focused — one logical change per commit
