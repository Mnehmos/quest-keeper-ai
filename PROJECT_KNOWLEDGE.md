# Quest Keeper AI Website - Knowledge Base Document

## Quick Reference

| Property | Value |
|----------|-------|
| **Repository** | https://github.com/Mnehmos/mnehmos.quest-keeper.website |
| **Primary Language** | HTML/CSS |
| **Project Type** | Website |
| **Status** | Active |
| **Last Updated** | 2025-12-29 |

## Overview

Quest Keeper AI Website is a static documentation and marketing site for the Quest Keeper AI project - an AI-powered tabletop RPG platform. The website provides comprehensive documentation including quick start guides, API references, system analysis, roadmaps, and showcases for the desktop application and MCP backend server. It features a retro-futuristic cyberpunk design aesthetic with glassmorphism effects, neon colors, and scanline overlays.

## Architecture

### System Design

The website is a static HTML/CSS site with no build process or JavaScript dependencies. It uses a multi-page structure with shared global styles and a consistent cyberpunk/terminal aesthetic across all pages. The site is deployed via GitHub Pages with a custom domain (questkeeperai.com) configured through CNAME. All pages reference a central stylesheet that provides the unified visual design system including animations, glassmorphism effects, and responsive layouts.

### Key Components

| Component | Purpose | Location |
|-----------|---------|----------|
| Landing Page | Main entry point, feature showcase, call-to-action | `index.html` |
| Global Styles | Unified design system with cyberpunk theme | `styles.css` |
| Quick Start Guide | Setup instructions for desktop app and MCP backend | `quickstart/index.html` |
| API Reference | Documentation for 135+ MCP tools | `api-reference/index.html` |
| System Analysis | Architecture deep dive and technical details | `analysis/index.html` |
| Roadmap | Project phases and feature development timeline | `roadmap/index.html` |
| Showcase | Case study and usage examples | `showcase/index.html` |
| Style Guide | Design system documentation | `style-guide/index.html` |
| Changelog | Version history and updates | `changelog/index.html` |
| Documentation | Comprehensive analysis and implementation guides | `documents/` |
| Favicon | SVG logo (D20 dice icon) | `favicon.svg` |

### Data Flow

```
User Browser → GitHub Pages CDN → Static HTML Files
                                   ↓
                            styles.css (Global Theme)
                                   ↓
                            Individual Page Content
```

No server-side processing or JavaScript runtime required. All content is pre-rendered HTML with CSS styling.

## API Surface

### Public Interfaces

This is a static website with no programmatic API. The site serves as documentation for the Quest Keeper AI project's actual APIs (rpg-mcp server).

