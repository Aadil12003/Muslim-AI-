## 2024-05-09 - Missing .gitignore
**Vulnerability:** Missing `.gitignore` file.
**Learning:** Common sensitive files like `.env` and `.streamlit/secrets.toml` could be accidentally committed to the repository, leading to credential leaks.
**Prevention:** Add a `.gitignore` file to prevent accidental commitment of sensitive files to the repository.

## 2024-05-24 - Automated Dependency Auditing
**Vulnerability:** Vulnerable dependencies could be introduced without detection.
**Learning:** Adding automated scanning in CI/CD pipeline ensures all dependencies are checked for known vulnerabilities before they are merged.
**Prevention:** Implementing a GitHub Actions workflow using `pip-audit` to scan `requirements.txt` on pushes, pull requests, and on a weekly schedule.
## 2024-05-18 - CI/CD Security Posture Enhancements
**Vulnerability:** The GitHub Actions workflow (`security-audit.yml`) lacked explicit permission declarations and did not include Static Application Security Testing (SAST) for the codebase.
**Learning:** Default GITHUB_TOKEN permissions can be overly permissive, leading to potential abuse if a workflow is compromised. Relying solely on dependency scanning (SCA) like pip-audit leaves the first-party code vulnerable to logic flaws or insecure coding practices.
**Prevention:** Always explicitly define `permissions: contents: read` (or the minimum required permissions) at the top level of workflows or within individual jobs. Implement defense-in-depth by running both SAST (e.g., Bandit) and SCA (e.g., pip-audit) in the CI pipeline to catch a broader range of vulnerabilities early.
