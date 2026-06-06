## 2024-05-09 - Missing .gitignore
**Vulnerability:** Missing `.gitignore` file.
**Learning:** Common sensitive files like `.env` and `.streamlit/secrets.toml` could be accidentally committed to the repository, leading to credential leaks.
**Prevention:** Add a `.gitignore` file to prevent accidental commitment of sensitive files to the repository.

## 2024-05-24 - Automated Dependency Auditing
**Vulnerability:** Vulnerable dependencies could be introduced without detection.
**Learning:** Adding automated scanning in CI/CD pipeline ensures all dependencies are checked for known vulnerabilities before they are merged.
**Prevention:** Implementing a GitHub Actions workflow using `pip-audit` to scan `requirements.txt` on pushes, pull requests, and on a weekly schedule.

## 2026-06-06 - CI/CD Least Privilege and SAST
**Vulnerability:** GitHub Actions workflows running with default overly permissive permissions and missing Static Application Security Testing (SAST).
**Learning:** Default GHA tokens can be abused if a workflow is compromised. Additionally, dependency auditing alone is insufficient without SAST to catch vulnerabilities in custom code.
**Prevention:** Enforce `permissions: contents: read` as a default least-privilege baseline in GHA workflows and include SAST tools like `bandit` alongside dependency scanners in the automated pipeline.
