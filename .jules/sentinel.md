## 2024-05-09 - Missing .gitignore
**Vulnerability:** Missing `.gitignore` file.
**Learning:** Common sensitive files like `.env` and `.streamlit/secrets.toml` could be accidentally committed to the repository, leading to credential leaks.
**Prevention:** Add a `.gitignore` file to prevent accidental commitment of sensitive files to the repository.

## 2024-05-24 - Automated Dependency Auditing
**Vulnerability:** Vulnerable dependencies could be introduced without detection.
**Learning:** Adding automated scanning in CI/CD pipeline ensures all dependencies are checked for known vulnerabilities before they are merged.
**Prevention:** Implementing a GitHub Actions workflow using `pip-audit` to scan `requirements.txt` on pushes, pull requests, and on a weekly schedule.

## 2026-06-18 - Missing SAST and Overpermissive GitHub Actions
**Vulnerability:** GitHub Actions workflow `security-audit.yml` lacked explicit read-only permissions (`permissions: contents: read`) and missed SAST integration.
**Learning:** Default permissions in CI/CD are overly broad, and dependency scanning alone fails to catch first-party code vulnerabilities.
**Prevention:** Always enforce the principle of least privilege in CI/CD pipelines and include static analysis tools like `bandit` to cover custom code vulnerabilities.
