# CLAUDE.md - AI Assistant Guide

This document provides comprehensive guidance for AI assistants working on this repository.

## Repository Overview

**Repository Name:** jack-react-test
**Type:** React/JavaScript Project (Intended)
**Current State:** Minimal setup - early stage development
**Primary Branch:** Not yet defined (use `main` or `master` as default)

### Current Structure

```
jack-react-test/
├── .git/           # Git version control
├── README.md       # Project documentation
└── CLAUDE.md       # This file - AI assistant guide
```

## Project Status

This is a newly initialized repository with minimal content. The project name suggests it's intended for React development, but no framework or dependencies have been set up yet.

### Initial State
- Single commit: "first commit" (339e8ae)
- Only contains: README.md
- No package.json, dependencies, or build configuration
- No source code files

## Development Workflow

### Git Workflow

**Branch Naming Convention:**
- Feature branches: `feature/<feature-name>`
- Bug fixes: `fix/<bug-description>`
- AI assistant branches: `claude/claude-md-<session-id>`
- Experimental: `experiment/<description>`

**Commit Message Guidelines:**
- Use imperative mood: "Add feature" not "Added feature"
- Keep first line under 72 characters
- Reference issues when applicable
- Be descriptive but concise

**Example commit messages:**
```
Add React project scaffolding with Vite

Set up initial component structure
- Add App component
- Add basic routing
- Configure ESLint and Prettier

Fix: Resolve rendering issue in Dashboard component
```

### Development Process

1. **Before Making Changes:**
   - Read relevant files first using the Read tool
   - Understand existing code structure
   - Check for similar patterns in the codebase

2. **Making Changes:**
   - Follow existing code style and conventions
   - Keep changes focused and minimal
   - Avoid over-engineering
   - Don't add features beyond what was requested

3. **After Changes:**
   - Test changes when possible
   - Commit with descriptive messages
   - Push to the designated branch

## Code Conventions (To Be Established)

### When React Project is Set Up

**File Structure (Recommended):**
```
src/
├── components/     # Reusable components
├── pages/          # Page-level components
├── hooks/          # Custom React hooks
├── utils/          # Utility functions
├── services/       # API and external services
├── context/        # React context providers
├── styles/         # Global styles/theme
├── types/          # TypeScript types (if using TS)
└── App.jsx         # Main application component
```

**Naming Conventions:**
- Components: PascalCase (e.g., `UserProfile.jsx`)
- Hooks: camelCase with 'use' prefix (e.g., `useAuth.js`)
- Utilities: camelCase (e.g., `formatDate.js`)
- Constants: UPPER_SNAKE_CASE (e.g., `API_BASE_URL`)

**Component Structure:**
```jsx
// Imports
import React, { useState, useEffect } from 'react';

// Component definition
function ComponentName({ prop1, prop2 }) {
  // Hooks
  const [state, setState] = useState(null);

  // Effects
  useEffect(() => {
    // effect logic
  }, [dependencies]);

  // Event handlers
  const handleEvent = () => {
    // handler logic
  };

  // Render
  return (
    <div>
      {/* JSX */}
    </div>
  );
}

// Export
export default ComponentName;
```

### Code Quality Guidelines

**DO:**
- Use functional components with hooks
- Keep components small and focused
- Extract reusable logic into custom hooks
- Use meaningful variable and function names
- Add comments only where logic isn't self-evident
- Handle errors at appropriate boundaries
- Validate user input at system boundaries

**DON'T:**
- Add unnecessary comments or documentation
- Over-engineer solutions
- Add error handling for impossible scenarios
- Create abstractions for one-time operations
- Add features not explicitly requested
- Use class components unless maintaining legacy code

## Dependencies Management

### When Setting Up Package.json

**Expected Dependencies (for React projects):**
- React & ReactDOM
- Build tool (Vite recommended, or Create React App)
- Router (React Router if needed)
- State management (only if needed - prefer Context API first)

**Development Dependencies:**
- ESLint (code linting)
- Prettier (code formatting)
- Testing library (Jest, Vitest, or React Testing Library)

**Installation:**
```bash
npm install
# or
yarn install
```

**Running Scripts:**
```bash
npm run dev      # Start development server
npm run build    # Build for production
npm run test     # Run tests
npm run lint     # Run linter
```

## Testing Guidelines

### When Tests Are Added

**Test File Naming:**
- Component tests: `ComponentName.test.jsx`
- Hook tests: `useHookName.test.js`
- Utility tests: `utilityName.test.js`

**Test Structure:**
```javascript
describe('ComponentName', () => {
  it('should render without crashing', () => {
    // test implementation
  });

  it('should handle user interaction', () => {
    // test implementation
  });
});
```

**Testing Priorities:**
1. Critical user paths
2. Complex business logic
3. Edge cases and error handling
4. Component rendering and props

## AI Assistant Instructions

### General Guidelines

1. **Always Read Before Modifying:**
   - Use the Read tool to view files before editing
   - Understand the context and existing patterns
   - Never propose changes to code you haven't read

2. **Use TodoWrite for Complex Tasks:**
   - Break down multi-step tasks
   - Track progress through the todo list
   - Mark tasks complete immediately when done

3. **Minimal Changes:**
   - Only make requested changes
   - Don't refactor unrelated code
   - Avoid adding extra features or "improvements"
   - Don't add error handling for impossible scenarios

4. **Code Style:**
   - Follow existing patterns in the codebase
   - Use consistent formatting
   - No emojis unless explicitly requested
   - Keep solutions simple and focused

