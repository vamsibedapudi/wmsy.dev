# Claude Development Context

This file contains context for Claude AI to better understand and work with this project.

## Project Overview

This is a simple personal website for Vamsi Bedapudi (wmsy.dev), hosted on GitHub Pages. It's a static site with minimal dependencies.

## Technology Stack

- **Frontend**: Vanilla HTML, CSS
- **Hosting**: GitHub Pages
- **Domain**: Custom domain (wmsy.dev) with SSL/TLS
- **Repository**: https://github.com/vamsibedapudi/wmsy.dev

## File Structure

- `index.html` - Main landing page with personal info and contact links
- `style.css` - Styling for the website
- `CNAME` - Custom domain configuration for GitHub Pages
- `README.md` - Project documentation
- `CLAUDE.md` - This context file
- `DEPLOYMENT.md` - Deployment setup and troubleshooting guide

## GitHub Pages Configuration

- **Source Branch**: main
- **Source Path**: / (root)
- **Build Type**: legacy
- **Status**: Built and deployed
- **URL**: https://wmsy.dev
- **Custom Domain**: Configured with Cloudflare DNS
- **SSL Certificate**: Auto-provisioned by GitHub Pages

## Development Guidelines

1. **Keep it simple**: This is intentionally a minimal static site
2. **No build process**: Direct HTML/CSS, no frameworks or build tools
3. **Mobile-first**: Ensure responsive design
4. **Performance**: Keep assets minimal and optimized

## Common Tasks

### Local Development
```bash
# Serve locally
python -m http.server 8000
```

### Deployment
- Push to main branch
- GitHub Pages automatically builds and deploys
- Custom domain SSL certificate auto-renews

### Testing
- Test locally before pushing
- Verify mobile responsiveness
- Check all contact links work
- Test HTTPS functionality at wmsy.dev

### Troubleshooting
For detailed troubleshooting information, see `DEPLOYMENT.md`:
- SSL certificate issues
- DNS propagation problems
- Custom domain configuration
- GitHub Pages build failures

## Contact Information

- **Email**: hello@wmsy.dev
- **GitHub**: vamsibedapudi
- **LinkedIn**: wamsib

## Notes

- Site uses GitHub Pages legacy build system
- Custom domain wmsy.dev configured with SSL/TLS
- HTTPS enforced by GitHub Pages
- DNS managed through Cloudflare
- Public repository
- Automatic SSL certificate renewal
- **Auto-deployment**: Always git add, commit, and push changes immediately after making them