# GitHub Copilot Instructions for Dev-Apps-And-Extensions

## Repository Overview

This is a monorepo for development of applications and extensions. It currently contains:

- **BearBuddy Free**: A VSCode extension - Free (MIT) edition
- **BearBuddy Pro**: A VSCode extension - Pro (Proprietary) edition

## Repository Structure

```
/
├── extensions/                         # VSCode extensions workspace
│   ├── bearbuddy-free/                 # BearBuddy Free edition (MIT License)
│   │   ├── src/                        # TypeScript source files
│   │   │   └── extension.ts            # Main extension entry point
│   │   ├── package.json                # Extension manifest & dependencies
│   │   ├── tsconfig.json               # TypeScript configuration
│   │   └── esbuild.js                  # Build configuration
│   ├── bearbuddy-pro/                  # BearBuddy Pro edition (Proprietary License)
│   │   ├── src/                        # TypeScript source files
│   │   │   └── extension.ts            # Main extension entry point
│   │   ├── package.json                # Extension manifest & dependencies
│   │   ├── tsconfig.json               # TypeScript configuration
│   │   └── esbuild.js                  # Build configuration
│   ├── core-extension/                 # Core extension package
│   └── pro-extension/                  # Pro extension package
├── docs/
│   └── bearbuddy/                      # BearBuddy GitHub Pages documentation
├── .github/                            # GitHub configuration
│   ├── workflows/                      # GitHub Actions workflows
│   ├── ISSUE_TEMPLATE/                 # Issue templates
│   └── pull_request_template.md        # PR template
└── README.md                           # Repository documentation
```

## Technologies & Tools

- **Language**: TypeScript
- **Package Manager**: npm (per extension), pnpm (monorepo root)
- **Build Tool**: esbuild for fast bundling
- **Platform**: VSCode Extension API (^1.80.0)
- **Node Version**: >= 18.0.0
- **npm Version**: >= 9.0.0

## Development Workflow

### Setup & Installation

```bash
# Install dependencies for BearBuddy Free
cd extensions/bearbuddy-free
npm install

# Install dependencies for BearBuddy Pro
cd extensions/bearbuddy-pro
npm install
```

### Building

```bash
# Build BearBuddy Free
cd extensions/bearbuddy-free
npm run build

# Build BearBuddy Pro
cd extensions/bearbuddy-pro
npm run build
```

### Development (Watch Mode)

```bash
# Watch BearBuddy Free
cd extensions/bearbuddy-free
npm run watch

# Watch BearBuddy Pro
cd extensions/bearbuddy-pro
npm run watch
```

### Packaging

```bash
# Package BearBuddy Free
cd extensions/bearbuddy-free
npm run package

# Package BearBuddy Pro
cd extensions/bearbuddy-pro
npm run package
```

### Testing

```bash
# Run tests (currently placeholder)
npm run test
```

### Linting

```bash
# Run linting (currently placeholder)
npm run lint
```

## Code Style & Conventions

### TypeScript

- Use TypeScript for all source files
- Enable strict type checking
- Use meaningful variable and function names
- Add JSDoc comments for public APIs
- Follow VSCode extension best practices

### Git Commits

Follow conventional commit format:

```
feat: add new feature
fix: fix bug
docs: update documentation
style: formatting changes
refactor: code refactoring
test: add tests
chore: maintenance tasks
```

## License Considerations

### BearBuddy Free

- **License**: MIT (Open Source)
- **Location**: `extensions/bearbuddy-free/`
- **Contributions**: Accepted for core features

### BearBuddy Pro

- **License**: Proprietary
- **Location**: `extensions/bearbuddy-pro/`
- **Contributions**: Limited to bug fixes and optimizations

**Important**: When making changes, be mindful of which edition you're working in and respect the license boundaries.

## Working with the Extensions

- Each BearBuddy edition is an independent package in the `extensions/` workspace directory
- Always run commands from the appropriate extension directory:
  - BearBuddy Free: `extensions/bearbuddy-free/`
  - BearBuddy Pro: `extensions/bearbuddy-pro/`
- Changes to one edition should not affect the other unless explicitly intended

## Testing VSCode Extensions

1. Open the project in VSCode
2. Press F5 to launch the Extension Development Host
3. Test your changes in the new VSCode window
4. Check the Debug Console for logs and errors
5. Use VSCode Extension Development best practices

## Important Notes

- Build artifacts are in `dist/` directories (ignored by git)
- Packaged extensions are `.vsix` files (ignored by git)
- `node_modules/` is ignored by git
- Always test extensions in the Extension Development Host before committing

## Documentation

- BearBuddy docs are in the `docs/bearbuddy/` directory
- Documentation is published to GitHub Pages
- Keep README files up to date when making significant changes

## Before Submitting Changes

1. Ensure code builds without errors
2. Test the extension in VSCode Extension Development Host
3. Follow the existing code style
4. Update documentation if needed
5. Write clear commit messages using conventional commit format
6. Verify you're working in the correct edition (Free vs Pro)
