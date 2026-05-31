## 2024-05-09 - Missing .gitignore
**Vulnerability:** Missing `.gitignore` file.
**Learning:** Common sensitive files like `.env` and `.streamlit/secrets.toml` could be accidentally committed to the repository, leading to credential leaks.
**Prevention:** Add a `.gitignore` file to prevent accidental commitment of sensitive files to the repository.

## 2024-05-24 - Automated Dependency Auditing
**Vulnerability:** Vulnerable dependencies could be introduced without detection.
**Learning:** Adding automated scanning in CI/CD pipeline ensures all dependencies are checked for known vulnerabilities before they are merged.
**Prevention:** Implementing a GitHub Actions workflow using `pip-audit` to scan `requirements.txt` on pushes, pull requests, and on a weekly schedule.

## 2024-05-31 - CI/CD Pipeline Least Privilege
**Vulnerability:** Default GitHub Actions permissions are too broad, which could allow compromised dependencies or actions to modify the repository.
**Learning:** Limiting the scope of the default `GITHUB_TOKEN` reduces the potential attack surface. Also, proactive security scanning ensures any code introduced is analyzed for common security issues.
**Prevention:** Apply `permissions: contents: read` to workflows to enforce the principle of least privilege, and incorporate a SAST tool like `bandit` alongside dependency scanning to identify vulnerabilities early in the CI pipeline.
