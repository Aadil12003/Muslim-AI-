## 2024-05-09 - Missing .gitignore
**Vulnerability:** Missing `.gitignore` file.
**Learning:** Common sensitive files like `.env` and `.streamlit/secrets.toml` could be accidentally committed to the repository, leading to credential leaks.
**Prevention:** Add a `.gitignore` file to prevent accidental commitment of sensitive files to the repository.

## 2024-05-24 - Automated Dependency Auditing
**Vulnerability:** Vulnerable dependencies could be introduced without detection.
**Learning:** Adding automated scanning in CI/CD pipeline ensures all dependencies are checked for known vulnerabilities before they are merged.
**Prevention:** Implementing a GitHub Actions workflow using `pip-audit` to scan `requirements.txt` on pushes, pull requests, and on a weekly schedule.

## 2026-06-10 - Enhancing CI Security with Least Privilege and SAST
**Vulnerability:** The security audit workflow was missing top-level permissions to enforce least privilege, and lacked static application security testing (SAST) for the codebase.
**Learning:** Adding `permissions: contents: read` restricts token permissions in GitHub Actions, reducing the impact of potential workflow compromises. Incorporating `bandit` provides automated SAST to catch common security issues in Python code.
**Prevention:** Ensure all GitHub Actions workflows define minimal permissions explicitly and include comprehensive security checks like SAST (`bandit`) alongside dependency scanning (`pip-audit`).
