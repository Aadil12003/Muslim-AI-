## 2024-05-09 - Missing .gitignore
**Vulnerability:** Missing `.gitignore` file.
**Learning:** Common sensitive files like `.env` and `.streamlit/secrets.toml` could be accidentally committed to the repository, leading to credential leaks.
**Prevention:** Add a `.gitignore` file to prevent accidental commitment of sensitive files to the repository.

## 2024-05-22 - Missing automated dependency scanning
**Vulnerability:** Missing automated vulnerability scanning for Python dependencies (`requirements.txt`).
**Learning:** Hardcoded dependencies can become vulnerable over time as new CVEs are discovered. Relying on manual checks is error-prone.
**Prevention:** Add a GitHub Actions workflow (`.github/workflows/security-audit.yml`) to automatically run `pip-audit` and `safety` on PRs, pushes, and on a schedule.
