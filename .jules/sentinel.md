## 2024-05-09 - Missing .gitignore
**Vulnerability:** Missing `.gitignore` file.
**Learning:** Common sensitive files like `.env` and `.streamlit/secrets.toml` could be accidentally committed to the repository, leading to credential leaks.
**Prevention:** Add a `.gitignore` file to prevent accidental commitment of sensitive files to the repository.

## 2024-05-24 - Automated Dependency Auditing
**Vulnerability:** Vulnerable dependencies could be introduced without detection.
**Learning:** Adding automated scanning in CI/CD pipeline ensures all dependencies are checked for known vulnerabilities before they are merged.
**Prevention:** Implementing a GitHub Actions workflow using `pip-audit` to scan `requirements.txt` on pushes, pull requests, and on a weekly schedule.

## 2024-06-05 - Missing SAST and Over-Permissive CI/CD Workflows
**Vulnerability:** The GitHub Actions workflow lacked SAST (Static Application Security Testing) scanning for the code, and did not restrict workflow permissions, adhering to excessive default permissions instead.
**Learning:** Over-permissive CI/CD workflows pose a significant risk, allowing potential privilege escalation or unauthorized repository changes if compromised. Missing code analysis means we rely solely on dependency scanning and may miss insecure coding patterns.
**Prevention:** Implementing `bandit` alongside `pip-audit` for comprehensive security checking, and applying the principle of least privilege by explicitly setting `permissions: contents: read` in GitHub Actions workflows.
