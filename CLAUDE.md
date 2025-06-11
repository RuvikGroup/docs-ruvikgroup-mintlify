# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is an internal Mintlify documentation site for Ruvik Group engineering teams. It contains technical documentation for setting up, developing, and maintaining Ruvik Group's SaaS products. This is NOT public-facing documentation.

## Development Commands

```bash
# Install Mintlify CLI globally
npm i -g mintlify

# Run development server (default: http://localhost:3000)
mintlify dev

# Run on custom port
mintlify dev --port 3333

# Validate all links in documentation
mintlify broken-links

# Upgrade Mintlify CLI to latest version
npm i -g mintlify@latest

# Migrate configuration from mint.json to docs.json
mintlify upgrade
```

## Architecture & Structure

### Configuration
- **`docs.json`**: Main configuration file containing navigation, theme settings, colors, and global settings
- **`api-reference/openapi.json`**: OpenAPI 3.1.0 specification that auto-generates API documentation

### Internal Documentation Structure
The documentation is organized for internal engineering use:

- **Navigation**: Organized by product tabs in `docs.json`
  - Overview tab: Company standards, infrastructure, team info
  - Product-specific tabs: Each product gets technical documentation
  
- **Directory Structure**:
  - `/ruvik-group/`: Company-wide engineering standards
    - `/standards/`: Naming conventions, git practices, security
    - `/overview/`: Team structure, infrastructure
  - `/my-best-pic/`: My Best Pic technical documentation
    - `/setup/`: Local development, environment vars, database, deployment
    - `/architecture/`: System design, database schema, API structure
    - `/development/`: Coding standards, testing, debugging
    - `/operations/`: Monitoring, backups, troubleshooting
  - Future products follow same pattern: `/product-name/`

### Content Organization
- **Pages**: All content files use `.mdx` extension
- **Reusable Content**: Snippets stored in `/snippets/` directory
- **Assets**: Images in `/images/`, logos in `/logo/` (separate files for light/dark themes)

### MDX Components
Mintlify provides built-in components that can be used in MDX files:
- `<Card>`, `<CardGroup>`: For creating card layouts
- `<Accordion>`, `<AccordionGroup>`: For collapsible content
- `<Tip>`, `<Note>`, `<Warning>`: For callout boxes
- `<CodeGroup>`: For showing code in multiple languages

## Important Notes

- This is **internal documentation only** - not for public users
- Focus on technical setup, architecture, and operational details
- Include development workflows, debugging tips, and troubleshooting guides
- Document infrastructure details, deployment processes, and monitoring
- Requires Node.js v19 or higher
- Navigation structure is entirely controlled by `docs.json`

## Content Guidelines

When adding documentation:
- Be specific about versions, dependencies, and system requirements
- Include actual commands, configuration examples, and code snippets
- Document both happy path and error scenarios
- Add troubleshooting sections for common issues
- Keep security best practices in mind (no credentials in docs)