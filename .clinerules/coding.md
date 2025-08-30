# Core Coding Principles

Ask if you need clarification of any of these rules or if they conflict one another

## Code Quality & Style

### Clarity & Maintainability:

- Write clear, readable code that explains its intent
- Use descriptive names with boolean prefixes (isLoading, hasPermission, canEdit)
- Add comments only when the "why" isn't obvious from the code
- Remove dead code and unused imports before committing

### Code Organization:

- Prefer functions over classes in modern JavaScript/TypeScript
- Use composition patterns and avoid deep inheritance
- Extract reusable logic into small, focused functions (generally under 20-30 lines)
- Don't repeat yourself: create utilities for common operations

### Completeness & Security:

- Write complete implementations, not placeholders or TODO comments
- Apply least privilege: only grant necessary permissions/access
- Validate inputs and handle edge cases

## Code Structure & Organization

### File Organization:

- Use kebab-case for directories (components/user-profile, not components/UserProfile)
- Colocate related files: place components, tests, and styles in the same directory
- Structure files within components: main component → subcomponents → utilities → types

### Exports:

- Use named exports by default (export const Button = ...)
- Reserve default exports for single-purpose modules or when required by frameworks
- Export types and interfaces alongside components

### Architecture:

- Follow Single Responsibility Principle: one clear purpose per file/function
- Use feature-based folder structure for complex applications
- Keep utilities and helpers close to where they're used

## Error Handling & Validation

### Function Structure:

- Use guard clauses and early returns for error conditions
- Keep the main logic (happy path) at the end of functions
- Avoid deeply nested conditional statements

### Error Management:

- Use try/catch for unexpected errors; return error objects for expected failures
- Provide contextual error messages that help with debugging
- Handle API failures gracefully with user-friendly feedback

### Validation:

- Validate inputs at boundaries (API endpoints, form submissions)
- Use runtime validation libraries like Zod for external data
- Write testable code by avoiding tight coupling

## UI & Styling

### Design System:

- Create reusable components when patterns repeat (3+ times)
- Use design tokens consistently for colors, spacing, and typography

### Component Architecture:

- Separate logic (custom hooks) from presentation (components)

### Responsive Design:

- Design mobile-first, enhance for larger screens
- Ensure 4.5:1 color contrast ratio for accessibility

## Performance Optimization

### Core Optimization:

- Monitor Core Web Vitals (LCP, CLS, INP) and optimize when needed
- Use code splitting with dynamic imports for large bundles
- Optimize images and fonts with framework-specific tools

### Caching & Data:

- Leverage data fetching libraries for intelligent caching
- Use server-side rendering when appropriate for initial load performance

### Maintenance:

- Keep dependencies updated for performance and security improvements
- Configure build tools to eliminate unused code

## Security

### Input & Data Protection:

- Validate and sanitize all user inputs on both client and server
- Use parameterized queries for database operations
- Never store sensitive data in client-side storage or state

### Authentication & Authorization:

- Implement secure session management
- Apply least privilege principle for all access controls
- Protect authenticated endpoints from unauthorized access

### Infrastructure:

- Use HTTPS in production environments
- Implement rate limiting on public API endpoints
- Apply security headers (CSP, etc.) to prevent common attacks

## Build & Deployment

### CI/CD Pipeline:

- Use environment variables with validation for configuration
- Monitor bundle sizes and performance metrics

### Production Monitoring:

- Implement error tracking and logging
- Use feature flags for gradual rollouts

### Deployment Strategy:

- Use containerization for consistent environments
- Implement caching strategies for better performance