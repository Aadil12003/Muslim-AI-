## 2024-05-09 - Missing .gitignore
**Vulnerability:** Missing `.gitignore` file.
**Learning:** Common sensitive files like `.env` and `.streamlit/secrets.toml` could be accidentally committed to the repository, leading to credential leaks.
**Prevention:** Add a `.gitignore` file to prevent accidental commitment of sensitive files to the repository.

## 2024-05-24 - Automated Dependency Auditing
**Vulnerability:** Vulnerable dependencies could be introduced without detection.
**Learning:** Adding automated scanning in CI/CD pipeline ensures all dependencies are checked for known vulnerabilities before they are merged.
**Prevention:** Implementing a GitHub Actions workflow using `pip-audit` to scan `requirements.txt` on pushes, pull requests, and on a weekly schedule.

## 2024-06-28 - Missing SAST and Excessive CI Permissions
**Vulnerability:** The GitHub Actions security audit workflow lacked Static Application Security Testing (SAST) and ran with default permissions. Unnecessary system dependencies were also present.
**Learning:** Default GitHub Actions permissions can lead to token compromise. Missing SAST tools like bandit leave application code unverified.
**Prevention:** Always explicitly set `permissions: contents: read` in workflows, include SAST tools alongside dependency scanners, and regularly remove unnecessary system dependencies.