#### External Links
- **GitHub Repositories**: Links to [QuestKeeperAI-v2](https://github.com/Mnehmos/QuestKeeperAI-v2) and [rpg-mcp](https://github.com/Mnehmos/rpg-mcp)
- **MCP Protocol**: Reference to [modelcontextprotocol.io](https://modelcontextprotocol.io)
- **Third-party Tools**: Claude Desktop, KiloCode, RooCode integration instructions

### Configuration

| Variable | Type | Default | Description |
|----------|------|---------|-------------|
| `CNAME` | string | `questkeeperai.com` | Custom domain configuration for GitHub Pages |

No environment variables or runtime configuration required.

## Usage Examples

### Basic Usage

```bash
# Clone the repository
git clone https://github.com/Mnehmos/mnehmos.quest-keeper.website.git
cd mnehmos.quest-keeper.website

# View locally (any static file server)
python -m http.server 8000
# Open http://localhost:8000 in browser
```

### Advanced Patterns

```bash
# Deploy to GitHub Pages
git add .
git commit -m "Update documentation"
git push origin main
# Site automatically deploys to questkeeperai.com

# Update content with unified theme
# 1. Edit HTML content in target file
# 2. Ensure stylesheet link: <link rel="stylesheet" href="../styles.css">
# 3. Use theme classes: .glass-card, .reveal, .neon-cyan, etc.
# 4. Apply reveal animations: class="feature-grid reveal"
```

## Dependencies

### Runtime Dependencies

| Package | Version | Purpose |
|---------|---------|---------|
| N/A | N/A | Pure HTML/CSS static site with no dependencies |

### Development Dependencies

| Package | Version | Purpose |
|---------|---------|---------|
| N/A | N/A | No build process required |

External resources loaded via CDN:
- Google Fonts: IBM Plex Mono, Share Tech Mono (for terminal aesthetic)

## Integration Points

### Works With

| Project | Integration Type | Description |
|---------|-----------------|-------------|
| [mnehmos.quest-keeper.game](https://github.com/Mnehmos/QuestKeeperAI-v2) | Documentation | Website documents the desktop Tauri application |
| [mnehmos.rpg.mcp](https://github.com/Mnehmos/rpg-mcp) | Documentation | Website provides API reference for MCP backend server |

### External Services

| Service | Purpose | Required |
|---------|---------|----------|
| GitHub Pages | Static site hosting | Yes |
| Google Fonts API | Terminal-style fonts (IBM Plex Mono, Share Tech Mono) | No (fallback available) |

## Development Guide

### Prerequisites

- Web browser (for local preview)
- Git (for version control)
- Optional: Static file server (Python http.server, Node.js http-server, etc.)

### Setup

```bash
# Clone the repository
git clone https://github.com/Mnehmos/mnehmos.quest-keeper.website
cd mnehmos.quest-keeper.website

# No dependency installation needed - pure HTML/CSS
```

### Running Locally

```bash
# Development mode (any static server works)
python -m http.server 8000
# OR
npx http-server -p 8000

# Open http://localhost:8000 in browser
```

### Testing

```bash
# Manual testing checklist:
# 1. Verify all internal links work
# 2. Check responsive layout on mobile/tablet/desktop
# 3. Validate CSS animations (.reveal classes)
# 4. Confirm external links (GitHub, docs) are current
# 5. Test glassmorphism effects render correctly
# 6. Verify scanline overlay displays properly
```

### Building

```bash
# No build process required
# Files are served as-is from repository

# Deployment to GitHub Pages:
git add .
git commit -m "docs: Update website content"
git push origin main
```

## Maintenance Notes

### Known Issues

1. **135+ Tools Update**: WEBSITE_UPGRADE_PLAN.md notes that the API reference page needs to be updated from 80+ tools to 135+ tools to reflect new spellcasting, economy, theft, corpse/loot, and NPC memory systems
2. **Roadmap Phase Updates**: Phase 2 (Advanced Systems) should be marked complete for spellcasting, theft & economy, corpse & loot, and NPC memory features
3. **Comparison Table**: Landing page comparison table needs updated tool counts for Roll20/D&D Beyond alternatives

### Future Considerations

1. **Content Automation**: Consider generating API reference from RPG-MCP-TOOL-METADATA.md rather than manual updates
2. **Build Process**: May benefit from static site generator (Astro, 11ty) for component reuse across pages
3. **Analytics**: Add privacy-respecting analytics to track feature interest and documentation usage
4. **Search Functionality**: Implement client-side search for API reference and documentation pages
5. **Dark/Light Mode Toggle**: Currently only dark theme; consider theme switcher

### Code Quality

| Metric | Status |
|--------|--------|
| Tests | None (static HTML/CSS site) |
| Linting | None |
| Type Safety | N/A (no JavaScript) |
| Documentation | README only + inline HTML comments |

---

## Appendix: File Structure

```
mnehmos.quest-keeper.website/
├── index.html                    # Landing page with hero, features, architecture, roadmap
├── styles.css                    # Global cyberpunk theme with glassmorphism and animations
├── favicon.svg                   # D20 dice logo
├── CNAME                         # Custom domain: questkeeperai.com
├── LICENSE                       # Apache 2.0 license
├── README.md                     # Project overview and quick links
├── WEBSITE_UPGRADE_PLAN.md       # Implementation plan for content/aesthetic upgrades
├── PROJECT_KNOWLEDGE.md          # This document
├── analysis/
│   └── index.html                # System architecture deep dive
├── api-reference/
│   └── index.html                # MCP tools documentation (135+ tools)
├── changelog/
│   └── index.html                # Version history and updates
├── quickstart/
│   └── index.html                # Setup guide for desktop app and MCP backend
├── roadmap/
│   └── index.html                # Development phases and feature timeline
├── showcase/
│   └── index.html                # Case study and usage examples
├── style-guide/
│   └── index.html                # Design system documentation
└── documents/
    ├── A seriously comprehensive analysis of Quest Keeper.md  # 67KB technical analysis
    └── rpg-mcp-implementation-roadmap.md                      # Backend development roadmap
```

---

*Generated by Project Review Orchestrator | 2025-12-29*
*Source: https://github.com/Mnehmos/mnehmos.quest-keeper.website*
