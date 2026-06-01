## 2024-05-09 - Missing .gitignore
**Vulnerability:** Missing `.gitignore` file.
**Learning:** Common sensitive files like `.env` and `.streamlit/secrets.toml` could be accidentally committed to the repository, leading to credential leaks.
**Prevention:** Add a `.gitignore` file to prevent accidental commitment of sensitive files to the repository.

## 2024-05-24 - Automated Dependency Auditing
**Vulnerability:** Vulnerable dependencies could be introduced without detection.
**Learning:** Adding automated scanning in CI/CD pipeline ensures all dependencies are checked for known vulnerabilities before they are merged.
**Prevention:** Implementing a GitHub Actions workflow using `pip-audit` to scan `requirements.txt` on pushes, pull requests, and on a weekly schedule.

## 2024-06-01 - SAST missing in GitHub Actions
**Vulnerability:** Missing Static Application Security Testing (SAST) in CI/CD pipelines. Default GitHub Actions token is overly permissive.
**Learning:** Adding `bandit` ensures code changes are vetted automatically. Least privilege principle dictates limiting token scopes to only what is needed (e.g., `contents: read`).
**Prevention:** Implement `bandit -r .` in the security audit CI workflow and explicitly restrict workflow token permissions to read-only for contents.
