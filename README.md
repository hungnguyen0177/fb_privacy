[![🔍 CI Quality Checks](https://github.com/geminisportsai/frontend-v2/actions/workflows/ci.yml/badge.svg)](https://github.com/geminisportsai/frontend-v2/actions/workflows/ci.yml)

# 🧪 Playwright End-to-End Testing Documentation

This repository uses [Playwright](https://playwright.dev/) for robust, automated end-to-end (E2E) browser testing. The test suite is designed to ensure the reliability and quality of both UI and critical user flows across multiple environments, with seamless local and CI integration.

---

## Project Structure

- **playwright.config.ts**: Main Playwright configuration file.
- **e2e_web/constants/**: Contains global constants, mock data, and shared configuration for the entire test suite.
- **e2e_web/desktop-layout/**: Tests for desktop layouts and features.
- **e2e_web/shadow-team/**: Tests for Shadow Team layouts and features
- **e2e_testId/**: Defines unique test IDs for identifying components in E2E tests.
- **e2e_web/auth.config.ts**: .

---

## Getting Started
### 1. Install Dependencies

```bash
# Install Playwright
yarn install playwright

# Install test browser
yarn playwright install
```

### 2. Environment Configuration

Tests can target different environments via the `TEST_ENV` variable. This ensures correct endpoints, credentials, and test data are loaded for each environment.

---

## Running Tests
### Run All Tests in a Specific Environment

| Environment   | Command                              |
|---------------|--------------------------------------|
| Local         | `yarn test:local`                    |
| Development   | `yarn test:dev`                      |
| Staging       | `yarn test:staging`                  |
| Production    | `yarn test:production`               |

Each command sets `TEST_ENV` for environment-specific configuration.

### Run a Specific Test File

```bash
yarn test:**[env]** **[path_to_test_file]**
```

- **[env]**: The environment to run tests in. Can be one of local, dev, staging, or production.
- **[path_to_test_file]**: The relative path to the test file you want to run.
  
---

## Viewing Test Reports

After running tests, view the HTML report with:
```bash
yarn playwright show-report
```

**Note:** If you encounter `EADDRINUSE` errors (port 9323 in use), free the port:
```
lsof -i :9323
kill -9 <PID>
```




