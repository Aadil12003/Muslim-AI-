## 2024-05-09 - Missing .gitignore
**Vulnerability:** Missing `.gitignore` file.
**Learning:** Common sensitive files like `.env` and `.streamlit/secrets.toml` could be accidentally committed to the repository, leading to credential leaks.
**Prevention:** Add a `.gitignore` file to prevent accidental commitment of sensitive files to the repository.

## 2024-05-24 - Automated Dependency Auditing
**Vulnerability:** Vulnerable dependencies could be introduced without detection.
**Learning:** Adding automated scanning in CI/CD pipeline ensures all dependencies are checked for known vulnerabilities before they are merged.
**Prevention:** Implementing a GitHub Actions workflow using `pip-audit` to scan `requirements.txt` on pushes, pull requests, and on a weekly schedule.

## 2026-06-07 - Workflow Permissions and SAST Integration
**Vulnerability:** GitHub Actions workflow lacked specific permissions restrictions and SAST scanning.
**Learning:** Running workflows with default permissions violates the principle of least privilege. Combining dependency auditing with Static Application Security Testing (SAST) like Bandit provides defense-in-depth.
**Prevention:** explicitly restrict workflow permissions to 'contents: read' and integrate both dependency and static code analysis in the security audit CI.
