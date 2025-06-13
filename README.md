# 🧪 Playwright End-to-End Testing Documentation

This repository uses [Playwright](https://playwright.dev/) for robust, automated end-to-end (E2E) browser testing. The test suite is designed to ensure the reliability and quality of both UI and critical user flows across multiple environments, with seamless local and CI integration.

---

## Project Structure

- **desktop-layout/**: Tests for desktop-oriented features and layouts.
- **layout-web/**: Tests for general web layouts and shared flows.
- **fixtures/**: Mock data and reusable test fixtures.
- **utils/**: Helper functions and custom selectors for tests.

---

## Getting Started
### 1. Install Dependencies

```bash
# Install Playwright for Python
pip install playwright
playwright install

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
yarn test:[env] [path_to_test_file]

- **[env]**: Can be local/dev/staging/production.

---

## Viewing Test Reports

After running tests, view the HTML report with:
> **Note:** If you encounter `EADDRINUSE` errors (port 9323 in use), free the port:
> ```
> lsof -i :9323
> kill -9 <PID>
> ```

```bash
yarn playwright show-report



