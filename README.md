# GH Actions Exercise 1

This project demonstrates a basic CI/CD workflow for a JavaScript/React application using GitHub Actions. It includes automated testing, linting, building, and artifact deployment.

## Project Structure

- **src/**: Source code for the React application.
- **dist/**: Build output directory (created after running the build).
- **.github/workflows/deploy-website.yml**: GitHub Actions workflow for CI/CD.
- **.eslintrc.json**: ESLint configuration for code linting.

## Workflow Overview

The GitHub Actions workflow (`deploy-website.yml`) runs on every push to the `main` branch and consists of three jobs:

1. **test**  
   - Checks out the code.
   - Caches and installs npm dependencies.
   - Runs linting (`npm run lint`).
   - Runs tests (`npm run test`).

2. **build**  
   - Runs after `test` passes.
   - Checks out the code.
   - Caches and installs npm dependencies.
   - Builds the project (`npm run build`).
   - Archives the `dist` folder as a build artifact.

3. **deploy**  
   - Runs after `build` completes.
   - Downloads the build artifact into the `dist` directory.
   - Outputs the main JS script file name.
   - Lists the contents of the workspace.
   - Placeholder for deployment command.

## How to Use

1. **Install dependencies:**
   ```sh
   npm ci
   ```

2. **Run linting:**
   ```sh
   npm run lint
   ```

3. **Run tests:**
   ```sh
   npm run test
   ```

4. **Build the project:**
   ```sh
   npm run build
   ```

## Notes

- The workflow caches npm dependencies for faster builds.
- Artifacts are uploaded and downloaded to preserve the `dist` directory between jobs.
- The deploy step currently only echoes a message; replace it with your actual deployment command.

## Requirements

- Node.js and npm
- GitHub repository with Actions enabled

---
*This project is for learning and demonstration purposes.*