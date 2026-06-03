## 2024-05-09 - Missing .gitignore
**Vulnerability:** Missing `.gitignore` file.
**Learning:** Common sensitive files like `.env` and `.streamlit/secrets.toml` could be accidentally committed to the repository, leading to credential leaks.
**Prevention:** Add a `.gitignore` file to prevent accidental commitment of sensitive files to the repository.

## 2024-05-24 - Automated Dependency Auditing
**Vulnerability:** Vulnerable dependencies could be introduced without detection.
**Learning:** Adding automated scanning in CI/CD pipeline ensures all dependencies are checked for known vulnerabilities before they are merged.
**Prevention:** Implementing a GitHub Actions workflow using `pip-audit` to scan `requirements.txt` on pushes, pull requests, and on a weekly schedule.

## 2024-05-18 - Missing Least Privilege and SAST in GitHub Actions Workflow
**Vulnerability:** The `security-audit.yml` GitHub Actions workflow was running with default permissions, which can be overly permissive (e.g., write access to repo contents depending on org settings). Additionally, while it had dependency scanning (`pip-audit`), it lacked Static Application Security Testing (SAST) for the codebase itself.
**Learning:** Default GitHub Actions token permissions often provide more access than a workflow needs. A purely read-only workflow like a security audit should explicitly declare `permissions: contents: read` to prevent a compromised dependency or workflow command injection from modifying repository code or making unapproved releases. Furthermore, defense in depth requires multiple layers of scanning: both third-party dependencies (SCA) and first-party code (SAST).
**Prevention:** Always follow the principle of least privilege by explicitly defining the minimum required `permissions` block at the top level or job level of every GitHub Actions workflow. Ensure that both SCA (e.g., `pip-audit`, `npm audit`) and SAST (e.g., `bandit`, `eslint`, `semgrep`) tools are incorporated into continuous integration pipelines to catch vulnerabilities in custom code alongside dependencies.
