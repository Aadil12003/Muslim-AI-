## 2024-05-09 - Missing .gitignore
**Vulnerability:** Missing `.gitignore` file.
**Learning:** Common sensitive files like `.env` and `.streamlit/secrets.toml` could be accidentally committed to the repository, leading to credential leaks.
**Prevention:** Add a `.gitignore` file to prevent accidental commitment of sensitive files to the repository.

## 2024-05-24 - Automated Dependency Auditing
**Vulnerability:** Vulnerable dependencies could be introduced without detection.
**Learning:** Adding automated scanning in CI/CD pipeline ensures all dependencies are checked for known vulnerabilities before they are merged.
**Prevention:** Implementing a GitHub Actions workflow using `pip-audit` to scan `requirements.txt` on pushes, pull requests, and on a weekly schedule.

## 2026-06-02 - Overly Broad CI Permissions and Missing SAST
**Vulnerability:** The security audit workflow was missing a Static Application Security Testing (SAST) tool to catch code vulnerabilities, and ran with overly broad default permissions.
**Learning:** A GitHub Actions workflow running without explicit minimal permissions has the potential to cause harm if a step is compromised. Furthermore, while dependencies were audited via `pip-audit`, the application's source code was not systematically analyzed for vulnerabilities.
**Prevention:** Configure GitHub Actions workflows with `permissions: contents: read` to apply the principle of least privilege, and incorporate `bandit` for SAST checks on the codebase.
