## 2024-05-09 - Missing .gitignore
**Vulnerability:** Missing `.gitignore` file.
**Learning:** Common sensitive files like `.env` and `.streamlit/secrets.toml` could be accidentally committed to the repository, leading to credential leaks.
**Prevention:** Add a `.gitignore` file to prevent accidental commitment of sensitive files to the repository.

## 2024-05-25 - Lack of Automated Dependency Scanning
**Vulnerability:** Vulnerable dependencies could be introduced without being detected.
**Learning:** Manual auditing of dependencies is error-prone and not scalable. An automated workflow is needed to ensure every commit is checked for known vulnerabilities.
**Prevention:** Created a GitHub Actions workflow `.github/workflows/security-audit.yml` that uses `pip-audit` to automatically scan `requirements.txt` for known vulnerabilities on push, pull request, and weekly schedule.
