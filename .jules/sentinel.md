## 2024-05-18 - Missing Automated Dependency Audit
**Vulnerability:** Lack of automated continuous dependency vulnerability scanning.
**Learning:** Dependencies may become vulnerable over time, and without automated checks, these vulnerabilities can persist in the codebase and pose significant security risks.
**Prevention:** Implement a GitHub Action workflow using `pip-audit` to automatically run continuous security audits on dependencies during CI/CD and on a schedule.

## 2024-05-09 - Missing .gitignore
**Vulnerability:** Missing `.gitignore` file.
**Learning:** Common sensitive files like `.env` and `.streamlit/secrets.toml` could be accidentally committed to the repository, leading to credential leaks.
**Prevention:** Add a `.gitignore` file to prevent accidental commitment of sensitive files to the repository.

## 2024-05-24 - Automated Dependency Auditing
**Vulnerability:** Vulnerable dependencies could be introduced without detection.
**Learning:** Adding automated scanning in CI/CD pipeline ensures all dependencies are checked for known vulnerabilities before they are merged.
**Prevention:** Implementing a GitHub Actions workflow using `pip-audit` to scan `requirements.txt` on pushes, pull requests, and on a weekly schedule.