5. **Security:**
   - Avoid command injection vulnerabilities
   - Prevent XSS attacks in React components
   - Sanitize user input at boundaries
   - Don't commit sensitive data (.env files, credentials)

### Tool Usage

**Preferred Tools:**
- `Read` - For reading files (not cat)
- `Edit` - For modifying files (not sed/awk)
- `Write` - For creating new files (not echo >)
- `Glob` - For finding files by pattern
- `Grep` - For searching file contents
- `Task` - For complex exploration or multi-step operations

**Bash Usage:**
- Use for git commands, npm/yarn, building, testing
- Don't use for file operations (use specialized tools instead)
- Chain dependent commands with &&
- Run independent commands in parallel

### Git Operations

**Committing:**
```bash
# Check status
git status

# View changes
git diff

# Add files
git add <files>

# Commit with message
git commit -m "$(cat <<'EOF'
Your commit message here
EOF
)"
```

**Pushing:**
```bash
# Push to designated branch
git push -u origin <branch-name>

# Retry on network failure (up to 4 times with exponential backoff)
```

**Creating Pull Requests:**
```bash
# Ensure branch is pushed
git push -u origin <branch-name>

# Create PR with gh CLI
gh pr create --title "PR Title" --body "$(cat <<'EOF'
## Summary
- Change 1
- Change 2

## Test Plan
- [ ] Test item 1
- [ ] Test item 2
EOF
)"
```

### Common Tasks

**Adding a New Component:**
1. Create component file in appropriate directory
2. Write component code following conventions
3. Export component
4. Add tests if applicable
5. Update relevant imports

**Fixing a Bug:**
1. Read the file containing the bug
2. Understand the root cause
3. Make minimal fix
4. Test the fix if possible
5. Commit with descriptive message

**Refactoring:**
1. Only refactor when explicitly requested
2. Maintain existing behavior
3. Keep changes focused
4. Don't mix refactoring with feature additions
5. Test thoroughly after refactoring

## Project Setup Guide (For Future Reference)

### Setting Up a React Project with Vite

```bash
# Create new Vite project
npm create vite@latest . -- --template react

# Or with TypeScript
npm create vite@latest . -- --template react-ts

# Install dependencies
npm install

# Start development server
npm run dev
```

### Setting Up with Create React App

```bash
# Create new CRA project
npx create-react-app .

# Start development server
npm start
```

### Essential Configuration Files

**package.json** - Dependencies and scripts
**vite.config.js** or **webpack.config.js** - Build configuration
**.eslintrc.js** - Linting rules
**.prettierrc** - Code formatting rules
**tsconfig.json** - TypeScript configuration (if using TS)
**.gitignore** - Files to exclude from git
**.env** - Environment variables (never commit this!)

## Common Patterns

### State Management

**Local State:**
```jsx
const [value, setValue] = useState(initialValue);
```

**Context (Global State):**
```jsx
const MyContext = createContext();

function MyProvider({ children }) {
  const [state, setState] = useState(initialState);
  return (
    <MyContext.Provider value={{ state, setState }}>
      {children}
    </MyContext.Provider>
  );
}
```

### Data Fetching

```jsx
function Component() {
  const [data, setData] = useState(null);
  const [loading, setLoading] = useState(true);
  const [error, setError] = useState(null);

  useEffect(() => {
    fetch('/api/data')
      .then(res => res.json())
      .then(setData)
      .catch(setError)
      .finally(() => setLoading(false));
  }, []);

  if (loading) return <div>Loading...</div>;
  if (error) return <div>Error: {error.message}</div>;
  return <div>{/* render data */}</div>;
}
```

### Custom Hooks

```jsx
function useCustomHook(param) {
  const [value, setValue] = useState(null);

  useEffect(() => {
    // hook logic
  }, [param]);

  return { value, setValue };
}
```

## Environment Setup

### Development Environment

**Node.js:** Version 16+ recommended
**Package Manager:** npm or yarn
**Editor:** Any (VS Code recommended with ESLint/Prettier extensions)
**Browser:** Modern browser with React DevTools extension

### Environment Variables

Create `.env` file for environment-specific configuration:
```
VITE_API_URL=http://localhost:3000
VITE_APP_TITLE=My App
```

Access in code:
```javascript
const apiUrl = import.meta.env.VITE_API_URL;
```

**Note:** Never commit `.env` files. Add to `.gitignore`.

## Troubleshooting

### Common Issues

**Port already in use:**
```bash
# Kill process on port 3000
lsof -ti:3000 | xargs kill -9
```

**Node modules issues:**
```bash
# Remove and reinstall
rm -rf node_modules package-lock.json
npm install
```

**Build errors:**
```bash
# Clear cache and rebuild
npm run clean  # if script exists
rm -rf dist
npm run build
```

## Resources

### Documentation
- [React Documentation](https://react.dev)
- [Vite Documentation](https://vitejs.dev)
- [MDN Web Docs](https://developer.mozilla.org)

### Best Practices
- [React Patterns](https://reactpatterns.com)
- [JavaScript Clean Code](https://github.com/ryanmcdermott/clean-code-javascript)

## Changelog

### 2026-01-05
- Initial CLAUDE.md created
- Documented repository structure and conventions
- Added guidelines for React development
- Established git workflow and naming conventions

---

**Last Updated:** 2026-01-05
**Document Version:** 1.0.0
**Maintained By:** AI Assistants working on this repository
