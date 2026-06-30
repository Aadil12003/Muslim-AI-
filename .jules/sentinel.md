## 2024-05-09 - Missing .gitignore
**Vulnerability:** Missing `.gitignore` file.
**Learning:** Common sensitive files like `.env` and `.streamlit/secrets.toml` could be accidentally committed to the repository, leading to credential leaks.
**Prevention:** Add a `.gitignore` file to prevent accidental commitment of sensitive files to the repository.

## 2024-05-24 - Automated Dependency Auditing
**Vulnerability:** Vulnerable dependencies could be introduced without detection.
**Learning:** Adding automated scanning in CI/CD pipeline ensures all dependencies are checked for known vulnerabilities before they are merged.
**Prevention:** Implementing a GitHub Actions workflow using `pip-audit` to scan `requirements.txt` on pushes, pull requests, and on a weekly schedule.

## 2024-07-01 - Missing SAST and Excessive Workflow Permissions
**Vulnerability:** The CI workflow lacked Static Application Security Testing (SAST) and executed with default (potentially broad) permissions.
**Learning:** Even repositories without application code initially should implement SAST (like Bandit) and restrict GITHUB_TOKEN permissions (`contents: read`) to establish a secure baseline and adhere to the principle of least privilege.
**Prevention:** Always configure `permissions: contents: read` in GitHub Actions workflows and include SAST tools in the security audit pipeline by default.
