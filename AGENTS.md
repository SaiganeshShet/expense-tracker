# Agent instructions

## Stack and layout

- Use React with Vite and JavaScript.
- Keep application state in `src/App.jsx`.
- Put each UI component in its own file under `src/components/`.
- Put reusable pure logic in `src/utils/`.
- Keep shared styles in `src/index.css` and component or app styles in the relevant CSS files.
- Put Cypress end-to-end specs in `cypress/e2e/`.

## Commands

- Install dependencies: `npm ci`
- Start the development server: `npm run dev`
- Build for production: `npm run build`
- Lint: `npm run lint`
- Run unit tests: `npx vitest run` (after Vitest is configured)
- Run unit tests with coverage: `npx vitest run --coverage` (after coverage is configured)
- Run Cypress end-to-end tests: `npm run cy:run` (after Cypress is configured)

In PowerShell, if the `npm` script is blocked by the execution policy, use `npm.cmd` instead (for example, `npm.cmd run dev`).

## Working rules

- Ask before adding or changing dependencies.
- Work on a dedicated branch for each scoped task; do not make feature changes directly on `main`.
- Before editing, present a short plan and wait for approval.
- Keep changes within the approved scope and run the relevant checks.
- Each component file should have a short comment explaining its props and any local state.
- Summarize the changes and test results for the pull request.
