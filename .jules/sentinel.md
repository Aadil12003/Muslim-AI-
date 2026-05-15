## 2024-05-09 - Missing .gitignore
**Vulnerability:** Missing `.gitignore` file.
**Learning:** Common sensitive files like `.env` and `.streamlit/secrets.toml` could be accidentally committed to the repository, leading to credential leaks.
**Prevention:** Add a `.gitignore` file to prevent accidental commitment of sensitive files to the repository.

## 2024-05-15 - Add Security Audit Workflow
**Vulnerability:** Lack of automated dependency vulnerability scanning in CI/CD pipeline.
**Learning:** Adding a GitHub Actions workflow using `safety` and `pip-audit` helps identify known vulnerabilities in dependencies during pushes and pull requests, preventing vulnerable packages from being merged into `main`. Also updated `SECURITY.md` to point to GitHub private vulnerability reporting.
**Prevention:** Implement automated security auditing for dependencies in CI pipelines and provide clear instructions for private vulnerability reporting.
