## 2024-05-09 - Missing .gitignore
**Vulnerability:** Missing `.gitignore` file.
**Learning:** Common sensitive files like `.env` and `.streamlit/secrets.toml` could be accidentally committed to the repository, leading to credential leaks.
**Prevention:** Add a `.gitignore` file to prevent accidental commitment of sensitive files to the repository.

## 2024-05-24 - Automated Dependency Auditing
**Vulnerability:** Vulnerable dependencies could be introduced without detection.
**Learning:** Adding automated scanning in CI/CD pipeline ensures all dependencies are checked for known vulnerabilities before they are merged.
**Prevention:** Implementing a GitHub Actions workflow using `pip-audit` to scan `requirements.txt` on pushes, pull requests, and on a weekly schedule.
## 2026-06-15 - Missing SAST and Overly Permissive CI
**Vulnerability:** The GitHub Actions workflow `security-audit.yml` lacked restricted permissions (`contents: read`) and did not perform Static Application Security Testing (SAST) with `bandit`.
**Learning:** Default GitHub Actions permissions can be overly broad, and dependency scanning alone (pip-audit) is insufficient without SAST to catch code-level vulnerabilities.
**Prevention:** Always explicitly define `permissions: contents: read` (or least privilege) in workflows and ensure both dependency and static code analysis tools are integrated into the CI pipeline.
