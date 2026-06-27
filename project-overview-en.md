# Infra Project - Website Redesign

## Project Overview

This project is a complete redesign and modernization of the [infrascan.net](https://www.infrascan.net/) website. The goal is to bring the existing infrastructure and security scanning service into a modern, user-friendly interface while maintaining the core functionality of the original platform.

**Current Deployment:**
- Main website: [infra-36j.pages.dev](https://infra-36j.pages.dev/)
- Production: [infrascan.net](https://www.infrascan.net/)

---

## Original Website Architecture

### Main Website (infrascan.net)
The original website is a traditional web application built with:
- **Security**: reCAPTCHA for form protection
- **Performance**: Cloudflare Rocket Loader for optimized asset delivery
- **Networking**: HTTP/3 support
- **Frontend**: Bootstrap 4.1.1 UI framework with jQuery 3.3.1
- **CDN**: Cloudflare for content delivery and security

### Blog Platform (blog.infrascan.net)
A WordPress-based blog supporting multilingual content:

**Languages Supported:**
- Dutch
- English
- French
- German
- Italian
- Russian
- Spanish
- Catalan
- Vietnamese

---

## Current Redesign (MVP)

### Objectives
The redesign focuses on modernizing the user experience and interface while establishing a scalable, maintainable platform for the future:

1. **Modern UX/UI**: Complete visual and interaction redesign with contemporary design patterns
2. **Content-Driven Architecture**: Markdown-based content management for easier maintenance
3. **Static Site Generation**: Deploy as static pages to Cloudflare Pages for improved performance and reliability
4. **Scalable Infrastructure**: Foundation for future integrations with headless CMS solutions
5. **Asset Management**: Connected R2 storage for efficient media handling

### Technology Stack

#### Core Framework
- **Nuxt 3**: Full-stack Vue framework for building the application
- **Vue 3**: Component-based UI architecture

#### Content Management
- **Markdown**: Primary content format for all pages and blog posts
- **@nuxt/content**: Content management integration layer for markdown processing

#### Styling & Design
- **Tailwind CSS**: Utility-first CSS framework for rapid, responsive UI development

#### Additional Features
- **Mapbox GL**: For interactive maps and location-based features
- **TypeScript**: Type-safe development across the entire application

#### Deployment & Infrastructure
- **Cloudflare Pages**: Static hosting with automatic deployments
- **Cloudflare R2**: Object storage for images, documents, and other assets

---

## Current Status: MVP Phase

The project is currently in **MVP (Minimum Viable Product)** stage with the following characteristics:

### ✅ Completed
- Modern redesign of core website UI/UX
- Nuxt 3 application structure and setup
- Markdown-based content management pipeline
- Cloudflare Pages deployment configuration
- R2 integration for asset storage
- Responsive design across all device sizes
- TypeScript configuration and type safety

### 🚧 In Progress / Planned

#### Content Migration
- **News Import**: Migrate existing news articles from the original website with proper URL mapping and redirects
- **Blog Integration**: Import blog posts from WordPress with maintained metadata and categories
- **URL Preservation**: Ensure SEO-friendly redirects from old URLs to new content structure

#### CMS Integration
The project is designed to work with markdown initially, with planned integration of headless CMS solutions:
- **Options Under Consideration**:
  - PageCMS
  - SveltiaCMS
  - DecapCMS
- **Timeline**: Phase 2 of the project
- **Purpose**: Enable non-technical team members to manage content without direct markdown editing

#### Content Updates
- Review and update existing website content
- Ensure accuracy of technical information
- Modernize language and tone
- Add missing information from original site

#### Enhanced Features (Future)
- Search functionality across all content
- Advanced filtering for news and resources
- User account system (if needed)
- Analytics integration
- Social media integration

---

## Project Structure

```
infra/
├── app.vue                 # Root application component
├── nuxt.config.ts          # Nuxt configuration
├── tsconfig.json           # TypeScript configuration
├── tailwind.config.ts      # Tailwind CSS configuration
│
├── pages/                  # Page routes (auto-generated)
├── components/             # Reusable Vue components
├── layouts/                # Page layout templates
├── composables/            # Reusable Vue composables
├── content/                # Markdown content files
├── assets/                 # Static assets (images, fonts, etc.)
├── public/                 # Public assets (robots.txt, favicons, etc.)
└── types/                  # TypeScript type definitions
```

---

## Getting Started

### Installation
```bash
npm install
```

### Development Server
```bash
npm run dev
```
Access the site at `http://localhost:3000`

### Build for Production
```bash
npm run build
```

### Generate Static Site
```bash
npm run generate
```
Creates optimized static files ready for Cloudflare Pages deployment.

### Preview Production Build
```bash
npm run preview
```

---

## Content Management Workflow

### Adding News Articles
1. Create a new markdown file in the `content/` directory
2. Include metadata (title, date, category, etc.) in the frontmatter
3. Write content in markdown format
4. Commit and push changes (auto-deploys via Cloudflare Pages)

### Adding Pages
1. Create a new `.vue` component in the `pages/` directory
2. Reference markdown content from the `content/` directory as needed
3. Deploy automatically on commit

### Managing Assets
1. Upload images and documents to Cloudflare R2
2. Reference R2 URLs in markdown content or components
3. Leverage R2's CDN for global distribution

---

## Deployment

### Cloudflare Pages
- **Automatic Deployments**: Connected to repository, deploys on each push
- **Branch Previews**: Pull requests generate preview deployments
- **Production Domain**: infrascan.net via Cloudflare managed DNS

### Environment Variables
Configuration stored in `.env` file (credentials not committed to repository)

---

## Next Steps & Priorities

### Phase 1 (Current MVP - In Progress)
- [ ] Complete content migration from original website
- [ ] Import all blog posts with proper categorization
- [ ] Establish URL redirect strategy
- [ ] Update content accuracy and completeness

### Phase 2 (Q3 2026)
- [ ] Integrate headless CMS for content management
- [ ] Setup team access to CMS without requiring technical knowledge
- [ ] Add search functionality
- [ ] Analytics integration

### Phase 3 (Q4 2026)
- [ ] Advanced filtering and categorization
- [ ] User engagement features (comments, newsletters)
- [ ] Performance optimization
- [ ] A/B testing framework

---

## Technical Notes

### Markdown Processing
The `@nuxt/content` module automatically processes markdown files with:
- **YAML Frontmatter**: Metadata extraction
- **Syntax Highlighting**: Code blocks are highlighted automatically
- **Table of Contents**: Auto-generated from headings
- **Link Validation**: Broken links can be detected during build

### Cloudflare Integration
- **R2 for Assets**: Provides S3-compatible object storage
- **Pages for Hosting**: Git-connected deployment platform
- **CDN**: Automatic global distribution of static assets
- **Security**: DDoS protection and SSL/TLS by default

---

## Contact & Contribution

For questions about the project architecture or to contribute to the redesign, please reach out to the development team.

---

**Last Updated**: June 2026  
**Status**: MVP - Active Development  
**Maintainers**: Development Team
