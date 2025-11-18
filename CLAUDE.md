# CLAUDE.md - AI Assistant Guide for belajar-vue

## Project Overview

**Project Name:** test-vue (belajar-vue)
**Version:** 0.1.0
**Type:** Vue.js 2 Single Page Application
**Framework:** Vue.js 2.6.10
**Build Tool:** Vue CLI 3.11.0

This is a learning/practice Vue.js project ("belajar" means "learn" in Indonesian/Malay) with a complete development setup including testing, linting, and build tooling.

## Technology Stack

### Core Dependencies
- **Vue.js 2.6.10** - Progressive JavaScript framework
- **core-js 2.6.5** - Polyfills for JavaScript standard library

### Development Tools
- **Vue CLI 3.11.0** - Standard tooling for Vue.js development
- **Babel** - JavaScript transpiler with babel-eslint parser
- **Webpack** - Module bundler (via Vue CLI)
- **Node Sass 4.9.0 + Sass Loader 7.1.0** - CSS preprocessing

### Testing Framework
- **Jest 23.6.0** - Unit testing with Vue Test Utils
- **Cypress 3.11.0** - End-to-end testing
- **@vue/test-utils 1.0.0-beta.29** - Official testing utilities for Vue

### Code Quality
- **ESLint 5.16.0** - JavaScript linting
- **@vue/eslint-config-standard** - Vue.js Standard style configuration
- **eslint-plugin-vue 5.0.0** - Official ESLint plugin for Vue.js

## Project Structure

```
belajar-vue/
├── public/                 # Static assets
│   ├── index.html         # HTML template
│   └── favicon.ico        # Favicon
├── src/                   # Source code
│   ├── assets/           # Project assets (images, fonts, etc.)
│   │   └── logo.png      # Vue logo
│   ├── components/       # Vue components
│   │   ├── HelloWorld.vue
│   │   └── test_component.vue
│   ├── App.vue          # Root component
│   └── main.js          # Application entry point
├── tests/               # Test files
│   ├── e2e/            # End-to-end tests (Cypress)
│   │   ├── plugins/    # Cypress plugins
│   │   ├── specs/      # Test specifications
│   │   └── support/    # Support files and custom commands
│   └── unit/           # Unit tests (Jest)
│       └── example.spec.js
├── .browserslistrc     # Target browser configuration
├── .editorconfig       # Editor configuration
├── .eslintrc.js        # ESLint configuration
├── .gitignore          # Git ignore patterns
├── babel.config.js     # Babel configuration
├── cypress.json        # Cypress configuration
├── jest.config.js      # Jest configuration
├── package.json        # Project dependencies and scripts
├── postcss.config.js   # PostCSS configuration
└── README.md           # Project documentation
```

## Development Workflow

### Initial Setup
```bash
npm install
```

### Available Scripts

| Command | Description |
|---------|-------------|
| `npm run serve` | Start development server with hot-reload |
| `npm run build` | Build for production (outputs to /dist) |
| `npm run lint` | Run ESLint and auto-fix issues |
| `npm run test:unit` | Run Jest unit tests |
| `npm run test:e2e` | Run Cypress end-to-end tests |

### Development Server
- Default port: 8080 (configured by Vue CLI)
- Hot module replacement enabled
- Development builds include source maps

## Code Standards and Conventions

### ESLint Configuration (.eslintrc.js:1-28)

**Style Guide:** JavaScript Standard Style (via @vue/standard)

**Key Rules:**
- `no-console`: Error in production, allowed in development
- `no-debugger`: Error in production, allowed in development
- Vue plugin essential rules enforced
- Babel-eslint parser for modern JavaScript support

### Component Naming
- Use PascalCase for component names (e.g., `HelloWorld.vue`)
- Component file names can use snake_case or PascalCase
- Component names in templates use kebab-case: `<hello-world/>`

### Vue Component Structure
Follow this order in .vue files:
1. `<template>` - Component markup
2. `<script>` - Component logic
3. `<style>` - Component styles

Example from App.vue:1-29:
```vue
<template>
  <!-- Template content -->
</template>

<script>
export default {
  name: 'app',  // Component name
  components: {
    // Registered components
  }
}
</script>

<style lang="scss">
/* Component styles with Sass */
</style>
```

### Style Guidelines
- **Preprocessor:** Sass/SCSS supported
- Use `lang="scss"` attribute on `<style>` tags
- Global styles go in App.vue
- Component-scoped styles recommended (add `scoped` attribute)

## Testing Guidelines

### Unit Testing (Jest)

**Configuration:** jest.config.js:1-31

**Location:** `tests/unit/**/*.spec.js` or `**/__tests__/*.{js,jsx,ts,tsx}`

**Path Alias:** Use `@/` to reference src directory
- Example: `import Component from '@/components/Component.vue'`

**File Extensions Tested:**
- `.js`, `.jsx`, `.json`, `.vue`

