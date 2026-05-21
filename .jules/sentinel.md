## 2024-05-09 - Missing .gitignore
**Vulnerability:** Missing `.gitignore` file.
**Learning:** Common sensitive files like `.env` and `.streamlit/secrets.toml` could be accidentally committed to the repository, leading to credential leaks.
**Prevention:** Add a `.gitignore` file to prevent accidental commitment of sensitive files to the repository.

## 2024-06-05 - Missing Continuous Security Monitoring
**Vulnerability:** Missing automated vulnerability scanning for Python dependencies.
**Learning:** Without automated scanning, vulnerable packages can be introduced and remain undetected in the codebase.
**Prevention:** Added a GitHub Actions workflow to run `pip-audit` and `safety` on `requirements.txt` on pushes and PRs to main to ensure dependencies are continuously audited.