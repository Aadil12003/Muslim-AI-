## 2024-05-09 - Missing .gitignore
**Vulnerability:** Missing `.gitignore` file.
**Learning:** Common sensitive files like `.env` and `.streamlit/secrets.toml` could be accidentally committed to the repository, leading to credential leaks.
**Prevention:** Add a `.gitignore` file to prevent accidental commitment of sensitive files to the repository.

## 2024-05-24 - Automated Dependency Auditing
**Vulnerability:** Vulnerable dependencies could be introduced without detection.
**Learning:** Adding automated scanning in CI/CD pipeline ensures all dependencies are checked for known vulnerabilities before they are merged.
**Prevention:** Implementing a GitHub Actions workflow using `pip-audit` to scan `requirements.txt` on pushes, pull requests, and on a weekly schedule.

## 2024-06-18 - Missing SAST Scanning in CI
**Vulnerability:** Lack of automated Static Application Security Testing (SAST) meant vulnerable code patterns could be introduced into the main branch undetected.
**Learning:** Adding a SAST tool like `bandit` alongside dependency auditing (`pip-audit`) provides defense-in-depth, catching insecure code patterns before deployment. Also, GitHub Actions workflows should always restrict default `GITHUB_TOKEN` permissions using `permissions: contents: read` to follow the principle of least privilege.
**Prevention:** Incorporate `bandit -r .` into the continuous integration pipeline and explicitly limit workflow permissions to prevent potential workflow compromises from having write access.