**Key Features:**
- Vue component testing with `vue-jest`
- Snapshot testing with `jest-serializer-vue`
- Asset mocking for CSS, images, fonts
- Babel transpilation for modern JavaScript

**Running Tests:**
```bash
npm run test:unit
```

### E2E Testing (Cypress)

**Configuration:** cypress.json

**Location:** `tests/e2e/specs/*.js`

**Output:**
- Screenshots: `tests/e2e/screenshots/` (gitignored)
- Videos: `tests/e2e/videos/` (gitignored)

**Running Tests:**
```bash
npm run test:e2e
```

## Build and Deployment

### Production Build
```bash
npm run build
```

**Output:** `/dist` directory (gitignored)

**Browser Support:**
From .browserslistrc:1-3:
- Browsers with >1% market share
- Last 2 versions of each browser

### Environment Files
- `.env.local` - Local environment variables (gitignored)
- `.env.*.local` - Environment-specific local files (gitignored)

## Key File Locations

### Entry Points
- **HTML Template:** `public/index.html`
- **JavaScript Entry:** `src/main.js:1-9` - Creates Vue instance and mounts to `#app`
- **Root Component:** `src/App.vue`

### Configuration Files
- **Package Config:** `package.json`
- **Babel:** `babel.config.js`
- **ESLint:** `.eslintrc.js`
- **Jest:** `jest.config.js`
- **Cypress:** `cypress.json`
- **PostCSS:** `postcss.config.js`
- **Browsers:** `.browserslistrc`
- **Editor:** `.editorconfig`

## Git Workflow

### Branch Information
- **Current Branch:** `claude/claude-md-mi3unp22dsvq9vq3-01TW5eN49TLFdZDcgDNfBuPg`
- **Repository:** Clean working directory
- All development should occur on the designated branch

### Ignored Files (.gitignore)
- `node_modules/`
- `/dist/` - Production build output
- `/tests/e2e/videos/` and `/tests/e2e/screenshots/`
- `.env.local` and `.env.*.local`
- IDE files (`.idea`, `.vscode`, etc.)
- OS files (`.DS_Store`)
- Log files

## Common Tasks for AI Assistants

### Adding a New Component
1. Create `.vue` file in `src/components/`
2. Use PascalCase for filename
3. Follow the template-script-style structure
4. Import and register in parent component
5. Create corresponding unit test in `tests/unit/`

### Modifying Existing Components
1. Always read the component file first
2. Follow existing code style and conventions
3. Update tests if behavior changes
4. Run `npm run lint` before committing
5. Consider if E2E tests need updates

### Adding Dependencies
1. Use `npm install <package>` for runtime dependencies
2. Use `npm install -D <package>` for dev dependencies
3. Update package.json
4. Commit package-lock.json changes

### Code Quality Checks
Before committing:
1. Run `npm run lint` - Fix linting issues
2. Run `npm run test:unit` - Ensure unit tests pass
3. Run `npm run build` - Verify production build works
4. (Optional) Run `npm run test:e2e` - E2E validation

## Important Notes for AI Assistants

### Vue 2 Specific Considerations
- This project uses Vue 2.6.10, not Vue 3
- Options API is the primary pattern (not Composition API)
- `new Vue()` instance creation in main.js
- Vue Test Utils beta version for Vue 2

### Do Not
- Do not modify configuration files without explicit request
- Do not add Vue 3 syntax (Composition API, Teleport, etc.)
- Do not commit to main/master without permission
- Do not ignore ESLint errors - fix them
- Do not create files in gitignored directories

### Always
- Read existing files before modifying
- Follow Standard JavaScript style guide
- Write tests for new components/features
- Use `@/` path alias for src imports in tests
- Check that builds succeed after changes
- Maintain consistent component structure
- Use Sass/SCSS for styles when needed
- Keep component names descriptive and clear

### File Naming Patterns
- Components: PascalCase or snake_case (`.vue`)
- Tests: `*.spec.js` for unit tests
- Config: `*.config.js` pattern
- Assets: Stored in `src/assets/`

### Version Compatibility
- Node.js environment required
- Vue CLI 3.x tooling
- ES6+ syntax supported (Babel transpilation)
- Legacy browser support via polyfills

## Project Context

This is a learning/educational project for Vue.js development. The setup follows Vue CLI 3 best practices with a complete testing infrastructure. The project name "belajar-vue" (learning Vue) indicates this is meant for experimentation and practice with Vue.js fundamentals.

When assisting with this project:
- Prioritize educational value in explanations
- Follow Vue.js best practices and conventions
- Maintain consistency with existing code patterns
- Ensure all tooling (lint, test, build) works correctly
- Document decisions and changes clearly

---

**Last Updated:** 2025-11-18
**Vue CLI Version:** 3.11.0
**Vue Version:** 2.6.10
**Node Environment:** Development
