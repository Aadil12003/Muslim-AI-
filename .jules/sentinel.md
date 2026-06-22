## 2024-05-09 - Missing .gitignore
**Vulnerability:** Missing `.gitignore` file.
**Learning:** Common sensitive files like `.env` and `.streamlit/secrets.toml` could be accidentally committed to the repository, leading to credential leaks.
**Prevention:** Add a `.gitignore` file to prevent accidental commitment of sensitive files to the repository.

## 2024-05-24 - Automated Dependency Auditing
**Vulnerability:** Vulnerable dependencies could be introduced without detection.
**Learning:** Adding automated scanning in CI/CD pipeline ensures all dependencies are checked for known vulnerabilities before they are merged.
**Prevention:** Implementing a GitHub Actions workflow using `pip-audit` to scan `requirements.txt` on pushes, pull requests, and on a weekly schedule.

## 2024-10-24 - SAST and Least Privilege in CI
**Vulnerability:** Missing Static Application Security Testing (SAST) and overly permissive GitHub Actions.
**Learning:** GitHub Actions default to broader permissions than necessary. Restricting them with `contents: read` follows the principle of least privilege. Additionally, running `bandit -r .` across the repository is safe and won't fail CI even if there are no Python source files present.
**Prevention:** Always restrict GitHub Action permissions using the `permissions` block and run `bandit` alongside dependency auditing for comprehensive static analysis.
