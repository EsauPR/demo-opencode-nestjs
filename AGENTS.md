Build/Lint/Test Commands

- Build: npm run build
- Lint: npm run lint
- Test (unit): npm test
- Test (e2e): npm run test:e2e
- Single test: npm test -- <path-to-spec.ts>
- Coverage: npm run test:cov
- Format: npm run format

Code Style Guidelines

- Imports: external first, then internal; group and order; prefer absolute imports with path aliases when configured.
- Formatting: follow Prettier; run `npm run format` before committing.
- Types: prefer explicit types; avoid `any`; use interfaces for public shapes; enable repo-wide strict TS rules.
- Naming: camelCase for variables/functions; PascalCase for classes/types; UPPER_SNAKE for constants.
- Error handling: throw descriptive errors; use custom error classes; preserve stack traces; avoid swallowing errors.
- Testing: add unit tests for critical paths; use descriptive test names; leverage Jest features.
- Async: use async/await; handle errors with try/catch; propagate context on rethrow.

Cursor Rules

- Cursor rules: The repository includes a Cursor policy defined in `.cursor/rules/global.mdc`; follow those guidelines for TypeScript/NestJS code, naming, and testing norms.

Copilot Rules

- Copilot rules: none detected (no `.github/copilot-instructions.md` present).
