## 2024-05-09 - Missing .gitignore
**Vulnerability:** Missing `.gitignore` file.
**Learning:** Common sensitive files like `.env` and `.streamlit/secrets.toml` could be accidentally committed to the repository, leading to credential leaks.
**Prevention:** Add a `.gitignore` file to prevent accidental commitment of sensitive files to the repository.

## 2024-05-24 - Automated Dependency Auditing
**Vulnerability:** Vulnerable dependencies could be introduced without detection.
**Learning:** Adding automated scanning in CI/CD pipeline ensures all dependencies are checked for known vulnerabilities before they are merged.
**Prevention:** Implementing a GitHub Actions workflow using `pip-audit` to scan `requirements.txt` on pushes, pull requests, and on a weekly schedule.

## 2026-06-08 - SAST Scanning and Workflow Permissions
**Vulnerability:** Missing Static Application Security Testing (SAST) and overly permissive CI/CD tokens.
**Learning:** Overly permissive `GITHUB_TOKEN` tokens in GitHub Actions could be leveraged by a malicious PR or compromised dependency. Additionally, while dependencies were being audited, the first-party code was not being statically analyzed for security issues.
**Prevention:** Explicitly set `permissions: { contents: read }` in GitHub Actions workflows to follow the principle of least privilege, and incorporate `bandit` for continuous SAST scanning.
