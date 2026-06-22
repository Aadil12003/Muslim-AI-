## 2024-05-09 - Missing .gitignore
**Vulnerability:** Missing `.gitignore` file.
**Learning:** Common sensitive files like `.env` and `.streamlit/secrets.toml` could be accidentally committed to the repository, leading to credential leaks.
**Prevention:** Add a `.gitignore` file to prevent accidental commitment of sensitive files to the repository.

## 2024-05-24 - Automated Dependency Auditing
**Vulnerability:** Vulnerable dependencies could be introduced without detection.
**Learning:** Adding automated scanning in CI/CD pipeline ensures all dependencies are checked for known vulnerabilities before they are merged.
**Prevention:** Implementing a GitHub Actions workflow using `pip-audit` to scan `requirements.txt` on pushes, pull requests, and on a weekly schedule.

## 2024-05-25 - SAST and Least Privilege in CI
**Vulnerability:** Missing Static Application Security Testing (SAST) and overly permissive GitHub Actions workflows.
**Learning:** Adding Bandit ensures Python code is statically analyzed for security flaws, and applying `contents: read` permissions follows the principle of least privilege, reducing the impact of compromised actions.
**Prevention:** Always configure explicit workflow permissions and include SAST tools like Bandit alongside dependency auditing.
