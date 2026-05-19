## 2024-05-18 - Missing Automated Dependency Audit
**Vulnerability:** Lack of automated continuous dependency vulnerability scanning.
**Learning:** Dependencies may become vulnerable over time, and without automated checks, these vulnerabilities can persist in the codebase and pose significant security risks.
**Prevention:** Implement a GitHub Action workflow using `pip-audit` to automatically run continuous security audits on dependencies during CI/CD and on a schedule.

## 2024-05-09 - Missing .gitignore
**Vulnerability:** Missing `.gitignore` file.
**Learning:** Common sensitive files like `.env` and `.streamlit/secrets.toml` could be accidentally committed to the repository, leading to credential leaks.
**Prevention:** Add a `.gitignore` file to prevent accidental commitment of sensitive files to the repository.
