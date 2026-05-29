# Migration from Quartz v4 to v5

## Date
2026-05-29

## Summary
This repository has been updated from Quartz v4 to v5 while preserving all custom configurations.

## Changes Made

### Configuration Migration
- **v4 config files** (TypeScript):
  - `quartz.config.ts` - Removed (v5 uses YAML)
  - `quartz.layout.ts` - Removed (v5 uses YAML)

- **v5 config file** (YAML):
  - `quartz.config.yaml` - Created with all your v4 customizations

### Preserved Customizations

#### Site Configuration
- **Page Title**: Harvey's Garden
- **Base URL**: www.h4rvey.com
- **Analytics**: Plausible (enabled)
- **SPA**: Enabled
- **Popovers**: Enabled

#### Theme
- **Fonts**:
  - Header: Schibsted Grotesk
  - Body: Source Sans Pro
  - Code: IBM Plex Mono

- **Colors** (both light and dark modes preserved):
  - Custom color scheme maintained
  - Light mode: warm tones with #284b63 secondary
  - Dark mode: dark tones with #7b97aa secondary

#### Ignore Patterns
All your custom ignore patterns have been preserved:
- `.obsidian` files
- `.DS_Store`
- Sync and backup files
- Custom scripts

#### Plugins
All your v4 plugins have been migrated to v5 equivalents:
- Created/Modified Date (priority: frontmatter → git → filesystem)
- Syntax Highlighting (github-light/dark themes)
- Obsidian Flavored Markdown
- GitHub Flavored Markdown
- Table of Contents
- Crawl Links (shortest resolution)
- LaTeX (KaTeX engine)
- Custom OG Images (enabled)

#### Layout
Your v4 layout has been preserved in v5 format:
- **Left sidebar**: PageTitle, Search (with toolbar), Darkmode, ReaderMode, Explorer
- **Right sidebar**: Graph, TableOfContents, Backlinks
- **Before body**: Breadcrumbs (not on index), ArticleTitle, ContentMeta, TagList
- **Footer**: Default Quartz links (you may want to customize these)

## What's New in v5

### Major Changes
1. **Configuration format**: TypeScript → YAML
2. **Plugin system**: Now uses GitHub-based plugin sources
3. **Layout system**: Declarative YAML-based layout configuration
4. **New features**:
   - Canvas support
   - Bases (Obsidian bases)
   - Note properties
   - Encrypted pages
   - Unlisted pages
   - Stacked pages (disabled by default)

### Breaking Changes
- Configuration files are now YAML instead of TypeScript
- Component/plugin architecture has changed
- Custom components may need to be rewritten

## Next Steps

1. **Test the build**:
   ```bash
   npx quartz build
   ```

2. **Update dependencies**:
   ```bash
   npm install
   ```

3. **Customize footer links** in `quartz.config.yaml`:
   ```yaml
   - source: github:quartz-community/footer
     options:
       links:
         GitHub: https://github.com/YOUR_USERNAME/garden
         # Add your custom links here
   ```

4. **Review new plugins**: Check the v5 plugins and enable any you want:
   - `canvas-page`: For Obsidian canvas files
   - `bases-page`: For Obsidian bases
   - `note-properties`: Display frontmatter properties
   - `encrypted-pages`: Password-protected pages
   - `unlisted-pages`: Hide pages from listings
   - `stacked-pages`: Andy Matuschak-style stacked notes

5. **Check for custom components**: If you had any custom components in v4, they will need to be rewritten for v5's new architecture.

## Rollback Instructions

If you need to rollback to v4:
```bash
git checkout v4
```

## Resources
- [Quartz v5 Documentation](https://quartz.jzhao.xyz/)
- [Migration Guide](https://quartz.jzhao.xyz/getting-started/migrating)
- [What's New in v5](https://quartz.jzhao.xyz/getting-started/whats-new)
