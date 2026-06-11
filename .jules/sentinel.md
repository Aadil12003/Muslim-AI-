## 2024-05-09 - Missing .gitignore
**Vulnerability:** Missing `.gitignore` file.
**Learning:** Common sensitive files like `.env` and `.streamlit/secrets.toml` could be accidentally committed to the repository, leading to credential leaks.
**Prevention:** Add a `.gitignore` file to prevent accidental commitment of sensitive files to the repository.

## 2024-05-24 - Automated Dependency Auditing
**Vulnerability:** Vulnerable dependencies could be introduced without detection.
**Learning:** Adding automated scanning in CI/CD pipeline ensures all dependencies are checked for known vulnerabilities before they are merged.
**Prevention:** Implementing a GitHub Actions workflow using `pip-audit` to scan `requirements.txt` on pushes, pull requests, and on a weekly schedule.

## 2026-06-11 - Harden GitHub Actions Workflow and Enable SAST
**Vulnerability:** The security audit workflow was running with default (broad) token permissions and only checking for dependency vulnerabilities, missing Static Application Security Testing (SAST).
**Learning:** Enforcing the principle of least privilege using `permissions: contents: read` for GitHub Actions mitigates the risk of a compromised workflow altering the repository. Additionally, combining dependency scanning (pip-audit) with SAST (bandit) provides better defense in depth.
**Prevention:** Always restrict `GITHUB_TOKEN` permissions in CI workflows and include comprehensive security checks (both SCA and SAST) where applicable.
