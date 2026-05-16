## 2024-05-09 - Missing .gitignore
**Vulnerability:** Missing `.gitignore` file.
**Learning:** Common sensitive files like `.env` and `.streamlit/secrets.toml` could be accidentally committed to the repository, leading to credential leaks.
**Prevention:** Add a `.gitignore` file to prevent accidental commitment of sensitive files to the repository.

## 2026-05-16 - Automated Dependency Security Audit
**Vulnerability:** No automated check for vulnerabilities in Python dependencies.
**Learning:** Relying on manual checks for dependency vulnerabilities can let critical flaws enter the codebase unnoticed.
**Prevention:** Create a GitHub Actions workflow that runs `pip-audit` and `safety` automatically on push, PR, and schedule to detect and prevent merging vulnerable dependencies.
