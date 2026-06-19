## 2024-05-09 - Missing .gitignore
**Vulnerability:** Missing `.gitignore` file.
**Learning:** Common sensitive files like `.env` and `.streamlit/secrets.toml` could be accidentally committed to the repository, leading to credential leaks.
**Prevention:** Add a `.gitignore` file to prevent accidental commitment of sensitive files to the repository.

## 2024-05-24 - Automated Dependency Auditing
**Vulnerability:** Vulnerable dependencies could be introduced without detection.
**Learning:** Adding automated scanning in CI/CD pipeline ensures all dependencies are checked for known vulnerabilities before they are merged.
**Prevention:** Implementing a GitHub Actions workflow using `pip-audit` to scan `requirements.txt` on pushes, pull requests, and on a weekly schedule.
## 2025-02-14 - Improve Security Audit Workflow

**Vulnerability:** GitHub Actions workflow `security-audit.yml` had overly permissive permissions and lacked SAST scanning.
**Learning:** Default GITHUB_TOKEN permissions can be too broad, increasing the risk if a workflow is compromised. Furthermore, while dependencies were checked for CVEs (`pip-audit`), the application code itself lacked automated security scanning.
**Prevention:** Always follow the principle of least privilege by explicitly defining `permissions: contents: read` (or similar minimal required scopes) in GitHub Actions workflows. Additionally, integrate a SAST tool (like `bandit` for Python) into the CI pipeline to catch hardcoded secrets and insecure coding practices early.
