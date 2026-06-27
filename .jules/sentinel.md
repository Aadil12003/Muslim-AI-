## 2024-05-09 - Missing .gitignore
**Vulnerability:** Missing `.gitignore` file.
**Learning:** Common sensitive files like `.env` and `.streamlit/secrets.toml` could be accidentally committed to the repository, leading to credential leaks.
**Prevention:** Add a `.gitignore` file to prevent accidental commitment of sensitive files to the repository.

## 2024-05-24 - Automated Dependency Auditing
**Vulnerability:** Vulnerable dependencies could be introduced without detection.
**Learning:** Adding automated scanning in CI/CD pipeline ensures all dependencies are checked for known vulnerabilities before they are merged.
**Prevention:** Implementing a GitHub Actions workflow using `pip-audit` to scan `requirements.txt` on pushes, pull requests, and on a weekly schedule.

## 2024-06-25 - Workflow Permissions and SAST
**Vulnerability:** GitHub Actions workflows with default permissions might be exploited, and source code lacks automated static application security testing (SAST).
**Learning:** Hardening workflows with `permissions: contents: read` limits the blast radius of compromised actions. Adding `bandit` scans for static security issues in the codebase.
**Prevention:** Always restrict workflow permissions to the minimum necessary and run a SAST tool like `bandit` alongside dependency audits.
