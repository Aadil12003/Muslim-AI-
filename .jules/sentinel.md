## 2024-05-09 - Missing .gitignore
**Vulnerability:** Missing `.gitignore` file.
**Learning:** Common sensitive files like `.env` and `.streamlit/secrets.toml` could be accidentally committed to the repository, leading to credential leaks.
**Prevention:** Add a `.gitignore` file to prevent accidental commitment of sensitive files to the repository.

## 2024-05-24 - Automated Dependency Auditing
**Vulnerability:** Vulnerable dependencies could be introduced without detection.
**Learning:** Adding automated scanning in CI/CD pipeline ensures all dependencies are checked for known vulnerabilities before they are merged.
**Prevention:** Implementing a GitHub Actions workflow using `pip-audit` to scan `requirements.txt` on pushes, pull requests, and on a weekly schedule.

## 2024-05-24 - CI Permissions and SAST
**Vulnerability:** Missing SAST scanning and potentially overly permissive CI execution permissions.
**Learning:** Relying purely on dependency scanning misses potential flaws in our own application code, and unrestricted GitHub actions token permissions provide a large blast radius if the workflow environment is compromised.
**Prevention:** Integrate Bandit SAST scanning alongside dependency scans, and restrict GitHub Actions workflow tokens to strictly required `contents: read` permissions following the principle of least privilege.
