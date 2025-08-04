# Deployment Documentation

This document outlines the deployment setup and configuration for the wmsy.dev website.

## GitHub Pages Configuration

### Repository Setup
- **Repository**: `vamsibedapudi/wmsy.dev`
- **Branch**: `main`
- **Source Path**: `/` (root directory)
- **Build Type**: Legacy GitHub Pages

### Custom Domain Configuration

#### 1. CNAME File
A `CNAME` file in the repository root contains:
```
wmsy.dev
```

#### 2. DNS Configuration
The domain uses Cloudflare DNS with the following key records:

```dns
; Main domain CNAME pointing to GitHub Pages
wmsy.dev.    1    IN    CNAME    vamsibedapudi.github.io.

; WWW subdomain
www.wmsy.dev.    1    IN    CNAME    wmsy.dev.
```

**Note**: The DNS resolves to GitHub Pages IP addresses:
- 185.199.108.153
- 185.199.109.153
- 185.199.110.153
- 185.199.111.153

#### 3. SSL/TLS Configuration
- **Provider**: GitHub Pages automatic SSL
- **Certificate Status**: Approved
- **Domains Covered**: `wmsy.dev`, `www.wmsy.dev`
- **HTTPS Enforcement**: Enabled
- **Certificate Renewal**: Automatic

## Deployment Process

### Automatic Deployment
1. Push changes to `main` branch
2. GitHub Pages automatically builds and deploys
3. Changes are live within 1-2 minutes

### Manual Verification
```bash
# Check DNS resolution
nslookup wmsy.dev

# Check GitHub Pages status
gh api repos/vamsibedapudi/wmsy.dev/pages

# Test site accessibility
curl -I https://wmsy.dev
```

## Troubleshooting

### Common Issues and Solutions

#### SSL Certificate Errors
- **Problem**: "Your connection is not private" or certificate errors
- **Cause**: Usually DNS propagation delays or missing CNAME file
- **Solution**: 
  1. Verify CNAME file exists in repository root
  2. Check DNS propagation with `nslookup wmsy.dev`
  3. Wait 24-48 hours for full DNS propagation
  4. GitHub will automatically provision SSL once DNS is correct

#### Custom Domain Not Working
- **Problem**: Site only accessible via github.io subdomain
- **Cause**: DNS misconfiguration or missing CNAME file
- **Solution**:
  1. Ensure CNAME file contains only the domain name
  2. Verify DNS CNAME record points to `vamsibedapudi.github.io`
  3. Check GitHub Pages settings show correct custom domain

#### Build Failures
- **Problem**: Site not updating after push
- **Cause**: Invalid HTML/CSS or repository issues
- **Solution**:
  1. Check repository Actions tab for build status
  2. Validate HTML/CSS syntax
  3. Ensure all files are properly committed

### Monitoring

#### Health Checks
- Site should be accessible at https://wmsy.dev
- SSL certificate should be valid and not expired
- All contact links should function properly

#### Performance
- Lighthouse score should remain high (static site)
- Page load time should be minimal
- Mobile responsiveness should be maintained

## Security Considerations

### GitHub Pages Security
- Repository is public (required for free GitHub Pages)
- No server-side processing (static site only)
- HTTPS enforced for all connections
- No sensitive data stored in repository

### DNS Security
- DNS managed through Cloudflare
- DNSSEC enabled for domain protection
- Regular monitoring of DNS records

## Future Improvements

### Potential Enhancements
- Enable GitHub Actions for advanced build process
- Add custom 404 page
- Implement Content Security Policy headers
- Add analytics (privacy-compliant)
- Consider using GitHub Pages custom domain apex setup

### Migration Considerations
- If moving away from GitHub Pages, update DNS CNAME to new provider
- Export all repository content and history
- Update documentation accordingly