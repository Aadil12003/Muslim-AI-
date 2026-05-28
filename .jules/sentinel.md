## 2024-05-09 - Missing .gitignore
**Vulnerability:** Missing `.gitignore` file.
**Learning:** Common sensitive files like `.env` and `.streamlit/secrets.toml` could be accidentally committed to the repository, leading to credential leaks.
**Prevention:** Add a `.gitignore` file to prevent accidental commitment of sensitive files to the repository.

## 2024-05-27 - Automated CI Dependency Vulnerability Scanning
**Vulnerability:** Missing automated vulnerability scanning for Python dependencies in CI pipeline.
**Learning:** While the project has a `requirements.txt` file and dependabot updates enabled, there was no continuous integration step to proactively scan dependencies for known vulnerabilities during the development process (push/pull request). This is a structural security gap that could allow developers to introduce vulnerable packages without immediate feedback.
**Prevention:** Implemented a GitHub Actions workflow (`.github/workflows/security-audit.yml`) to automatically run `pip-audit -r requirements.txt` on every push to main, pull request, and weekly. This ensures that any introduced vulnerabilities are caught immediately in the CI pipeline before merging.
