# AI Testing - Vite + React.js Web Application

AI testing is a Vite + React.js web application for AI testing purposes. This repository contains a modern React application built with Vite for fast development and optimized production builds.

**ALWAYS reference these instructions first and fallback to search or bash commands only when you encounter unexpected information that does not match the info here.**

## Working Effectively

### Bootstrap and Setup
The repository already contains a fully configured Vite + React.js project. If starting from a fresh clone:

```bash
npm install
```
- **Timing**: Takes ~17 seconds
- **NEVER CANCEL**: Wait for completion
- **Timeout**: Set timeout to 60+ seconds for safety

### Build Commands
```bash
# Development build and serve
npm run dev
```
- **Timing**: Starts in ~210ms, runs continuously
- **URL**: http://localhost:5173/
- **NEVER CANCEL**: Runs until manually stopped
- **Timeout**: Set timeout to 3600+ seconds (1 hour) for development sessions

```bash
# Production build
npm run build
```
- **Timing**: Takes ~1-2 seconds
- **Output**: Creates `dist/` directory with optimized assets
- **Timeout**: Set timeout to 120+ seconds

```bash
# Preview production build
npm run preview
```
- **Timing**: Starts immediately, runs continuously
- **URL**: http://localhost:4173/
- **NEVER CANCEL**: Runs until manually stopped
- **Timeout**: Set timeout to 3600+ seconds (1 hour) for preview sessions

### Code Quality
```bash
# Lint the codebase
npm run lint
```
- **Timing**: Takes ~0.5 seconds
- **NEVER CANCEL**: Always wait for completion
- **Timeout**: Set timeout to 60+ seconds
- **CRITICAL**: Always run before committing changes

### Testing
- **No test suite configured**: The project does not include a test runner by default
- Adding tests requires installing a testing framework like Vitest or Jest

## Validation Scenarios

**ALWAYS manually validate changes by running through these complete end-to-end scenarios:**

### Primary Validation Workflow
1. **Start development server**: `npm run dev`
2. **Open browser**: Navigate to http://localhost:5173/
3. **Test counter functionality**: 
   - Click the "count is 0" button multiple times
   - Verify counter increments correctly (0 → 1 → 2 → etc.)
4. **Test Hot Module Replacement (HMR)**:
   - Edit `src/App.jsx` and save
   - Verify changes appear instantly without page reload
5. **Test production build**:
   - Stop dev server
   - Run `npm run build`
   - Run `npm run preview`
   - Navigate to http://localhost:4173/
   - Verify application works identically to development

### Code Change Validation
- **ALWAYS** run `npm run lint` before committing
- **ALWAYS** test the modified functionality in the browser
- **ALWAYS** verify both development and production builds work
- **ALWAYS** check that HMR works after making changes to React components

## Project Structure

### Key Files and Directories
```
├── .github/                 # GitHub configuration and workflows
│   └── copilot-instructions.md
├── dist/                    # Production build output (generated)
├── node_modules/            # Dependencies (generated)
├── public/                  # Static assets
│   └── vite.svg            # Vite logo
├── src/                     # Source code
│   ├── assets/             # React assets
│   │   └── react.svg       # React logo
│   ├── App.css             # Main component styles
│   ├── App.jsx             # Main React component
│   ├── index.css           # Global styles
│   └── main.jsx            # Application entry point
├── .gitignore              # Git ignore rules
├── eslint.config.js        # ESLint configuration
├── index.html              # HTML template
├── package.json            # Dependencies and scripts
├── package-lock.json       # Locked dependency versions
├── README.md               # Project documentation
└── vite.config.js          # Vite configuration
```

### Important Code Locations
- **Main component**: `src/App.jsx` - Contains the primary application logic and counter functionality
- **Entry point**: `src/main.jsx` - React application bootstrap
- **HTML template**: `index.html` - Base HTML structure
- **Configuration**: `vite.config.js` - Vite build configuration
- **Linting**: `eslint.config.js` - Code quality rules

## Common Tasks

### Adding New Components
1. Create new `.jsx` files in `src/` directory
2. Import and use in `src/App.jsx` or other components
3. Test with `npm run dev`
4. Always run `npm run lint` before committing

### Modifying Styles
1. Edit `src/App.css` for component-specific styles
2. Edit `src/index.css` for global styles
3. Changes are hot-reloaded automatically in development

### Debugging
1. Use browser DevTools for runtime debugging
2. Check console for React warnings and errors
3. Use React DevTools browser extension for component inspection
4. Vite provides detailed error overlay in development mode

## Node.js and Dependencies

### Current Versions (Validated)
- **Node.js**: v20.19.5
- **npm**: 10.8.2
- **Vite**: ^7.1.2
- **React**: ^19.1.1

### Key Dependencies
- **@vitejs/plugin-react**: React support for Vite
- **eslint**: Code linting with React-specific rules
- **eslint-plugin-react-hooks**: React Hooks linting
- **eslint-plugin-react-refresh**: React Fast Refresh linting

## Troubleshooting

### Common Issues
1. **Build fails**: Run `npm install` to ensure dependencies are installed
2. **Lint errors**: Run `npm run lint` to see specific issues
3. **Dev server won't start**: Check if port 5173 is available
4. **HMR not working**: Restart dev server with `npm run dev`

### Performance Notes
- **Development**: Vite provides extremely fast HMR and build times
- **Production**: Optimized bundles with code splitting and minification
- **Assets**: Static assets in `public/` are copied as-is to build output

### Browser Compatibility
- Modern browsers supporting ES2020+
- Vite uses native ESM in development
- Production builds include necessary polyfills

## CI/CD Considerations
- Always include `npm run lint` in CI pipeline
- Run `npm run build` to verify production builds work
- Consider adding automated testing framework for CI validation
- Use `npm ci` instead of `npm install` in CI for reproducible builds