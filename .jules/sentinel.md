## 2024-05-09 - Missing .gitignore
**Vulnerability:** Missing `.gitignore` file.
**Learning:** Common sensitive files like `.env` and `.streamlit/secrets.toml` could be accidentally committed to the repository, leading to credential leaks.
**Prevention:** Add a `.gitignore` file to prevent accidental commitment of sensitive files to the repository.

## 2024-05-24 - Automated Dependency Auditing
**Vulnerability:** Vulnerable dependencies could be introduced without detection.
**Learning:** Adding automated scanning in CI/CD pipeline ensures all dependencies are checked for known vulnerabilities before they are merged.
**Prevention:** Implementing a GitHub Actions workflow using `pip-audit` to scan `requirements.txt` on pushes, pull requests, and on a weekly schedule.

## 2026-06-29 - Secure CI/CD Workflow
**Vulnerability:** The GitHub Actions workflow `security-audit.yml` lacked permission restrictions and was missing Static Application Security Testing (SAST).
**Learning:** Workflows without explicit permissions default to broader access than necessary, violating the principle of least privilege. Furthermore, only checking dependencies (`pip-audit`) misses vulnerabilities in the codebase itself.
**Prevention:** Always define `permissions: contents: read` (or similar least privilege) at the workflow level and include tools like `bandit` for SAST in Python projects.
